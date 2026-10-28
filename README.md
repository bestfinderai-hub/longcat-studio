# LongCat Studio SE — Talking Avatar

Ladda upp ett foto + skriv text på svenska → få en talande video.

Bygger på [LongCat-Video-Avatar 1.5](https://github.com/meituan-longcat/LongCat-Video) av Meituan (MIT-licens).

---

## Snabbstart

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bestfinderai/longcat-studio/blob/main/LongCat_Studio_SE.ipynb)

1. Klicka "Open In Colab"
2. **Aktivera A100:** Runtime → Change runtime type → A100 *(kräver Colab Pro)*
3. Kör cellerna **1–7** uppifrån och ner (tar ~15 min första gången)
4. Kör cell **8** → klicka på den publika Gradio-länken → börja generera

---

## Krav

| GPU | VRAM | Status |
|-----|------|--------|
| **A100 (40 GB)** | 40 GB | ✅ Rekommenderas |
| **V100 (32 GB)** | 32 GB | ✅ Fungerar |
| T4 (15 GB) | 15 GB | ❌ För liten |

Colab Pro kostar ~10 USD/mån och ger tillgång till A100.

---

## Vad som händer

```
Ditt foto + din svenska text
        ↓
Edge-TTS (Microsoft, gratis)
    → Swedish WAV-fil
        ↓
LongCat-Video-Avatar-1.5 (Meituan, MIT)
    → Talking head video (MP4)
        ↓
Gradio UI → Preview + nedladdning
```

**Pipeline:**
- **TTS:** Microsoft Edge TTS (`sv-SE-SofieNeural` / `sv-SE-MattiasNeural`) — gratis, ingen API-nyckel
- **Video:** LongCat Avatar 1.5 med INT8-kvantisering + steg-distillation (8 steg = snabbt)
- **Cache:** Modeller (~25 GB) sparas i din Google Drive — laddas bara ner en gång

---

## Tekniska detaljer

- Model: `LongCat-Video-Avatar-1.5` (Whisper-large-v3 audio encoder)
- Inference: `--use_int8 --use_distill` (8 steg, ~5-10 min per video på A100)
- Upplösning: 480p (standard) eller 720p
- Format: MP4, 25fps

---

## Licens

Notebook: MIT  
Modell-vikter: MIT (Meituan)  
Edge-TTS: Microsoft (gratis för personligt bruk)
