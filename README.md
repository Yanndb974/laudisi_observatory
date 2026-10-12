# Observatoire Laudisi

Laudisi watches French rolling news. Since March 2026 it has been recording, transcribing
and analysing the French rolling-news channels without interruption — BFMTV, CNews,
franceinfo and LCI nationally, plus seventeen regional channels (10 BFM local stations and
7 France 3 stations) — putting the spoken word, who is speaking, and the text on screen
onto one shared timeline.

The idea is to look at continuous news as it actually goes out, minute by minute, rather
than through the summaries and transcripts that come afterwards. So far it has been useful
for three questions: how much of the agenda the channels share, where they diverge once the
topic is held constant, and how the day is structured hour by hour.

## How it fits together

```mermaid
flowchart TD
    B[BFMTV] --> T[token manager + supervisor]
    C[CNews] --> T
    F[France Info] --> T
    LC[LCI] --> T
    RG["17 regional channels<br/>BFM · France 3"] --> T

    T --> A[Audio]
    T --> K[Keyframes]

    A --> V["Voice activity<br/>+ voice register"]
    A --> FP["Ad + simulcast<br/>fingerprints"]
    A --> R["Transcription<br/>+ diarisation"]
    K --> O["On-screen<br/>text zones"]
    K --> X[Faces]

    V --> DB
    FP --> DB
    R --> DB
    O --> DB
    X --> DB

    DB["Time-aligned store · segments · banners · detections · voice and face registries"]

    DB --> L[Topic layer]
    DB --> M[Lexical and framing]
    DB --> E[Export + QC]

    classDef chan stroke-width:2px
    class B,C,F,LC,RG chan
    style B stroke:#c0392b
    style C stroke:#1f6fb2
    style F stroke:#6d4c9f
    style LC stroke:#e8542e
    style RG stroke:#666,stroke-width:2px,stroke-dasharray:5 5
    style X stroke:#b5651d,stroke-width:2px,stroke-dasharray:5 5
    style DB fill:#f1ede6
```

Faces are held in the database but stay out of anything exported.

## What's here

Just this description and the diagram. The code, the models and the recordings aren't in
this repository.

It was presented for the first time at the Computational Humanities Research Group seminar
at King's College London, on 9 September 2026.

## Get in touch

If you work on something adjacent, or you're curious about the data, I'd be glad to hear
from you.

## Citing it

Metadata is in [`CITATION.cff`](CITATION.cff). In short:

> de Boisvilliers, Y. (2026). *Observatoire Laudisi: a continuous multimodal observatory of
> French rolling-news television.* https://github.com/Yanndb974/laudisi_observatory

---

## En bref

Laudisi enregistre, transcrit et analyse en continu depuis mars 2026 l'information en
continu en France — BFMTV, CNews, franceinfo et LCI au niveau national, et dix-sept
chaînes régionales (10 antennes BFM locales et 7 antennes France 3). La parole, les
locuteurs et les textes affichés à l'écran sont replacés sur une même ligne de temps, de
façon à observer l'information telle qu'elle est diffusée.

Ce dépôt ne contient que cette présentation et le schéma ; ni le code, ni les modèles, ni
les enregistrements n'y figurent.

© 2026 Yann de Boisvilliers — voir [`LICENSE`](LICENSE).

---

## Contact

[✉️ yann.deboisvilliers@psl.eu](mailto:yann.deboisvilliers@psl.eu)
