# Changelog

## 0.2.7
- Added public vesion weekly update checks at launch, verified platform downloads, installation handoff, and release notes on the first launch after updating. Android uses its system installer, Linux replaces the AppImage, Windows preserves installer/portable packaging, and macOS uses signed Sparkle updates.
- Made desktop shortcut settings searchable by action, page, and key, with an enabled-only filter, visible suggested keys for disabled actions, direct reassignment, and cancellable recording. Added seven shortcuts for main-page tool launches and Local Board pass, variation mode, and KataGo analysis.
- Aligned KataGo and saved-review Details with the next recorded move and the board's rank-filtered recommendations. Mistake navigation stops immediately before the mistake; variation previews use the correct source position, support mouse-wheel stepping, and leave the selected game-tree node unchanged. Details text and links can be selected and copied.
- Added manual ownership correction to score estimates: click an empty point to cycle Black, White, and neutral ownership, updating applicable totals immediately without placing a stone or rerunning the estimate. Corrections survive dead-group recalculation, and estimator window positions now persist across app restarts.
- Fixed older cloud snapshots making completed SRS reviews due again after restart. Restores preserve locally changed schedules and graduation when the cloud entry is unchanged, apply remote review changes when the local entry is unchanged, and resolve simultaneous changes as a complete schedule. Hidden SRS queues no longer refresh while solving.
- Made KataGo Auto Setup cancellation interrupt stalled network operations, added network timeouts, and improved redirect handling.
- Prepared cloud statistics for the v0.2.8 transition: v0.2.7 uses compressed v2 sync while the server continues supporting older clients. Existing snapshots migrate on restore or upload, and retryable background batches cover inactive accounts without changing usernames or sync keys. Fixed repeated restore/conflict merges counting the same remote progress more than once.
- Added native OGS, KGS, and IGS (Pandanet) clients in Play, with sign-in, server profiles, player and game lists, challenges and incoming requests, live play, spectating, chat, and game records.
- Unified server workspaces with labeled desktop navigation, compact mobile drawers, responsive filters, and server branding. Improved live-game reconnection, clock and overtime handling, handicap starts, pending-move feedback, and server-authorized game controls.
- Added shared game-record actions for Review in SWHub, Open in KataGo, Open in AI Sensei, and Download SGF. Fixed KGS archive dates/revisions and private-record fallbacks, Pandanet archive discovery and SGF retrieval, and OGS historical-game chat and review links.
- Added native OGS review discovery, creation, viewing, and authoring, including a visual game tree, variations, setup stones, comments, labels, shapes, territory, and pen drawing. Local exploration stays separate from the presenter, and publishing requires server-granted control. Live analysis respects the server's game restrictions.
- Moved public playing-profile charts from Game Focus onto Me below the training heatmap, replacing the type radar and separate Profile shortcut. Full training breakdowns remain in Puzzles > Statistics, and profile charts are included in Share stats.
- Consolidated rank-guided analysis and unranked Career practice into the normal KataGo page. Rank guide supports 20k–9d and the current Career rank, rank-aware overlays and reports, and unrecorded practice with configurable teaching auto-undo.
- Refined ranked Career's HumanSL opponents and added distinct names to ordinary KataGo bots while retaining their strategy descriptions. Improved HumanSL style-estimate performance and analysis-hover responsiveness.
- Added a saved Game Focus target-rank selector, defaulting to the recorded player rank. New analysis or reanalysis can use a chosen 20k–9d target for accepted answers, drills, and saved overlays without altering imported ranks or the independent dashboard rank estimate.
- Added analyzed-game tags such as Comeback, Epic Comeback, Dragon Slaying, Perfect Play, and Rollercoaster, derived from saved analysis and game replay without extra engine queries.
- Added bulk Game Focus drill export by all/due drills, phase, or region, deduplicating overlapping categories and preserving setup stones, turns, answers, and variations in multi-game SGF files. Saved reviews continue to work offline, with stronger-rank overlays limited to the evidence stored during analysis.
- Started Game Focus on a fresh `game_focus_v2.db`. The previous `game_focus.db` is not automatically imported; keep it as a backup and reimport/reanalyze source games for the new library. Training statistics remain in their separate database.
- Hardened local and remote KataGo startup, readiness, cancellation, reconnection, and query cleanup. Game Focus now reports startup progress and exhausted connection attempts instead of leaving analysis queues apparently running, and closed pages cannot revive obsolete engine sessions.
- Updated KataGo Auto Setup with hardware-aware backend selection, verified downloads, readiness checks, cancellation, benchmarking, and cached thread/batch tuning. CUDA setup uses v1.18.2, with backend-specific releases for other hardware; TensorRT still requires manual setup.
- Updated Colab and Modal analysis/contribution workflows to KataGo v1.18.2 CUDA, repaired runtime dependencies and launch fallbacks, added reusable Google Drive caching for analysis, and isolated remote query IDs and cancellation between WebSocket sessions.
- Added rectangular-board viewing for KataGo Contribution, reliable Finish & stop shutdown, and clearer buffered-game counters that distinguish locally retained viewer games from contribution/upload totals.
- Added local board-photo import to Local Board and Image to SGF in KataGo. Align four corners, set full or partial grid dimensions, correct detected stones, choose the next player, and confirm the position before replacing the board. Detection runs on the device.
- Reworked the shared local score estimator around Monte Carlo ownership estimates, background calculation, rule-aware score totals, and whole-group dead/alive correction. Its movable, resizable window keeps the board usable and scores a stable position snapshot until reopened.
- Added custom board, black-stone, and white-stone images in Appearance. Applied global coordinate settings across boards and corrected overlay alignment with realistic stone placement.
- Centralized desktop keyboard shortcuts into page cards with enable, rebind, reset, disable, and conflict checks. Bindings start disabled, text editing is protected, and mouse-wheel navigation remains independent with Shift for ten moves and Ctrl for start/end.
- Expanded voice prompts to English, Chinese, Spanish, Japanese, Korean, and Russian, with two randomized stone-sound pools and migration of older sound selections.
- Added the Custom Exam option Only new tasks, without repeats, excluding previously solved tasks and using each eligible task once. Requests support up to 10,000 tasks, cap at the available unique pool, and preserve the option in presets.
- Added 750 Korean Problem Academy problems across four volumes and refreshed collection ordering.
- Improved compact board layouts, shared review controls, high-frequency redraw performance, rounded notifications, and app-bar color consistency. Organized the in-app FAQ into topic pages and expanded translation coverage across all eight locales.
- Hardened the KataGo Colab/Modal notebooks with pinned dependencies and verified atomic downloads, a medium-transformer analysis default, current b28/b40 presets, one-container Modal cost controls, direct Quick Tunnel monitor polling, complete remote-query cleanup/error reporting, safe single-session Colab contribution startup, and executable generated-Python validation.
- Added persistent Google Drive caching to the contribution Colab while keeping KataGo execution local to the runtime and excluding temporary downloads and credentials from the cache.

## 0.2.6+78
- Added a cumulative estimated HumanSL rank to Game Focus Dashboard Home. Each completed rank-aware analysis contributes a bounded phase-balanced sample of the app user's moves across 20k–9d, and deleting a game immediately removes its evidence from the recalculated estimate.
- Made Game Focus rank-aware analysis status accurate, including explicit partial/unavailable objective fallbacks, and normalized OGS numeric rankings so unclear SGF ranks can use the discovered account rank.
- Unified KataGo, Career, and Game Focus opening/midgame/endgame labels with fixed per-board-size move cutoffs, migrated saved Game Focus drill phases without reanalysis, and made the Career/Game Focus AI Top 5 metric a literal top-five match.
- Made Performance Report rank output clearer and more honest: it now reports a HumanSL style fit with its full uncertainty range, while two-symmetry raw-policy probes reduce noise without changing normal KataGo analysis workloads.
- Hardened stats and leaderboard sync with restore-before-upload startup and manual Me-page syncing, acknowledged score retries, rolling periods, compressed per-user snapshots, and conflict-safe multi-device merges while retaining compatibility with pre-v0.2.7 clients.
- Renamed the Train and Home destinations to Puzzles and Tools, moved Joseki and Global Leaderboards into their owning sections, capped both tile grids at three columns, put Me first in the wide navigation rail, added a direct Game Focus Profile action, and hid the stats-sync key on screen.
- Replaced Game Tsumegos with Game Focus: import complete local or supported public-account games, analyze them in a resumable KataGo queue, review saved results offline, and turn mistakes into full-board drills with their own two-week schedule.
- Added Game Focus Profile, combining configured public EGD/server identities into source-filterable rank-progress and win/loss charts, cached locally without starting KataGo.
- Improved Game Focus weakness review by ranking groups by average points lost per mistake, opening saved reviews at the selected pre-mistake position, and keeping previews focused on the played move.
- Extended Game Focus with a Last-10/All-time overall and phase-accuracy graph in Weaknesses, cached Performance Reports, shared KataGo settings, optional point-loss filtering, SGF drill export, compact in-chart tooltips, and reliable Refresh after restoring `game_focus.db`.
- Added KataGo Contribution in Tools. Contribute through a compatible secure WebSocket endpoint or a local KataGo process, with live game/analysis viewing and Colab or Modal setup guides.
- Added HumanSL Rank(Avg.) estimates to Performance Report and Career Analysis, and refined Career's rank-guided human-model opponents and styles.
- Updated KataGo Auto Setup for KataGo v1.17.1 and v1.17 transformer models: it resolves backend-specific official releases, matches CUDA with cuDNN, prefers compatible transformer models, and falls back safely; TensorRT remains unavailable until capability detection is supported. New Zealand even games now default to 7.0 komi.
- Hardened Pattern Search for large or interrupted imports with recoverable checkpoints, safer lifecycle handling, restored-index rebuilding, accurate continuation search, and staged portable `.db` database bundle import/export, including direct streaming from Android's system picker.
- Further hardened Pattern Search by rejecting incomplete or illegal SGFs, rebuilding auxiliary indexes atomically with rollback, restoring exact SGF branches and setup actions, preserving stable snapshot identities, and displaying every indexed hit with its correct outline, orientation, and continuation filtering.
- Replaced the legacy Joseki assets with an offline generated OGS explorer containing about 20k positions, full-board Fuseki support, official move categories and marks, source/tag filters, descriptions, and bundled or external related-position links.
- Preserved SGF setup stones, cleared points, player-to-move markers, and compressed setup rectangles across board, record, teaching, task-conversion, and Pattern Search imports.
- Added five stone-sound options with Random playback and selectable English or Chinese voice prompts.
- Improved score estimation across study and game boards with correct prisoner accounting, authoritative side-to-move playouts, urgent capture and atari-save handling, rules-appropriate territory/area/stone totals, safer unconditional-life detection, conservative automatic dead-stone decisions, and whole-group manual marking.
- Report P2P connection failures once instead of dropping or duplicating errors.
- Refined board-coordinate layout and clipping across board views, widened large-screen Performance Report and Pattern Search statistics dialogs, fixed tsumego solution navigation, kept SRS reviews independent when My Mistakes entries are cleared or ignored, and refreshed the app icon and About-page acknowledgements.
- Improved KataGo candidate-PV hover responsiveness and made shortcut focus checks safe during page disposal; completed and corrected German, Spanish, Italian, Romanian, Russian, Ukrainian, and Chinese localization coverage.

## 0.2.5+67
- Joseki page in Train, including about 5,000 bundled variations, pass/tenuki branches, a readable corner board, linked comments, cleaned labels/source data, and debug-only source-saving tools.
- Improved SRS review with neutral cancellation, speed-based scheduling, short failed-review retries, capped intervals, and 5-correct graduation.
- Improved Pattern Search and Pattern Management with better selected-area search, imports/indexing/rebuild progress, search history, position statistics, metadata repair/normalising summaries, duplicate handling, and safer maintenance.
- Rebuilt KataGo Page with a modular SWHub-style analysis/play UI, themed controls, persisted panels, local/alternate/remote engine setup, hardware-aware Auto Setup, modest b18/b28 model downloads, manual OpenCL choice, and a Colab notebook.
- Expanded KataGo study/play with human-rank heatmaps, aligned analysis overlays, full-game reanalysis, Tsumego Frame, timers, AI styles, and a sortable/filterable Performance Report mistakes tab.
- Added Game Tsumegos from KataGo analysis, with manual position saves, bulk mistake-position saves, tags/notes, a Home list view, board previews, filtering/sorting, multi-select delete, and playable PV review.
- Added Career Mode under Play, with ranked KataGo human-model games, Fox-style rank windows, rank history/peak tracking, post-game review, Career SGF saves, and stronger-rank teaching practice with auto-undo.
- Improved SGF workflows with SGF/GIB/NGF import from picker, drag/drop, clipboard, file association, save/save-as/copy, folder favorites, metadata/notes preservation, analysis feedback export, Linux/AppImage thumbnails, and single-instance desktop file opening.
- Standardized desktop-generated files under `Documents/SWHub`, refined board/task visuals and SGF/game-tree handling, refreshed FAQ/localization coverage, cleaned legacy code/assets, and added focused SRS, Pattern Search, KataGo, SGF, and game-record tests.

## 0.2.41
- Added Teaching Rooms from Play, with live shared boards, room chat/voice, teacher/student roles, and turn-based student move assignment.
- Expanded SGF tools with connected-group liberty counts, dynamic smiley status markers, group marker toggles, and theme-aware move icons.
- Added one-at-a-time student voice permission in Teaching Rooms, so a teacher can let one student speak alongside the teacher broadcast while everyone hears both.
- Added optional Teaching Room passwords for protected room entry.
- Improved pen drawing cursor tracking of sgf tools.
- Added Smiley and Liberties SGF Tool Markers.

## 0.2.4
- Added automatic stats and leaderboard sync, including sync-key credential handling and safer stats export.
- Improved leaderboard history, period/category reporting, and merge support for exams and leaderboard attempts.
- Reworked the desktop KataGo page with a stronger review UI, improved analysis controls, player setup, timers, and SGF save fixes.
- Kept desktop KataGo out of Android builds while preserving cloud katago on all platforms.
- Added SRS graduation counting and fixed SRS, tsumego variation, Ghost Mode, and server scoring issues.
- Made SGF Management available from Home on all supported platforms and restricted task management to debug/developer mode.
- Improved local board page to have more sgf editing options, and fixed the visual game tree looks.
- Updated FAQ content and refreshed/fixed task database content.

## 0.2.3
- Added SSGS multiplayer rooms with invitations, team games, Rengo-style play, One Color Go, Traitor Go, Blind Go, and Phantom Go variants.
- Improved SSGS scoring sync with host-only counting controls, synchronized manual dead-stone marking, full ownership-map transmission, and reset of scoring acceptance state.
- Added byo-yomi period management and timeout handling to the SWHub/SSGS server.
- Fixed SSGS and Traitor variant desync/reconnection issues, including state redaction and client-side reconciliation.
- Added "solve all correct variations" support for tsumego, with follow-up fixes for multi-variation solving.
- Fixed Ghost Mode so initial stones stay visible and unrelated/random stones do not appear.
- Fixed SRS-related issues and refreshed/fixed task data, including Diabolical warm-up answers.
- Made SGF Management available on all supported platforms while keeping task management developer-only/debug-only.
- Cleaned up OGS-related code and added a robust portable Windows build workflow.
- Improved sync-related behavior and updated the FAQ.

## 0.2.2
- Added the Me page with profile-style stats, sharing, unique solved tracking, and a GitHub-style training heatmap.
- Added global leaderboards for training modes, with period filters and duplicate-username handling.
- Added stats persistence/sync improvements and safeguards against stats loss on upgrade.
- Added more stone sound options.
- Added Diabolical tsumego placeholders and initial Diabolical task data.
- Improved local-board scoring mode and leaderboard reporting.
- Cleaned up localization files and fixed black-screen/startup issues.

## 0.2.1
- Added Pattern Search exploration improvements, Guess mode support, score estimation, and a fuller-height search layout.
- Added position statistics dialogs with histograms, dynamic date ranges, winrate charts, and improved continuation displays.
- Improved Pattern Search and Pattern Management pages, including duplicate detection robustness, metadata display, player names, and sidebar summaries.
- Modernized and optimized libkombilo with C++17 support, binary caching, faster startup/loading, and safety/UX fixes. Plus fixed a lot of libkombilo TODO & bugs.
- Fixed Pattern Search import crashes, handicap-game discovery, metadata filtering, continuation disappearance, and hidden-coordinate board padding.
- Improved leaderboard periods and histogram behavior.

## 0.2.0
- Optimized SGF Management and Pattern Management, including faster rank filtering and better metadata handling.
- Renamed the local server/client flow to SSGS and fixed duplicate users in the SSGS lobby.
- Added the FAQ page in Settings, Esc shortcut support, board mouse-scroll navigation, and broader keyboard shortcut coverage.
- Improved Pattern Search database import/export and added Ctrl+S shortcut support.
- Added new/updated collections, synced puzzle databases, and added placeholder Diabolical collection content.
- Added many status/count tasks, including 9x9, 13x13, and 19x19 count tasks.
- Fixed task reset interactivity, Ghost Mode behavior, and ghost stone shadows.
- Added auto-next for ranked mode and collections.
- Consolidated user data files into the SWHub folder on desktop.
- Updated FAQ/about text and Android workflow cleanup.

## 0.1.16
- 294 Status type tasks added
- 391 Count type tasks added
- Ghost Mode in Task Attempts
- Randomize Task Colors
- Block Stone Placements in Count & Status by default
- Count Hard Mode
- New Collection
- Added/updated count task rank ranges and task database content.
- Improved behavior around status/count task variations.

## 0.1.15
- Added Simple Go Server support, later renamed/refined as SSGS.
- Added custom board cursor assets and cursor settings.
- Added stone scaling support.
- Added fuzzy stone placement for more realistic stone positions.
- Added wiggle animation when placing stones.
- Added the new Status and Count task types.
- Improved Local Board behavior and fixed Local Board page issues.
- Fixed board preview updates in Appearance settings.
- Improved board line/stone rendering to support the new placement and scaling options.

## 0.1.14
- Added P2P Tsumego Battle support with lobby/rematch fixes, timer fixes, presence/resumption improvements, and updated worker configuration.
- Added the first Pattern Search workflow, including Guess Mode groundwork, crash fixes, and TODO cleanup.
- Added developer Task Management improvements, including recursive SGF folder import, collection filtering, bulk rank/type/tag assignment, default branch status fixes, bulk delete, and automatic SGF rank assignment.
- Added SRS review for mistakes, with dedicated SRS/mistakes tables, detailed SRS page, ETA/count-up timer, solution navigation, and robust database initialization.
- Added status and count task types, static-position conversion, sidebar answer highlights, custom rank ranges/topics, and related SRS/attempt tracking fixes.
- Improved Local Board and task editor with Japanese score estimation, dead-stone detection, variation persistence, tree-view visibility, and visual feedback.
- Added mouse-scroll board navigation, auto-next/auto-remove-mistakes behavior, and decoupled task sidebar work.
- Improved board/server performance and time synchronization.
- Added early development documentation and task-topic guidance.

## 0.1.13
- The SADGE update of WeiqiHub
