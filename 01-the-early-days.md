# 1. The early days

*Two problems, one week, and Python 2.7.*

## Two servers and a slow connection

This story didn't begin with a plan to build a large automation system. It began with two servers, an ADSL connection, and a personal challenge: learning Python 2.7 in roughly a week.

I wasn't new to programming. I came from C# and .NET development, and I already had experience administering Linux and FreeBSD systems. Python was the unfamiliar part. Rather than learn it through exercises alone, I wanted to solve a couple of real problems.

The setup was simple: a remote seedbox downloaded files, while a local NAS and media center stored them and served the collection through Plex. Getting files from one machine to the other, however, was still a manual job.

My ADSL connection offered less than 2 MB/s. A transfer running during the day could make online gaming miserable. FileZilla worked, but manually retrieving files was tedious: I had to remember what I had already copied, notice anything I'd missed, and sometimes stay up late just to bring a few files home.

Even once the files arrived, they still needed to be sorted into directories Plex could use. That meant more repetitive work, and more opportunities for mistakes.

These were two separate annoyances, but they made good material for the same week-long Python experiment.

## Let the night do the work

The first script was originally called *Night Sync*. The name described its schedule more than its purpose.

Cron launched the transfer job at 11 PM and attempted to run it every 30 minutes through the night. Another scheduled task interrupted it in the morning, around 6 AM, so the connection would be available again during the day.

There was no reason to build a scheduler: the operating system already had one.

The trickier requirement was remembering what had been retrieved. A normal directory mirror wasn't what I wanted. Once a file reached the local server, I might move it somewhere else; that shouldn't cause the same file to be downloaded again. A small SQLite database kept track of files that had already been transferred.

That behavior eventually gave the script its more descriptive name: *One Time Sync*.

### Why rsync instead of SCP?

If all I needed was a secure file copy, SCP would have been sufficient. But my transfers had to survive the end of the nightly window and continue on another night rather than start from scratch.

That stop-and-resume requirement was the reason for choosing `rsync`, not a desire to maintain an exact mirror of the remote directory.

Security was part of the design too. Transfers ran over SSH, using keys managed in memory by an SSH agent rather than embedding credentials in the script. Python and Paramiko handled remote operations, while rsync did the actual copying.

It was a natural combination of my two backgrounds: system utilities doing the work they were good at, with Python providing the missing coordination and memory.

## An assistant for sorting files

The second script, *Anime AutoMove*, addressed the next chore: putting episodes in the right places for Plex.

Anime releases often followed recognizable fansub filename conventions. That made it possible to extract a series name and propose a destination without attempting to understand every possible filename.

But I didn't want a program that guessed everything and moved files wherever it pleased.

Anime AutoMove was closer to a small rule-based assistant than a fully autonomous sorter. It had two distinct modes.

In *learn* mode, it looked for unfamiliar series names and suggested sorting rules. I could accept the proposed destination or choose another. The resulting association was saved in SQLite.

In *execute* mode, it applied the stored rules to matching files, creating destination directories as needed and moving episodes without asking the same questions again. This mode ran automatically through cron.

The word *learn* didn't mean machine learning. The program wasn't training a model or discovering new rules by itself. Its knowledge was a set of explicit decisions made with human assistance: a simple, older style of rule-based automation.

That limitation was deliberate. These scripts belonged to a broader approach to building small assistance tools that were easy to write, understand, and maintain. Human intervention was fine when it avoided unnecessary complexity. The goal was to eliminate repetitive work, not automate every decision at any cost.

After all, automation was supposed to make life easier, not become another maintenance burden.

## Independent jobs, shared purpose

One Time Sync and Anime AutoMove weren't steps in a centrally orchestrated pipeline. They were independent programs, each launched through its own cron jobs.

There was even a small extra task for Plex. In my FreeBSD environment, automatic detection of filesystem changes wasn't working as expected, so I used Plex's command-line tooling to request a metadata refresh after files had been organized.

None of this required a dedicated controller. Cron scheduled the work, SSH secured remote access, rsync handled resumable transfers, SQLite remembered state and sorting rules, and Python connected the pieces where needed.

Both scripts came out of that initial rush to learn Python 2.7. The public Git history preserves later versions of them, but not their complete early development.

At the time, the result was simply a collection of small tools with clear responsibilities. I no longer needed to stay up to retrieve files, keep a mental list of previous transfers, or manually sort every episode.

There was no grand architecture behind it. There didn't need to be.

## Historical source code

The two original projects are available as public archives:

- [One Time Sync](https://github.com/SuperMiaw/archived-one-time-sync) — resumable, one-time file retrieval.
- [Anime AutoMove](https://github.com/SuperMiaw/archived-anime-automove) — rule-based assistance for organizing files.

These repositories are preserved as historical and educational examples, not as maintained or ready-to-use software.

There was an earlier attempt to make the code public, but the projects later returned to private development. Their published Git histories were deliberately shortened to protect information from the original environment, so they do not capture the full story of their creation.

This time, the code is being released for good: the repositories will remain public in their current, archived state.
