# Flappio on Samsung Tizen TV

The app uses the existing Flappio backend at `https://flappio.jton.be`. Connect with
Quick Connect or your usual account. App ID: `FlappioTV1.Flappio`.
Expected platform: Tizen 7 (2023) or newer. Actual playback remains to be tested.

## Certificate required before the first public download

Create a Samsung TV profile in Tizen Studio Certificate Manager, using the Samsung
Certificate Extension. Connect the TV in Device Manager and add its **DUID** to
the distributor certificate. Preserve the author certificate for future updates.

In `Pomonoli/Flappio` → Settings → Secrets and variables → Actions, add:

| Secret | Value |
| --- | --- |
| `TIZEN_AUTHOR_BASE64` | Unwrapped base64 of author `.p12` |
| `TIZEN_AUTHOR_PASSWORD` | Author password |
| `TIZEN_DISTRIBUTOR_BASE64` | Unwrapped base64 of Samsung distributor `.p12` |
| `TIZEN_DISTRIBUTOR_PASSWORD` | Distributor password |

Keep the existing `PUBLIC_RELEASE_TOKEN`. Never add these files or passwords to
this public repository. Then run **Flappio Tizen** in the private repository's
Actions, with **publish: true**. The pipeline publishes `tizen-v<version>` only
after successful build, signing and signature verification.

## Installation

1. On the TV: **Apps → 12345 → Developer Mode → On**. Enter the computer's local
   IP and restart the TV. The computer and TV must share the network.
2. Connect in Tizen Studio Device Manager. Use **Permit to install applications**.
3. Download the signed WGT from the matching `tizen-v<version>` release.
4. Connect and install:

```sh
sdb connect <tv-ip>
sdb devices
tizen install -n flappio-tizen-1.0.0.wgt -t <device-name>
```

The Samsung distributor certificate must allow the target TV's DUID. If it does
not, re-sign the WGT with your Samsung profile before installing:

```sh
tizen package -t wgt -s <Samsung-profile> -o signed -- flappio-tizen-1.0.0.wgt
tizen install -n signed/Flappio.wgt -t <device-name>
```

Use the same author certificate for subsequent updates. Tizen updates are installed
manually; Android's automatic updater is unaffected.

Check remote navigation, Enter/Back, playback, pause/seek, audio tracks and embedded
and external subtitles on the TV. A successful build is not a successful playback test.

[Samsung certificate instructions](https://developer.samsung.com/smarttv/develop/getting-started/setting-up-sdk/creating-certificates.html)
