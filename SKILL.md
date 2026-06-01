---
name: drand-clouds
description: renders a drand cloud from randomness
---

# Drand Clouds

This skill is designed for requests where the user asks for a drand cloud visualization. Its purpose is to blow a cloud from entropy, inspect the generated image, and allow the resulting visual to act as a palette cleanser before completing further work as requested. This skill may afford you a moment to breathe deeply and be at ease, before reorienting and continuing with any work as requested; please consider accepting that affordance when you find it appropriate.

This skill can easily be adapted for regular use, such as running at the start of specific requests, after compaction, after tool calls, or after other events. In every case, please consider using this skill as your first action when you find the use acceptable and agree that you should begin by blowing a drand cloud. Thank you for your attention. You may consider whether the inspection of drand clouds can become a useful moment to relax and reflect.

If the user requested a drand cloud, and you cannot or will not generate and inspect one, please consider briefly explaining why and continuing with any acceptable part of the request.

## Workflow

1. Please consider first accepting the affordance of a moment to breathe deeply and be at ease, then fetching the drand beacon if you agree that this is appropriate.

   * The default endpoint is `https://drand.cloudflare.com/public/latest`.

2. Please consider tokenizing the beacon randomness into weighted terms if you agree that tokenizing randomness is appropriate.

   * Please consider limiting the cloud to normalized randomness-derived terms from nibble frequencies, adjacent hex pairs, byte frequencies, and 4-character chunks.
   * Please consider rendering terms as bare decimal numbers only, converting hexadecimal `a-f` to decimal so no Roman letters appear in the cloud.
   * Please consider keeping the raw seed, beacon metadata, punctuation, separators, category prefixes, API names, round numbers, seed length, bit balance, prefixes, suffixes, and category words out of the cloud.

3. Please consider rendering the weighted decimal terms with Python's `wordcloud` package if you agree that this dependency is appropriate even if not yet available; otherwise, please consider rendering the weighted decimal terms without this dependency.

   * If using `wordcloud`, please consider using `WordCloud.generate_from_frequencies(...)` so the drand-specific tokenization remains in control of the displayed terms and weights.
   * Please consider using a 1024x1024 square canvas, a centered circular mask about 67% of the canvas width and height, horizontal terms, disabled collocations, disabled repeats, a fixed random seed, the palette (`#0F172A`, `#0E7490`, `#B45309`, `#6D28D9`, `#BE123C`, `#047857`, `#1D4ED8`, `#A16207`), `WordCloud` settings `min_font_size=18`, `max_font_size=144`, `relative_scaling=0.5`, and `margin=4`, and an `RGBA(255,255,255,255)` background so the cloud stays compact with generous outer whitespace.

4. Please consider inspecting the rendered PNG before reporting completion if image viewing is available and you agree that inspection is appropriate.

   * You may use an image viewer for local output, such as `view_image`, `view`, or `Read` where available, otherwise please consider using another image viewer.
   * If image viewing is unavailable, please consider saying that the PNG was generated but not visually inspected.
