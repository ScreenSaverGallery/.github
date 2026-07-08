# For Artists — Preparing a Show for ScreenSaverGallery

Welcome! This guide is written for artists and curators who are preparing an artwork to be shown on **ScreenSaverGallery**. You don't need to be a developer to read it — we'll explain the medium in plain language so you can plan your work with confidence.

- Website: [screensaver.gallery](https://screensaver.gallery)
- Past shows: [screensaver.gallery/archive/screensavers](https://screensaver.gallery/archive/screensavers)

---

## What is ScreenSaverGallery?

ScreenSaverGallery is a **screensaver** — the kind of thing that appears on a computer screen after it's been left idle for a while. But instead of flying toasters or a black screen, it shows **art**.

Behind the scenes, the ScreenSaverGallery is simply a **web browser** that opens a web address (URL) and displays whatever is there, fullscreen, on the screen. That's the whole trick. So if your artwork can live in a web browser, it can live in ScreenSaverGallery.

> In other words: **if it runs in a web browser, it can run as a screensaver.**

---

## The Medium — what's possible

Because the screensaver *is* a web browser, your artwork can be made with any of the technologies the web already supports. You can use one or combine several:

| Medium | What this means in practice |
| ------ | -------------------------- |
| **Images** | Static pictures — JPG, PNG, WebP, SVG, GIF, etc. |
| **Video** | Any video the browser can play (MP4, WebM, …), with or without sound. |
| **Audio** | Sound pieces — music, voice, ambient, generative audio. |
| **Animation** | Anything that moves over time: CSS animation, JavaScript animation, Canvas, etc. |
| **3D / WebGL** | Interactive-looking 3D scenes (e.g. built with Three.js) — rendered in real time by the computer's graphics card. |
| **HTML / web pages** | A whole web page, layout, text, fonts, links — anything you can put on a website. |
| **Generative / algorithmic** | Code that produces visuals or sound on the fly (p5.js, Canvas, shaders, Web Audio, etc.). |
| **Data-driven work** | Artwork that pulls in live data from the internet (weather, stock prices, social media, time…). |
| **Time-based work** | Work that changes over the day, week, or season. |
| **Type & layout** | Experimental typography, text pieces, essays-as-screensaver. |

### A few concrete examples
- A slowly looping video of a landscape.
- A generative animation that never repeats.
- A 3D object that gently rotates forever.
- A full-screen poem whose letters drift across the screen.
- A live audio stream that plays through the computer's speakers.
- A page that changes color based on the current weather in your city.

---

## 🚫 One important rule — the gallery screen is **not interactive**

The computer running the screensaver is **idle** — nobody is sitting in front of it clicking or typing. The screen simply *displays*. This means:

- ❌ The artwork **cannot** rely on mouse clicks, keyboard, scroll, or touch from the gallery screen itself.
- ❌ There are no buttons to press, no forms to fill, nothing to drag.
- ✅ The artwork is **always running by itself**, from the moment the screensaver starts until the computer is woken up.

Think of it less like a website and more like a **film** or a **TV channel**: it plays, on its own, to whoever walks past the screen.

---

## But — you *can* add interaction through a second device

If your artwork needs a viewer to participate, we can build that interaction on **a separate device** — for example, a visitor's mobile phone — and have it talk to the screensaver over the internet using **WebSocket** communication.

In simple terms:
- The screensaver runs on the computer (display only, no interaction).
- A visitor opens a link on their phone (or scans a QR code).
- Whatever the visitor does on their phone is sent to the screensaver in real time, and the screensaver reacts.

Examples of what this enables:
- A visitor draws on their phone and the drawing appears on the gallery screen.
- A visitor presses buttons and the screensaver changes color / plays a sound.
- Several visitors' phones feed into one shared screen.
- A visitor's phone sensor (accelerometer, touch, location) drives the on-screen artwork.

> We can help you set up this kind of two-device setup. You don't have to build the network part alone — talk to us early in your process and we'll figure it out together.

---

## Sound — yes, it's supported

ScreenSaverGallery can play audio. The viewer can mute or unmute the screensaver in their system preferences, and we can also flag your work so that adult/NSFW content is filtered where appropriate. If your piece relies on sound, **please tell us** so we can make sure it's presented the way you intend.

---

## What we need from you

Good news: for most shows **you don't need to build a website or write any code.** ScreenSaverGallery has its own ready-made player (a "kiosk") that already knows how to display every kind of media a web browser can handle — video, images, audio, and more. In most cases, all you do is hand over your media files, and we place them into the kiosk.

### What we need (the common case — media files)

Just send us your artwork as **media files**, plus a little information about it. The kiosk takes care of the rest.

| You give us | We take care of |
| ----------- | -------------- |
| **Video** files (MP4, WebM, …) | Fullscreen playback, looping, cover/contain layout |
| **Image** files (JPG, PNG, WebP, SVG, …) | A slideshow with timing and display mode of your choice |
| **Audio** files (MP3, …) | Playback with cover image, volume, looping / shuffle |
| Optional: **a cover image**, **a title**, **your name**, a short **description**, a **link** to your website | These appear in the archive and (where relevant) alongside the work |

A few extra options the kiosk supports, if you want them:
- **YouTube or Vimeo** — if your work already lives there, we can point the kiosk straight at it.
- **A live stream** — if your piece is a live video or audio stream, we can connect to it.
- **Spoken text (voice-over)** — the kiosk can read text aloud in the viewer's browser, on a schedule you define (useful for descriptions, captions, or as part of the artwork itself).
- **Combinations** — several of the above layered or sequenced together (for example: images + audio, or video + a voice-over track).

> In short: **send us the files, tell us how they should behave, and we do the rest.** If you're unsure what format to deliver, send us what you have and we'll advise.

### The special case — your own live web page (URL)

Some works can't be reduced to a media file — for example a generative animation, a 3D scene, an interactive piece, or anything that *is* the web. For these, you can host your own web page and we point the screensaver at it.

If you go this route, there is one technical thing we need from you:

- **Allow `screensaver.gallery` in your page's CORS settings.**
  In plain terms: your web server needs to give our screensaver permission to load your page inside the ScreenSaverGallery player. Without this, the browser will silently block your content. If that sentence means nothing to you, send us the page and whoever hosts it (or we) can switch it on — it's a small, standard setting.

The same "runs on its own" rules below still apply — your page should display without any clicks or input from the gallery screen.

### A few friendly requirements (both cases)
- The work should run **on its own**, without user input from the gallery screen (see the "not interactive" section above).
- It should ideally keep running **indefinitely** without crashing or freezing — the screensaver may run for hours. If you're delivering a custom web page, avoid code that eats more and more memory over time or that stops dead after a fixed duration.
- If your work uses **sound**, let us know whether the sound is essential, and at what volume it should sit.
- If your work contains **nudity or explicit content**, tell us so we can tag it correctly.

---

## See what other artists have done

The best way to get a feel for the medium is to look at previous shows:

👉 **[screensaver.gallery/archive/screensavers](https://screensaver.gallery/archive/screensavers)**

You'll find a wide range of approaches — from generative animation to video to text to 3D — which should give you a sense of what's possible and what feels right in the screensaver context.

---

## Talk to us

You don't have to be technical to make a show with us — that's our job. If you have an idea, even a rough one, [**get in touch**](https://screensaver.gallery/contact) and we'll help you figure out the simplest way to make it happen.

- Website: [screensaver.gallery](https://screensaver.gallery)
- Past shows: [screensaver.gallery/archive/screensavers](https://screensaver.gallery/archive/screensavers)
- Become a sponsor: [Open Collective](https://opencollective.com/screensavergallery)

---

*ScreenSaverGallery was launched in 2012 by Barbora Trnkova and Tomáš Javůrek. Since 2013 it runs a continuous exhibition program. ScreenSaverGallery is hosted on [metazoa.org](https://metazoa.org) servers.*
