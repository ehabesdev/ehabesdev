# Emirhan Hanifi Habeş

I build software end to end — from low-level C to games that run in the browser.
What I care about most is finishing: tests, CI and a live link, not another abandoned prototype.

📍 Türkiye

---

## Projects

### [Overglaze](https://github.com/ehabesdev/overglaze) &nbsp;·&nbsp; [▶ Play in your browser](https://ehabesdev.github.io/overglaze/)

A merge + auto-battler you can finish in five minutes. No art assets — every shape is
drawn in code, every sound is synthesised with the Web Audio API, so the whole game
ships in about 200 KB gzipped.

The part I'm proudest of is invisible: the game logic has no idea the renderer exists,
so the same simulation runs headless in Node. That let me build a balance harness that
plays **35,000 seeded runs** across five artificial player strategies and reports win
rates, damage distribution per unit type and the effect of each modifier. The tuning
numbers in the game come from those measurements rather than from guesswork.

`TypeScript` `PixiJS` `Vite` `Vitest` &nbsp;·&nbsp; 118 tests &nbsp;·&nbsp; deployed from CI

### [Geçit](https://github.com/ehabesdev/gecit) &nbsp;·&nbsp; [▶ Landing page](https://ehabesdev.github.io/gecit)

A Windows desktop app that makes blocked sites reachable and filters ads — but only on
the sites you explicitly add. Everything else passes through untouched: byte for byte,
certificate chain intact.

That restriction is the whole design. Reading an HTTPS body means terminating TLS, and
most tools do it to *every* connection, which breaks certificate pinning and banking
apps. Here every connection takes one of three paths — full MITM, refused CONNECT, or
raw tunnel — and only the first one opens anything.

The part I'm proudest of is that none of the evasion is guessed. The app splits the TLS
ClientHello to defeat SNI-based blocking, and the split point came from measurement, not
folklore — six attempts per method against a blocked domain, verified by checking the
certificate identity rather than trusting "connected":

```
no split       0/6      split at 20 bytes    0/6
1 byte         0/6      split at 64 bytes    0/6
mid-hostname   0/6      40-byte chunks       0/6
5 bytes        6/6      5 bytes + delay      6/6
```

Splitting inside the server name — theoretically the strongest move — does nothing,
which tells you the middlebox reassembles TCP segments. Only a split exactly on the TLS
record boundary survives. Since that result is network-specific, the app now re-runs the
measurement per host and remembers which method worked.

`JavaScript` `Electron` `Node` &nbsp;·&nbsp; DoH resolver, selective MITM proxy, SOCKS5 server
&nbsp;·&nbsp; 10 test suites, 230+ checks

### [Tabledit](https://github.com/ehabesdev/tabledit) &nbsp;·&nbsp; [▶ Live demo](https://ehabesdev.github.io/tabledit)

A cloud spreadsheet editor: Excel-like cell editing, real-time updates, drag & drop file
management, offline support and Firebase authentication.

`JavaScript` `Firebase` `HTML` `CSS`

### Systems programming in C

Low-level projects written without the standard library — because rebuilding it was the point.

| Project | What it is |
| --- | --- |
| [philosophers](https://github.com/ehabesdev/philosophers) | Dining philosophers with POSIX threads — no deadlock, no starvation |
| [push_swap](https://github.com/ehabesdev/push_swap) | Sorting a stack through a restricted instruction set, optimised for move count |
| [minitalk](https://github.com/ehabesdev/minitalk) | Client/server communication using UNIX signals only |
| [printf](https://github.com/ehabesdev/printf) | A reimplementation of `printf` with variadic arguments |
| [get_next_line](https://github.com/ehabesdev/get_next_line) | Buffered line-by-line file reading with persistent state |
| [libft](https://github.com/ehabesdev/libft) | A C standard library written from scratch |
| [so_long](https://github.com/ehabesdev/so_long) | A small 2D game built on MiniLibX |

---

## Tech

**Languages**

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![C](https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=c-sharp&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-0095D5?style=for-the-badge&logo=kotlin&logoColor=white)

**Platforms & tools**

![Web](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Electron](https://img.shields.io/badge/Electron-47848F?style=for-the-badge&logo=electron&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Unity](https://img.shields.io/badge/Unity-100000?style=for-the-badge&logo=unity&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=white)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)

## Contact

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ehabesdev?tab=repositories)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:habes.emirhanifi@gmail.com)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/emrhn.hbs/)
