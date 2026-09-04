<div align="center">

<img src="https://raw.githubusercontent.com/blue-broadcast/.github/main/profile/bb-logo.png" alt="BlueBroadcast" width="112" />

# BlueBroadcast - Open Media Transport, mobile-first

**Broadcast video over IP from a phone, no proprietary transport license.**
Part of the [OMT (Open Media Transport)](https://github.com/openmediatransport) ecosystem, built by **Bethel Tech Africa**.

[![OMT](https://img.shields.io/badge/protocol-OMT-3B82F6)](https://github.com/openmediatransport)

</div>

---

OMT is a royalty-free video-over-IP protocol: intra codec **VMX1**, Planar Float audio, bidirectional Tally, mDNS discovery. What we build:

- an **Android SDK** turning a phone into an OMT source - **VMX1** for vMix and any standard receiver, **hardware H.264** for Wi-Fi links (~2.5× lower bitrate, near-zero CPU);
- an **H.264 proposal** (pass-through) submitted upstream for low-power / low-bandwidth sources;
- **tooling forks** of the OBS plugin and the C# reference implementation.

The Android SDK is **proprietary** (end-user license). Everything else - spec, forks, samples, docs - is **open**.

---

## Repositories

| Repo | Content | License | Status |
|---|---|---|---|
| **[omt-android](https://github.com/blue-broadcast/omt-android)** | Android SDK (`.aar`): VMX1 + H.264 sender, capped trial mode, Compose sample-app | Proprietary (SDK) · MIT (tooling & sample) | v0.2.1 |
| **[omt-h264](https://github.com/blue-broadcast/omt-h264)** | H.264 pass-through proposal for OMT (FourCC, frame format, negotiation) + demo APK | CC-BY | Proposal |
| **[omtplugin](https://github.com/blue-broadcast/omtplugin)** | OBS plugin fork - Tally + H.264 decoding | GPL-2.0 | Active fork |
| **[libomtnet](https://github.com/blue-broadcast/libomtnet)** | C# reference implementation fork - H.264 path (FFmpeg) | MIT | Active fork |
| **[.github](https://github.com/blue-broadcast/.github)** | This profile + `CONTRIBUTING`, `SECURITY`, templates | - | - |

> Versioned `.aar` builds are published in `omt-android`'s **[Releases](https://github.com/blue-broadcast/omt-android/releases)**.

---

## Getting started

**Consume the Android SDK** (see [omt-android/README](https://github.com/blue-broadcast/omt-android#readme)):

```kotlin
val sender = OmtSender(
    context,
    OmtSenderConfig(
        sourceName = "STUDIO-CAM-1",
        captureWidth = 1920, captureHeight = 1080, fps = 30,
        quality = OmtQuality.Medium,
        encodeWidth = OmtResolution.HD_720.width,
        encodeHeight = OmtResolution.HD_720.height,
        videoCodec = OmtVideoCodec.Vmx1,   // or H264 (receiver: Bethel's OBS plugin)
    ),
)
sender.start()
```

**Receiving**: vMix, OBS Studio (+ `omtplugin`), or any standard OMT receiver for VMX1.

---

## Contributing

- **Ideas, RFCs, bugs, PRs** → on the relevant repo (`enhancement` / `question` issue, or the *Bug* template). See [`CONTRIBUTING.md`](https://github.com/blue-broadcast/.github/blob/main/CONTRIBUTING.md).
- **Security** → [`SECURITY.md`](https://github.com/blue-broadcast/.github/blob/main/SECURITY.md) - responsible disclosure, no public issues.
- The H.264 proposal targets **upstream**: `omt-h264` will be discussed with [openmediatransport](https://github.com/openmediatransport).

---

<div align="center">
<sub>Bethel Tech Africa · in collaboration with the Open Media Transport ecosystem</sub>
</div>
