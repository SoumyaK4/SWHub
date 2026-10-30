# KataGo Contribution on Modal

SWHub has a KataGo Contribution page in normal release builds that controls a
dedicated Modal GPU contributor and displays its self-play games live. This is
separate from `Kata_Modal.ipynb`, which remains an analysis server for normal
Kata and Career Mode. The easiest setup is `Kata_Modal_Contribution.ipynb`,
which contains the complete Modal app, writes it into the notebook runtime,
creates the endpoint, deploys the contributor, and prints the exact WebSocket
URL to paste into SWHub. No repository checkout, separate Python file, Modal
secret, or application login is required for the default setup. An optional
controller login can be enabled as described below.

## Deploy

Run `Kata_Modal_Contribution.ipynb` from top to bottom. Its **Write the Modal
app** cell creates `modal_katago_contribute.py` only in the notebook runtime,
and the later cell deploys that generated app. By default there is no
application login. To require one, set `ENABLE_CONTRIBUTOR_LOGIN = True` in
the optional authentication cell and run it before deploying. It reads a
username/password and passes them through an ephemeral Modal secret, SWHub
sends matching Controller login fields in `endpointAuth`. This is separate
from the training account and proxy credentials. Keep the URL private even
when enabled: the application login happens after container startup.

Modal prints an HTTPS function URL. Convert it to WebSocket form and append the
contribution path:

```text
https://WORKSPACE--katago-contribute-contribution-app.modal.run
wss://WORKSPACE--katago-contribute-contribution-app.modal.run/contribute
```

Open **Tools > KataGo Contribution** in SWHub, open its settings dialog, and
enter:

- the `wss://.../contribute` URL,
- a verified `katagotraining.org` username and unique password,
- the desired contribution settings.

SWHub saves the endpoint, optional controller login and training account in
local shared preferences.
After the first setup, opening the page and pressing **Start** is sufficient.

The default deployment requests one T4, four CPU cores, 8 GiB memory, a
4-hour maximum session, and at most one Modal container. Change `MODAL_GPU` or
`SESSION_TIMEOUT_HOURS` near the top of the notebook's embedded app cell, then
rerun that cell and redeploy, if needed.

## Behavior and safety

- The service uses the standard KataGo v1.18.2 CUDA 12.8/cuDNN 9.8 binary.
  Its official GitHub SHA-256 digest is pinned and verified before extraction.
  Do not replace it with a `+bs50` build, which cannot contribute.
- KataGo's contribution server selects and downloads the current training
  network and task. SWHub does not select a small/medium/large analysis model.
- Network/task caches live in the `katago-contribute` Modal Volume. Account
  credentials are written only to a mode-`0600` temporary config and deleted
  when the session ends.
- SWHub persists the katagotraining.org username and password in local shared
  preferences, as requested, along with the endpoint and tuning settings.
  Shared preferences are ordinary local app storage, not a password vault.
  An optional authenticated-proxy password remains memory-only.
- The settings dialog exposes the supported contribution options,
  including proxy authentication, model mirrors, task batching, and
  performance-report cadence. Backend/future options remain available as
  validated additional config lines. Set `maxRatingMatches` to `0` to disable
  rating tasks while continuing normal self-play, it is ignored when
  rating-only mode is enabled. Each SWHub control explains what it changes,
  when to use it, and the recommended value for the notebook's T4.
- `logGamesAsJson=true` is forced so SWHub can display games. The official
  `pause`, `resume`, `quit`, and `forcequit` stdin commands drive the controls.
- On wide windows, session/game/log details are on the left, the live board is
  centered, and streamed score/win-rate graphs plus KataGo's candidate moves
  are on the right. The app bar does not duplicate the already-visible details
  panel. On smaller windows, where that panel cannot fit, it remains available
  as a drawer and live analysis uses the opposite drawer. Scroll the mouse
  wheel over the board to move backward or forward one position. Candidate
  markers are shown only on the exact position that KataGo analyzed, the newest
  played move can be one position ahead of that analysis snapshot.
- Closing SWHub or losing the WebSocket force-stops the process so an orphaned
  GPU session does not continue spending. **Finish games & stop** sends `quit`
  and lets in-progress games upload first. If contribution was paused, SWHub
  resumes it automatically first because KataGo cannot finish paused games.
- The app-bar Back button, system Back, and Escape always ask for confirmation
  before leaving this page. Leaving during an active session force-stops it,
  use **Finish games & stop** first when the active games should upload.
- Partial games are not uploaded. Prefer sessions of at least an hour and use
  graceful stop whenever possible.

Create and verify the training account at
<https://katagotraining.org/accounts/signup/>. Contribution totals appear at
<https://katagotraining.org/contributions/>.
