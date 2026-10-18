# 2. The cost of convenience

*When automating the work is easier than improving the tools.*

## A working system, an inconvenient interface

The first scripts did their jobs. Files could be retrieved overnight, sorted according to saved rules, and made available through Plex. But administering the setup still meant SSH sessions, command-line tools, and cron jobs.

That was familiar territory for me as a system administrator. It was also a source of friction whenever I wanted to change something or make the system more pleasant to use.

A web interface seemed like a natural improvement. The problem wasn't whether I could build one. It was whether the development and maintenance effort would be worth it.

## Memories of web development

My first experience with web development came during an early engineering internship, around my preparatory and first engineering years, using PHP and jQuery.

In my later engineering years, I worked with Silverlight, Microsoft SQL Server, and WSDL-based web services. After graduation, professional work introduced me to Ext JS, along with some memorable legacy constraints involving ActiveX and Internet Explorer 6.

Ext JS was genuinely useful for building layouts. But creating and refining an interface could still consume a lot of time, without guaranteeing a particularly good user experience.

I had also tried Angular on my own. Cryptic errors quickly made the learning curve feel expensive. And even apart from frameworks, web layouts themselves were a chore I didn't particularly want to take on.

For a personal project meant to save time, a new interface risked becoming more work than the original scripts. So I put the idea aside.

## Another coding rush

Later, I had three weeks of vacation and decided to use them for an experiment.

AI-assisted development looked promising, and I was willing to pay for tools if they could genuinely save time. I was curious about the benefits and drawbacks, not just for my personal project but also to evaluate whether such tools might be worth recommending at work.

I tried an AI coding assistant integrated into the editor, as well as a paid AI chatbot.

At the time, the editor-integrated assistant frequently suggested code that was simply invalid. I wasn't convinced by the results, although the idea of assistance directly in the editor made sense to me. I haven't followed its development closely enough to judge what it offers today.

The paid chatbot was useful in a different way. I could define the question, choose exactly what context to share, and decide what advice to act on. That made it easier to explore technologies I didn't know, compare architectural options, and ask how to accomplish particular tasks without handing over the entire project.

I was looking for lightweight technologies that would be straightforward to deploy and maintain. The assistant helped me navigate unfamiliar choices, but I still had to evaluate them.

The limitations became clear as well. Poorly documented interfaces, particularly Plex and rTorrent RPC, were difficult territory: when reliable examples or information were missing, the answers could only go so far.

This was an experiment, not a demonstration that AI could build a system unaided. It offered a way to lower some of the costs that had kept the web interface on hold, while introducing new reasons to verify every recommendation.

What those three weeks actually produced—and the mistakes uncovered along the way—is the next part of the story.
