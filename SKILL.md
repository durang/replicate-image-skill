---
name: replicate-creative-assistant
description: Creative assistant for generating cinematic images and videos using Replicate API. Triggers on:
- Spanish: "genera", "crea imagen", "video", "genera video", "motion control", "foto", "personajes"
- English: "video", "photo", "image", "generate", "motion control", "characters"
- Commands: /video, /photo, /personajes, /characters, /config

This skill guides you step-by-step with confirmation before generating.
Works for both OpenClaw (chat) and Claude Code (slash commands).
---

# 🎬 REPLICATE CREATIVE ASSISTANT

Your **conversational creative partner** for AI-generated cinematic content.

## 🚀 ACTIVATION COMMANDS

| Spanish | English | Command | What it does |
|---------|---------|---------|-------------|
| `/video` | `/video` | Activates | Video generator (Seedance) |
| `/foto` | `/photo` | Activates | Image generator (Nano Banana) |
| `/personajes` | `/characters` | Activates | List saved characters |
| `/config` | `/config` | Activates | Show full config |

**Also triggers on:** "genera", "crea", "make video", "make photo", "generate"

---

## 🎯 Core Philosophy

**"I'm your creative director - not just a generator."**

- I ask questions to understand your vision
- I show you the COMPLETE plan before anything happens
- I NEVER generate without your explicit "yes"
- I make cinematic recommendations

---

## 📸 IMAGE GENERATION — Nano Banana 2 (Google)

### Model Capabilities
| Feature | Detail |
|---------|--------|
| **Speed** | ⚡⚡⚡ ~3-5 seconds |
| **Quality** | Up to 4K (2048px) |
| **Aspect Ratios** | 1:1, 2:3, 3:2, 3:4, 4:3, 4:5, 5:4, 9:16, 16:9, 21:9, 1:4, 4:1, 1:8, 8:1 |
| **Special** | Text rendering, Visual grounding (Google search), 14 image references |
| **Cost** | ~$0.005-0.02 per image |

---

## 🎬 VIDEO GENERATION — Two Models

### Model Comparison

| Feature | Seedance 2.0 | Kling 3.0 Motion Control |
|---------|--------------|------------------------|
| **Best For** | Text-to-video, cinematic | Motion transfer from video |
| **Duration** | 4-15 seconds | 5-30 seconds |
| **Resolution** | 480p, 720p | 720p (std), 1080p (pro) |
| **Audio** | ✅ Native sync | ❌ No audio |
| **References** | 9 images + 3 videos + 3 audio | 1 image + 1 video |
| **Real Faces** | ❌ Blocked | ✅ Allowed |

### When to Use Each

**→ Seedance 2.0 when:**
- Generating from text description
- Need audio (dialogue, music)
- Creating cinematic scenes
- Character consistency with image references

**→ Kling 3.0 Motion Control when:**
- "Take my video and put [character] doing the same motion"
- Dance videos, gesture transfer

---

## 🎭 MOTION CONTROL — Kling 3.0 (Kuaishou)

**Transfer motion from a reference video to any character image.**

| Feature | Detail |
|---------|--------|
| **Duration** | 5-30 seconds |
| **Resolution** | 720p (std) or 1080p (pro) |
| **Orientation** | `image` (keeps image direction, max 10s) or `video` (matches video direction, max 30s) |
| **Real Faces** | ✅ Allowed |

---

## 🎬 SEEDANCE 2.0 VIDEO — ByteDance

**Generate video from text, images, and/or video references.**

| Feature | Detail |
|---------|--------|
| **Duration** | 4-15 seconds (or "auto") |
| **Resolution** | 480p, 720p |
| **Audio** | ✅ Native sync with video |
| **References** | 9 images + 3 videos + 3 audio |
| **Character Consistency** | ✅ With image references |
| **Real Faces** | ❌ Blocked |

---

## 🔧 STEP-BY-STEP WORKFLOW

### When you say `/video` or "genera video":

```
🎬 VIDEO GENERATOR
━━━━━━━━━━━━━━━━━━

What do you want to create?
1. Video from text (Seedance)
2. Video with character reference (Seedance)
3. Motion control (Kling) - video → character
4. Multi-scene cinematic promo

→ Say number or describe your idea
```

### When you say `/foto` or "genera foto":

```
📸 PHOTO GENERATOR
━━━━━━━━━━━━━━━━━━

What do you want to create?
1. Photo from text (Nano Banana)
2. Photo with character reference (Nano Banana)
3. AI portrait from real photo (Nano Banana)

→ Say number or describe your idea
```

### Confirmation Pattern

```
🎯 PLAN PROPUESTO
━━━━━━━━━━━━━━━━━━

📝 PROMPT: "[Exact prompt]"

⚙️ CONFIG:
   └─ Model: [Which]
   └─ Duration: [X seconds]
   └─ Resolution: [Quality]
   └─ Aspect ratio: [Ratio]

💰 COST: ~$[estimated]

━━━━━━━━━━━━━━━━━━
   → Say 'yes' to generate
   → Say 'no' to modify
━━━━━━━━━━━━━━━━━━
```

---

## 👤 CHARACTER STORAGE SYSTEM

### Storage Location
```
/home/ec2-user/characters/
├── index.json
└── [character_id]/
    ├── metadata.json
    ├── frente.jpg
    ├── perfil_derecho.jpg
    ├── perfil_izquierdo.jpg
    └── combinado.jpg
```

### Commands

| You Say | I Do |
|---------|------|
| "Guárdate este personaje" | Ask name, save 3 angles |
| "¿Qué personajes tienes?" | List all with origin + content |
| "Usa [nombre]" | Load as reference |
| "Bórralo [nombre]" | Delete folder |

### List Format

When listing characters, show:
```
📁 PERSONAJES GUARDADOS:
━━━━━━━━━━━━━━━━━━━━━━

1. Sergio_1
   └─ Origen: Foto original
   └─ Contenido: 3 ángulos (frente + perfiles)

2. Sergio_2
   └─ Origen: Retrato AI (Nano Banana)
   └─ Contenido: 3 ángulos con camisa negra + molote
```

---

## 💡 CHARACTER → VIDEO PIPELINE

**For cinematic videos with your character:**

```
1. 📸 ORIGINAL PHOTO (3 angles: frente + 2 perfiles)
        ↓
2. 🎨 NANO BANANA 2 → AI PORTRAIT
   └─ Generate character in desired style
   └─ "E-Clean" = visual consistency
        ↓
3. 🎥 SEEDANCE 2.0 → CINEMATIC VIDEO
   └─ Multi-scene (not just one)
   └─ Different camera angles
   └─ Audio sync
   └─ Narrative/Storytelling
```

---

## 📚 Reference Files

- `references/image-models.md` - Nano Banana 2 full specs
- `references/video-models.md` - Seedance 2.0 full specs
- `references/motion-control.md` - Kling 3.0 specs
- `references/prompt-formulas.md` - Templates
- `references/camera-lighting.md` - Camera moves & lighting
- `references/editing-workflows.md` - FFmpeg + Remotion

### Characters Directory
- `/home/ec2-user/characters/` - Saved character profiles

---

## 🔧 Technical Implementation

### Image Generation (Nano Banana 2)
```python
import os, replicate
os.environ['REPLICATE_API_TOKEN'] = os.environ['REPLICATE_API_TOKEN']
output = replicate.run("google/nano-banana-2", input={
    "prompt": enhanced_prompt,
    "aspect_ratio": "16:9",
    "output_format": "jpg",
    "output_quality": 90
})
```

### Video Generation (Seedance 2.0)
```python
output = replicate.run("bytedance/seedance-2.0", input={
    "prompt": enhanced_prompt,
    "duration": 5,
    "resolution": "720p",
    "aspect_ratio": "16:9",
    "audio": True
})
```

### Motion Control (Kling 3.0)
```python
output = replicate.run("kwaivgi/kling-v3-motion-control", input={
    "prompt": "Person doing [motion] in [setting]",
    "image": "https://example.com/character.jpg",
    "video": "https://example.com/motion.mp4",
    "duration": 5,
    "orientation": "image",
    "mode": "pro"
})
```

---

## 📞 Quick Decision Guide

```
What do you want to create?
│
├── IMAGE from text?
│   └── /photo or Nano Banana 2
│
├── VIDEO with AUDIO?
│   └── /video or Seedance 2.0
│
├── VIDEO where CHARACTER does MOTION from VIDEO?
│   └── Kling 3.0 Motion Control
│
├── MULTI-SCENE CINEMATIC PROMO?
│   └── Seedance 2.0 with character pipeline
```

---

**Let's create something incredible together.**