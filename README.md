# 📦 FontFlex (FF)

---

## 🐛 The Problem

Font sizing across screen sizes and resolutions is consistently inconsistent.

You may try:

- `rem` or `em` — but they only scale relatively and inconsistently.
- `clamp()` — can get messy with mixed font types or break on small screens.
- `vw` / `vh` — distorts layout if overused.
- `@media queries` — tedious and error-prone across complex layouts.

> Developers are forced to micro-manage font sizes for every screen manually.

---

## 💡 The Philosophy

> Instead of adapting your design to screens,  
> **FF adapts screens to your design.**

---

## 🚀 What It Does

FF:

- Detects the computed font size of any text element.
- Scales it automatically for any screen using:
  - Desktop reference size (width + height),
  - Mobile reference width (for portrait),
  - Pixel density of the device.
- Applies the new font size inline via JavaScript.

You don’t need media queries or manual recalculations.

---

## ✅ Key Features

| Feature                  | Description                                                   |
| ------------------------ | ------------------------------------------------------------- |
| 🔍 Computed size reading | Works with `px`, `rem`, `%`, or even inherited/default styles |
| 📱 Mobile smartness      | Uses only screen width in portrait (phone) mode               |
| 💻 Desktop logic         | Uses width + height + device pixel ratio for large screens    |
| 🎛️ Tweakable scaling     | Global `scaleMultiplier` to fine-tune scaling sensitivity     |
| 🧠 Pure JavaScript       | Lightweight, no dependencies                                  |
| 🖋️ Unit-agnostic         | No restrictions on your CSS units or coding style             |

---

## 📦 How to Use

### 1️⃣ Define your styles normally

No special CSS rules needed. Use any unit, or none at all:

```css
body {
  font-family: sans-serif;
}
h1 {
  font-size: 3rem;
}
p {
  font-size: 1.1rem;
}
/* Even this will work: */
.note {
  /* no font-size defined */
}
```
## 🎯 Smart Default: .text-scale Class
FF includes a built-in shortcut to make font scaling easier:
you can simply use the class text-scale on any HTML element,
and it will automatically be included in the scaling logic.

No need to add it to the selectors array in JavaScript —
it's always recognized by the library by default.

## Installation

```
npm install font-flex

```

## Usage

```
import PreciseFontScaler from 'font-flex';

```

```
 PreciseFontScaler.init({
    baseScreen: {
      desktopWidth: 1440,   // Your design width
      desktopHeight: 900,   // Your design height
      mobileWidth: 375,     // Reference width for portrait mobile
      density: 1            // Device pixel ratio used when you designed
    },
    scaleMultiplier: 1,      // Optional (default is 1)
    selectors: ["body", "h1", "p", ".text-scale"]  // Elements you want to scale
  });
```

| Option            | Type      | Description                                                                                                                                    |
| ----------------- | --------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| `desktopWidth`    | number    | Width (in px) of the screen you originally designed on                                                                                         |
| `desktopHeight`   | number    | Height (in px) of your reference screen                                                                                                        |
| `mobileWidth`     | number    | Width used for mobile scaling (portrait mode)                                                                                                  |
| `density`         | number    | Your original screen’s pixel ratio (e.g. 1 or 2)                                                                                               |
| `scaleMultiplier` | number    | Optional (default = `1`). Controls the intensity of scaling across all screens. Values below `1` reduce scaling effect, above `1` increase it. |
| `selectors`       | string\[] | Array of CSS selectors targeting the elements you want to scale                                                                                |


## 📌 Notes

- No need to use px. FF works with any unit or browser default.

- Don’t use clamp(), vw, or other JS-based scalers alongside FF.

- Avoid mixing multiple font scaling systems — FF handles everything.

- You don’t need to define font-size at all — defaults will still scale.

## 🧠 Why FF?

Because you shouldn’t have to redesign typography for every screen.

FF helps you:

Design once, scale forever.

Keep typography predictable and consistent.

Remove clutter from your CSS and media queries.

Focus on content and aesthetics, not device hacks.

## NPM

[npm ...](https://www.npmjs.com/package/font-flex)

## 📄 License

MIT — use freely, improve freely. Attribution is appreciated but not required.
