# HandlerCut Pro

**HandlerCut Pro** is a mobile-first web application built to optimize window film cutting on a **72-inch Film Handler** equipped with **2 slitting blades** (up to 3 strips per pull). It minimizes film waste, side-trim, and pull tails while organizing multi-film jobs into a clean, step-by-step cut queue.

## Current Features (v1)

### 1. Cut-List-First Workflow & Smart Note Parsing

* **Quick Paste Note Parser:** Paste raw job notes directly from your phone. Automatically detects film section headers (e.g., `Blackout`, `Ceramic 35`, `White Frost`, `DR 20`, `EV`, `[Decorative]`), room labels before or after dimensions (`Transom - (1) 36x27` or `(2) 24x34 Living Room`), quantities, and `W x H` measurements.

* **Manual & Grouped Entry:** Add individual window measurements or spin up dedicated film groups with built-in film presets and live pane/square-footage totals.

### 2. Per-Film Roll Inventory & Cut Tolerances

* **Per-Film Roll Toggles:** Track which roll widths (`72"`, `60"`, `48"`, `36"`, or custom widths) are on hand **independently for each film type** in your cut queue.

* **Margin & Allowance Controls:**

  * **Extra Margin (`+0"` / `+1"`):** Automatically add bleed/trim allowance to width and height before optimizing.

  * **Max Side-Trim (`2"`, `3"`, `4"`, `6"`):** Constrain horizontal strip slack per lane.

  * **Max Tail Allowance (`2"`, `3"`, `4"`, `6"`, `8"`):** Penalize pull pairings that leave excessive vertical tails at the bottom of a drop.

### 3. Hardware-Accurate Optimization Engine

* **72" Left-Stop (`0"`) & 2-Blade Positioning:** Calculates exact blade positions measured from the `0"` left stop (or marks blades as `Parked` when unused).

* **Automatic Multi-Roll Combinations:** Evaluates single-roll plans alongside 2- and 3-roll combinations (e.g., splitting wide panes onto a `72"` roll and narrow panes onto a `36"` roll) and ranks the lowest-waste plan automatically.

* **Lowest Waste vs. Fast Split (1-Blade):** Offers multi-stage setups when shifting a single blade mid-job saves time with minimal waste trade-off.

* **Smart Pane Rotation:** Automatically rotates panes 90° when doing so reduces side-trim or pull length.

### 4. Step-by-Step Cut Queue & Visual Cut Diagrams

* **Single-Film Cut Queue:** Displays one film type at a time with queue tabs and **Prev / Next Film** navigation buttons so you stay focused on the roll currently loaded on your handler.

* **Interactive 0"–72" SVG Ruler & Layout Diagrams:** Visualizes blade lines (`B1`, `B2`), lane assignments (`L1`–`L3`), rotated panes, drops, and pull lengths (`↓`).

* **Sequential Pull Checklists:** Tap each pull card as you cut to check off progress.

* **Shop Branding & Themes:** Supports Dark and Light modes plus an optional customizable shop name saved locally via `localStorage`.

## Tech Stack & Deployment

* **Architecture:** Lightweight, dependency-free vanilla HTML, CSS, and JavaScript (`index.html`) for instant local testing (`file://`) and fast mobile loading.

* **Hosting:** Deployed via GitHub + Netlify (`handlercutpro.netlify.app`) and installable to iOS/Android Home Screens.

## Roadmap & Future Stretch Goals (v2+)

### Workflow & Editor Improvements

* **Mass Edit in Cut List:** Bulk-edit film types, room names, or dimensions across multiple rows at once (e.g., quickly changing a group of panes from one shade to another).

* **Save State & Persistence:** Automatically save active cut lists, tolerances, and queue progress locally (and in the cloud) so refreshing or closing the browser never loses a job in progress.

* **Voice Input:** Hands-free speech-to-cut entry to dictate room names, quantities, and window measurements directly into the cut list.

### Codebase & Architecture

* **Modular File Split:** Separate `index.html` into dedicated `index.html`, `styles.css`, and `app.js` files as features expand.

* **Build Pipeline & Code Protection:** Add a production build/minification step for deployment.

### Accounts, Inventory & Shop Management

* **User Authentication:** Account creation and sign-in so installers and shops can sync data across devices.

* **Roll & Box Inventory Page:** Dedicated inventory tracker storing shade/film types, roll widths, and remaining linear footage per box.

* **Box / Barcode Scanning:** Scan film box barcodes with a phone camera to log new rolls or deduct pulled footage automatically.

* **Jobs History Page:** Archive completed jobs with total film pulled, net glass installed, and waste metrics.

* **Drop Tracking:** Log reusable drop offcuts by film shade and dimensions so they can be pulled first on future small panes.

* **Themes & Color Customization Page:** Expand beyond Dark/Light mode with custom accent colors and shop theme presets.