# Seedance 2.0 — Complete Model Reference

## Overview
**Model ID:** `bytedance/seedance-2.0`
**Owner:** ByteDance (TikTok's parent)
**Release:** April 2026
**Type:** Multimodal AI Video Generation (Text + Image + Video + Audio)

---

## Capabilities

### ✅ Core Features
- **Text-to-Video:** Natural language prompts
- **Image-to-Video:** Animate still images, control start/end frames
- **Video-to-Video:** Style transfer, editing, extension
- **Multimodal:** 9 images + 3 videos + 3 audio in single generation
- **Native Audio:** Video + audio generated together, synchronized
- **Character Consistency:** Maintain character across shots with references

### 🎬 What You Can Create
- Cinematic trailers and short films
- Product showcases and advertisements
- Social media content (Reels, TikTok, Shorts)
- Animated avatars and explainers
- Visual effects and transitions
- Music videos
- Tutorial/instructional content

---

## Output Specifications

| Parameter | Options | Default |
|-----------|---------|---------|
| **prompt** | string (required) | — |
| **duration** | 4-15 seconds, or -1 (auto) | 5 |
| **resolution** | 480p, 720p | 720p |
| **aspect_ratio** | 16:9, 4:3, 1:1, 3:4, 9:16, 21:9, adaptive | 16:9 |
| **audio** | boolean (true/false) | true |
| **image** | URL (for image-to-video) | null |
| **video** | URL (for video-to-video) | null |
| **prompt_strength** | 0-1 (creativity vs adherence) | 0.8 |

---

## Resolution Guide

| Resolution | Quality | Speed | Best For |
|------------|---------|-------|----------|
| **480p** | Good | Fastest | Previews, social (low bandwidth) |
| **720p** | Better | Medium | Most use cases, balanced |
| **2K** | Best | Slowest | Professional, high-quality |

### Aspect Ratio by Platform

| Ratio | Dimensions | Best For |
|-------|------------|----------|
| **16:9** | 1280×720 | YouTube, general |
| **9:16** | 720×1280 | Reels, TikTok, Shorts |
| **1:1** | 960×960 | Instagram feed |
| **4:3** | 1112×834 | Classic TV feel |
| **21:9** | 1470×630 | Cinematic letterbox |
| **3:4** | 834×1112 | Portrait editorial |

---

## The 6-Step Director Formula

**Format:** `[Subject], [Action], in [Environment], camera [Camera], style [Style], avoid [Constraints]`

| Step | Element | Requirement | Example |
|------|---------|-------------|---------|
| 1 | **Subject** | Specific visual features | "A young woman in a red dress" |
| 2 | **Action** | Specific verbs, quantified | "slowly turns around, hair blowing" |
| 3 | **Environment** | Location + lighting + atmosphere | "rooftop at sunset, city skyline" |
| 4 | **Camera** | ONE primary movement | "slow push-in" |
| 5 | **Style** | Visual references + mood | "cinematic, film grain, warm tones" |
| 6 | **Constraints** | What to avoid | "avoid jitter, bent limbs" |

### Example Breakdown

```
A cyberpunk assassin (Subject)
crouches on a rain-soaked rooftop, scanning the city (Action)
neon signs reflecting in puddles, fog rolling in (Environment)
camera slow orbit around her, starting wide to close-up (Camera)
cyberpunk aesthetic, purple-red neon palette, cinematic (Style)
avoid jitter, avoid bent limbs, avoid temporal flicker (Constraints)
```

---

## Camera Movement Guide

### 8 Core Movements

| Type | Keywords | Effect | Best For |
|------|----------|--------|----------|
| **Push-in** | push-in, dolly in, slow approach | Camera moves toward subject | Emotional focus, tension |
| **Pull-out** | pull back, dolly out, reveal | Camera moves away | Environmental context |
| **Pan** | lateral pan, horizontal sweep | Camera moves left/right | Scanning, tracking |
| **Tracking** | follow, tracking shot | Camera follows movement | Action, walking, driving |
| **Orbit** | orbit, arc, circle around | Camera rotates around subject | Product showcase, reveal |
| **Aerial** | drone shot, bird's eye, aerial | High angle overview | Landscapes, cities, scale |
| **Handheld** | handheld, shaky cam | Slight natural shake | Documentary, realism |
| **Fixed** | locked off, fixed frame | Camera completely still | Focus on subject action |

### Speed Keywords

| Speed | Keywords | When to Use |
|-------|----------|-------------|
| **Extremely Slow** | imperceptible, barely | Subtle breathing, tiny movements |
| **Slow** | slow, gentle, gradual | Cinematic, smooth motion |
| **Medium** | smooth, controlled | Natural, balanced |
| **Fast** | dynamic, swift | ⚠️ HIGH RISK - only ONE element |

### ⚠️ Critical Rules

**Rule 1: ONE primary camera instruction**
```
❌ Wrong: "camera push-in, then pan left, zoom out, orbit"
✅ Correct: "camera slow push-in"
```

**Rule 2: Separate camera from subject movement**
```
❌ Wrong: "spinning camera around a dancing person"
✅ Correct: "The dancer spins slowly. Camera holds fixed."
```

**Rule 3: "Fast" is dangerous**
- Fast camera + fast subject + complex scene = jitter/artefacts
- Choose only ONE element to be fast
- Better: slow camera, dynamic subject movement

---

## Lighting Keywords (Highest Impact!)

Lighting is the **#1 quality multiplier** for video. Always include at least one.

| Type | Keywords | Effect | Example |
|------|----------|--------|---------|
| **Golden Hour** | golden hour, sunset, warm | Warm, soft, nostalgic | "soft golden hour lighting" |
| **Neon** | neon-lit, neon glow | Cyberpunk, urban, night | "neon-lit rainy street" |
| **Rim Light** | rim light, edge light | Dramatic separation | "dramatic rim light against dark" |
| **Backlit** | backlit, silhouette | Dramatic, moody | "backlit silhouette at sunset" |
| **Overcast** | overcast, diffused | Soft, even, natural | "even overcast diffused light" |
| **Natural** | natural light, window | Organic, real | "soft natural window light" |
| **Dramatic** | dramatic, chiaroscuro | High contrast | "dramatic Rembrandt lighting" |
| **Cinematic** | cinematic, 35mm | Film look | "cinematic film tone" |

### Lighting + Mood Combos
```
- Rainy + Neon = Cyberpunk, urban night
- Sunset + Golden = Warm, nostalgic, romantic
- Overcast + Natural = Realistic, documentary
- Backlit + Silhouette = Dramatic, mysterious
- Studio + Soft = Clean, professional
```

---

## Style Keywords

### Quality Boosters
| Keyword | Effect |
|---------|--------|
| 4K, ultra HD | Sharper, more detail |
| film grain | Cinematic texture |
| 35mm lens | Cinematic look |
| shallow depth of field | Professional, focused |
| cinematic | General film quality |
| high detail | More textures |

### Color/Tone
| Keyword | Effect |
|---------|--------|
| warm tones, cool palette | Color bias |
| desaturated | Muted, gritty |
| vibrant, saturated | Bold colors |
| teal-orange | Popular grading |
| noir | Black and white, dramatic |

### Mood
| Keyword | Effect |
|---------|--------|
| moody | Dark, atmospheric |
| dreamy | Soft, ethereal |
| ethereal | Light, floaty |
| gritty | Rough, raw |
| elegant | Refined, sophisticated |

---

## Negative Prompts (Essential!)

Always include these at the end of your prompt:

### Core Set (Use Always)
```
avoid jitter, avoid bent limbs
```

### For Characters
```
avoid temporal flicker, avoid identity drift
```

### For Complex Scenes
```
avoid chaotic composition, avoid jitter
```

### For Long Duration (10+ seconds)
```
avoid temporal flicker, avoid identity drift, avoid bent limbs
```

---

## Multimodal References

### Reference Limits
- **Images:** Up to 9 files (reference character, style, product)
- **Videos:** Up to 3 clips (motion reference, choreography)
- **Audio:** Up to 3 files (background music, sound effects)
- **Total:** Max 12 files combined

### Reference Syntax in Prompt
```
"The character from [Image1] performs the dance from [Video1]
while [Audio1] plays in background"
```

### Use Cases

**Character Consistency:**
```
Use [Image1] as the character's face and clothing reference.
Prompt: "A woman with the face and outfit from [Image1] 
walking through a forest..."
```

**Motion Reference:**
```
Use [Video1] for dance choreography reference.
Prompt: "The person performs hip-hop dance moves matching
the style and rhythm of [Video1]..."
```

**Audio Sync:**
```
Use [Audio1] for music to sync visuals.
Prompt: "A dancer moving to the beat of [Audio1]..."
```

### Image-to-Video Specifics

**First Frame Mode:**
```
Animate this image, [subject] begins the action.
Camera: [movement].
Lighting: [preserve/change].
Duration: 5 seconds.
```

**Start + End Frame Mode:**
```
[Image1] is the first frame, [Image2] is the last frame.
The transition should show [action].
Camera: [movement].
```

### Video-to-Video (Editing)

**Style Transfer:**
```
Transform [Video1] to [style]:
- Color palette: [description]
- Mood: [description]
- Keep original motion and timing
- Avoid identity drift
```

**Extension:**
```
Continue from where [Video1] ends.
The character [description of next action].
Maintain [consistent elements].
Duration: 5 more seconds.
```

---

## Duration Guidelines

| Duration | Use Case | Complexity |
|----------|----------|------------|
| **4-5 seconds** | Testing, social hooks | Simple |
| **6-8 seconds** | Standard content, transitions | Moderate |
| **10-12 seconds** | Storytelling, impact moments | Complex |
| **13-15 seconds** | Full scenes, mini-narratives | Very complex |

### "Auto" Duration (-1)
Let the model decide optimal length based on prompt complexity. Good for:
- When unsure how long action should be
- Complex scenes with multiple beats
- Testing workflows

---

## Prompt Length Guidelines

### ✅ Optimal: 60-100 words

**Too Short (<30 words):**
- Missing key details
- Model improvises too much
- Inconsistent results

**Too Long (>150 words):**
- Conflicting instructions
- Model gets confused
- Quality degrades

### Quality Words vs Filler Words
```
❌ Filler: "amazing, beautiful, epic, cool, awesome"
✅ Quality: "specific lighting, exact colors, precise action"
```

---

## Three Core Prompt Structures

### 1. Five-Segment (Beginners)
**Best for:** Single shots, simple compositions

```
Subject + Scene/Atmosphere + Action/Performance + Camera + Style
```

### 2. CRAFT Framework (Multimodal)
**Best for:** Multiple references, complex projects

```
Context + Reference (@assets) + Action + Framing/Timing + Tone/Audio
```

### 3. Timeline Storyboard (Multi-Shot)
**Best for:** Narratives, longer content

```
0-4s: [Wide shot description]
4-9s: [Medium shot description]
9-13s: [Close-up description]
13-15s: [Final shot description]
```

---

## Iteration Methodology

### One Variable at a Time

```
1. Generate baseline (2-3 options)
2. Change ONE element (camera OR style OR action)
3. Compare results
4. Keep best, refine further
```

### Pre-Generation Checklist
- [ ] Read prompt aloud (does it flow like director instructions?)
- [ ] Remove redundant adjectives
- [ ] Confirm ONE primary camera movement
- [ ] Check constraints are achievable
- [ ] Verify no conflicting style/motion instructions

---

## Troubleshooting

| Issue | Cause | Solution |
|-------|-------|----------|
| **Jittery/flickery** | Multiple camera moves, "fast" keyword | Use ONE camera, add "slow", include "avoid jitter" |
| **Bent/distorted limbs** | Complex motion | Add "avoid bent limbs", use simpler action |
| **Identity drift** | Long generation, character movement | Use reference image, add "avoid identity drift" |
| **Wrong lighting** | Too vague | Be specific: "golden hour" not just "nice light" |
| **Motion blur** | Camera too fast | Use "slow", "smooth", "controlled" |
| **Audio out of sync** | Complex dialogue | Simplify prompt, shorter dialogue |
| **Composition messy** | Too many elements | Simplify scene, focus on ONE subject |

---

## Prompt Templates by Use Case

### Cinematic Trailer
```
[Subject] in [dramatic environment].
[Action with tension-building movement].
camera [dynamic movement].
[Style: film grain, dramatic lighting].
[Sound/ambient: tense music, wind, rain].
avoid jitter, avoid bent limbs.
```

### Product Showcase
```
Close-up of [product].
[Rotation/reveal movement].
camera [smooth movement].
[Style: clean, luxury, high-end].
Background: [abstract/blur].
```

### Social Media Hook
```
Hook: [attention-grabbing open - 0-2s]
[Subject] doing [relatable/interesting action].
camera [dynamic movement].
[Lighting: vibrant, eye-catching].
Format: 9:16 vertical.
```

### Tutorial/Explainer
```
[Subject] in [simple environment].
[Action demonstrating process].
camera [clear, educational movement].
[Style: clean, well-lit, professional].
[Person should look at camera occasionally].
```

### Dance/Choreography
```
[Character with specific outfit].
[Movement following reference: @Video1].
[Emotion/mood: energetic/smooth/etc].
camera [tracking/follow movement].
Music: @Audio1.
avoid identity drift.
```

### Fantasy/Sci-Fi
```
[Supernatural/CI subject].
[Otherworldly action with physics].
[Epic environment].
camera [dramatic movement].
[Special lighting: ethereal/dramatic].
Style: [movie reference if applicable].
```

---

## Cost Estimation

Seedance 2.0 is more expensive than image generation:
- 480p, 5s: ~$0.05-0.10
- 720p, 5s: ~$0.10-0.20
- 720p, 15s: ~$0.30-0.50
- Higher resolution/longer = more expensive

**Tips:**
1. Start with 480p, 5s for testing
2. Scale up once prompt is refined
3. Use "auto" duration initially to find optimal length
4. Batch similar generations to compare

---

## Best Practices Summary

1. **Be specific** - "A woman" vs "A 28-year-old woman in a red dress"
2. **One camera** - Choose the most important movement
3. **Lighting first** - It's the biggest quality multiplier
4. **Include constraints** - Always "avoid jitter, avoid bent limbs"
5. **Test with 5s** - Before scaling to 10-15s
6. **Use references** - For character consistency
7. **Separate camera/subject** - Don't mix movements
8. **60-100 words** - Optimal prompt length
9. **Read aloud** - Should sound like director instructions
10. **Iterate one thing** - Change only one variable at a time