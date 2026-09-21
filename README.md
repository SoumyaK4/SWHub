<h1 align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./Images/header_dark.png">
    <img alt="SWHub" src="./Images/header_light.png">
  </picture>
</h1>
<h1 style="text-align: center;">
  <a href="./CHANGELOG.md">Changelog</a> |
  <a href="https://github.com/SoumyaK4/SWHub/releases/">Download</a> |
  <a href="https://soumyak4.in/">Other Go Projects</a>
</h1>
<div style="display: flex; justify-content: center;">
<a href="#">
  <img src="https://hits.sh/github.com/soumyak4/SWHub.svg?label=Views&color=brightgreen" >
</a>
</div>

SWHub is a local-first Go/Baduk/Weiqi studying app. 
It combines ```Tsumego Training``` modes, ```Pattern Search```, ```Joseki/Fuseki``` Explorer, ```KataGo Analysis```, ```Online Play with Variants```, ```Teaching/Review Rooms```, ```Progress Tracking``` and ```Online Servers``` in one app.

## Free Cloud KataGo

### For [Play/Analysis](./Docs/Free%20Cloud%20Katago/Analysis/README.md)

### For [Contribution](./Docs/Free%20Cloud%20Katago/Contribute/)

## Screenshots/Demo

<table>
  <tr>
    <td><img src="./Images/Screenshots/Puzzles.png" width="400"></td>
    <td><img src="./Images/Screenshots/Tools.png" width="400"></td>
    <td><img src="./Images/Screenshots/Play.png" width="400"></td>
  </tr>
  <tr>
    <td><img src="./Images/Screenshots/Pattern.png" width="400"></td>
    <td><img src="./Images/Screenshots/Kata.png" width="400"></td>
    <td><img src="./Images/Screenshots/KataGoes.png" width="400"></td>
  </tr>
</table>

## Feature Highlights

SWHub is organized around four destinations: **Puzzles**, **Tools**, **Play**, and **Me**. Compact layouts use bottom navigation, while wider windows use a navigation rail.

<details>
<summary>What can I do in Puzzles?</summary>

- **Grading Exam:** solve ten same-rank problems with 45 seconds per problem, eight correct answers pass the exam.
- **Endgame Exam:** the same ten-problem format using endgame positions.
- **Time Frenzy:** solve as many increasingly difficult problems as possible in three minutes, with the run ending after three mistakes.
- **Ranked Mode:** adaptive untimed solving that raises difficulty as accuracy and speed improve.
- **Collections and Topics:** work through curated books/sets or train a chosen topic, subtopic, and rank range.
- **Custom Exam:** combine selected topics, collections, rank ranges, or prior mistakes into a personal exam. Enable **Only unique tasks, without repeats** to exclude previously solved tasks and use each eligible task once. Exams can request up to 10,000 problems, capped by the available pool in this mode.
- **My Mistakes and SRS Review:** inspect missed problems and revisit them on a spaced schedule. SRS remains independent when a mistake is cleared or ignored, and problems graduate after a sustained correct streak.
- **Statistics and Leaderboards:** review recent activity, rank/type breakdowns, personal bests, and global results for supported training modes and periods.
- **Find Task:** open a task directly from its shared identifier. Management tools remain developer/debug features.

Puzzle solving also supports multiple correct variations, optional solution continuation, color/orientation randomization, always-black-to-play, Auto-Next, Count and Status problem types, Count Hard Mode, and Ghost Mode for visualization training.
</details>

<details>
<summary>What can I do in Tools?</summary>

- **Local Board:** create and edit variations, navigate a visual game tree, annotate SGFs, count liberties and group status, and draw pen marks. Import a board photo, align its corners, correct detected stones, and turn the position into an SGF. A movable local score estimator supports rule-aware totals and whole-group dead/alive correction, plus click-to-cycle Black/White/neutral ownership on empty points. Ownership edits update the estimate without placing stones; the estimator remembers its window position across app restarts.
- **Pattern Search:** build a private Kombilo database from local 19x19 SGFs, search full-board, corner, or selected-area patterns, filter game metadata, inspect continuations, player profiles, date/win-rate statistics, and exact indexed hits, save search history and snapshots, or try Guess the Next Move. Large imports are checkpointed, invalid SGFs are skipped, and portable `.db` bundles keep the `.ps` database together with its required auxiliary files.
- **Joseki:** browse about 19,800 bundled OGS positions completely offline on a full 19x19 board. The explorer includes Joseki and Fuseki branches, pass and tenuki, official move categories and labels, board marks, descriptions, source/tag filters, and related-position or external links.
- **KataGo Analysis:** use a bundled/local process, custom command, or remote WebSocket engine on supported platforms. Review top moves, point loss, score/win-rate graphs, ownership, policy, variations, move statistics, notes, and a Performance Report with opening/midgame/endgame filters and optional HumanSL Rank(Avg.) estimates. Auto Setup detects compatible hardware, installs and verifies binaries/models, and tunes the engine. The shared **Rank guide** offers 20k–9d guidance and unranked teaching practice; named bots retain their distinct playing strategies. Details describes the next recorded move and follows the same rank filter as board suggestions. Mistake navigation stops before the mistake; hover or pin a variation link and use the mouse wheel to step through its preview. Image to SGF is also available here, alongside deeper analysis, alternatives, all-move analysis, and areas of interest.
- **Game Focus:** import complete local or supported server-account games, analyze them in a resumable queue, and keep completed reviews offline. Dashboard, Drills, and Weaknesses show a cumulative HumanSL style estimate, phase/region/severity breakdowns, accuracy trends, saved Performance Reports, and game tags such as Comeback or Dragon Slaying. Choose the recorded player rank or a 20k–9d target for new analysis. Export individual drills or selected categories as SGF, drills use an independent schedule up to two weeks.
- **KataGo Contribution:** contribute through a compatible controller or local KataGo process and watch live games, analysis, logs, and session progress, including rectangular contribution games. Colab and Modal guides cover analysis and contribution; both Colab workflows can cache reusable engine/model files in Google Drive. Finish & stop lets contribution shut down cleanly.

</details>

<details>
<summary>What can I do in Play?</summary>

- **Career Mode:** play ranked games against rank-guided KataGo HumanSL styles, track recent-window promotion/demotion progress and peak rank, save finished SGFs, and review games. Unranked guided practice is now part of the normal KataGo page.
- **OGS, KGS, and IGS(Pandanet):** sign in and play through native clients inside SWHub. Browse players and live games, send or answer challenges, resume ongoing games where supported, chat, and open game records. Record actions include Review in SWHub, Open in KataGo, Open in AI Sensei, and Download SGF. Each server retains its own rules and available controls.
- **OGS Reviews:** discover, create, and open shared reviews with a visual game tree, comments, setup stones, variations, marks, territory, and pen drawing. Follow the presenter or explore locally; publishing edits requires server-granted control.
- **SSGS:** use SWHub's built-in lobby and game client for challenges, matchmaking, chat, standard Go, team/Rengo play, and One Color, Traitor, Blind, or Phantom variants. Game settings include rules, board size, komi, and time controls; completed records can be saved as SGF or opened for analysis.
- **Tsumego Battles:** create or join a room code, configure rank/type/time ranges, chat and ready up, then solve the same synchronized problem set.
- **Teaching Rooms:** when enabled for a build, create password-protected shared boards with teacher/student roles, assigned colors and turns, chat, board annotations, scoring, and controlled voice participation.
</details>

<details>
<summary>What is on the Me page?</summary>

- Avatar and player identity, unique solved count, total problem count, and highest solved ranks for recent periods and all time.
- Personal bests, training activity, and a calendar heatmap. Full rank/type training statistics remain under Puzzles > Statistics.
- Your playing profile below the heatmap, with source-filterable rank history and win/loss results fetched directly from configured EGD and supported server identities. Charts cover the rolling past year; some servers provide a shorter result history. Profiles are cached for six hours.
- Actions to edit profile identities, refresh sources, share a stats image, or sync local training stats using a leaderboard username and private sync key.
</details>

<details>
<summary>What appearance and controls can I customize?</summary>

- Board and stone themes, including custom boards and stones images under **Settings > Appearance**.
- Inside, outside, or hidden coordinates across boards; realistic stone placement, shadows, hover stones, custom cursors etc.
- Separate stone, interface, and voice volumes, two randomized stone-sound pools, and English, Chinese, Spanish, Japanese, Korean, or Russian voice prompts.
- Desktop keyboard bindings under **Settings > Keyboard shortcuts**. Search by action, page, or key, or show only enabled actions. Actions start disabled with suggested keys visible: enable one or click its key field to assign and enable another combination. Changes apply immediately, recording can be cancelled, and conflicts between actions that share a page are blocked.
- Added shortcuts include main-page access to Local Board, Pattern Search, Joseki, and shortcut settings, plus Local Board pass, variation mode, and opening KataGo analysis. KataGo and saved reviews inherit shared Game navigation bindings unless you override them.
- Mouse-wheel move navigation works independently of keyboard bindings: one move normally, ten with Shift, or the start/end with Ctrl.
</details>

## F.A.Q.

<details>
<summary>Frequently Asked Questions</summary>

### Where should I start?

Start with **Puzzles** if you want structured reading practice, **Tools** if you have a game or position to study, **Play** for live games and shared sessions, and **Me** when you want to see progress, or sync data. The in-app **Settings > FAQ** contains longer operational notes and troubleshooting.

### Which features work offline?

Bundled puzzles, Local Board, Joseki, existing Pattern Search databases, local statistics, saved SGFs, and saved Game Focus reviews work offline. Local KataGo also works offline after its executable and models are installed. Public-profile/archive imports, remote KataGo, leaderboards/sync, OGS, KGS, Pandanet, SSGS, Tsumego Battles, and Teaching Rooms require a network connection. Board-photo detection runs locally.

### What is the difference between My Mistakes, SRS, and Game Focus Drills?

**My Mistakes** records failed attempts. **SRS Review** schedules those for long-term repetition. **Game Focus Drills** are generated from point losses in your own analyzed games, retain the full board and KataGo answers, and use a separate short schedule that tops out at two weeks.

### How do I move a Pattern Search database?

Use Pattern Management's exported `.db` bundle. A raw `.ps` file is only one part of the database; its `.pa`, `.ps1`, `.ps2`, and other required siblings must stay together. Large bundle imports are streamed and installed through a
staged rollback-safe process.

### Where is my data, and what should I back up?

On desktop, app-managed data is under `Documents/SWHub`. Important items are `swhub_stats.db`, `game_focus_v2.db`, the `PS` directory, saved SGFs, and KataGo files. Close SWHub before copying live databases. Use exported Pattern Search bundles for portable backups and keep your leaderboard sync key somewhere safe; it cannot be recovered if lost.

### Do I need a new account or sync key for the stats upgrade?

No. Version 0.2.7 uses the newer compressed stats sync with your existing username and sync key. The transition server also supports older clients and prepares existing cloud statistics, including inactive accounts, for the v0.2.8 changeover. Keep using the same credentials; v0.2.7 already speaks the protocol that will remain supported afterward. SRS restore also preserves newer local review progress when the cloud schedule has not changed; if both devices changed a schedule, the earlier review takes priority. This concerns training statistics, independently of Game Focus storage.

### Where did my older Game Focus games go?

Version 0.2.7 starts Game Focus in `game_focus_v2.db`. It does not automatically import the previous `game_focus.db`. Keep the older database as a backup, then reimport and analyze your source games to populate the new library. Training statistics are stored separately in `swhub_stats.db`.

### How do I connect my playing profile?

Edit identities on **Me** and enter your EGD PIN or supported server usernames. OGS, KGS, and Pandanet can use credentials saved on the device through Profile identities or Play; KGS/Pandanet archive access needs those credentials. A failed source can retain matching cached results. KGS exposes only the latest six months of game results, so its past-year chart may be incomplete.

### Does SWHub upload my games?

Local KataGo analyzes on your machine; a remote engine receives the positions you send to it. Saved Game Focus reviews use stored analysis without reconnecting to KataGo. Stats sync sends leaderboard identity, supported attempts, and a statistics snapshot, not your SGF or Pattern Search library. Automatic app-open telemetry has been removed.

### Why is a feature missing from my build?

Feature availability varies by platform and build configuration. Local KataGo needs a supported engine environment. Teaching Rooms, FoxWQ and Kata-Coach not available in the public build.

</details>

### How does the new update system work?

Production builds check for stable GitHub releases at launch once a week. Checks run after startup, and update prompts can be dismissed. Updates preserve saved data and show the installed version's release notes on the next launch. Android uses system installation confirmation; desktop updates use the platform's installation or replacement flow. Existing users must manually install the first version(v0.2.7) with the updater.

## Feedback

- Report bugs through [SWHub issues](https://github.com/SoumyaK4/SWHub/issues).
- Join [my Discord](https://discord.gg/ptjzTWU9SP) for discussion, or the GUI channel in the [Computer Go Community](https://discord.gg/TMGEP5dxA) for KataGo and [training contribution](https://katagotraining.org/) topics.

## License

SWHub is proprietary software; it is not open source. It is distributed under the [SWHub Non-Commercial Proprietary License](LICENSE.md), which prohibits unauthorized commercial use, monetization, modification, builds, and redistribution. Third-party components remain under their respective terms, [available here](./Docs/Licenses/).
Official SWHub copies are available only from SoumyaK4 directly or through [the official SWHub binary releases](https://github.com/SoumyaK4/WeiqiHub/releases), third-party mirrors, stores, repositories, and re-uploads are not authorized.
SWHub source code is not included in the public distribution or licensed for use.
