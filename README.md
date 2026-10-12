<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./Images/header_dark.png">
    <img alt="SWHub" src="./Images/header_light.png" width="720">
  </picture>
</p>

<p align="center"><strong>Study, Practise and Play Go in one app.</strong><br>Windows · Linux · macOS · Android</p>

<p align="center">
  <a href="https://github.com/SoumyaK4/SWHub/releases"><strong>Download</strong></a> ·
  <a href="CHANGELOG.md">Changelog</a> ·
  <a href="https://github.com/SoumyaK4/SWHub/issues">Report Issue</a> ·
  <a href="https://discord.gg/ptjzTWU9SP">Discord</a>
</p>

<div style="display: flex; justify-content: center;">
<a href="#">
  <img src="https://hits.sh/github.com/soumyak4/SWHub.svg?label=Views&color=brightgreen" >
</a>
</div>

<p align="center">
  SWHub is a personal Swiss Army Knife Study/Play tool for the game of Go/Baduk/Weiqi, I built for myself.<br>
  It brings together Tsumego, KataGo, Review, Pattern Search, Online Play, Teaching and Progress Tracking under one roof.
</p>

## Screenshots/Demo

<p align="center">
<table>
  <tr>
    <td><img src="./Images/Screenshots/Puzzles.png" width="400"></td>
    <td><img src="./Images/Screenshots/Tools.png" width="400"></td>
    <td><img src="./Images/Screenshots/Play.png" width="400"></td>
  </tr>
</table>
</p>

## Explore SWHub

| Destination | What you can do |
| --- | --- |
| **Puzzles** | Practise collections and topics, take exams, revisit mistakes with SRS, save favourites, or try Breakthrough and Subjects. |
| **Tools** | Analyse with KataGo, review games and practise drills in Game Focus, explore Joseki, search Game Patterns, or study on a local board. |
| **Play** | Play Career Mode, connect to OGS, KGS, Pandanet or FoxWQ, explore Variant Server, race through Tsumego Battles, or use Teaching Rooms. |
| **Me** | See your progress, activity and personal bests, link playing profiles, and optionally sync training statistics. |

## A few highlights

- **Train your reading.** Grading and Endgame exams, Time Frenzy, adaptive Ranked Mode, custom exams and spaced repetition.
- **Try something different.** Breakthrough alternates Best move and Who is ahead with 60-second puzzles and a highest-level leaderboard. Subjects offers eight categories with sequential kyu/dan progression and HumanSL opponents.
- **Understand your games.** KataGo analysis, score and win-rate graphs, variations, performance reports and HumanSL rank-fit estimates. Game Focus keeps completed reviews offline and creates drills from mistakes.
- **Build your study library.** Local SGF editing, board-photo import, downloadable Joseki and Kombilo pattern search across your own games.
- **Play at your pace.** Career Mode uses HumanSL opponents, random styles and an 18K–9D ladder. Online servers retain their own rules and controls.
- **Make it comfortable.** Responsive phone and desktop layouts, board themes, dark colour palettes, resizable panels and configurable shortcuts.

## Get started

1. **Download** the package for your platform from [official releases](https://github.com/SoumyaK4/SWHub/releases).
2. **Open Puzzles or Joseki** to download their data. Installed dictionaries work offline, puzzle-data updates activate after restarting SWHub.
3. **Set up KataGo** when you want engine analysis, Career or Subjects. Use local Auto Setup on supported desktops, or connect a remote engine.
4. Open **Settings → FAQ** or the **?** button for detailed feature guides. On desktop, **F1** opens shortcut search, other app shortcuts are opt-in.

## Free Cloud KataGo

| Use | Setup |
| --- | --- |
| Play and analysis | [Colab notebook](Docs/Free%20Cloud%20Katago/Analysis/Kata_Colab.ipynb) · [Modal notebook](Docs/Free%20Cloud%20Katago/Analysis/Kata_Modal.ipynb) |
| Training contribution | [Colab guide](Docs/Free%20Cloud%20Katago/Contribute/Kata_Colab_Contribution.ipynb) · [Modal guide](Docs/Free%20Cloud%20Katago/Contribute/Kata_Modal_Contribution.ipynb) |

Career and Subjects need both regular KataGo and HumanSL configured. Opponent moves come from HumanSL, regular KataGo supplies evaluations and related features. And these notebooks are pre-configured so you won't have to figure things out.

## Quick F.A.Q.

For more detailed feature guides and controls, open **Settings > F.A.Q.** or use the **?** button inside the app.

<details>
<summary><strong>What works offline?</strong></summary>

Downloaded Puzzles and Joseki, Local Board, Pattern Search libraries, local statistics, saved SGFs and completed Game Focus reviews. Local KataGo also works offline after setup. Subjects and Career need a running engine, using a remote engine requires internet. Online play, cloud analysis, profile imports and sync need a connection.

</details>

<details>
<summary><strong>Do I need an account, and how do I back up?</strong></summary>

Local training statistics and file backups work without a sync username or key. Server outages and sync quota limits do not stop local saving.

- **Android:** Settings → Statistics backup.
- **Desktop:** close SWHub before copying `Documents/SWHub/swhub_stats.db`.

The stats backup includes favourites, SRS, training history, Subjects/Breakthrough progress and any linked username and sync key. Keep it private. Restoring replaces local training stats and account linkage.

**App settings, Career progress, Game Focus libraries and SGFs are separate.** Back up those files too when moving or reinstalling. Keep the complete Game-Focus and Pattern Search folders, Pattern Search also supports portable exports.

From v0.2.11 onward, `swhub_stats.db` is the long-term training statistics file. Future changes should upgrade it automatically without resets or manual reimports. Devices sharing a sync account must use same app and puzzle-data versions, keep your existing username and key when updating.

</details>

<details>
<summary><strong>How do Breakthrough and Subjects work?</strong></summary>

**Breakthrough:** alternate Best move and Who is ahead, with 60 seconds per puzzle and three failures per run. The leaderboard records your highest level. Its puzzles stay outside regular puzzle totals, search, favourites and SRS.

**Subjects:** solve puzzles in order, complete every puzzle in a rank to unlock the next. You have three 60-second byo-yomi periods. Pass with at least 90% estimated human win rate after 40 additional moves counting both players, or after both players pass in Endgame. Attempts and unlocks save locally, with optional sync. Subjects has no leaderboard.
</details>

<details>
<summary><strong>Does SWHub upload my games?</strong></summary>

Local analysis stays on your machine. A remote KataGo engine receives the positions you send it. Stats sync sends supported training statistics and leaderboard identity, it does not back up your SGF or Pattern Search library. Saved Game Focus reviews use stored analysis without reconnecting.

</details>

<details>
<summary><strong>Where are the controls and troubleshooting guides?</strong></summary>

Use **Settings → FAQ** for feature guides and mouse gestures, and **Settings → Keyboard shortcuts** for bindings. **F1** opens shortcut search on desktop. Mouse-wheel navigation and **Alt + left-click** stone-history navigation work independently of enabled keyboard bindings where supported.

</details>

## Community

[Report a bug](https://github.com/SoumyaK4/SWHub/issues) · [Discord](https://discord.gg/ptjzTWU9SP) · [Computer Go Community](https://discord.gg/5aTGusWxvc) · [Other Go projects](https://soumyak4.in/)

## License

SWHub is proprietary software, it is not open source. The [SWHub Non-Commercial Proprietary License](LICENSE.md) prohibits unauthorized commercial use, monetization, modification, builds and redistribution. [Third-party components](./Docs/Licenses/) retain their own terms.
For the parts that are reverse engineered implementations, I cannot provide any guarantee stability or promises about your account not getting compromised for using it. Try using a spare account for that if possible. So far I've tested with a few accounts and haven't faced any issues.

Get official copies from SoumyaK4 or the [official releases](https://github.com/SoumyaK4/SWHub/releases). Third-party mirrors, stores and re-uploads are not authorized. SWHub source code is not included in the public distribution or licensed for use.
