# Flappio for TV

Flappio is an Android TV and Android app based on [AIOStreams](https://github.com/Viren070/AIOStreams), with its native player, subtitle tools and profiles.

**Flappio 1.0.0 is available.** [View the release and all downloads](https://github.com/Pomonoli/Flappio-releases/releases/tag/android).

## Downloads

| Device architecture | Signed APK |
| --- | --- |
| ARM 32-bit, including Google TV Streamer | [armeabi-v7a](https://github.com/Pomonoli/Flappio-releases/releases/download/android/flappio-android-armeabi-v7a-1.0.0.apk) |
| ARM 64-bit Android | [arm64-v8a](https://github.com/Pomonoli/Flappio-releases/releases/download/android/flappio-android-arm64-v8a-1.0.0.apk) |
| x86 64-bit Android | [x86_64](https://github.com/Pomonoli/Flappio-releases/releases/download/android/flappio-android-x86_64-1.0.0.apk) |

Choose the architecture supported by the installed Android operating system, which may differ from the processor architecture.

## Install and connect

1. Download the APK for your Android device and open it on that device. Allow installation from the app used to open the APK if Android asks.
2. Open Flappio and connect to `https://flappio.jton.be`.
3. Sign in using Quick Connect or your usual server account.

Flappio uses application ID `be.jton.flappio` and can be installed alongside the official AIOStreams app. Its first sign-in is separate. Subsequent Flappio releases use the same signing certificate so updates retain Flappio's settings and sign-in.

## Updates and verification

The app checks the Flappio stable update feed on startup and periodically while running. You can also check through Settings → Updates → Check now. Android may require confirmation to install an update. The web interface is bundled in the APK, so interface updates arrive through app releases.

- [Stable update feed](https://github.com/Pomonoli/Flappio-releases/releases/download/android/update.json)
- [SHA256 checksums](https://github.com/Pomonoli/Flappio-releases/releases/download/android/SHA256SUMS)
- [Signing certificate SHA256](https://github.com/Pomonoli/Flappio-releases/releases/download/android/signing-certificate.sha256)

## Source and license

The matching source for version 1.0.0 is available as [flappio-source-1.0.0.tar.gz](https://github.com/Pomonoli/Flappio-releases/releases/download/android/flappio-source-1.0.0.tar.gz), under [AGPL-3.0](https://github.com/Pomonoli/Flappio-releases/releases/download/android/LICENSE). Each published app version includes its corresponding source archive.

## Samsung Tizen TV

The Flappio Tizen wrapper reuses the existing web interface, Samsung remote support,
AVPlay and subtitle handling with the same backend. Builds target Tizen 7 / 2023 or newer.
Public `.wgt` downloads are published only after signing and signature verification.
Without a Samsung certificate profile, the build remains an unsigned private Actions artifact.
Playback has not been verified on a physical Samsung TV.

See [Samsung installation and certificate setup](INSTALL-TIZEN.md).
