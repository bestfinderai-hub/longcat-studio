# Talking Avatar Studio SE

Ladda upp ett foto + skriv text på svenska → få en talande video.

---

## 🎬 SadTalker Studio SE ⭐ REKOMMENDERAS

Funkar på **gratis Colab T4** (15 GB) — ingen betalplan behövs.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bestfinderai-hub/longcat-studio/blob/main/SadTalker_Studio_SE.ipynb)

| GPU | VRAM | Status |
|-----|------|--------|
| **T4 (15 GB)** | 15 GB | ✅ Gratis Colab |
| **V100 (16 GB)** | 16 GB | ✅ Fungerar |
| **A100 (40 GB)** | 40 GB | ✅ Fungerar |

**Snabbstart:**
1. Klicka "Open In Colab"
2. Aktivera GPU: Runtime → Change runtime type → **T4 GPU** *(gratis)*
3. Kör cellerna **1–6** (tar ~10 min första gången)
4. Kör cell **7** → kopiera `gradio.live`-länken → klistra in i dashboarden

**Pipeline:**
```
Foto + text
    ↓
Edge TTS (Microsoft, gratis) → WAV 16kHz
    ↓
SadTalker (MIT-licens) → Talande video MP4
    ↓
Gradio UI → Förhandsvisning + nedladdning
```

**TTS-röster:** Sofie (rikssvenska) · Mattias (rikssvenska) · Noora (finlandssvenska)  
**Tid per video:** ~1–2 min (256 px) eller ~3–4 min (512 px)  
**Modeller:** ~1.3 GB, cachas i Google Drive (laddas ner en gång)

---

## 🗄️ LongCat Studio SE (arkiverad)

Kräver **A100 (40 GB)** — Colab Pro ~10 USD/mån.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/bestfinderai-hub/longcat-studio/blob/main/LongCat_Studio_SE.ipynb)

Baserat på LongCat-Video-Avatar 1.5 (Meituan, MIT). Ger något högre kvalitet men kräver mycket mer VRAM.

---

## GDPR / Dataskydd

- Bilder och ljud bearbetas i din Colab-VM och rensas vid sessionsslut
- Modeller lagras i ditt Google Drive (ditt eget konto)
- **OBS:** TTS-text skickas till Microsoft Edge TTS API — inkludera inte känsliga personuppgifter

## Licens

Notebooks: MIT  
SadTalker: MIT (OpenTalker)  
LongCat-modell: MIT (Meituan)  
Edge-TTS: Microsoft (gratis för personligt bruk)
