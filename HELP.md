# Wavmaster — Help

## The idea: top vs bottom (A / B / R)
- **Top graph = A (working)** — green. Your effects + EQ are heard here. **A is always the top and
  never moves.**
- **Bottom graph = the original *or* the reference** — you choose which with the
  **[B original]** (blue) and **[R reference]** (violet) buttons. The bottom graph's title and
  colour always show what's loaded there.
- **C = alternate playback between the top (A) and the bottom** — at the **same playback spot**.
  It's a clean 2-way toggle; it never cycles through three.
- **Match Loudness** — **anchors on your working track (A)**: A plays at its **true, intended
  loudness** and the original/reference are brought **up to A's level** (each boost capped so it
  can't clip), so you hear your master at full level and still judge *tone*, not just "louder."
  The readout by the button shows the gain applied (`Match: A 0 dB · B +5.0 dB`). Off = every
  source at its true level.
- Effects are **non-destructive**: **every "Apply effects" re-renders A from the dry original** —
  it never stacks effects on already-processed audio, so you can Apply as many times as you like
  with no degradation. Only **Cut/Paste/Trim edits** change the actual audio (the bottom mirrors
  them so the two stay aligned), and only **Save** writes a file.

## Workflow

Color-coded to the buttons: 🟢 working · 🔵 original · 🟣 reference · 🔴 render · 🟡 analyze.

| # | | Step | What you click | What happens |
|:--:|:--:|---|---|---|
| 1 | 📂 | **Open your song** | `File ▸ Open` | Loads it — 🟢 **A (working)** on top, 🔵 **original** on bottom. **Auto-analyzes**: Preset → *Suggested*, EQ filled + on, report ready. |
| 2 | 🟣 | **Load a reference** *(optional)* | `Load Reference` → `Copy Ref` | Reference loads on the **bottom** (turns 🟣 violet). **Copy Ref** aims the whole chain at its tone + loudness. |
| 3 | 🟡 | **Read the analysis** *(optional)* | `Analyzed Report` / `Re-analyze` | Opens LUFS · true-peak · LRA · crest · width · 12-band balance + the full suggested chain. Re-analyze after edits. |
| 4 | 🎚️ | **Pick how much to apply** | `Preset` ▸ Clean/Suggested/All · `Apply Suggested EQ` | Just *loads* the knobs/switches — nothing renders yet. You start on **Suggested**. |
| 5 | 🛠️ | **Tweak to taste** | EQ bands · processor switches · basics | 🟢 on = lit, ⚪ off = grey. **EQ On** = hear EQ live on A (the bottom stays dry). |
| 6 | 🔴 | **Apply effects** | `Apply effects` | Renders the full chain onto 🟢 **A** — **always from the dry original, never stacking**. Re-apply as often as you like. ♾️ |
| 7 | 🔁 | **Compare** | `[B original]` / `[R reference]`, then **C** | Sets the **bottom**; **C** alternates 🟢 top ⇄ bottom at the same spot, loudness-matched. |
| 8 | 💾 | **Save the master** | `File ▸ Save master as…` | Writes a **new** file (WAV 16/24/32f · FLAC · MP3) + a recipe `.txt`. Only this step writes anything. |

**🧭 Two quick routes**

| Route | Path |
|---|---|
| ⚡ **Fast** | 📂 Open → *(auto-Suggested)* → 🔴 Apply effects → 💾 Save |
| 🟣 **Reference** | 📂 Open → 🟣 Load Reference → Copy Ref → 🔴 Apply effects → 🔁 compare 🟢⇄🟣 with **C** → 💾 Save |

**⚠️ Good to know**

| | |
|:--:|---|
| ✅ | **A is always on top** and never moves; the **bottom** is whatever you pick (🔵 original or 🟣 reference). |
| ✅ | **Apply effects is non-destructive** — renders from the dry original every time, so **no degradation** no matter how many times you press it. |
| 🛟 | **Reset Original Audio** is *only* for undoing ✂️ Cut/Paste/Trim edits — **not** needed between Apply passes. |
| 🧹 | **Clear effects** zeros all knobs (A becomes dry again) and keeps your cut/paste edits. |
| 🔒 | Your **original input file is never modified** — only 💾 **Save** writes, to a new file. |
| ⬜ | **Off = blank** — an effect that's off shows **blank** in its dropdown, so only engaged effects show a value. |

## Selection & loop
- **Left-drag across waveform A** to select a region (drag the orange lines to nudge;
  middle-drag pans; scroll zooms).
- **Loop** (on/off) — loop the selected region; play starts at the loop's beginning.
  **Clear loop** drops the loop and selection.
- **Stop** returns to the loop start (or the very start) and parks the playhead there.

## Editing (cut / copy / paste / trim)

There's **one editable audio** (the dry song). Edits reshape it; **A and B always stay the same
length** (🔵 B = the audio *dry*, 🟢 A = the same audio *with effects*). After any edit the effects
**auto re-render** onto A.

> **⚠️ "Original" = dry, not untouched.** Once you edit, 🔵 **B "original"** is the *edited* audio
> without effects — **not** the as-loaded file. To get the untouched file back: **Ctrl+Z** (one
> step) or **Reset Original Audio** (drop all edits).

| Edit | What happens to the audio | Length | Use it to… |
|---|---|:--:|---|
| ✂️ **Trim** | keeps **only** the selection, discards the rest (crop) | shrinks | isolate the song body / drop dead air at the head or tail |
| ✂️ **Cut** | removes the selection; later audio **slides left** | shrinks | drop a long count-in, silence, a cough/click, or a bad bar |
| 📋 **Copy** | copies the selection (**dry**) to the clipboard | — | grab a section to paste elsewhere |
| 📌 **Paste** | inserts the clipboard **at the playhead**; later audio **slides right** | grows | extend an outro, repeat a section, rebuild an intro |

Copy/Cut grab **dry** audio and Paste inserts dry, so after the re-render your effects apply
**evenly** across the whole thing (no double-processing of a pasted bit).

**Smoothest order:** edit the **audio** first (trim/cut/paste), *then* dial in effects + EQ — each
edit triggers a fresh effects render. But you can edit any time; effects just re-apply on top,
non-destructively.

## Tone (Basic Effects)
- **Preset** — fills the basic knobs from a choice: **Clean** (all off), **Suggested** (the
  analyzer's picks, shown green), **All** (everything on), or a **genre**. It only fills the knobs
  so you can see/tweak them — press **Apply effects** to hear it. Off effects show **blank**.
- **Clarity** — presence/definition (≈3 kHz + highs), plain EQ. More = crisper. *(off · subtle · normal · bright)*
- **Bass** — low-end shelf weight. *(off · subtle · normal · heavy)*
- **Air** — very-high "sparkle" on top. *(off · subtle · normal · sparkle)*
- **De-mud** — cuts boxy buildup around 250–300 Hz. *(off · subtle · normal · aggressive)*
- **Warmth** — adds low-mid body (≈180–200 Hz). *(off · subtle · normal)*
- **Punch** — compression for glue and impact. More = denser, less dynamic. *(off · gentle · normal · hard)*
- **Loudness** — overall level boost. Ignored when *Exact LUFS* is on. *(off · gentle · normal · loud · max)*
- **Ambience (reverb)** — adds depth/space. A little goes a long way on a master. *(off · subtle · normal · lush)*
- **Spatial (headphone 3D)** — **fake** 3D surround for **headphones**: widens/opens the
  stereo image. Not real surround, and it partly collapses on a mono speaker. *(off · surround)*

## Extended Effects (sliders 0–10)
> Each basic effect and its extended twin are **1-or-the-other, both ways** — set either side
> and the OTHER switches **OFF and tints maroon** (it stays visible/editable): **Clarity Exciter ⇄
> Clarity**, **Loudness Maximizer ⇄ Loudness**, **Stereo Widener ⇄ Spatial**. Just set the one you
> want; its twin goes off.

- **Clarity Exciter** — an exciter that **adds new high harmonics** (separate from the Clarity
  EQ, not a replacement). Adds air/sheen to dull sources; overdone = fizzy.
- **Loudness Maximizer** — pushes gain into a limiter to get **louder** (separate from the
  Loudness control). Peaks stay capped; higher = **more squashed**, not better. For streaming,
  prefer *Exact LUFS* instead of just maxing this.
- **Stereo Widener** — a Mid/Side widener: a cleaner, more controllable way to make the image
  wider/roomier. More width = less mono-compatible.
- **Highpass Hz** — **type a frequency** to remove sub-rumble below it (0 = off; 30 is typical).
- **HPF slope (dB/oct)** — how steeply the highpass cuts below that frequency: **12** = gentle and
  transparent, **24** = tighter, **48** = near-brickwall (kills subsonic junk hard, with a little
  more phase shift near the cutoff).
- **Exact LUFS (loudnorm)** — hits the **Target LUFS** exactly (best for streaming). When ON it
  **disables both Loudness and the Maximizer** and **enables Target LUFS** (green slider).
- **Target LUFS** — the loudness it normalizes to (≈ −14 for most platforms, −16 for some).
  Locked until **Exact LUFS** is checked; resets to −14 when unchecked.

## Processors (knob-based)

The **Processors** box holds effects that need real knobs rather than a preset level. Each one has
an **ON/OFF switch** (green = on, grey = off) — it just enables/bypasses the effect; the knob
settings stay put. So you can dial a setting, flip it off to A/B, or reuse the same settings on a
stem vs the full song. **Analyze** flips the **Compressor** on when it suggests one.

- **Saturation — Drive (0–10)** — drives the signal into a soft-clip to add warm harmonics /
  grit. Higher = thicker and more colored; 0 = off.
- **Saturation — Mix (0–100%)** — blends the saturated signal back with the dry one. 100 = full
  effect; **lower = subtle parallel saturation** (adds body/weight without dulling transients).
- **Compressor** — a real compressor:
  - **Ratio** — compression strength. **1:1 = off (bypass)**; 2–4:1 is gentle "glue," higher is
    more squashed.
  - **Threshold (dB)** — the level where compression kicks in; lower catches more of the signal.
  - **Attack / Release (ms)** — how fast it clamps down and lets go. Fast attack tames transients;
    slower attack lets the punch through.
  - **Makeup (dB)** — gain added back after compressing to restore level.
  - **Stages (1 / 2)** — 2 cascades the same compressor twice in series for smoother, less obvious
    gain reduction (make-up is applied once, on the 2nd stage).

## Keys
- **C** — compare: alternate playback between the top (A) and the bottom (B original or R reference)
- **A / B** — pick the source: A = working (top), B = original (bottom)
- **Space** — play / pause
- **Ctrl+Z** — undo the last edit (cut / paste / trim)

## How it works (technical)
*(Full write-up with diagrams is in the README's "How it works (technical)" section.)*

- **The tools** — 🟦 **ffmpeg** decodes + measures, 🟨 **SoX** + ffmpeg do the processing,
  🟩 **numpy** holds the audio + does the spectral analysis, 🟪 **mpv** plays it back for A/B/R.
  Wavmaster orchestrates them; it doesn't reinvent the DSP.
- **Source of truth** — on load, ffmpeg decodes any file to a 32-bit stereo WAV → a numpy
  `float32[frames,2]` buffer = **B / original**. Cut/Paste/Trim edit this buffer; effects never do.
- **32-bit pipeline** — decode → process stays 32-bit end to end (SoX forced `-b 32`, every ffmpeg
  hop `pcm_s32le`); only **Save** down-converts, with noise-shaped TPDF **dither** for 16-bit
  (24/32-float skip dither).
- **Render chain** — SoX runs the tone/dynamics pass (highpass → 16-band EQ → de-mud → warmth →
  bass → clarity → air → reverb → compand → normalize); then ffmpeg hops do de-esser → dynamic-EQ
  → compressor → multiband → exciter → saturation → spatial → widener → maximizer → limiter →
  (two-pass loudnorm if Exact LUFS). **All controls off = bit-identical passthrough.**
- **Analyze — measure** — ffmpeg's `loudnorm` pass → integrated **LUFS / true-peak / LRA**; numpy →
  **crest** (peak/RMS), **stereo correlation + width**, and a **12-band spectral balance** from a
  Welch-averaged 32k-point FFT (Hanning, 50 % overlap).
- **Analyze — suggest** — each band's energy share vs. a balanced-master reference curve, in dB:
  > 2.5 dB hot → EQ cut; > 3 dB thin → boost. Crest < 7 → no comp; 7–12 → 1.8:1; > 12 → 2.5:1
  2-stage. Limiter always; de-esser if highs hot; dynamic-EQ if presence spikes; multiband if very
  dynamic.
- **Reference (Copy Ref)** — ffmpeg decodes the reference + measures **its** 12-band shares and
  LUFS; Analyze re-runs against the reference's curve (not the generic one), so the suggested
  EQ/loudness push your song toward the reference's **measured tone** — not its literal settings.
- **Live EQ + meters** — mpv holds 3 tracks (aid 1 = B, 2 = A, 3 = R); switching is `set aid` +
  matched volume (instant, same spot). The EQ is an ffmpeg `equalizer` filter chain pushed to mpv's
  `af` in real time, **on A only** — a preview baked into the file only at Save. Live LUFS meters =
  a numpy mean-square envelope offset to match ffmpeg's integrated LUFS.
