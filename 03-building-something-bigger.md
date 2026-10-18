# 3. Building something bigger

*From independent scripts to a coordinated application.*

## More than a web interface

At the end of those three weeks, I had something I had been putting off for a long time: a working web interface, backed by Python.

That alone would have been a satisfying outcome. I could finally interact with the system through a mobile-friendly interface instead of relying entirely on SSH, command-line scripts, and cron configuration.

But the experiment had gone further than putting a convenient front end on the old tools.

The application could now coordinate tasks from beginning to end. Operations that had previously run as separate jobs could follow one another in a logical sequence, without me having to bridge the gaps manually.

Importantly, that didn't mean giving up automation. The system could still work in the background. I had simply gained a more convenient way to interact with it, and a better view of what it was doing.

## A different way of working

The biggest surprise wasn't necessarily a feature of the application. It was discovering that web development no longer had to feel like the expensive, frustrating undertaking I remembered.

I wanted a lightweight setup, not an elaborate collection of frameworks that would require constant attention. The chatbot helped me compare unfamiliar technologies and figure out how to implement particular pieces. I still made the decisions, but I could reach them much faster.

I also came away with a more disciplined development workflow: Git hooks, linting, and other small checks that helped catch mistakes and keep the code consistent.

None of those practices was new. What was new to me was how quickly I could assemble a practical workflow around them without turning the project into a factory of tools and configuration.

For the first time, building a web interface felt compatible with the original purpose of the project: saving effort rather than creating more of it.

## Background work and live feedback

The new application also felt much more modern than the original collection of scripts.

Background processing meant that the actual work didn't depend on someone keeping a page open. The interface was there when I wanted it, while automation continued doing its job.

WebSocket communication added another dimension: the interface could receive live information about parts of the system's activity.

This changed the experience of using the software. With the old setup, understanding what had happened often meant checking logs or inspecting the server. Now, at least some operations were observable from the interface itself.

It was a substantial leap in convenience and visibility, not just in appearance.

## The price of moving fast

Of course, AI-assisted development didn't remove the need to understand the code.

Near the end of the three-week rush, I discovered that the SQLAlchemy integration had been built using deprecated APIs recommended during development. Fixing that meant rewriting part of something I had already spent time building.

It was a particularly effective reminder that a plausible answer isn't necessarily a current or correct one.

There were other hard limits. Integrating with Plex and rTorrent's RPC interface exposed gaps in the information available to the assistant. When documentation and examples were scarce, it couldn't reliably tell me how every API behaved.

Those parts still demanded investigation, testing, and judgment. The AI could help me navigate unfamiliar territory, but it couldn't replace evidence from the systems I was actually using.

The experiment had made development faster. It hadn't made verification optional.

## The same philosophy, on a larger scale

Despite the new architecture, the philosophy hadn't really changed since Anime AutoMove.

I wasn't trying to remove every human decision. I wanted to remove unnecessary friction.

Originally, that meant teaching a script where files belonged and letting it apply the rule afterward. Now it meant letting a coordinated system carry out a sequence of tasks automatically, while giving me a convenient place to step in when needed.

The mobile-friendly interface, background processing, WebSockets, and development tooling were all means to that end.

Three weeks earlier, I had been experimenting with whether AI could make a web application worth building. By the end, I had a working application, a faster development workflow, and a clearer understanding of where AI assistance helped—and where it could lead me astray.

What began as two small, independent scripts was becoming something much bigger than I had planned.

Looking back, I'm fairly sure the same result could be achieved much faster with today's AI development tools.

What took me three weeks of intensive coding, with AI mostly acting as an advisor, might now take considerably less time with a capable coding agent.

Back then, I was still doing the implementation myself, one problem at a time.

And that's perhaps the most striking part of this story: the tools have evolved so quickly that my original experiment already feels like a different era.

## A system I can't quite share

Unfortunately, unlike the original scripts, I can't publicly release the complete application due to potential legal concerns surrounding its intended use.

That's a little frustrating, considering how much it has evolved.

But while I can't share the entire system, I can still share the story behind it, the technical decisions, and the lessons learned along the way.

And perhaps that's the more interesting part anyway.

---

[← Previous: The cost of convenience](02-the-cost-of-convenience.md) · [↑ Contents](README.md) · [Next: Epilogue →](04-epilogue-the-madness-continues.md)
