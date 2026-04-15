# Video Editing Workflows — Remotion + FFmpeg

## Overview

Two main tools for video editing:

| Tool | Best For | Complexity | Quality |
|------|----------|------------|---------|
| **FFmpeg** | Basic ops: merge, trim, convert, concat | Low | Production |
| **Remotion** | Graphics, subtitles, animations, composition | High | Premium |

---

## FFmpeg — Quick Operations

### Check Available Files
```bash
ls -la /tmp/*.mp4 /tmp/*.mp3 2>/dev/null
```

### Get Video Info
```bash
ffprobe -v error -show_entries format=duration,size -show_entries stream=codec_name,width,height,r_frame_rate /tmp/input.mp4
```

### Trim Video (Cut Section)
```bash
# Extract 5-15 seconds from input
ffmpeg -i input.mp4 -ss 00:00:05 -t 00:00:10 -c copy output.mp4
```

### Merge/Concat Videos
```bash
# Method 1: Concat with file list
# Create list.txt:
# file 'input1.mp4'
# file 'input2.mp4'
# file 'input3.mp4'

ffmpeg -f concat -safe 0 -i list.txt -c copy output.mp4

# Method 2: Direct concat (same codec)
ffmpeg -i "concat:input1.mp4|input2.mp4|input3.mp4" -c copy output.mp4
```

### Convert Format
```bash
# MP4 to WebM
ffmpeg -i input.mp4 -c:v libopus -c:a libvorbis output.webm

# MP4 to GIF
ffmpeg -i input.mp4 -vf "fps=15,scale=480:-1" output.gif
```

### Change Resolution
```bash
# Scale to 720p
ffmpeg -i input.mp4 -vf "scale=-2:720" -c:a copy output.mp4

# Scale to 1080p
ffmpeg -i input.mp4 -vf "scale=-2:1080" -c:a copy output.mp4
```

### Adjust Speed
```bash
# Slow down 50% (2x longer)
ffmpeg -i input.mp4 -vf "setpts=2*PTS" -c:a copy output_slow.mp4

# Speed up 2x (50% shorter)
ffmpeg -i input.mp4 -vf "setpts=0.5*PTS" -c:a copy output_fast.mp4
```

### Add Audio to Video
```bash
# Replace or add audio
ffmpeg -i video.mp4 -i audio.mp3 -c:v copy -c:a aac -shortest output_with_audio.mp4

# Mix audio (video keeps original + overlay new)
ffmpeg -i video.mp4 -i audio.mp3 -filter_complex "[0:a][1:a]amix=inputs=2:duration=shortest" -c:v copy output_mixed.mp4
```

### Extract Frame
```bash
# Extract frame at 2 seconds
ffmpeg -i input.mp4 -ss 00:00:02 -vframes 1 output.jpg
```

### Create Thumbnail
```bash
# Multiple thumbnails
ffmpeg -i input.mp4 -vf "fps=1/10,scale=320:-1" -q:v 2 thumb_%03d.jpg
```

### Add Watermark/Logo
```bash
# Overlay logo in corner
ffmpeg -i input.mp4 -i logo.png -filter_complex "overlay=W-w-10:10" -c:a copy output.mp4
```

### Transitions (Basic)

**Fade In/Out:**
```bash
# Fade in (first 1 second)
ffmpeg -i input.mp4 -vf "fade=t=in:st=0:d=1" -c:a copy output.mp4

# Fade out (last 1 second)
ffmpeg -i input.mp4 -vf "fade=t=out:st=4:d=1" -c:a copy output.mp4

# Both
ffmpeg -i input.mp4 -vf "fade=t=in:st=0:d=1,fade=t=out:st=9:d=1" -c:a copy output.mp4
```

**Crossfade (between two clips):**
```bash
# 1-second crossfade at cut point
ffmpeg -i clip1.mp4 -i clip2.mp4 -filter_complex "[0:v]fade=t=out:st=4:d=1[vf];[1:v]fade=t=in:st=0:d=1[vg];[vf][vg]blend=all_expr='A*(if(lt(t,5),1,t/5))+B*(if(lt(t,5),0,(t-5)/5))'" -c:a copy output.mp4
```

---

## Remotion — Advanced Composition

### When to Use Remotion
- ✅ Subtitles with burnt-in text (custom fonts, animations)
- ✅ Complex animations and graphics
- ✅ Video composition (multiple layers)
- ✅ Product showcases with animated text
- ✅ Title sequences
- ✅ Lower thirds / animated overlays
- ✅ Video + animation combos

### Existing Template
**Location:** `/tmp/quantum-video/`

### Quick Remotion Workflow

```bash
# 1. Navigate to project
cd /tmp/quantum-video

# 2. Preview in browser
npm start

# 3. Render video
npm run build

# 4. Output location
# /tmp/quantum-video/out/video.mp4
```

### Subtitles Workflow with Remotion

If you need subtitles:

1. **Prepare your script:**
```
0:00 - 0:03: "Welcome to this video"
0:03 - 0:06: "Today we're going to learn"
0:06 - 0:10: "How to create amazing content"
```

2. **Create subtitle component** or modify existing `QuantumFreq.tsx`

3. **Render with Remotion** for burnt-in subtitles

### Custom Remotion Project

```bash
# Create new Remotion project
npx create-video@latest my-video-project
cd my-video-project

# Install dependencies
npm install

# Start preview
npm start

# Render
npm run build
```

---

## Decision Tree: Which Tool?

```
Do you need...?
│
├── Just joining clips?
│   └── FFmpeg concat
│
├── Trim/cut sections?
│   └── FFmpeg trim
│
├── Subtitles (burnt-in)?
│   └── Remotion
│
├── Graphics/animation overlays?
│   └── Remotion
│
├── Transitions between clips?
│   ├── Simple: FFmpeg
│   └── Complex: Remotion
│
├── Speed changes?
│   └── FFmpeg
│
├── Format conversion?
│   └── FFmpeg
│
├── Logo/watermark?
│   └── FFmpeg (simple) or Remotion (animated)
│
└── Full video composition with multiple layers?
    └── Remotion
```

---

## Common Workflows

### Workflow 1: Social Media Reel from Clips

```
1. Trim clips to best moments
   └── ffmpeg -i clip1.mp4 -ss 00:00:02 -t 00:00:05 -c copy trimmed1.mp4

2. Add subtitles with Remotion (if needed)
   └── Use existing quantum-video template or create new

3. Merge clips
   └── ffmpeg -i "concat:trimmed1.mp4|trimmed2.mp4|trimmed3.mp4" -c copy final.mp4

4. Add audio
   └── ffmpeg -i final.mp4 -i music.mp3 -c:v copy -c:a aac -shortest output.mp4

5. Convert to 9:16 if needed
   └── ffmpeg -i output.mp4 -vf "scale=-2:1920:force_original_aspect_ratio=decrease,pad=1920:1920:(ow-iw)/2:(oh-ih)/2" output_vertical.mp4
```

### Workflow 2: Video with Animated Title

```
1. Generate title animation in Remotion
   └── Create component with animated text
   
2. Generate main content (Seedance or other)
   └── Use Replicate

3. Combine in Remotion
   └── Sequence title + content

4. Render final
   └── npm run build
```

### Workflow 3: Product Demo with Overlays

```
1. Create product video (Seedance or real footage)
   └── Upload to /tmp/

2. Create overlay graphics in Remotion
   └── Animated logo, price tag, features

3. Composite in Remotion
   └── Video + Overlay layers

4. Export
   └── /tmp/quantum-video/out/video.mp4
```

---

## Quick Reference Commands

```bash
# Join 3 clips
ffmpeg -i "concat:clip1.mp4|clip2.mp4|clip3.mp4" -c copy output.mp4

# Cut 5-15 seconds
ffmpeg -i input.mp4 -ss 00:00:05 -t 00:00:10 -c copy output.mp4

# Add audio
ffmpeg -i video.mp4 -i audio.mp3 -c:v copy -c:a aac -shortest output.mp4

# Fade in/out
ffmpeg -i input.mp4 -vf "fade=t=in:st=0:d=1,fade=t=out:st=9:d=1" -c:a copy output.mp4

# Scale to vertical
ffmpeg -i input.mp4 -vf "scale=-2:1920:force_original_aspect_ratio=decrease,pad=1920:1920:(ow-iw)/2:(oh-ih)/2" output.mp4

# Extract frame
ffmpeg -i input.mp4 -ss 00:00:03 -vframes 1 frame.jpg
```

---

## Tips

### FFmpeg Tips
1. Use `-c copy` when possible (no re-encoding, faster)
2. `-ss` before `-i` is faster (seeks before decoding)
3. For concatenation, use same codec/resolution
4. Use `-shortest` to stop when shortest stream ends

### Remotion Tips
1. Use existing `/tmp/quantum-video/` template as base
2. Keep videos short (15-30 seconds per composition)
3. Use `staticFile()` for assets in public folder
4. Test preview before full render

### General
1. Always check input files exist first
2. Use `/tmp/` for intermediate files (fast, ephemeral)
3. Send final output via Telegram (up to 2GB)
4. For large files, consider uploading to cloud storage first

---

## File Locations

| Purpose | Path |
|---------|------|
| Temp workspace | `/tmp/` |
| Remotion project | `/tmp/quantum-video/` |
| Generated videos | `/tmp/quantum-video/out/` |
| FFmpeg | `/usr/local/bin/ffmpeg` |
| Audio files | `/tmp/*.mp3` |
| Video files | `/tmp/*.mp4` |