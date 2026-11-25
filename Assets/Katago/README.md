# Experimental Android KataGo downloads

The catalog offers native Eigen CPU and OpenCL GPU engines for 64-bit ARM Android devices. SWHub downloads the compact b6 analysis model and the original FP32 HumanSL model directly from upstream. The smaller analysis model favors speed over strength.

The updated SWHub app runs ordinary analysis with the b6 model and uses HumanSL when a rank policy is requested. On capable phones, setup can compare a parallel CPU profile with the other available settings. Open **Settings → Local KataGo → Test performance** to retest an existing installation. Use **Repair or update downloads** to check for newer packages or fix damaged files.

The CPU v2 engine ships with `katago-1.18.2-android-source-v2.tar.gz`. The OpenCL v1 engine ships with `katago-1.18.2-android-source-v1.tar.gz`. Keep the matching source archives and license notices alongside the engines.

Use `sha256sum -c SHA256SUMS` to verify the files in this folder.
