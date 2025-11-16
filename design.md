
# **TransRefine – What the App Does (Summary)**

**TransRefine** is a bilingual **English–Chinese translation and refinement web-app** designed to go beyond simple word-for-word translation. It combines **accurate translation**, **stylistic refinement**, and **writer-assistant features** into one streamlined tool for students, educators, and professionals.

---

## **Core Functions**

### **1. High-Quality Translation (EN ⇄ ZH)**

* Converts English → Chinese or Chinese → English with context-aware accuracy.
* Handles academic, technical, conversational, and professional writing.

### **2. Refinement / Polishing**

* Improves clarity, tone, style, and grammar while preserving meaning.
* Modes include:

  * **Simple / Natural**
  * **Academic**
  * **Professional**
  * **Concise**
  * **Formal / Polite**

### **3. Dual-Panel Output**

* Left panel = user input
* Right panel = refined/translated output
* Allows immediate side-by-side comparison.

### **4. Multi-Step Writing Support**

* Rewrite
* Expand
* Shorten
* Explain
* Summarize
  The user can select a mode and instantly improve text.

### **5. Quality-Control Tools**

* **Highlight changes** (what changed and why)
* **Explain this translation** (interpretation + reasoning)
* **Grammar check**
* **Tone adjustment**
* **Vocabulary suggestions**

---

## **Design / UX Features You've Built**

* Clean, Figma-designed interface (blue EN + red ZH bubble identity).
* Desktop-first responsive layout.
* Toggle between **Translate** and **Refine** modes.
* Future plan for **history**, **favorites**, and **clipboard copying**.
* Dark/light mode support.
* PWA-friendly layout (optional).

---

## **Overall Purpose**

TransRefine is built to help users **translate**, **polish**, and **understand** English/Chinese writing with:

* Accuracy
* Clear explanations
* Professional refinement
* Fast workflow

It is optimized for your use cases: ESL studies, academic writing, teaching preparation, and web-design prototyping.

---


Primary (English): Blue #4F8EFF  RGB(79 , 142 , 255) 
      Trust, clarity, digital tech – represents English sideSecondary (Chinese): Red #E84A5F2 RGB(32 , 74 , 95) 
      Energy, passion, cultural depth – represents Chinese sideAccent / Harmony: Purple #8B63A9 RGB(139 , 99 , 169) 
      Blend of blue + red – symbolizes balance between languages
Success / Active: Green #6EE7B7 RGB(110 , 231 , 183)
 .    Confirmation, refinement complete
Background Dark: Navy #0F1733 RGB(15 , 23 , 51) 
      Depth, focus on content
Background Light: White #FFFFFF RGB(255 , 255 , 255)
 .    Clean workspace
Text Primary: Ink #1A1A1A RGB(26 , 26 , 26) 
      Readability
Text Muted: Gray #A9B3D1 RGB(169 , 179 , 209) 
      Secondary info or placeholders


Icon Sizes & Scaling
Mobile (1×)     Action buttons  24 px
Tablet (1.5×)   Toolbars            32 px
Desktop(2×)   Headers/Cards 48 px

Button + Function Designs
🔘 Primary Button (Translate), Fill : #4F8EFF, Text : #FFFFFF, Border : none, Corner radius :8px, Shadow : 0 2px 4px rgba(79, 142, 255, 0.25), Icon (optional, left) 24 px
🔴 Secondary Button (Refine), Fill : #E84A5F, Text : #FFFFFF, Shadow : 0 2px 4px rgba(232, 74, 95, 0.25)
⚪ Ghost / Outline, Border : 2 px solid #4F8EFF, Text : #4F8EFF, Background : transparent (hover fill #EAF1FF)
🔘 Disabled, Fill : #A9B3D1, Text : #E0E4EF, No shadow

---

## **Information Architecture & Screens (frames.pdf + flow.png)**

Screen IDs follow the flow diagram (`S1`, `S2`, …) so that the wireframes, prototype (`index.html`), and future backend stay in sync.

### **S1 – Home / TranslateRefine**

* Default landing screen and primary workspace.
* Top row: **voice selector** (Nova, Shimmer, Echo, etc.), large **“Start Speaking”** primary button, and a **“Refine Only”** checkbox to keep the language and polish text instead of translating.
* Center: two stacked bars:
  * **Transcript text** row with edit icon (opens S3) and copy button.
  * **Translation / refined text** row with play‑audio icon, copy button, and share icon (opens S12).
* Below: **recent history list** – each item shows `transcription / translation` plus:
  * Speaker icon = replay audio.
  * Copy transcription, copy translation.
  * Share icon = open share dialog (S12).
* Bottom left: **“History Details”** button → S11.
* Bottom right: floating **“Hold2Say”** microphone button for press‑and‑hold recording.
* Top right: **menu (☰)** button → S2.

### **S2 – Menu Overlay**

* Slide‑out panel on the right over S1.
* Items (each navigates to its screen):
  * **Login** → S4
  * **Import** → S5
  * **Export** → S6
  * **Settings** → S7
  * **Subscribe** → S14
  * **Help** → S8
* Tapping outside or choosing an item returns to the previous screen when done.

### **S3 – Edit Text Input**

* Full‑screen editor titled **“Edit text input”**.
* Large multiline field labeled **“Input or Modify text”**.
* **Cancel** discards edits and returns to the caller (usually S1).
* **OK** saves text back into the transcript/translation field that opened it, then returns to S1.

### **S4 – Login** and **S13 – Register**

**S4 – Login**

* Fields: **Your Email**, **Your Password**.
* Actions: **Cancel**, **OK**, plus an **“Or Register”** call‑to‑action → S13.

**S13 – Register**

* Fields: **Your Email**, **Your Password**, **Retype password**.
* Actions: **Cancel**, **OK**.
* On success, user returns to S1 (logged‑in) and the menu/Login item can change to reflect auth state in future iterations.

### **S5 – Import**

* Title: **Import**.
* Primary call‑to‑action: wide button **“Import from file …”** (opens a file picker).
* Actions: **Cancel** (no changes), **OK** (confirm import and merge records into history on S1/S11).

### **S6 – Export**

* Title: **Export**.
* Primary call‑to‑action: **“Export to file …”** (choose location / filename).
* Actions: **Cancel** (close without exporting), **OK** (confirm export of current history or selected items).

### **S7 – Settings**

* Title: **Settings**.
* Two editable numeric fields:
  * **Max history records number** – upper limit for stored history entries (e.g., `100000`).
  * **Max voice input duration (minutes)** – cap for a single recording (design default: `20`, matches the 20‑minute timeout in `index.html`).
* Actions: **Cancel** (revert changes), **Save** (apply and return to previous screen).

### **S8 – Help**

* Reached from the menu (S2).
* Simple content screen explaining:
  * How to **Start Speaking / Hold2Say**.
  * Difference between **Translate** and **Refine Only**.
  * How history, import/export, and subscription work at a high level.
* Single primary action (e.g., **Back** or **OK**) returns to S1.

### **S9 – Play Voice**

* Title: **Play Audio**.
* Components:
  * **Select voice** control (same voice choices as S1).
  * Audio playback bar with play head and speaker icon.
* Actions: **Cancel** (back without changes), **OK** (confirm selected voice and return).
* Typically entered when the user wants to preview a voice or replay audio in a more focused view.

### **S11 – History Records Details**

* Title: **History Records Details**.
* Scrollable list of past `transcription / translation` pairs.
* Each row includes:
  * Speaker icon = replay audio.
  * Copy icon = copy text.
  * Share icon = open share dialog (S12).
  * Delete/trash icon = remove this history item.
* Bottom: **Back** button returning to S1.

### **S12 – Share Audio**

* Title: **Share Audio**.
* Options:
  * **Air Drop**
  * **Email**
  * **OtherApp**
* Actions: **Cancel** (close without sharing), **OK** (confirm chosen share method after system share dialog).

### **S14 – Subscribe**

* Subscription and payment screen (also referenced as a “History Records Details” overlay in the wireframe).
* Left block:
  * Plan buttons: **Monthly – $10**, **Yearly – $100**.
  * **Payment Methods** section:
    * **Credit Card** form (card number, expiry, CVC).
    * **PayPal** button for external checkout.
  * Actions: **Cancel**, **Subscribe & Pay**.
* Right block:
  * **Subscribe Status** panel with states: **None**, **Monthly**, **Yearly** (current state marked with a check).
* After successful subscription, user returns to S1; subscription status can influence limits or premium features later.

---

## **Key User Flows (from flow.png)**

1. **Quick Translate/Refine**
   * Open app → S1.
   * Choose **voice** and decide whether to tick **Refine Only**.
   * Press **Start Speaking** or use **Hold2Say** to record.
   * Backend returns **transcription + translation/refinement** → UI updates the top pair and appends a new entry to the history list.

2. **Edit and Re‑run a Translation**
   * On S1, tap the **edit (pencil)** icon next to the transcript → S3.
   * Modify text and press **OK** → updated text appears on S1.
   * Re‑trigger processing (e.g., Start Speaking again or a future “Refine” action) to get a new refined/translated output.

3. **Play and Share Audio**
   * On S1 or S11, tap the **speaker** icon to play audio in‑place or go to **Play Audio (S9)** for a focused view.
   * From S1/S11, tap the **share** icon on an item → **Share Audio (S12)**.
   * Pick **Air Drop / Email / OtherApp**, then confirm with **OK**.

4. **Manage History**
   * From S1, tap **History Details** → S11.
   * From S11, replay, copy, share, or delete individual entries.
   * Use **Back** to return to S1.

5. **Import / Export History**
   * Tap menu (☰) on S1 → S2.
   * Choose **Import** → S5, pick a file, then **OK** to merge records.
   * Choose **Export** → S6, select destination, then **OK** to save current records.

6. **Login / Registration / Subscription**
   * From S2 choose **Login** → S4; enter credentials and **OK**.
   * If new user, tap **Register** on S4 → S13; fill fields and **OK**.
   * Once logged in, choose **Subscribe** from S2 → S14; pick **Monthly** or **Yearly**, enter payment info, and **Subscribe & Pay**.

7. **Configure Limits & Help**
   * From S2 choose **Settings** → S7; adjust **max history records** and **max voice input duration (minutes)**, then **Save**.
   * From S2 choose **Help** → S8 to review instructions; then return to S1.

---

## **Implementation Notes (index.html alignment)**

* The current prototype (`index.html`) already implements:
  * Voice selection, Start/Stop Speaking, **Hold2Say**, and a **20‑minute recording cap**.
  * Transcript and translation text areas with edit, play‑back, copy‑to‑clipboard, and share actions.
  * A dynamic **history list** that mirrors S1/S11 rows, including audio replay and copy/share buttons.
  * A **menu button** exposing **Import**, **Home**, and **Login** (Export/Settings/Subscribe/Help are planned per the wireframes).
  * Basic **login** and **history import** endpoints (`/china/login`, `/china/translation_history`) plus clipboard helpers and small “Copied!” toasts.
* Future UI work should extend this prototype to cover all the screens and flows described above while keeping the existing color system and component styles.

---

## **Icon Set (`icons/` directory) and Frame Usage**

All UI icons come from the Material‑style SVGs in `icons/`. This section documents how each icon maps to the wireframes (`frames.pdf`) and screens S1–S14.

### **Icon files and meaning**

* `menu_24dp_...svg` – Hamburger menu. Opens the side menu (S1 header → S2).
* `dehaze_24dp_...svg` – Alternate three‑line menu/overlay icon; optional variant for menu on larger screens (same behavior as `menu` on S1).
* `list_24dp_...svg` – List/dropdown indicator. Shown beside **Select voice** in S1 and S9.
* `mic_24dp_...svg` – Microphone. Used inside **Start Speaking** and **Hold2Say** buttons on S1.
* `volume_up_24dp_...svg` – Speaker icon. Used for playback buttons in S1 history rows, S9 Play Audio bar, and S11 History Records rows.
* `play_arrow_24dp_...svg` – Play button in the audio progress bar on S9 Play Audio.
* `edit_24dp_...svg` – Pencil/edit icon. Beside the main **Transcript text** row on S1 to open S3 Edit Text Input.
* `content_copy_24dp_...svg` – Copy icon. Used next to transcript/translation text on S1 and per‑row in S1/S11 history lists.
* `share_24dp_...svg` – Share icon. Used beside translation rows in S1 and S11 to open S12 Share Audio.
* `history_2_24dp_...svg` – History icon. Used on the **History Details** button on S1 and/or in the S11 header.
* `delete_24dp_...svg` – Trash/delete icon. Right‑most action in S11 rows to remove a history record.
* `settings_24dp_...svg` – Gear icon. Used for the **Settings** entry in S2 and optionally in the S7 header.
* `help_24dp_...svg` – Help icon. Used for the **Help** entry in S2 and optionally in the S8 header.
* `export_notes_24dp_...svg` – Export/import document icon. Used for both **Import** (S5) and **Export** (S6) entries in S2, and in the main call‑to‑action buttons in S5/S6.
* `translate_24dp_...svg` – Translation symbol. Placed near the app title **Translation/Refine** on S1 and as the icon for the “Home/Translate” item in S2.
* `check_box_outline_blank_24dp_...svg` – Empty checkbox. State for **Refine Only** when not selected (S1) and for inactive subscription options in S14 Subscribe Status.
* `check_box_24dp_...svg` – Checked checkbox. State for **Refine Only** when selected (S1) and for the active subscription option in S14.
* `check_24dp_...svg` – Standalone tick mark. Used inside plan cards or status labels in S14 to indicate the current billing plan.

### **Screen‑by‑screen icon usage**

**S1 – Home / TranslateRefine**

* Header: `translate_24dp` next to the **Translation/Refine** title; `menu_24dp` (or `dehaze_24dp` on wide layouts) at top‑right to open S2.
* Voice selector row: `list_24dp` beside **Select voice**.
* Capture actions: `mic_24dp` inside **Start Speaking** and the floating **Hold2Say** button.
* Refine toggle: `check_box_outline_blank_24dp` / `check_box_24dp` for the **Refine Only** checkbox.
* Main text rows:
  * Transcript row: `edit_24dp` to open S3; `content_copy_24dp` to copy the transcript.
  * Translation row: `volume_up_24dp` (play audio), `content_copy_24dp` (copy translation), `share_24dp` (open S12).
* History list: per row – leading `volume_up_24dp`, trailing `content_copy_24dp` (transcription), `content_copy_24dp` (translation), `share_24dp`.
* History entry point: **History Details** button uses `history_2_24dp`.

**S2 – Menu Overlay**

* Panel top: `menu_24dp` as a close/back control (or simply the same icon as the opener).
* Menu items:
  * **Translate / Home** – `translate_24dp`.
  * **Login** – text‑only (no dedicated icon in the current set).
  * **Import** – `export_notes_24dp`.
  * **Export** – `export_notes_24dp`.
  * **Settings** – `settings_24dp`.
  * **Subscribe** – `check_24dp` (emphasizing upgrade/status).
  * **Help** – `help_24dp`.

**S3 – Edit Text Input**

* Content is primarily the large text area; optional small `edit_24dp` in the header to reinforce that this is an edit view.

**S4 – Login / S13 – Register**

* Frames show text‑only. No dedicated icons are required from `icons/`, though a small `translate_24dp` could be reused in the header to keep branding consistent.

**S5 – Import**

* Header or main button uses `export_notes_24dp` next to **Import from file …**.

**S6 – Export**

* Header or main button uses `export_notes_24dp` next to **Export to file …**.

**S7 – Settings**

* Header uses `settings_24dp`.

**S8 – Help**

* Header uses `help_24dp`.

**S9 – Play Audio**

* Voice selector: `list_24dp` beside **Select voice**.
* Audio bar: `play_arrow_24dp` at the left of the waveform/progress, `volume_up_24dp` at the right for loudness/playback emphasis.

**S11 – History Records Details**

* Header: `history_2_24dp`.
* Each row:
  * Leading `volume_up_24dp` for playback.
  * Right‑side actions: `content_copy_24dp` (copy), `share_24dp` (share), `delete_24dp` (delete).

**S12 – Share Audio**

* Header: `share_24dp`.
* Optional: `share_24dp` repeated in each share option row (AirDrop, Email, OtherApp) with different labels.

**S14 – Subscribe**

* Plan selection area: `check_24dp` inside the active **Monthly** or **Yearly** plan card.
* Subscribe Status panel: `check_box_24dp` for the current status row, `check_box_outline_blank_24dp` for inactive rows.

---

## **Logo (`logo/logo.svg`) Usage**

`logo/logo.svg` is the primary brand mark for TransRefine. It shows two overlapping speech bubbles in **blue (#4F8EFF)** and **red (#E84A5F)** with “EN” and “中”, plus the wordmark “TransRefine”.

**Placement**

* Web app header (desktop): left side of the top bar on S1 Home, with the wordmark; height ≈ `48–56px`.
* Mobile: condensed mark (bubbles + “EN中”) centered above the **Translation/Refine** title; height ≈ `32–40px`.
* Login/Register (S4/S13): place the logo centered at the top, above the form fields, at `32–48px` height.
* Marketing/landing pages: full logo (bubbles + “TransRefine”) used in the hero section and footer.

**Color & background**

* Always use the original SVG colors: blue bubble `#4F8EFF`, red bubble `#E84A5F`, white “EN/中” text.
* Preferred backgrounds: **Background Light** (`#FFFFFF`) or **Background Dark** (`#0F1733`). On dark backgrounds, keep the logo as‑is and ensure enough padding so the bubbles remain clear.
* Do not recolor the bubbles independently of the app’s primary palette; treat the logo as a locked asset.

**Sizing & clear space**

* Minimum on‑screen width: `120px` (for wordmark version) to keep “TransRefine” legible.
* Maintain clear space equal to at least half the logo’s height on all sides; no other icons or text should touch the bubbles.

**Interaction**

* Clicking/tapping the logo in the app header navigates to **S1 – Home / TranslateRefine** (acts as “home” link).
* The logo itself is non‑interactive in modal/dialog screens (e.g., S5–S7, S12, S14); it’s purely a brand anchor.
