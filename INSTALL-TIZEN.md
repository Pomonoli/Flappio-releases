# Flappio on Samsung Tizen TV

[Download Flappio Tizen 1.0.0](https://github.com/Pomonoli/Flappio-releases/releases/download/tizen-v1.0.0/flappio-tizen-1.0.0.wgt)

The app uses https://flappio.jton.be. Connect with Quick Connect or your usual account.
App ID: `FlappioTV1.Flappio`. Expected platform: Tizen 7 (2023) or newer.

This release uses ordinary Tizen author/distributor certificates. No DUID is embedded.
Both XML signatures and all app files have been verified; the payload matches the original CI build.
Installation, remote navigation, playback and subtitle behavior still require a physical TV test.

## Install

1. On the TV: Apps → enter **12345** → Developer Mode → On. Enter the installing
   computer's local IP and restart the TV. TV and computer must share the network.
2. Install Tizen Studio on the computer. Download the WGT to a local folder.
3. Open a terminal in that folder. With Tizen Studio's `tools` and `tools/ide/bin`
   directories on PATH, run:

```sh
sdb connect <tv-ip>
sdb devices
tizen install -n flappio-tizen-1.0.0.wgt -t <device-name>
```

Use the device name shown by Device Manager / `sdb devices`.
Open Flappio and connect to https://flappio.jton.be.

## If the TV rejects the ordinary certificate

Create a **Samsung TV** profile in Tizen Studio Certificate Manager using the
Samsung Certificate Extension. Add the target TV's **DUID** to its distributor
certificate; the DUID can be entered manually or selected from a connected TV.
In Device Manager, right-click the TV and select **Permit to install applications**.

Extract the WGT into an empty directory named `flappio-tizen`. Remove only
`author-signature.xml` and `signature1.xml` from that extracted directory, then
package it with your Samsung profile:

```sh
mkdir -p signed
tizen package -t wgt -s <Samsung-profile> -o signed -- <absolute-path-to-flappio-tizen>
tizen install -n signed/Flappio.wgt -t <device-name>
```

[Samsung certificate instructions](https://developer.samsung.com/smarttv/develop/getting-started/setting-up-sdk/creating-certificates.html)

## Updates and certificate backup

Updates are installed manually; Android's automatic updater is unaffected.
Preserve the original author key and password for subsequent updates.
The author certificate in this release expires on **2027-01-01 UTC**.

The matching source archive, AGPL-3.0 license, SHA256 checksums and author
fingerprint are attached to the [release](https://github.com/Pomonoli/Flappio-releases/releases/tag/tizen-v1.0.0).
Source commit: `bea93ca540e4efefdd4c8c1a54505a78bf697e57`.
