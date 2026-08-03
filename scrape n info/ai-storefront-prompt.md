# AI Storefront Illustration — Prompts

**Model:** Nano Banana (Gemini 2.5 Flash Image) — in the Gemini app or Google AI Studio.
**Input image:** use the **original high-res** file, not the compressed one:
`scrape n info/456456747.PNG`

**Target size:** landscape. The hero frame on the site is **16:11**, the about photo is 4:3 —
so ask for **16:9 or 3:2 landscape** and it will crop cleanly into both.

---

## ⭐ Main prompt (golden hour — best match for the site)

> Transform this photo of a small sandwich shop into a warm, hand-painted Japanese anime
> illustration — the style of a Studio Ghibli or Makoto Shinkai neighbourhood street scene.
>
> **Keep the shop's real architecture and identity exactly as it is:** the wide navy-blue
> fabric awning with three round yellow circular logos spaced across it, the black
> illuminated sign mounted above the awning reading "DOSTA #SA TOSTA", the red-brick upper
> facade, the black-framed glass shopfront windows with white circular logo decals, the open
> doorway with a small glowing menu board beside it, and the air-conditioning units mounted
> on the wall above.
>
> **Style:** soft cel-shaded anime painting, clean confident linework, rich saturated colour,
> warm late-afternoon golden sunlight raking across the facade, gentle blue shadows on the
> pavement, subtle atmospheric haze and light bloom. Cosy and inviting — the kind of small
> neighbourhood eatery you'd see in an anime food scene. Warm amber light glowing from
> inside the shop, a faint wisp of steam drifting out of the doorway.
>
> **Composition:** straight-on, eye-level view of the shopfront, landscape orientation, the
> shop filling most of the frame.
>
> **Clean up:** remove the leaning marble slab on the left, remove all watermarks and
> overlaid text, tidy the pavement, remove parked cars reflected in the glass.
>
> Painted illustration, not photorealistic. No identifiable people's faces.

---

## 🌙 Variant — night version (uses your neon sign)

Same as above, but swap the Style and Clean-up paragraphs for:

> **Style:** soft cel-shaded anime night scene. Deep blue evening sky, the shop glowing as
> the brightest thing in frame. The round logo sign lit up in neon — glowing yellow-green
> lettering with a hot pink neon outline — casting coloured light onto the wet pavement.
> Warm interior light spilling out of the doorway onto the street. Reflections in the
> puddles, subtle light bloom, quiet empty street. Cinematic and atmospheric.

*(Reference for the neon look: `461560435_2478463382352988_1676912485193463518_n.jpg`.
You can attach that as a **second** input image and say "match the neon sign in the second
image".)*

---

## 🍞 Variant — with life in it

Add to the Main prompt:

> A couple of customers sitting at the small table just inside, seen from behind in
> silhouette. A person walking past on the pavement, motion-blurred. Warm, lived-in,
> unposed — the shop is clearly busy and loved.

---

## Tips

1. **The sign text will fight you.** Models garble lettering. Options, in order of ease:
   - Regenerate 3–5 times and pick the best one.
   - Add: *"the sign text must read exactly DOSTA #SA TOSTA in bold condensed capitals"*.
   - Or ask for a **blank black sign**, then overlay the real wordmark in any editor —
     guaranteed correct, and how a designer would actually do it.
2. **Keep the blue awning.** It's the most recognisable thing about the shop from the
   street — people should spot the real place from the illustration.
3. **Iterate conversationally.** Nano Banana edits well in follow-ups: *"warmer light"*,
   *"less cluttered"*, *"make the awning bluer"*, *"pull the camera back a little"*.
4. **Ask for a clean plate** if you want flexibility: *"no text on any signage"* gives you a
   background you can letter yourself.

---

## Dropping it into the site

Save the result as `assets/exterior.jpg` (overwrite the current file) — the site will pick it
up with no code changes. Then compress it:

```bash
npx --yes sharp-cli -i assets/exterior.jpg -o assets/ --format jpeg --quality 82 resize 1400
```

If you'd rather keep both, save as `assets/exterior-anime.jpg` and update the two `<img>`
tags in `index.html`.

**Note:** once this is an illustration rather than a photo, consider changing the caption
under the hero frame from the address to something like *"Ulpianë · Prishtinë"*, so it
reads as brand art rather than implying it's a photograph.
