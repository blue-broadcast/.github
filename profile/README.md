<div align="center">

<img src="https://raw.githubusercontent.com/blue-broadcast/.github/main/profile/bb-logo.png" alt="BlueBroadcast" width="112" />

# BlueBroadcast - Open Media Transport, mobile-first

**Émettre de la vidéo broadcast sur IP, depuis un téléphone, sans licence propriétaire de transport.**
Écosystème [OMT (Open Media Transport)](https://github.com/openmediatransport) porté par **Bethel Tech Africa**.

[![OMT](https://img.shields.io/badge/protocole-OMT-3B82F6)](https://github.com/openmediatransport)

</div>

---

## FR

OMT est un protocole vidéo-sur-IP libre de droits : codec intra **VMX1**, audio Planar Float, Tally bidirectionnel, découverte mDNS. Notre travail :

- un **SDK Android** qui transforme un téléphone en source OMT - **VMX1** pour vMix et tout récepteur standard, **H.264 matériel** pour les liaisons Wi-Fi (débit ~2,5× plus bas, CPU proche de 0) ;
- une **proposition H.264** (pass-through) faite en amont pour les sources basse-conso / basse bande passante ;
- des **forks outillés** du plugin OBS et de l'implémentation de référence C#.

Le SDK Android est **propriétaire** (licence utilisateur final). Tout le reste - spec, forks, exemples, docs - est **ouvert**.

## EN

OMT is a royalty-free video-over-IP protocol: intra codec **VMX1**, Planar Float audio, bidirectional Tally, mDNS discovery. What we build:

- an **Android SDK** turning a phone into an OMT source - **VMX1** for vMix and any standard receiver, **hardware H.264** for Wi-Fi links (~2.5× lower bitrate, near-zero CPU);
- an **H.264 proposal** (pass-through) submitted upstream for low-power / low-bandwidth sources;
- **tooling forks** of the OBS plugin and the C# reference implementation.

The Android SDK is **proprietary** (end-user licence). Everything else - spec, forks, samples, docs - is **open**.

---

## Dépôts / Repositories

| Dépôt | Contenu | Licence | Statut |
|---|---|---|---|
| **[omt-android](https://github.com/blue-broadcast/omt-android)** | SDK Android (`.aar`) : émetteur VMX1 + H.264, mode d'essai bridé, sample-app Compose | Propriétaire (SDK) · MIT (outillage & sample) | v0.2.1 |
| **[omt-h264](https://github.com/blue-broadcast/omt-h264)** | Proposition H.264 pass-through pour OMT (FourCC, format de trame, négociation) + APK de démo | CC-BY | Proposition |
| **[omtplugin](https://github.com/blue-broadcast/omtplugin)** | Fork du plugin OBS - Tally + décodage H.264 | GPL-2.0 | Fork actif |
| **[libomtnet](https://github.com/blue-broadcast/libomtnet)** | Fork de l'implémentation C# de référence - chemin H.264 (FFmpeg) | MIT | Fork actif |
| **[.github](https://github.com/blue-broadcast/.github)** | Ce profil + `CONTRIBUTING`, `SECURITY`, templates | - | - |

> Les `.aar` versionnés sont publiés dans les **[Releases](https://github.com/blue-broadcast/omt-android/releases)** de `omt-android`.

---

## Démarrer

**Consommer le SDK Android** (voir [omt-android/README](https://github.com/blue-broadcast/omt-android#readme)) :

```kotlin
val sender = OmtSender(
    context,
    OmtSenderConfig(
        sourceName = "STUDIO-CAM-1",
        captureWidth = 1920, captureHeight = 1080, fps = 30,
        quality = OmtQuality.Medium,
        encodeWidth = OmtResolution.HD_720.width,
        encodeHeight = OmtResolution.HD_720.height,
        videoCodec = OmtVideoCodec.Vmx1,   // ou H264 (récepteur : plugin OBS Bethel)
    ),
)
sender.start()
```

**Recevoir** : vMix, OBS Studio (+ `omtplugin`), ou tout récepteur OMT standard pour VMX1.

---

## Contribuer

- **Idées, RFC, bugs, PR** → sur le dépôt concerné (issue `enhancement` / `question` ou gabarit *Bug*). Voir [`CONTRIBUTING.md`](https://github.com/blue-broadcast/.github/blob/main/CONTRIBUTING.md).
- **Sécurité** → [`SECURITY.md`](https://github.com/blue-broadcast/.github/blob/main/SECURITY.md) - divulgation responsable, pas d'issue publique.
- La proposition H.264 vise l'**amont** : `omt-h264` sera discuté avec [openmediatransport](https://github.com/openmediatransport).

---

<div align="center">
<sub>Bethel Tech Africa · en collaboration avec l'écosystème Open Media Transport</sub>
</div>
