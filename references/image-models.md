# Nano Banana 2 — Complete Model Reference

## Overview
**Model ID:** `google/nano-banana-2`
**Also Known As:** Gemini 3.1 Flash Image
**Owner:** Google
**Release Date:** February 26, 2026
**Context Window:** Multimodal (text + up to 14 images)

---

## Capabilities

### ✅ Strengths
- **Speed:** Fastest high-quality image gen (3-5 seconds)
- **Text Rendering:** Excellent multilingual text in images
- **Visual Grounding:** Uses Google Search to represent real places/species accurately
- **Multi-image Fusion:** Combines up to 14 reference images
- **Instruction Following:** Strong complex prompt adherence
- **Cost:** ~95% of Pro quality at fraction of cost

### ⚠️ Limitations
- Cannot search for specific people
- 4K generation costs more
- Best results require prompt enhancement

---

## Output Specifications

| Parameter | Options | Default |
|-----------|---------|---------|
| **aspect_ratio** | 1:1, 2:3, 3:2, 3:4, 4:3, 4:5, 5:4, 9:16, 16:9, 21:9, 1:4, 4:1, 1:8, 8:1 | 1:1 |
| **match_input_image** | auto-match input aspect ratio | off |
| **output_format** | jpg, png | jpg |
| **output_quality** | 1-100 | 90 |
| **resolution** | 512px, 1K, 2K, 4K | 1K |
| **prompt** | string (required) | — |

---

## Resolution Tiers

| Resolution | Speed | Cost | Best For |
|------------|-------|------|----------|
| **512px** | Fastest | Cheapest | Batch variations, previews |
| **1K** | Fast | Low | Social media, web |
| **2K** | Medium | Medium | Print, high-quality web |
| **4K** | Slower | Higher | Professional, large prints |

### Cost Optimization Workflow
```
1. Generate 4-6 variations at 512px (batch, 50% discount)
2. Select best composition
3. Upscale to 2K or 4K
```

---

## Visual Grounding (Google Search Integration)

Nano Banana 2 can search Google for real-world subjects:

### ✅ Works Well
- **Locations:** Specific churches, bridges, city squares, monuments
- **Nature:** Exact animal species, breeds, plants, insects
- **Objects:** Specific products, logos, landmarks

### ❌ Doesn't Work
- **People:** Cannot search for specific individuals

### Example Prompts

**Location Grounding:**
```
"A cinematic photograph of the Trevi Fountain in Rome, Italy.
 Ancient baroque sculpture, crystal clear water, tourists 
 around the edges, golden evening light, 35mm lens, film grain"
```

**Species Grounding:**
```
"A realistic image of a male peacock displaying its full 
 plumage, iridescent blue-green feathers fanned out, 
 in a forest clearing with soft natural light"
```

**Specific Breed:**
```
"A close-up portrait of a Shiba Inu puppy at 8 weeks old,
 fox-like expression, orange-and-cream coat, perked ears,
 soft studio lighting, shallow depth of field"
```

---

## Image-to-Image Editing

Pass up to 14 reference images for:

### Style Transfer
```
"Transform this photo into a Studio Ghibli animation style,
 preserving the subject's pose and expression, soft watercolor
 aesthetic, warm color palette"
```

### Background Replacement
```
"Place this product (watch) on a marble surface with soft
 shadows, remove the original background, add a subtle
 reflection, professional product photography lighting"
```

### Image Composition
```
"Combine Image1 (person) with Image2 (beach background),
 keep person's pose and size, natural integration with 
 lighting matching, cinematic quality"
```

### Outfit/Appearance Change
```
"Change the person's outfit from Image1 to formal business 
 attire (dark navy suit, white shirt, red tie), keep same 
 pose and facial expression, preserve background"
```

---

## Prompt Engineering Tips

### DO ✅
- Be specific about subject details (color, texture, expression)
- Include lighting type and direction
- Add compositional elements (angle, depth of field)
- Mention style references (cinematic, editorial, etc)
- Include technical specs (4K, film grain, etc)

### DON'T ❌
- Use vague adjectives ("nice", "good", "beautiful")
- Overload with conflicting instructions
- Forget to specify aspect ratio for intended use
- Skip lighting details (biggest quality difference)

### High-Impact Additions (in order of importance)
1. **Lighting description** — biggest quality multiplier
2. **Subject details** — more specific = better results
3. **Style reference** — guides aesthetic
4. **Camera/angle** — compositional direction
5. **Atmosphere/mood** — emotional tone

---

## Example Prompts by Category

### Portrait Photography
```
"A 30-year-old woman with natural curly auburn hair, warm 
 smile, direct eye contact with camera. Outdoor golden hour 
 lighting from left side creating soft Rembrandt pattern. 
 Shallow depth of field, bokeh background of autumn park. 
 Editorial quality, slight film grain, 85mm lens, 4K"
```

### Product Photography
```
"Premium wireless headphones on a walnut wood surface, 
 dramatic spotlight from above creating soft shadows, 
 minimalist dark background, luxury tech aesthetic, 
 reflections on glossy surfaces, 8K quality, commercial photography"
```

### Landscape
```
"Majestic mountain valley at sunrise, layered mist in the 
 valley floor, golden light hitting peaks, wildflowers in 
 foreground, wide-angle 16mm lens, polarizing filter, 
 vibrant yet natural colors, cinematic panoramic 2:1 ratio"
```

### Food Photography
```
"Fresh sushi platter from above, salmon sashimi, tuna nigiri,
 wasabi on the side, dark slate board, garnish with micro 
 greens, dramatic side lighting, condensation on glasses 
 in background, editorial food photography, shallow DOF"
```

### Architecture
```
"Modern concrete brutalist library interior, geometric 
 staircases, dramatic shafts of natural light through 
 clerestory windows, people silhouettes for scale, 
 black and white conversion with high contrast, 24mm lens"
```

### Fantasy/CGI
```
"A phoenix rising from flames, iridescent orange-gold 
 feathers, embers floating upward, dramatic rim lighting 
 against dark background, smoke and fire particles, 
 cinematic composition, 4K render quality"
```

### Text in Image
```
"A vintage handwritten sign on a wooden barn that reads 
 'FRESH PRODUCE - OPEN DAILY', warm morning light, rustic 
Farmhouse aesthetic, weathered paint texture, flower boxes 
 below window, cinematic lighting, 4K photorealistic"
```

---

## Aspect Ratio Guide

| Ratio | Dimensions | Best For |
|-------|------------|----------|
| **1:1** | Square | Instagram post, profile, profile |
| **2:3** | Portrait 2:3 | Portrait photos, posters |
| **3:2** | Standard photo | General photography |
| **3:4** | Portrait 3:4 | Magazines, portraits |
| **4:3** | Classic TV | General content |
| **4:5** | Instagram portrait | Social posts |
| **5:4** | Large format | Print, posters |
| **16:9** | Widescreen | YouTube, banners |
| **9:16** | Vertical | Stories, Reels, TikTok |
| **21:9** | Cinematic | Letterbox, ultrawide |
| **1:4** | Tall banner | Web banners |
| **4:1** | Wide banner | Continuous strips |
| **1:8** | Extreme tall | Web banners, comics |
| **8:1** | Panoramic | Landscapes, timelines |

---

## Output Format Options

### JPG
- Smaller file size
- Universal compatibility
- Good for web/social
- Lossy compression

### PNG
- Larger file size
- Transparency support
- Lossless quality
- Best for editing/overlay

---

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Blurry results | Add "sharp focus", "high detail", increase resolution |
| Wrong colors | Specify color palette, add lighting temp (warm/cool) |
| Text unreadable | Add "clear text", "legible text", "crisp letters" |
| Bad composition | Include camera angle, rule of thirds, framing |
| Inconsistent style | Be more specific about style reference |
| Too dark/bright | Specify lighting intensity, exposure |

---

## Cost Estimation

Based on Replicate pricing (check current rates):
- 512px: ~$0.005
- 1K: ~$0.01
- 2K: ~$0.015
- 4K: ~$0.02

**Batch workflow (50% discount on bulk):**
1. Generate 6 variations at 512px = ~$0.015 each
2. Pick best
3. Upscale to 2K/4K = ~$0.015-0.02

Total: ~$0.03-0.04 for optimal result vs $0.02 for single 4K