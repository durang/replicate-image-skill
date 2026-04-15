# Kling 3.0 Motion Control — Complete Reference

## Overview
**Model ID:** `kwaivgi/kling-v3-motion-control`
**Owner:** Kuaishou (via Replicate)
**Release:** March 2026
**Type:** Motion transfer video generation
**Key Feature:** Transfer motion from reference video to any character image

---

## What It Does

**Transfer motion from a reference video to any character image.**

```
📥 YOU PROVIDE:
   1. Reference IMAGE → Character appearance (anime, game, your photo)
   2. Reference VIDEO → Motion you want transferred (dance, gesture, etc)
   3. Optional PROMPT → Context/environment

📤 RESULT:
   → The CHARACTER from your image
   → Performing the MOTION from your video
```

---

## Capabilities

### ✅ Strengths
- **Motion transfer** - Takes any motion and applies it to any character
- **Character consistency** - Your image's look preserved throughout
- **High resolution** - Up to 1080p in pro mode
- **Real faces allowed** - Unlike Seedance, supports real person photos
- **Longer duration** - Up to 30 seconds (vs Seedance's 15s)
- **Character orientation modes** - Image-facing or video-facing

### ⚠️ Limitations
- **No audio** - Output is silent (mute)
- **Single character** - Optimized for one character at a time
- **Data privacy** - Data sent to Kuaishou (not just Replicate)
- **Proportions matter** - Full body to full body works best

---

## Input Specifications

### Reference Image
| Aspect | Detail |
|--------|--------|
| **Format** | JPG, PNG, WebP |
| **Content** | Single character (person, mascot, avatar) |
| **Visibility** | Full body and head clearly visible, no obstructions |
| **Pose** | Standing pose works best for full-body motion |
| **Proportions** | Should match reference video proportions |

### Reference Video
| Aspect | Detail |
|--------|--------|
| **Format** | MP4, MOV |
| **Duration** | Same as desired output (5-30s) |
| **Content** | Motion you want transferred |
| **Quality** | Clear, steady movement works best |
| **Motion type** | Moderate, controlled motion preferred |

### Text Prompt (Optional but Recommended)
- Guide background, environment, style
- Reinforce the motion context
- Add atmospheric details

---

## Output Specifications

| Parameter | Options | Default |
|-----------|---------|---------|
| **duration** | 5-30 seconds | 5 |
| **orientation** | image, video | image |
| **mode** | std (720p), pro (1080p) | std |

### Orientation Modes

| Mode | Meaning | Max Duration | Use When |
|------|---------|--------------|----------|
| **image** | Character faces same direction as in image | 10 seconds | Want character to face forward |
| **video** | Character matches orientation in video | 30 seconds | Complex orientations, dancing |

### Quality Modes

| Mode | Resolution | Cost | Best For |
|------|------------|------|----------|
| **std** | 720p | Lower | Testing, social media previews |
| **pro** | 1080p | Higher | Final output, high-quality content |

---

## 🚀 STEP-BY-STEP WORKFLOW (Motion Control)

### Conversation Flow

```
YOU: "I want motion control" (or send images directly)

───────────────────────────────────────────────────────────

JARVIS: "Perfecto! Para el Motion Control necesito:

1️⃣ ¿Qué foto es el PERSONAJE?
   └─ (Anime, game, your photo, etc)
   
2️⃣ ¿Qué VIDEO tiene el MOTION?
   └─ (Send me the video with the motion you want)
   
3️⃣ ¿Qué motion quieres?
   └─ (The dance, gesture, action from that video)

4️⃣ ¿Duración preferida?
   └─ (5s test / 10s / 15s / 30s)

5️⃣ ¿Resolution?
   └─ std (720p) para testing
   └─ pro (1080p) para calidad final"

───────────────────────────────────────────────────────────

YOU: [Provide images + answers]

───────────────────────────────────────────────────────────

JARVIS: "Análisis completado!

🎬 RECOMENDACIÓN: Kling 3.0 Motion Control
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📹 VIDEO DE REFERENCIA:
   └─ [Description]
   └─ Duration: X seconds
   └─ Motion: [What happens]

🖼️ IMAGEN DE PERSONAJE:
   └─ [Description]
   └─ Source: [Anime/Game/Your photo]

⚙️ CONFIGURACIÓN:
   └─ Duration: X seconds
   └─ Resolution: 1080p (pro mode)
   └─ Orientation: image (keeps character facing forward)

📝 PROMPT: [Generated contextual prompt]

🎯 LO QUE HARÁ:
   └─ Transfer motion from: [video description]
   └─ To character from: [image description]
   └─ Output: X-second video

⚠️ NOTA: Video sin audio (mute)

💰 COSTO APROX: ~$0.15-0.30

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
→ Say 'yes' to generate
→ Say 'change X' to modify
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━"

───────────────────────────────────────────────────────────

YOU: "yes"

───────────────────────────────────────────────────────────

JARVIS: [Generates and delivers]
```

---

## Prompt Templates for Motion Control

### Dance Transfer
```
"A [style] dancer performing [specific move/genre] dance,
 in [venue/setting], [lighting description]"
```

**Examples:**
```
"A person doing an energetic hip-hop dance in a neon-lit
 nightclub, dynamic lighting, colorful spotlights"

"A graceful ballet dancer performing a pirouette in an
 elegant theater with warm stage lighting"

"A person doing traditional Latin dance moves in a
 festive outdoor carnival setting with string lights"
```

### Gesture Transfer
```
"[Character description] performing [specific gesture/action],
 in [context/setting]"
```

**Examples:**
```
"A business person doing a confident presentation gesture
 at a professional conference stage"

"A chef performing a plating gesture in a high-end
 restaurant kitchen with warm ambient lighting"

"A fitness instructor demonstrating an exercise move
 in a modern gym with bright natural light"
```

### Sports Motion Transfer
```
"[Character avatar] performing [sport action] with
 [skill level] proficiency, in [venue/setting]"
```

**Examples:**
```
"An animated character performing a golf swing on a
 scenic course at golden hour"

"A mascot character doing an energetic high jump in
 an athletic stadium setting"
```

### Social Media Trend Transfer
```
"[Character from image] doing the viral [trend name]
 trend, [setting with props/atmosphere]"
```

**Examples:**
```
"My photo doing the latest viral TikTok dance trend
 in my living room with disco lights"

"A portrait of me as a superhero doing the trending
 superhero landing pose"
```

---

## Best Practices

### DO ✅
1. **Match proportions** - Full-body image + full-body video
2. **Clear visibility** - Entire body and head visible
3. **Steady motion** - Clear, moderate movement in reference
4. **Write contextual prompts** - Help the model understand the scene
5. **Start with 5s** - Test before longer durations
6. **Use pro mode** - For final output quality

### DON'T ❌
1. **Don't mix proportions** - Half-body image + full-body video
2. **Avoid chaotic motion** - Very fast or erratic movement
3. **Don't use obstructed images** - Hidden faces/bodies fail
4. **Don't expect audio** - Always mute output
5. **Avoid long durations first** - Test with 5s

---

## Troubleshooting

| Issue | Cause | Solution |
|-------|-------|---------|
| Motion looks distorted | Reference video too fast/complex | Use slower, clearer video |
| Character looks wrong | Proportion mismatch | Match image/video proportions |
| Character face changed | Multiple characters in video | Use single-character video |
| Blurry output | Resolution too low | Use pro mode (1080p) |
| Motion not transferred | Video unclear | Use clearer reference video |
| Identity lost | Poor quality image | Use high-quality character photo |

---

## Comparison with Seedance 2.0

| Feature | Kling 3.0 Motion Control | Seedance 2.0 |
|---------|------------------------|--------------|
| **Input** | Image + Video | Text, Image, Video, Audio |
| **Motion** | From reference video | Described in prompt |
| **Audio** | ❌ None | ✅ Synchronized |
| **Duration** | 5-30 seconds | 4-15 seconds |
| **Resolution** | 720p / 1080p | 480p / 720p |
| **Real faces** | ✅ Allowed | ❌ Blocked |
| **Character consistency** | From image | From image references |
| **Cost** | Medium | Medium |

### When to Use Each

| Use Case | Model |
|----------|-------|
| "Make me dance like this video" | Kling 3.0 |
| "Generate a cinematic scene" | Seedance 2.0 |
| "Put my face on a dancer" | Kling 3.0 |
| "Create video from text description" | Seedance 2.0 |
| "Animate my mascot logo" | Kling 3.0 |
| "Generate video with dialogue" | Seedance 2.0 |
| "Sync my face to audio" | Seedance 2.0 |
| "Trending dance challenge" | Kling 3.0 |

---

## Cost Estimation

| Mode | Duration | Approximate Cost |
|------|----------|------------------|
| std (720p) | 5s | ~$0.05-0.10 |
| std (720p) | 10s | ~$0.10-0.15 |
| pro (1080p) | 5s | ~$0.10-0.20 |
| pro (1080p) | 15s | ~$0.25-0.40 |
| pro (1080p) | 30s | ~$0.50-0.80 |

*Check current Replicate pricing as it varies*

---

## Privacy Note

⚠️ **Data sharing:** Videos and images are sent from Replicate to **Kuaishou** (Kling's parent company) for processing.

**Privacy Policy:** https://app.klingai.com/global/dev/privacy-policy
**Terms of Service:** https://app.klingai.com/global/dev/service-agreement

---

## Resources

- **Playground:** https://replicate.com/kwaivgi/kling-v3-motion-control
- **Examples:** https://replicate.com/kwaivgi/kling-v3-motion-control/examples
- **API:** https://replicate.com/kwaivgi/kling-v3-motion-control/api

---

## Quick Reference

```
┌─────────────────────────────────────────────────────────────┐
│ Kling 3.0 Motion Control — At a Glance                     │
├─────────────────────────────────────────────────────────────┤
│ What it does: Transfer motion from video to character image │
│ Input: 1 reference image + 1 reference video               │
│ Output: Video of your character doing the motion           │
│ Max duration: 30 seconds                                   │
│ Max resolution: 1080p                                      │
│ Audio: None (mute)                                         │
│ Real faces: ✅ Allowed                                     │
│                                                              │
│ USE WHEN:                                                   │
│ • "Make me dance like this video"                          │
│ • "Put my face on a dancer"                                │
│ • "Animate this mascot with motion reference"              │
│ • Social media dance challenges                             │
└─────────────────────────────────────────────────────────────┘
```