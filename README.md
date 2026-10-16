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

**Flappio Tizen 1.0.0**: [Download the signed WGT](https://github.com/Pomonoli/Flappio-releases/releases/download/tizen-v1.0.0/flappio-tizen-1.0.0.wgt) · [Release and matching source](https://github.com/Pomonoli/Flappio-releases/releases/tag/tizen-v1.0.0)

Uses the existing web interface, Samsung remote support, AVPlay and subtitles with
the same backend. Expected platform: Tizen 7 / 2023 or newer.
The WGT is signed with ordinary Tizen certificates, with no DUID embedded.
Signature and original build contents are verified; installation and playback
have not been tested on a physical Samsung TV. Some TVs may require re-signing
with a Samsung certificate listing their DUID.

See [Samsung installation and certificate setup](INSTALL-TIZEN.md).
