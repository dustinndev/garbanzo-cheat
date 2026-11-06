# Garbanzo Cheat

A one-click helper for **garbanzo.io** assignments. Open an assignment, click a bookmark, press **Complete assignment**, and it works through every step for you.

![The Garbanzo Cheat panel completing an assignment](docs/demo.gif)

---

## How to use it

### 1. Add the bookmark (one time only)

1. Open **https://garbanzo-app.fly.dev** in your browser.
2. Drag the pink **Garbanzo Script** button up into your bookmarks bar.

![Dragging the Garbanzo Script button into the bookmarks bar](docs/bookmarklet.png)

> **Can't see a bookmarks bar?** Press <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>B</kbd> (or <kbd>⌘</kbd> + <kbd>Shift</kbd> + <kbd>B</kbd> on a Mac) to show it.

You only do this once. The bookmark never needs updating, because it always loads the latest version.

#### Another way: make the bookmark yourself

If dragging doesn't work (on some laptops, school computers, or phones), you can make the bookmark by hand:

1. Copy all of the code below:

   ```text
   javascript:(function(){if(window.__garbanzoQaGuiLoaded){window.dispatchEvent(new CustomEvent('garbanzo-qa-toggle'));return;}var b="https://garbanzo-app.fly.dev";var s=document.createElement('script');s.src=b+'/public/loader.js';s.onerror=function(){alert('could not reach the relay at '+b);};document.body.appendChild(s);})();
   ```

2. Right-click your bookmarks bar and choose **Add page…** (Chrome/Edge) or **Add Bookmark…** (Firefox).
   - Safari: bookmark any page first, then right-click the new bookmark and choose **Edit Address**.
3. For **URL**, paste the code you copied.
4. Save.

### 2. Use it on an assignment

1. Log in to garbanzo.io and open the assignment you want.
2. Click **Garbanzo Script** in your bookmarks bar. A panel appears in the top-right corner.
3. Wait for the dot next to the title to turn green and say **Live**.
4. Press **Complete assignment**.

That's it. The panel shows its progress (for example "3 of 10 steps done") and reads **Lesson complete** with your score when it finishes.

### What the panel's controls do

| Control | What it does |
|---|---|
| **Live** / **Connecting** dot | Green means it's ready. Wait for green before you start. |
| **Wrong first** | How many questions to answer wrong once before answering correctly, so a perfect score doesn't look suspicious. `0` means every answer is right first time. |
| **Complete assignment** | Works through every remaining step, starting from the one you're on. |
| **Answer Current Question** | Only shows up on a question step. Answers just that one question. |
| ⏸ Pause | Stops after the current step and takes you to the newest step, so you can use the page yourself. Press **Complete assignment** to carry on. |
| ⏹ Stop | Stops the run. |
| – / ✕ | Minimize or close the panel. Click the bookmark again to bring it back. |

You can drag the panel anywhere by its title bar.

**If something goes wrong**, a red message appears in the panel with a **Copy debug report** button. Copy the report and send it to a dev in the [Hackemos Discord](https://hackemos.com/discord). 
