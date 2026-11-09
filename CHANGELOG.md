# Changelog

## 0.2.13

- Preserve verified metadata repairs during Pattern Management's name/rank normalization and uncertain-name marking. Keep manual edits available and retain verification through reindexing and database export.
- Require four consecutive agreeing earlier professional ranks before Rank normalise raises a later lower rank. Preserve promotions, reject same-day or undated correction evidence, and prevent proposed corrections from supporting further changes in the same preview.
- Add F2 as a global desktop shortcut to open Settings. It starts enabled and can be remapped or disabled in Keyboard shortcuts.
- Separate task-data publication from the leaderboard and statistics-sync Worker, matching the standalone Joseki host. Prepare compatibility redirects and preserve installed catalogs, with deployment deferred.
- Speed up offline Joseki position reads with a local SQLite dictionary. Existing downloads convert automatically and preserve their original data. Remove the redundant "Compiled from OGS" heading from the empty board.
- Add control panels to all four cloud KataGo notebooks, with model choices, workspace selection, start/deploy and stop buttons, progress, logs and a connection address to copy. Setup shows the current stage, elapsed time and three recent log lines, including time since the last log during quiet steps. Remove the optional Colab heartbeat. Run only the top Open control panel block. All code blocks default to collapsed, and each notebook remains standalone.
- Show Fox's daily fast-match allowance refusal instead of a generic matchmaking error, with localized feedback after the search dialog closes.
- Match Variant Server’s repeated large-board column labels and trim unused outer water while keeping the full board editor. Show water around custom-board islands, base phone warnings on the visible board, and default new games to 19 × 19 with 5 minutes plus 20 seconds per move.
- Match current OGS undo eligibility: require a played move of your own, include passes and free-handicap placements, avoid duplicate pending requests and hide undo in Rengo.
- Keep paused OGS clocks at their remaining time when the pause began, including overtime, instead of restoring the time from the previous move.
- Bring the experimental Tygem integration from debug to release version.
- Restore interrupted Fox games from fresh player state even when the profile service is delayed. Show separate Gold, Platinum and Growth membership dates and subscription cadence in profiles.
- Support optional device-tested Qualcomm NPU engine packages for Android local KataGo, with separate analysis models and verified runtime files. Keep full-precision HumanSL, fixed batch limits and responsive cancellation while installed files are checked. Existing CPU/OpenCL downloads and model defaults remain available.
- Show Variant Server mixes directly in creation, with incompatible choices disabled. Add custom-board painting, fill tools, autosaved drafts and previews, configurable Katachi mouse/keyboard controls, five last-move markers, Magnetic slide animation and live lobby updates. Preserve mixed settings when remaking games and support zero-overtime clocks.
- Fix Variant Server failing to connect with `invalid_session`. Restore saved guest sessions and retain refreshed credentials after changing the display name.
- Update Variant Server for compact lobby summaries, incremental room updates and separately loaded review history. Add Katachi card controls, Magnetic, custom boards up to 52 × 52 and six board presets. Preserve layouts when resizing, keep card hands private and pause reconnect controls until a valid snapshot for the current room arrives.
- Prepare automatic updates for the January 2027 switch to date-based versions such as 2027.01.01, while continuing to support current-format releases.
- Make v0.2.13 the migration checkpoint for later releases. Install and open it before upgrading from an older version to a later release, and let saved-data preparation finish.
- Finish saved-data upgrades at startup, including unopened Game Focus profiles, Teaching identities, Fox accounts and collection signatures before the first puzzle download. Preserve every profile's identifiers, saved reviews, drills, resume state and current account selection. Show preparation progress and offer retry after a failed upgrade, without connecting to servers or starting KataGo.
- Upgrade old installed statistics, including versioned filenames, committed WAL data, SRS schedules and exam history, in the one-time startup migration. Preserve original recovery files and older backup restores. Later launches use the normalized installed format.
- Preserve Teaching room passwords, participant identities and permissions across server restarts. Save room creation atomically so failed saves can retry without leaving partial rooms.
- Save previously implicit animation, sound, Android KataGo, KataGo panel and shortcut preferences once before use, preserving disabled choices, existing settings and current Career progress. Remove feature-entry migration dependencies and repeated old-task-cache deletion.

## 0.2.12

- Improve localisation.
- Fix macOS startup and saved-password access after adding secure storage, keeping existing credentials in the system Keychain.
- Run the Modal KataGo analysis and contribution setup notebooks from Colab with a CPU runtime or local Jupyter. Select the target workspace and environment before deployment, and keep log and stop commands on that target.
- Preserve first moves stored in SGF root nodes. Restore previously lost root moves in new Pattern Search libraries from matching original SGF files, without changing sources. Identify merge failures by source and game ID, and offer explicit skipping with a reported count.
- Add Merge databases in Pattern Search's database manager and Create database from selection in Manage Games. Create new searchable libraries from complete sources, checked games or all filtered games, with duplicate handling, metadata and tag preservation, progress and cancellation. Keep source libraries and snapshots unchanged.
- Keep invalid Pattern Search rank ranges from broadening searches or bulk deletes, discard stale management refreshes and show selected-area continuations for the current player. Validate companion indexes before imports, refresh snapshot statistics after metadata edits and reject damaged snapshots without losing the current search.
- Initialize new empty Pattern Search libraries so they can be exported and reopened before the first game import.
- Show Pattern Search results with a smaller first game batch while retaining complete board continuations, counts and win rates. Reuse unchanged metadata filters in memory, skip obsolete search stages and show searching feedback during refresh and debounce.
- Validate Pattern Search database imports before replacement, retain originals when installation fails, reject unsupported database headers safely and preserve interrupted-import recovery during renames.
- Preserve valid SGF setup overwrites and explicit next-player nodes in Pattern Search. Count main-line moves correctly, retain terminal setup matches, refresh snapshot continuations after deletions and restore snapshot areas and filters without stale results.
- Preserve imported SGF metadata and unknown node properties in Local and Teaching Boards. Prefill save details, retain komi precision and stop adding default player ranks. Add separate edit history and validated branch copy/paste, with teacher-only editing and history reset after student moves.
- Keep root moves, annotation-only branches and explicit next-player properties when importing KataGo SGFs. Remove duplicated annotation help from saved records.
- Preserve stronger KataGo candidate analysis when weaker or equal refinement results arrive later. Keep scores, variations and visit counts from the same search.
- Keep fuzzy stones from overlapping by adjusting placement around neighbors, including contact nudges, Variant play and rectangular contribution boards. Keep shadows and markers aligned and remove sideways drift from the landing animation.
- Keep the Android screen awake during local KataGo setup, check battery temperature before loading models, and compare fixed opening, middle-game and late-game positions. Locking the phone or leaving SWHub still cancels the test.
- Add Android-only Settings > Local KataGo with performance testing and an explicit enable switch. Hide local engine choices until enabled, keep tests separate from enabling, and stop local analysis when disabled. Compare local tuning candidates with matching warm-up and cleared neural caches before longer timing samples.
- Save Android search sample ranges, separate HumanSL performance across all 29 ranks, and the test date. Keep cold GPU startup outside the comparison budget and preserve compatible kernel caches when benchmark methods change. Add download repair, verify installed files before retesting, recover completed partial downloads, and avoid unnecessary decoding and stream listeners for native probes. Keep query timeouts effective while native write acknowledgments are delayed.
- Store disposable caches in the OS app cache location instead of desktop Documents. Remove caches older than seven days automatically, including public Fox images, graph snapshots, native Pattern Search lists and managed KataGo runtime caches. Preserve installed engines, models and user libraries.
- Store saved passwords, API keys and private KataGo endpoints in device secure storage, automatically migrating existing settings. Preserve login and remember behavior, keep sync-key backups unchanged, and use private temporary files for local contribution credentials. Linux requires an unlocked desktop keyring.
- Place compact Fox room player cards above the board and size them automatically so the complete board stays visible. Hide the bottom navigation while a room is open, preserving the lobby bar and wide feature rail.
- Show compact Fox game records and Watch rooms as readable entries with wrapping categories, full player details and reachable game actions. Hide Fox record numbers in both layouts while preserving record identity and actions.
- Automatically recover interrupted Fox games with up to four fresh login attempts and increasing delays. Keep the last confirmed board visible with controls disabled, restore play from fresh server state, and return to Play if recovery fails. Never resend pending actions.
- Align compact OGS, KGS, IGS and Fox past-game views with live rooms: player strips around a centered board, visible navigation/actions, and match/FineArt details in a drawer. Keep OGS chat and score tools reachable, preserve post-game actions, and leave wide layouts unchanged.
- Keep cached OGS, KGS and IGS profile rank graphs visible while checking for updates silently. Preserve unchanged series, refresh on changed rank evidence and foreground profile checks, and avoid loading indicators over cached graphs while profile details reload.
- Add Performance Report to the saved-review display menu so compact layouts can open reports directly from stored analysis.
- Enlarge compact KataGo move navigation with two rows of touch-sized controls. Remove mobile page and saved-review titles, evenly space the main app-bar buttons, use S and R for style and rank, place display options after the hamburger menu, and move the right-sidebar button directly before Analysis Options.
- Check for app updates on every launch, including immediately after a failed check, instead of waiting 24 hours after success or six hours after failure. Keep cached update offers available offline and show only one startup dialog when post-update release notes are pending.
- Add OGS browser sign-in with PKCE alongside username/password login, with session-only tokens and a shared HTTPS callback. Fetch all incoming challenge and friend pages instead of silently truncating them.
- Align OGS turn indicators with the current realtime API's direct active-player field. Fix matchmaking cancellation while a board is opening, preserve readable server rejection messages and correct bot challenge limits at dan boundaries.
- Collapse long OGS profile sections by default and keep Active games collapsed with a count and complete clickable list. Paginate game history in groups of 20 without reloading the profile. Cache public rank graphs across scrolling and profile visits, retaining the last graph during background refreshes and failures.
- Show every OGS ongoing game in the scrollable list, removing the four-game cap. Highlight and list your turns first using OGS's active player ID, preserve live updates during refreshes and refresh after reconnecting. Display long game clocks in days, hours and minutes, with stable layout in wide player rows and compact cards.
- Switch Android tablets automatically between compact portrait and wide landscape layouts across navigation, puzzles, study boards, KataGo and online rooms. Respect available space in split-screen windows and keep existing phone and desktop layout rules.
- Add experimental Android local KataGo with separate CPU/GPU engine and model downloads, HumanSL validation, automatic tuning and memory/temperature guards. Compare available backends and keep validated CPU support when OpenCL is unavailable or slower. Desktop setup remains separate.
- Add instant FAQ search across topics, answers and shortcut instructions in all eight languages, with matching answers expanded and a clear button to return to browsing.
- Update all four Worker projects to patched deployment and testing dependencies, refresh generated bindings and adapt the runtime tests to Miniflare's updated configuration.
- Expire cloud statistics backups after 365 days without a successful sync, preserving usernames, keys, public leaderboard history and local device data. Safely recreate expired backups with the current app, preserve local favourites and SRS during recovery, and explain retention in the sync screens and FAQ in all eight languages. Older apps keep syncing unexpired accounts and require an update after an account's first backup expiry.
- Reduce Worker work for active statistics backups. Reuse parsed sync documents, update only changed snapshot chunks, stream stored chunks and avoid repeated large buffer copies. Cache public leaderboard results until their next exact time boundary, notify relevant viewers only when history changes and avoid full account scans after hibernation. Serialize room broadcasts once, reply to state requests individually and skip duplicate battle readiness/progress writes.
- Keep private reconnect identities out of battle and Teaching participant lists. Preserve Teaching rooms throughout the teacher's five-minute return window, expire lessons whose teacher never joins and keep the previous shared board if saving an update fails.
- Reject malformed and oversized room requests and messages, protect stored Teaching passwords with verifiers, and release rejected statistics-sync response streams so idle connections can hibernate. Generate Worker binding types from deployment configuration and keep room credentials out of automatic URL logs.
- Preserve live-game passes, initial turn and results in SGF exports. Support larger-board position hashes and legal multiple-stone self-captures under New Zealand rules, including replay and capture counts.
- Safely delete Teaching variations while viewing another branch. Preserve SGF comments, node markers and explicit player-to-move information, share territory corrections and calculate estimates for late joiners. Use participant IDs for roles, moderation and voice, and bound room HTTP requests.
- Support Status and Count battle answers, reject incomplete puzzle sets safely and retain battle progress through reconnects. Save accepted answers before a suspended client reaches the deadline, validate immutable final results and drop disconnected players from rematch readiness. Keep puzzle indexes when the same puzzle appears twice.
- Keep Pattern Search independent of saved Local Board studies. Export complete pattern databases and search indexes without changing the active database or filtered results. Keep board-size metadata read-only in Pattern Management.
- Save Local Board comments and markers immediately, preserve SGF node annotations, comment-only branches and player-to-move information, and safely delete variations while viewing another branch.
- Cancel stale Joseki End navigation, preserve IPv6 KataGo addresses, and correct Game Focus calendar dates and weekly activity across timezone and daylight-saving changes.
- Keep Me profile credentials separate from Play and require an explicit refresh for KGS authentication. Retain cached graphs across tab switches and failed refreshes, refresh each source silently and keep identity settings available. Keep the previous account chart visible until its replacement arrives, including after returning to Me while it loads.
- Correct Me's weekly records across New Year, heatmap dates across daylight saving and profile tooltip dates across timezones. Exclude future dates from current activity, skip invalid saved ranks and refresh training summaries at local midnight and on resume. Preserve Ranked Mode penalties during statistics sync, including remote-only rank decreases.
- Keep Statistics chart Y-axis labels readable for large sessions and durations, with adaptive intervals, measured label widths and layouts that grow with text size.
- Load puzzle previews in small batches, prioritize visible tiles and cancel queued work after scrolling away. Cache recent starting positions, defer solution loading until a puzzle opens and reuse Subjects positions across redraws.
- Add Subject to the Statistics > Charts Type selector for saved results and recent pass rates, and a Subjects toggle on By type for category success rates with a radar or progress bars. Keep Subjects and Breakthrough separate from ordinary puzzle totals and SRS.
- Require at least three stones for puzzle pattern search, support dragging the black or white tool to paint stones, and reject matches that require empty points outside the board.
- Preserve pass moves, comment-only nodes and nested branches in SGF puzzle imports. Recognize negative outcome comments before positive ones without matching parts of unrelated words.
- Save Ranked Mode rank changes immediately after an answer and retain them while reviewing earlier puzzles. Finalize completed collection runs on exit or Continue, preserving mistakes, duration and the best result by accuracy then time.
- Stop exam Previous at the first question and offer Next exam only for supported ranks with available puzzles. Restore Status and hard-mode Count retries, reveal counting solutions after score entry and keep automatic opponent replies working after custom-move review.
- Discard puzzle sessions exited before any answer. Show partial runs as Stopped with actual answer counts, grade completed exams only, and show SRS sessions as Reviewed instead of failed, including existing SRS history. Save completed results when exiting after the final answer and handle system Back consistently.
- Expand Android Settings to Backup and restore with separate Statistics and Game Focus actions. Export all Game Focus profiles, selection, accounts, games, saved analysis, drills and review history as one ZIP using SQLite snapshots that include committed WAL data. Validate archives and database structures before replacing the library, require Game Focus to be closed for restore, and recover interrupted folder publication. Preserve existing statistics backups and translate the new controls in all eight languages.
- Analyze every non-pass focus-player move across the full 20k–9d HumanSL range in Game Focus, replacing the eight-moves-per-phase cap. Share one checkpointed pass between rank guidance, saved review and the all-game radar, and reuse completed policies on resume. Older games need reanalysis for full coverage, flat or negligible evidence remains excluded from rank fits.
- Add a compact Game Focus skill radar across all saved analyzed games in the active profile, using the focus player's side in each game. Share KataGo's five skill axes, show category coverage, point loss and supported Reading depth, and keep the Dashboard offline. Place the chart beside its summary on wide screens and stack a smaller chart on narrow screens.
- Normalize Game Focus HumanSL samples and exclude flat, negligible or incomplete evidence. Use the same saved evidence for the radar Overall and style comparison, require ten informative moves, and show broad or boundary fits as inconclusive. Recover suitable evidence from older saved reviews, reanalysis adds missing evidence.
- Require Game Focus drill answers to have finite searched scores and improve on the recorded move by more than half a point, including rank-appropriate fallback answers. Measure tolerance from the best searched score for either color. Successful reanalysis refreshes answers and retires positions that no longer qualify while preserving matching drill history.
- Add Territorial, Influential and Flexible style labels below Performance Report player radars, describing strategic choices in this game. Show a dash when evidence is insufficient.
- Improve Reading estimates with meaningful tactical choices, killing groups and making groups live before capture. Count repeated replies in the same resolved fight once and filter trivial captures. Show average tactical depth when at least three separate successful sequences support it, counting moves by both players.
- Separate suggested keyboard actions: Alt+Left for global Back, P for online autoplay, and Ctrl+P for online Pass. Share autoplay across OGS, KGS, Pandanet and Fox reviews, preserve saved bindings and puzzle-arrow behaviour, and pause local playback when history, focus or visibility changes.
- Drag with the left mouse button or a finger to place multiple stones with the black or white tool on Local Board and teacher-owned Teaching Boards. Replace existing stones with the selected color, preserving undo/redo, SGF records and teaching-room updates.
- Keep Pandanet connected when profile lookup fails or times out, show missing users inline, and preserve command ordering before resuming lobby requests. Accept the returned profile name's capitalization.
- Improve OGS reconnects, early moves, Rengo/free-handicap turns and scoring updates, recover IGS move gaps and isolate canceled or finished sessions, repair KGS matchmaking, negotiation state, response cleanup and chat removals. Keep delayed requests from rolling back newer board state.
- Restore finished OGS results and keep scoring/completed clocks paused after late updates. Recognize additional IGS results and prevent overlapping history from duplicating moves. Preserve unrelated KGS comments and territory during SGF removals and ignore duplicate property additions.
- Add rank history graphs to OGS and IGS profiles, including IGS player dialogs opened from games. Hide email and birth-date fields in KGS and IGS profile summaries.
- Use one joint HumanSL likelihood fit throughout Performance Report. Match radar Overall and phase axes to their tabs, require ten informative moves, and keep bootstrap uncertainty tied to matching evidence. Put declared SGF ranks beside player names.
- Preserve rank radars, category selection and scroll position across report tabs, update them live, and remove rank loading animations. Center category controls and player stats, keep wide stats side by side.
- Match board rank labels to Move strength’s most likely HumanSL rank, including new saved reviews. Keep legacy means separate and show unknown ranks when evidence is unavailable.
- Add two five-axis HumanSL rank radars at the top of Performance Report > Rank, with per-category ranks, Overall centers, detected tactical/strategic contexts and selectable move evidence. Place them side by side on wide layouts and stack them on compact layouts. Leave missing axes unplotted and keep saved reviews offline.
- Guard HumanSL-dependent actions with settings guidance in the status area. Preserve ordinary analysis when a human model is unavailable, without an engine-recovery popup for missing-HumanSL queries.
- Keep analysis Move strength and board rank labels independent of Rank guide's suggestion range. Fetch full HumanSL rank coverage and preserve existing analysis when the filter changes, without a reanalysis prompt.
- Use the next player's stone color for KataGo's perimeter next-move markers and remove the best-move overlay's white rim so analysis overlays stay readable.
- Show each player's estimated rank for Entire Game, Opening, Midgame and Endgame in Performance Report. Simplify Analysis Move strength to the highest-probability rank.
- Add per-move HumanSL strength charts to Performance Report > Rank alongside the whole-game style estimate, with a text summary in Analysis. New Game Focus reviews retain compact evidence for offline use.
- Match Fox counting ownership and territory markers to the received rules and preserve living stones and last-move markers. Correct result reasons and SGF outcomes, and reject stale finished-game exports after a rematch.
- Correct known Fox three-digit komi encodings in downloaded SGFs before saving, review and KataGo. Preserve valid custom komi and the record's other bytes.
- Recover fox's uncertain Ignore changes with an exact-account read, show unresolved Quiz errors without releasing pending bets, and name Flying Knife score winners from the joined room.
- Show fox Ring's received support countdown in the room and Bet Info without treating local timer expiry as server closure.
- Improve desktop KataGo Auto Setup with validated GPU-to-CPU fallback, Mac installation guidance and native Linux ARM support, cancellable tuning, and a Benchmark and tune action. And preserve existing settings after failed setup.
- Repair extracted KataGo AppImage startup on Linux and cached executable permissions in both Modal notebooks.
- Repair missing CUDA 12 libraries automatically in both Colab notebooks without replacing Colab's Python packages.
- Confirm successful same-option fox Quiz stake increases from authoritative cumulative totals, while retaining uncertain bets safely.
- Apply fox compact spectator undo to the board and clock, including room-zero watches and Flying Knife rollbacks to an empty board within the same known game. Preserve subsequent move updates.
- Apply Fox spectator pause/resume updates and preserve player and spectator elapsed time when the server pauses a clock without sending a new time sample. Keep following moves synchronized and reject stale events across rematches.
- Preserve new fox private messages and reopened conversations when a delayed Clear all or Delete reply arrives, including while older history is loading.
- Disable stale fox reward actions after a failed refresh and keep Receive all unavailable while Regular Tasks are refreshing.
- Keep Fox profiles side by side on PC with larger avatars, adapt mobile profiles to narrow screens, and preserve readable text and reachable controls with larger text, short windows and the on-screen keyboard.

## 0.2.11

- Grant incoming networking to macOS releases for Teaching Rooms voice, and validate network and microphone sandbox permissions.
- Include Fox images, sound and romanization assets in the normal app manifest for every build. Validate new asset folders before release and remove temporary test/build injection.
- Bound stalled Fox runtime requests and retire failed sessions without replaying uncertain actions. Decode large production responses off the UI isolate.
- Explain pending Magic and Treasure confirmations without resending the action. Use received Quiz coin values and fees in its help.
- Existing Career progress resets to 18K once for the revised rules, later updates preserve the new progress. Ordinary training statistics and linked sync accounts are unaffected.
- One production build set now includes FoxWQ and Teaching Rooms. Teaching Rooms requires a local access password, remembered after successful entry, and its server is not contacted before access is granted.
- Add Statistics backup in Android Settings to export and restore a standalone stats database, including the linked username and sync key. Validate backups before replacing local progress.
- Make related puzzle, SRS, counter and collection writes atomic. Roll back failed schema upgrades, preserve unreadable databases, and include committed WAL data when importing legacy filenames.
- Establish v0.2.11 database compatibility tests and cover offline backup, restore and failed sync. Continue using the same `swhub_stats.db` across future releases, with automatic, data-preserving schema additions when needed.
- Show selectable Markdown release notes before updating, with Update, Later and a release-page link for manual downloads. Keep cancellation and visible download progress, format post-update notes the same way.
- Match Career's 18K–9D promotion and demotion thresholds to Fox's published table, including double-rank changes. Pick opponent styles randomly per game without requiring every style before promotion.
- Start Career opponents two HumanSL ranks below the displayed rank, retaining results-based adjustment. Subjects keeps its fixed three-rank offset and rank-adjusted sampling without rotating styles. (For Now)
- Require valid HumanSL move probabilities for Career and Subjects, filter illegal moves and avoid regular-model move fallback. Keep regular KataGo for resignation, scoring and review. Hide routine engine status chatter during Career play.
- Show KataGo win rate and estimated score after Subject passes, failures and timeouts. Allow evaluation retries without recording another attempt.
- Reuse available HumanSL comparisons in Performance Report and fetch only missing data for a full rank estimate. Remove redundant symmetry requests and reduce repeated result processing and UI updates, no notebook changes or persistent cache are required.
- Use SGF player names in KataGo and Performance Report, falling back to Human when absent. Simplify rank/style controls, remove the Career-rank shortcut, arrange rank options in two columns, and wrap report tabs on narrow screens.
- Restore Analyze and Estimate controls in OGS, KGS and Pandanet historical game viewers. Add Estimate to OGS shared reviews and use the label Estimate consistently.
- Reduce stalls when opening OGS reviews and show complete time controls in the OGS custom-match list.

## 0.2.10

- Choose Career opponent moves and passes from HumanSL probabilities with rank and style adjustments, removing regular-model search weighting. Retain automatic resignation, think time, scoring, and review through regular KataGo, existing engine and notebook setup remains supported.
- Move Find Puzzle to a Puzzles-only floating button on wide layouts and before Help on compact layouts, retaining identifier and pattern search. Give Favourites a bookmark icon and reorder Star and Management.
- Release Star modes from the downloadable task DB: 18,354 Breakthrough puzzles, balanced at 9,177 per type, and 12,800 Subjects positions, with dedicated authoring tabs. Breakthrough keeps its alternating 60-second puzzles and three-failure runs, adds a highest-level leaderboard, and remains excluded from regular puzzle libraries and totals. Subjects persists sequential rank/puzzle unlocks and attempt counts, with HumanSL replies, three 60-second byo-yomi periods and a 90% win-rate pass check, it has no leaderboard.
- Protect the new progress schema from older sync clients while preserving existing accounts and keys. Devices using v0.2.9 must upgrade before syncing an account adopted by v0.2.10.
- Reduce Cloudflare write usage by updating only changed leaderboard history. Allow idle leaderboard, Tsumego Battle, and Teaching Room sockets to hibernate. Replace lobby polling with room-change events and periodic leaderboard refreshes with activity-based updates, hopefully no more sync issues.

- Add an opt-in global Show/hide move navigation bars shortcut (Ctrl+Shift+N), remembering visibility across board, review, puzzle, and study pages while preserving keyboard and board-mouse navigation. Hide the entire KataGo bottom strip with that toggle, including Pass and the engine indicator, and return its height to the board in compact and wide layouts.
- Show average-rank badges and solved-puzzle percentage rings on collection and section rows, matching the Topics layout and replacing navigation chevrons.
- Use “Puzzle” consistently in English puzzle labels, settings, counts, messages, and help text.
- Move Teaching Rooms nickname and identity writes to the shared app settings store, retaining existing saved names and IDs while removing the competing legacy write path.
- Remove superseded Tsumego Battle reservation cleanup and unused room-code labels while preserving the one-minute empty-room rejoin window.
- Add a shared Tsumego Battle lobby with named rooms, optional passwords, and remembered nicknames. Remove room-code joining and block new entrants after a battle starts until the host starts a new round.
- Refresh help in all supported languages for SRS review rules, Joseki downloads and Tenuki, Career practice, Ranked Mode difficulty, collection continuation, and Tsumego Battle readiness.
- Place leaderboard position/name and rank/total in a compact centered row, center page headings, and remove the ranking-explanation banner.
- Retire obsolete task-deletion patches and unused My Mistakes code, translations, and dependencies. Preserve catalog-based progress cleanup and older database upgrades, modern stats databases no longer acquire retired SRS columns on relaunch.
- Add dark app color palettes in Settings > Appearance: Forest Green, Ocean Blue, Violet, Amber, and Rose. Keep the existing green palette as the default, changes apply immediately and persist independently of board and stone themes.
- Keep custom board images and stone-size controls in an expandable section that starts collapsed when the Custom board theme is selected.
- Add opt-in Global keyboard shortcuts to open Joseki and Pattern Search from any page. Configure them in Settings > Keyboard shortcuts, Back returns to the previous page.
- Fix Linux AppImage browser and external-program launches by keeping bundled libraries out of the environment inherited by host programs. Validate relocatable library paths and check packaged startup and browser handoff before GitHub uploads either Linux build.
- Strengthen release checks for Flutter runtime files, assets, and all three Android APK architectures. Prevent an unused desktop Java dependency and correct macOS framework asset validation and disabled-updater cleanup.
- Scan Windows app folders and completed packages with updated Defender definitions before GitHub uploads, retaining hashes and diagnostic logs when a scan fails. Check the completed portable archive's integrity before scanning.

## 0.2.9

- Replace My Mistakes with Favourites and the puzzle Copy SGF action with Save to favourites. Browse saved puzzles by Recent or Rank, favourites persist and sync independently of solves and SRS graduation. Remove the auto-remove-correctly-solved-mistakes setting.
- Add From Favourites and From SRS to Custom Exam. SRS exams include registered puzzles regardless of due date and record ordinary exam statistics without changing SRS membership, schedules, streaks, or graduation. Saved pools use each selected puzzle once, cap the count to availability, and are reused on redo. Existing My Mistakes presets now use SRS.
- Make Custom Exam’s Unique tasks only exclude any puzzle solved correctly at least once, including puzzles with later mistakes. Availability and selection use the same history filter.
- Rank puzzle leaderboards by difficulty first, then correct answers, with shared places for ties. Time Frenzy uses one best run selected by correct answers, then difficulty, exam ranks use only passed exams. Recalculate rolling periods from dated synced attempts, preserving v0.2.8 accounts and sync compatibility. Shared places and clearer labels require the updated app and leaderboard server.
- Add remembered, resizable wide puzzle sidebars, remaining allowed mistakes in exams and remaining lives in Time Frenzy. Timed puzzle countdowns use the game voice clips for the final nine seconds. Show verified Sensei’s Library technique links outside active attempts.
- Limit alternate-variation prompts to two after the initial correct puzzle solve, including repeated correct lines and navigation away and back. Let exam summaries and action buttons grow and scroll with larger text.
- Check for puzzle-data updates when opening puzzle features, including without a sync account, while keeping installed puzzles usable offline. Downloaded updates activate after relaunch.
- Add an optional KataGo Suggestion style menu beside Rank guide: Simple, Settle Stones, Local, Tenuki, Territorial, and Influential. It defaults to Off, remembers the selection, and favors reasonable alternatives within the active rank range while retaining engine scores and the selected opponent strategy.
- Remove Calibrated Rank and Score Loss from ordinary KataGo playstyles. Old selections fall back to standard KataGo, Career ranks, results and HumanSL styles are preserved.
- Configure Suggested line, 2nd suggested line, Played line, or Intuition PV independently for KataGo’s comparison boards, including offline Game Focus reviews. Either left board can be hidden to reveal the game tree. Animate available suggested and Intuition lines, and pause/step previews with the mouse wheel. Add an opt-in shortcut to hide or restore both left boards.
- Give wide KataGo sidebars equal, jointly resizable widths that are remembered. Show estimated point loss and evidence-based better/worse rank-fit feedback, new Game Focus analyses save rank-fit labels for offline review, while older reviews need reanalysis to add them.
- Require HumanSL and a supported recorded or selected target rank for Game Focus analysis and reanalysis. Pause with setup guidance when HumanSL output is missing or incomplete, preserving existing reviews. Generate drills only from answers fitting one to four ranks above the target, capped at 9d, existing drills adopt this rule on reanalysis.
- Make F1 open a global searchable shortcut editor, including disabled actions and page overrides, with direct enable/disable and reassignment. F1 starts enabled, other bindings remain opt-in. Keep one binding per action and preserve the first saved legacy binding.
- Group shortcuts into Global, Board & game tree, Online play, KataGo, Puzzle solving, and Study tools. Add study-workflow and room chat/board-focus actions, respect page overrides during conflict checks, and remove retired Main-page bindings. Saved bindings from that section no longer run.
- Preserve exit confirmation for KataGo and Pattern Search across global, system, and page Back actions. Allow puzzle Exit and Pattern Search Leave to share Escape with global Go back.
- Keep Ctrl+wheel and Shift+wheel available independently of keyboard shortcuts. Ctrl targets the mainline start/end from variations, Shift steps ten moves, respecting preview and explored-history limits.
- Apply a forest-green and sage theme with darker backgrounds, menu buttons and raised panels. Improve narrow-window and large-text layouts, desktop menu proportions, scrollable dialogs, keyboard focus, hover feedback, and empty/error states across study and play screens.
- Reduce the Linux GTK title bar’s height while retaining native controls, desktop colors and growth for larger fonts. Desktop-managed title bars keep their system sizing.
- Make selecting BadukTV disable only stone shadows, preserving custom cursor, fuzzy placement and stone animation preferences.
- Add independent local review for Variant Server games, with original history, editable variations and score estimates. Finished games open review automatically while the room is foreground, special variants use manual position editing. Preserve rectangular boards, missing intersections and team colors, and label estimates that lack captured-stone totals.
- Improve Variant Server clocks, remembered sidebar width and board-bottom history controls. Keep OGS/KGS/Pandanet move controls visible but disabled while actions are pending, and repair shared Estimate toggling and remembered window positions across games.
- Make KataGo Contribution follow regular top-move display preferences, hide local contribution on Android, and show optional endpoint credentials only when enabled.
- Add optional heartbeat cells to both Colab notebooks. Repair executable permissions for cached KataGo extractions and CUDA library discovery for contribution, and check the actual contribution executable before starting its tunnel.
- Check for app updates on launch once 24 hours have passed since the last successful check, instead of once a week.
- In developer Task Management, skip identical SGF position/solution duplicates, compare remaining tasks with playable side-by-side previews and search filters, and defer edits/deletions until final import confirmation. Cancelling review leaves the catalog unchanged.
- In optional FoxWQ builds, improve startup reads, retained move/resign and counting permissions, post-game matchmaking, FineArt verification, wager refresh recovery and Season Pass timeouts. Compact room-history controls and remove the footer gap. FoxWQ remains outside the public build.

## 0.2.8

- Preserve all fields in mixed-column statistics imports, including local credentials and sync baselines, roll back malformed imports instead of clearing tables. Handle corrupt compressed sync uploads without unhandled stream errors, and keep Pandanet's selected room consistent after a successful switch followed by a listing failure.
- Completed the v2-only sync cutoff. Existing usernames and sync keys remain valid, legacy-only apps must upgrade. Once an account adopts dated task data, its other devices must update their app/catalog before syncing again.
- Remember OGS/KGS/IGS game-room sidebar width, add a persisted resizable Players section, and show dismissible pass notices over game navigation controls.
- Added always-available Alt+left-click navigation from a visible stone to its placement in the current game tree or retained move history, including setup and captured/replayed stones, while preserving review and live-game restrictions.
- Added an App-wide coordinate shortcut (suggested Ctrl+Shift+C) cycling inside, outside, and hidden coordinates with immediate persisted updates across boards. KataGo coordinate cycling now uses the same global preference.
- Removed Settings-page and numbered Server workspace keyboard bindings. Variant review now uses shared Game navigation, KataGo dialog commands are listed and configurable. Fox room commands now honor the displayed enabled state instead of installing implicit defaults.
- Kept mouse gestures independent of keyboard enablement, protected standalone modifier bindings from mouse chords, and moved the mouse reference into the FAQ while removing duplicated keyboard-only key lists. Updated README controls guidance.
- Removed the KifuSnap board theme, existing selections fall back to Plain.
- Prevent delayed cloud replies and queued uploads from changing a newly restored account, commit upload baselines atomically, reject malformed sync responses, and preserve local credentials during stats imports.
- Download dated task catalogs independently of app updates, with verified first-use setup, leaderboard/sync update checks and an explicit relaunch prompt. Activate updates and migrate progress safely before cleaning old copies. Guard cloud statistics against older catalog clients overwriting newer task progress. Installed task data works offline, first use requires a download.
- Preserve complete collection results and collection/SRS resume sessions during stats sync, keep repeated mistakes visible, retain distinct exams sharing a timestamp, reserve deleted collection IDs, and count overlapping custom-exam tags accurately.
- Reconcile changed task catalogs, remove deleted task references from saved progress and sync, and preserve progress when task ranks/types change. Protect collection resume positions after membership changes and prevent reuse of deleted task IDs.
- Corrected Custom Exam’s Unique tasks only option to prevent repeats within the current exam without excluding tasks solved in previous sessions. Selected filters and saved checkbox preferences are preserved.
- Moved the Joseki dictionary out of the app bundle into a separate verified download. Download is offered when opening Joseki, Joseki includes a data-update check and offline browsing after installation. Failed updates preserve existing data.
- Improved OGS review navigation, local comments, branch deletion, and shared variation links. Fixed KGS room/watch list updates, repeated joins, chat closing, and reconnect state, isolated IGS room refreshes and concurrent game observations.
- Replaced SSGS with Variant Server in Play, with native guest profiles, game browsing, invitations, ongoing games, multiplayer seats, combined variants, custom/Circloid boards, hidden and Joseki setup, scoring, review, clocks, and reconnect handling.
- Removed the SSGS client.
- Removed external review upload actions from game records and finished games. Use Open in KataGo for analysis within SWHub.
- Updated the optional large KataGo transformer model and Colab/Modal notebook dependencies. Fixed compatibility checks for training-site transformer names and the Linux OpenVINO fallback download checksum.
- Added an Online game room shortcut (suggested M) to cycle move numbers through none, last, and all in OGS, KGS, and IGS, including OGS reviews.
- Added separate size sliders for custom black and white stone images, with live preview and individual resets.
- Split realistic stone placement into independent Fuzzy placement and Stone animation toggles, preserving existing preferences. Hover previews stay centered on intersections even with fuzzy placement enabled.

## 0.2.7
- Added public vesion weekly update checks at launch, verified platform downloads, installation handoff, and release notes on the first launch after updating. Android uses its system installer, Linux replaces the AppImage, Windows preserves installer/portable packaging, and macOS uses signed Sparkle updates.
- Made desktop shortcut settings searchable by action, page, and key, with an enabled-only filter, visible suggested keys for disabled actions, direct reassignment, and cancellable recording. Added seven shortcuts for main-page tool launches and Local Board pass, variation mode, and KataGo analysis.
- Fixed shortcut changes taking effect only after reopening a page, arrow keys being consumed by focus traversal, and duplicate callbacks. KataGo and saved reviews now inherit shared Game navigation bindings unless explicitly overridden, with conflict checks for commands sharing a board.
- Aligned KataGo and saved-review Details with the next recorded move and the board's rank-filtered recommendations. Mistake navigation stops immediately before the mistake, variation previews use the correct source position, support mouse-wheel stepping, and leave the selected game-tree node unchanged. Details text and links can be selected and copied.
- Reorganized Game Focus Imports / Games into separate Analysis, Import, and Filters panels, with independently scrolling controls on wide windows and expandable sections on narrow screens. Saved-review display corrections also apply to existing analysis without rerunning KataGo.
- Added manual ownership correction to score estimates: click an empty point to cycle Black, White, and neutral ownership, updating applicable totals immediately without placing a stone or rerunning the estimate. Corrections survive dead-group recalculation, and estimator window positions now persist across app restarts.
- Fixed older cloud snapshots making completed SRS reviews due again after restart. Restores preserve locally changed schedules and graduation when the cloud entry is unchanged, apply remote review changes when the local entry is unchanged, and resolve simultaneous changes as a complete schedule. Hidden SRS queues no longer refresh while solving.
- Made KataGo Auto Setup cancellation interrupt stalled network operations, added network timeouts, and improved redirect handling.
- Prepared cloud statistics for the v0.2.8 transition: v0.2.7 uses compressed v2 sync while the server continues supporting older clients. Existing snapshots migrate on restore or upload, and retryable background batches cover inactive accounts without changing usernames or sync keys. Fixed repeated restore/conflict merges counting the same remote progress more than once.
- Added native OGS, KGS, and IGS (Pandanet) clients in Play, with sign-in, server profiles, player and game lists, challenges and incoming requests, live play, spectating, chat, and game records.
- Unified server workspaces with labeled desktop navigation, compact mobile drawers, responsive filters, and server branding. Improved live-game reconnection, clock and overtime handling, handicap starts, pending-move feedback, and server-authorized game controls.
- Added shared game-record actions for Review in SWHub, Open in KataGo, and Download SGF. Fixed KGS archive dates/revisions and private-record fallbacks, Pandanet archive discovery and SGF retrieval, and OGS historical-game chat and review links.
- Added native OGS review discovery, creation, viewing, and authoring, including a visual game tree, variations, setup stones, comments, labels, shapes, territory, and pen drawing. Local exploration stays separate from the presenter, and publishing requires server-granted control. Live analysis respects the server's game restrictions.
- Moved public playing-profile charts from Game Focus onto Me below the training heatmap, replacing the type radar and separate Profile shortcut. Full training breakdowns remain in Puzzles > Statistics, and profile charts are included in Share stats.
- Consolidated rank-guided analysis and unranked Career practice into the normal KataGo page. Rank guide supports 20k–9d and the current Career rank, rank-aware overlays and reports, and unrecorded practice with configurable teaching auto-undo.
- Refined ranked Career's HumanSL opponents and added distinct names to ordinary KataGo bots while retaining their strategy descriptions. Improved HumanSL style-estimate performance and analysis-hover responsiveness.
- Added a saved Game Focus target-rank selector, defaulting to the recorded player rank. New analysis or reanalysis can use a chosen 20k–9d target for accepted answers, drills, and saved overlays without altering imported ranks or the independent dashboard rank estimate.
- Added analyzed-game tags such as Comeback, Epic Comeback, Dragon Slaying, Perfect Play, and Rollercoaster, derived from saved analysis and game replay without extra engine queries.
- Added bulk Game Focus drill export by all/due drills, phase, or region, deduplicating overlapping categories and preserving setup stones, turns, answers, and variations in multi-game SGF files. Saved reviews continue to work offline, with stronger-rank overlays limited to the evidence stored during analysis.
- Started Game Focus on a fresh `game_focus_v2.db`. The previous `game_focus.db` is not automatically imported, keep it as a backup and reimport/reanalyze source games for the new library. Training statistics remain in their separate database.
- Hardened local and remote KataGo startup, readiness, cancellation, reconnection, and query cleanup. Game Focus now reports startup progress and exhausted connection attempts instead of leaving analysis queues apparently running, and closed pages cannot revive obsolete engine sessions.
- Updated KataGo Auto Setup with hardware-aware backend selection, verified downloads, readiness checks, cancellation, benchmarking, and cached thread/batch tuning. CUDA setup uses v1.18.2, with backend-specific releases for other hardware, TensorRT still requires manual setup.
- Updated Colab and Modal analysis/contribution workflows to KataGo v1.18.2 CUDA, repaired runtime dependencies and launch fallbacks, added reusable Google Drive caching for analysis, and isolated remote query IDs and cancellation between WebSocket sessions.
- Added rectangular-board viewing for KataGo Contribution, reliable Finish & stop shutdown, and clearer buffered-game counters that distinguish locally retained viewer games from contribution/upload totals.
- Added local board-photo import to Local Board and Image to SGF in KataGo. Align four corners, set full or partial grid dimensions, correct detected stones, choose the next player, and confirm the position before replacing the board. Detection runs on the device.
- Reworked the shared local score estimator around Monte Carlo ownership estimates, background calculation, rule-aware score totals, and whole-group dead/alive correction. Its movable, resizable window keeps the board usable and scores a stable position snapshot until reopened.
- Added custom board, black-stone, and white-stone images in Appearance. Applied global coordinate settings across boards and corrected overlay alignment with realistic stone placement.
- Centralized desktop keyboard shortcuts into page cards with enable, rebind, reset, disable, and conflict checks. Bindings start disabled, text editing is protected, and mouse-wheel navigation remains independent with Shift for ten moves and Ctrl for start/end.
- Expanded voice prompts to English, Chinese, Spanish, Japanese, Korean, and Russian, with two randomized stone-sound pools and migration of older sound selections.
- Added the Custom Exam option Only new tasks, without repeats, excluding previously solved tasks and using each eligible task once. Requests support up to 10,000 tasks, cap at the available unique pool, and preserve the option in presets.
- Added 750 Korean Problem Academy problems across four volumes and refreshed collection ordering.
- Rebuilt debug-only Task Management with separate Tasks, Collections, and Topics controls, custom topic creation/renaming, collection hierarchy editing, bulk task edits, and file or recursive-folder SGF imports. Imports infer ranks from SGF metadata unless overridden, task conversion uses solution markers but discards comment text. Management boards follow Appearance settings.
- Added reordering of tasks within collections/topics and of the collection/topic catalogs themselves, including the management sidebars and child lists. Published catalog order is used throughout the app, deleting or reordering tasks, topics, and collections never renumbers surviving IDs. These editing tools remain debug-only.
- Improved compact board layouts, shared review controls, high-frequency redraw performance, rounded notifications, and app-bar color consistency. Organized the in-app FAQ into topic pages and expanded translation coverage across all eight locales.
- Hardened the KataGo Colab/Modal notebooks with pinned dependencies and verified atomic downloads, a medium-transformer analysis default, current b28/b40 presets, one-container Modal cost controls, direct Quick Tunnel monitor polling, complete remote-query cleanup/error reporting, safe single-session Colab contribution startup, and executable generated-Python validation.
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
- Updated KataGo Auto Setup for KataGo v1.17.1 and v1.17 transformer models: it resolves backend-specific official releases, matches CUDA with cuDNN, prefers compatible transformer models, and falls back safely, TensorRT remains unavailable until capability detection is supported. New Zealand even games now default to 7.0 komi.
- Hardened Pattern Search for large or interrupted imports with recoverable checkpoints, safer lifecycle handling, restored-index rebuilding, accurate continuation search, and staged portable `.db` database bundle import/export, including direct streaming from Android's system picker.
- Further hardened Pattern Search by rejecting incomplete or illegal SGFs, rebuilding auxiliary indexes atomically with rollback, restoring exact SGF branches and setup actions, preserving stable snapshot identities, and displaying every indexed hit with its correct outline, orientation, and continuation filtering.
- Replaced the legacy Joseki assets with an offline generated OGS explorer containing about 20k positions, full-board Fuseki support, official move categories and marks, source/tag filters, descriptions, and bundled or external related-position links.
- Preserved SGF setup stones, cleared points, player-to-move markers, and compressed setup rectangles across board, record, teaching, task-conversion, and Pattern Search imports.
- Added five stone-sound options with Random playback and selectable English or Chinese voice prompts.
- Updated SWHub's Non-Commercial Proprietary License to version 1.1, clarified official distribution and redistribution terms, and expanded the in-app Licences page with notices for bundled engines, networks, icons, themes, and Joseki content.
- Improved score estimation across study and game boards with correct prisoner accounting, authoritative side-to-move playouts, urgent capture and atari-save handling, rules-appropriate territory/area/stone totals, safer unconditional-life detection, conservative automatic dead-stone decisions, and whole-group manual marking.
- Report P2P connection failures once instead of dropping or duplicating errors.
- Refined board-coordinate layout and clipping across board views, widened large-screen Performance Report and Pattern Search statistics dialogs, fixed tsumego solution navigation, kept SRS reviews independent when My Mistakes entries are cleared or ignored, and refreshed the app icon and About-page acknowledgements.
- Improved KataGo candidate-PV hover responsiveness and made shortcut focus checks safe during page disposal, completed and corrected German, Spanish, Italian, Romanian, Russian, Ukrainian, and Chinese localization coverage.

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
- Kept desktop KataGo out of Android builds while preserving supported platform behavior.
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
- Added developer SGF Management tools with Linux support, recursive folder import, loading states, select-all, sortable columns, advanced filters, metadata trimming, SGF check/normalize, duplicate checking, and bulk metadata editing.
- Added developer Task Management improvements, including recursive SGF folder import, collection filtering, bulk rank/type/tag assignment, default branch status fixes, bulk delete, and automatic SGF rank assignment.
- Added SRS review for mistakes, with dedicated SRS/mistakes tables, detailed SRS page, ETA/count-up timer, solution navigation, and robust database initialization.
- Added status and count task types, static-position conversion, sidebar answer highlights, custom rank ranges/topics, and related SRS/attempt tracking fixes.
- Improved Local Board and task editor with Japanese score estimation, dead-stone detection, variation persistence, tree-view visibility, and visual feedback.
- Added mouse-scroll board navigation, auto-next/auto-remove-mistakes behavior, and decoupled task sidebar work.
- Improved board/server performance and time synchronization.
- Added early development documentation and task-topic guidance.

## 0.1.13
- The SADGE update of WeiqiHub
