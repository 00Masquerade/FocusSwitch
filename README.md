# FocusValve
A lightweight, local-first Chrome Extension that introduces a healthy layer of "cognitive friction" to your social feeds. Keep your eyes on what matters, mute the rest, relieving FOMO without hoarding data.

## The Problem
Social timelines are designed to hijack your attention. Even a highly curated following list spans multiple domains—one minute you are tracking breakthrough research, the next you are sucked into sports drama, corporate PR, or sponsored ads. 

Relying on raw willpower to stay focused doesn't work. On the other hand, traditional content blockers are too paternalistic—they delete elements entirely, breaking page layout physics and triggering your FOMO (*"What did I just miss?"*).

## The Solution
**Focus Valve** doesn't erase the timeline; it buffers it. It applies a heavy visual blur over posts matching your custom filter criteria, muting the psychological noise while keeping you in complete control.

- **Instant "Peek" Mechanic:** Hover your cursor over a blurred post to instantly lift the shield. Move your mouse away, and it locks back up instantly. 

- **No Algorithmic Battle:** Stop wasting hours trying to "train" the recommendation algorithm to match your shifting daily context. Just toggle your parameters instantly.

- **Perfect Ad Blocker:** Simply add `ad` as a filter keyword to cleanly blur out promoted posts.

## How It Works (Under the Hood)
To ensure 60fps scrolling without UI stuttering, Focus Valve splits UI mutations from evaluation:
1. **Layer 1 (Regex Routing):** Instantly parses high-frequency social elements, optimized for specific platform tags, handles, and system markers (like `#ad` or `@username`).

2. **Layer 2 (Local Phrase Chunking):** Uses a local, edge-based execution context to evaluate abstract context snippets without cloud latency.

3. **Friction Shield:** Injects a dynamic interactive layer over targeted DOM nodes, handling mouse entry/exit lifecycles smoothly.

## Installation

Since this project adheres to a strict **local-first philosophy**, all processing happens inside your browser. No data leaves your machine, no external APIs are called, and it works completely offline.

1. Clone this repository:
   
   ```bash

   git clone [https://github.com/yourusername/focus-valve.git](https://github.com/yourusername/focus-valve.git)

   ```

2. Open Google Chrome and navigate to `chrome://extensions/`.

3. Enable **Developer mode** via the toggle switch in the top-right corner.

4.  Click **Load unpacked** and select the root directory of this project.

5. Pin the extension, add your current distraction keywords (case-insensitive), and take back your attention.

## Current Scope & Limitations

- **X/Twitter (Web):** Fully optimized with native boundary filtering.

- **Rednote/Xiaohongshu (Web):** Supported via global string matching. 
	- Note: Because Chinese text segmentation is loose in this iteration, keyword matching on single characters operates in a high-sensitivity "maximum defense" mode. Pull requests to refine Chinese token boundaries are welcome.
