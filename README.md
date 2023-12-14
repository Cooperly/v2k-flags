# Why not just use aikar's flags?
His GC is based on G1, it's extremely stable but extremely slow, why should current gen servers be held back by last gen algorithms?
I propose to get rid of it in favor of ZGC, why? It clears memory alongside the server instead of pausing it each time, and it's wicked fast. Seriously.

# Who should use these flags?
Larger servers with at least 10GB of memory allocated, anything under can just use G1GC as it's flawless and doesn't need a lot of optimization for most use cases.
Keep in mind ZGC could use a lot more processor cycles compared to other GCs, if your cpu is the main problem in your machine, this will worsen the issue.

# Which Java Runtime should I use with these flags?
I would suggest Oracle GraalVM, as it has an extremely aggressive java compiler, resulting in around 25% additional performance without even tweaking flags yet.
You could theoretically run corruflags on any runtime, but some optimizations are exclusive to GraalVM and may or may not not work.

# Flags
- [x] Vanilla (Not recommended)
- [x] Spigot, Paper, Purpur, Mirai, you get the point.
- [x] Fabric (Suggested, will benefit the most.)
- [x] Quilt (Untested)
- [x] Forge (Untested)
- [x] Most server software, even non minecraft (No support, not recommended.)

***For most servers:***
```java
added later
```

*don't forget to adjust -Xms and -Xmx to your server configuration, along with java path and server.jar if applicable*