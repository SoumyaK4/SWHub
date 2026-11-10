# Experimental Android KataGo downloads

The current catalog offers native CPU and
OpenCL GPU engines, one b6 objective model and the HumanSL.
Both models download directly from their upstream URLs. No model weights are
uploaded here or included in the APK.

The current CPU package is `katago-1.18.2-android-arm64-v8a-cpu-v2.so`, with
`katago-1.18.2-android-source-v2.tar.gz`. The current GPU package is
`katago-1.18.2-android-arm64-v8a-opencl-v1.so`, with
`katago-1.18.2-android-source-v1.tar.gz`. Both pairs are required, despite their
different revision numbers. Keep the source archives and license notices with
the matching binaries.

An updated APK supplies review-aware tuning and the startup-deadline fix.
Existing installations get the current model through Repair or update downloads.
The smaller objective model trades analysis strength for speed.
