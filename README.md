<div align="center">

# 🎨 CSS Fundamentals: Page Layout, Float & Selectors

**Three projects on building a full page layout, wrapping text around images, and styling things that aren't in the HTML**

</div>

---

## 📖 About This Repository

This repository contains mini-projects I built while learning CSS. Each folder holds a single `index.html` file, so every concept is easy to see, edit, and experiment with.

No frameworks, no build tools. Just HTML and CSS.

---

## 📑 Table of Contents

1. [Project Structure](#-project-structure)
2. [Project 1: Modern Page Layout](#-project-1-modern-page-layout)
3. [Experiment 2: Float & Clear](#-experiment-2-float--clear)
4. [Experiment 3: Selectors & Pseudo-elements](#-experiment-3-selectors--pseudo-elements)
5. [How to Run](#-how-to-run)
6. [Key Takeaways](#-key-takeaways)
7. [Roadmap](#-roadmap)

---

## 📂 Project Structure

```
css-fundamentals/
│
├── 12-modern-layout/
│   └── index.html
│
├── 13-float-and-clear/
│   └── index.html
│
├── 14-selectors-pseudo-elements/
│   └── index.html
│
└── README.md
```

> 💡 Rename the folders to match your own layout. Each `index.html` is fully standalone.

---

## 🧭 Project 1: Modern Page Layout

📁 `12-modern-layout/index.html`

### 🎯 Goal
Combine several earlier lessons into one complete, dark-themed page with a **sticky navbar**, a **flexible content area**, a **welcome card**, scrollable sections, and a **footer with a corner logo**.

### 🧱 Page Structure

<table>
  <tr>
    <th>Section</th>
    <th>Contents</th>
    <th>Key technique</th>
  </tr>
  <tr>
    <td><b>Navbar</b></td>
    <td>Centered site title</td>
    <td><code>position: sticky</code> with <code>z-index</code></td>
  </tr>
  <tr>
    <td><b>Main section</b></td>
    <td>Two colored boxes and a welcome card</td>
    <td>Flexbox with <code>flex-wrap</code> and <code>gap</code></td>
  </tr>
  <tr>
    <td><b>Content</b></td>
    <td>About Us, Services, Contact blocks</td>
    <td>Extra height to demonstrate scrolling</td>
  </tr>
  <tr>
    <td><b>Footer</b></td>
    <td>Copyright text and an orange logo</td>
    <td><code>position: relative</code> parent with an <code>absolute</code> child</td>
  </tr>
</table>

### 🔑 Concepts Covered

<table>
  <tr>
    <th>Concept</th>
    <th>Where it's used</th>
    <th>Why it matters</th>
  </tr>
  <tr>
    <td>Sticky navbar</td>
    <td><code>.navbar</code></td>
    <td><code>position: sticky; top: 0;</code> keeps the bar visible while scrolling.</td>
  </tr>
  <tr>
    <td><code>z-index</code></td>
    <td><code>.navbar</code> (<code>100</code>)</td>
    <td>Keeps the navbar above the content that scrolls beneath it.</td>
  </tr>
  <tr>
    <td>Flex wrapping</td>
    <td><code>.container-area</code></td>
    <td><code>flex-wrap: wrap</code> lets the boxes drop onto separate lines on narrow screens instead of overflowing.</td>
  </tr>
  <tr>
    <td><code>gap</code></td>
    <td><code>.container-area</code></td>
    <td>Even spacing between flex items without margin tricks.</td>
  </tr>
  <tr>
    <td>Centered, readable width</td>
    <td><code>.main-section</code>, <code>.content</code></td>
    <td><code>max-width: 1200px</code> with <code>margin: auto</code> keeps content centered and not too wide.</td>
  </tr>
  <tr>
    <td>Rounded card</td>
    <td><code>.welcome-card</code></td>
    <td>Large <code>border-radius</code> (<code>35px</code>), a border, and dark background create a modern card.</td>
  </tr>
  <tr>
    <td>Relative size units</td>
    <td><code>3rem</code>, <code>1.1rem</code></td>
    <td>Text scales with the root font size.</td>
  </tr>
  <tr>
    <td>Absolute positioning</td>
    <td><code>.footer-logo</code></td>
    <td>Pinned <code>20px</code> from the footer's bottom-right corner.</td>
  </tr>
  <tr>
    <td>Smooth scrolling</td>
    <td><code>html { scroll-behavior: smooth; }</code></td>
    <td>Anchor links glide to their target instead of jumping.</td>
  </tr>
  <tr>
    <td>Hover lift</td>
    <td><code>.box:hover</code></td>
    <td><code>transition</code> plus <code>translateY(-8px)</code> gives subtle feedback.</td>
  </tr>
</table>

### 🧪 Code Highlight

```css
/* Navbar stays at the top while scrolling */
.navbar {
  width: 100%;
  height: 80px;
  background: #ff85e8;
  display: flex;
  justify-content: center;
  align-items: center;
  position: sticky;
  top: 0;
  z-index: 100;
}

/* Boxes wrap onto new lines on narrow screens */
.container-area {
  background: #006400;
  padding: 35px;
  border-radius: 10px;
  display: flex;
  gap: 40px;
  justify-content: center;
  flex-wrap: wrap;
}

/* Footer is the anchor for the absolute logo */
.footer {
  position: relative;
  background: white;
  min-height: 150px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.footer-logo {
  position: absolute;
  bottom: 20px;
  right: 20px;
  width: 45px;
  height: 45px;
  background: orange;
  border-radius: 50%;
  border: 3px solid white;
  box-shadow: 0 0 15px rgba(255, 165, 0, 0.5);
}
```

### 🎨 Color Palette

<table>
  <tr>
    <th>Use</th>
    <th>Value</th>
  </tr>
  <tr>
    <td>Page background</td>
    <td><code>#0d0d0d</code></td>
  </tr>
  <tr>
    <td>Navbar</td>
    <td><code>#ff85e8</code></td>
  </tr>
  <tr>
    <td>Container area</td>
    <td><code>#006400</code></td>
  </tr>
  <tr>
    <td>Box 1 / Box 2</td>
    <td><code>#ff9ea8</code> / <code>#4d8cff</code></td>
  </tr>
  <tr>
    <td>Welcome card</td>
    <td><code>#111</code> with a <code>#6b6b6b</code> border</td>
  </tr>
  <tr>
    <td>Content sections</td>
    <td><code>#181818</code></td>
  </tr>
  <tr>
    <td>Footer logo</td>
    <td><code>orange</code></td>
  </tr>
</table>

### 🔬 Try It Yourself

<details>
<summary><b>Click to expand the experiment steps</b></summary>

<br>

1. **Scroll the page** and watch the pink navbar stay pinned at the top.
2. Remove `z-index: 100` from `.navbar` and check whether any content slides over it while scrolling.
3. Resize the window below roughly 950px and watch the two boxes wrap onto separate lines because of `flex-wrap: wrap`.
4. Remove `position: relative` from `.footer`. The orange logo jumps to a corner of the whole page instead of the footer.
5. Change `top: 0` on the navbar to `top: 20px` and see the offset where it sticks.
6. Add navigation links and section ids, then click them to see `scroll-behavior: smooth` in action.

</details>

---

## 🌊 Experiment 2: Float & Clear

📁 `13-float-and-clear/index.html`

### 🎯 Goal
Learn how to wrap text around an image with `float`, why the parent container **collapses**, and how `clear` and `flow-root` solve it.

### 🔑 Concepts Covered

<table>
  <tr>
    <th>Concept</th>
    <th>Example</th>
    <th>What it does</th>
  </tr>
  <tr>
    <td><code>float: left</code></td>
    <td><code>img { float: left; }</code></td>
    <td>Pulls the image to the left and lets <b>text flow around it</b>.</td>
  </tr>
  <tr>
    <td><code>clear: both</code></td>
    <td><code>.card:nth-child(3)</code></td>
    <td>Forces an element to start <b>below</b> any floated elements.</td>
  </tr>
  <tr>
    <td><code>display: flow-root</code></td>
    <td><code>.cards</code></td>
    <td>Makes the parent <b>contain its floated children</b>, fixing the collapsed height.</td>
  </tr>
  <tr>
    <td><code>:nth-child(n)</code></td>
    <td><code>.card:nth-child(3)</code></td>
    <td>Selects an element by its position among its siblings.</td>
  </tr>
</table>

### 🧪 Code Highlight

```css
.cards {
  border: 2px solid black;
  display: flow-root;   /* parent now wraps around the floated image */
}

img {
  float: left;
}

.card {
  border: 2px solid red;
}

.card:nth-child(3) {
  background-color: aqua;
  clear: both;          /* start below the floated image */
}
```

### 🧠 What Happens Here

<table>
  <tr>
    <td>1️⃣</td>
    <td>The image is floated left, so the text in the first card <b>wraps around it</b>.</td>
  </tr>
  <tr>
    <td>2️⃣</td>
    <td>Block boxes ignore floats, so the red card borders run <b>behind the image</b>. Only the text lines are shortened to make room.</td>
  </tr>
  <tr>
    <td>3️⃣</td>
    <td>A floated element is taken out of normal flow, so a parent would normally <b>collapse</b> and ignore its height. <code>display: flow-root</code> prevents that.</td>
  </tr>
  <tr>
    <td>4️⃣</td>
    <td><code>clear: both</code> pushes the targeted card below the image so it no longer sits beside it.</td>
  </tr>
</table>

### 🧩 Ways to Contain Floats

<table>
  <tr>
    <th>Method</th>
    <th>Code</th>
    <th>Notes</th>
  </tr>
  <tr>
    <td><b>flow-root</b> (modern)</td>
    <td><code>display: flow-root;</code></td>
    <td>Cleanest option, built for exactly this purpose.</td>
  </tr>
  <tr>
    <td>Clearfix</td>
    <td><code>.clearfix::after { content: ""; display: block; clear: both; }</code></td>
    <td>The classic hack. Still seen in older code.</td>
  </tr>
  <tr>
    <td>Overflow</td>
    <td><code>overflow: hidden;</code></td>
    <td>Works, but can clip content like shadows and dropdowns.</td>
  </tr>
</table>

### 🐛 Common Pitfalls

<table>
  <tr>
    <td>⚠️</td>
    <td><b>Counting with <code>:nth-child</code>:</b> it counts <b>all</b> children, including the <code>&lt;img&gt;</code>. Here the image is child 1, the first card is child 2, the long card is child 3, and "Card 3" is child 4. So <code>.card:nth-child(3)</code> targets the long paragraph card, not the one labelled "Card 3".</td>
  </tr>
  <tr>
    <td>⚠️</td>
    <td><b>Image width:</b> the HTML attribute should be a plain number (<code>width="230"</code>), not <code>width="230px"</code>. Browsers tolerate the latter, but the number form is the correct one.</td>
  </tr>
  <tr>
    <td>⚠️</td>
    <td><b>Hotlinked images:</b> thumbnail links from search engines can stop working at any time. Use a stable image source or a local file.</td>
  </tr>
</table>

### 🔬 Try It Yourself

<details>
<summary><b>Click to expand the experiment steps</b></summary>

<br>

1. Remove `display: flow-root` from `.cards` and watch how the black border stops wrapping around the floated image.
2. Remove `clear: both` and see the highlighted card sit beside the image again.
3. Change `float: left` to `float: right` to move the image to the other side.
4. Change `.card:nth-child(3)` to `.card:last-child` to target the card labelled "Card 3".
5. Add `margin-right: 15px` to the image so the text doesn't touch it.
6. Rebuild the same layout with Flexbox and compare how much simpler it is.

</details>

> 📝 **Note:** Float was designed for wrapping text around images. For page layouts, modern tools like Flexbox and Grid are the right choice.

---

## ✨ Experiment 3: Selectors & Pseudo-elements

📁 `14-selectors-pseudo-elements/index.html`

### 🎯 Goal
Style parts of the page that **don't exist in the HTML**, such as generated content, the first letter, highlighted text, and placeholders, and practice precise element selection.

### 🔑 Active Pseudo-elements in This Project

<table>
  <tr>
    <th>Selector</th>
    <th>What it styles</th>
    <th>Code in this project</th>
  </tr>
  <tr>
    <td><code>::before</code></td>
    <td>Generated content <b>before</b> an element's content</td>
    <td><code>.boxes::before { content: "Ahmad is good"; color: blue; }</code></td>
  </tr>
  <tr>
    <td><code>::after</code></td>
    <td>Generated content <b>after</b> an element's content</td>
    <td><code>.boxes::after { content: "Sigma course is also good"; color: red; }</code></td>
  </tr>
  <tr>
    <td><code>::selection</code></td>
    <td>Text highlighted by the user</td>
    <td><code>::selection { color: aqua; background-color: black; }</code></td>
  </tr>
  <tr>
    <td><code>::first-letter</code></td>
    <td>The first letter of a block</td>
    <td><code>.box::first-letter { color: peru; font-size: 45px; }</code></td>
  </tr>
  <tr>
    <td><code>::placeholder</code></td>
    <td>Hint text inside an input</td>
    <td><code>input::placeholder { color: rgb(84, 84, 88); }</code></td>
  </tr>
</table>

### 🧪 Code Highlight

```css
.boxes::before {
  content: "Ahmad is good";
  color: blue;
}

.boxes::after {
  content: "Sigma course is also good";
  color: red;
}

::selection {
  color: aqua;
  background-color: black;
}

.box::first-letter {
  color: peru;
  font-size: 45px;
}

input::placeholder {
  color: rgb(84, 84, 88);
}
```

### 💬 Selectors Practiced in the Commented Code

These were tested and then commented out. Uncomment each one to see the effect.

<table>
  <tr>
    <th>Selector</th>
    <th>What it matches in this HTML</th>
  </tr>
  <tr>
    <td><code>.box:first-child</code></td>
    <td>The first <code>.box</code> only.</td>
  </tr>
  <tr>
    <td><code>.box::first-line</code></td>
    <td>The first rendered line of text in each box.</td>
  </tr>
  <tr>
    <td><code>.boxes *</code></td>
    <td><b>Every</b> descendant of <code>.boxes</code>, including the input.</td>
  </tr>
  <tr>
    <td><code>[data-color="primary"]</code></td>
    <td>Any element with that attribute. No element in this HTML has it, so it matches nothing until you add <code>data-color="primary"</code>.</td>
  </tr>
  <tr>
    <td><code>.box:nth-child(odd)</code></td>
    <td>The 1st and 3rd boxes (children 1 and 3). The input is child 4.</td>
  </tr>
  <tr>
    <td><code>.box:nth-last-child(2)</code></td>
    <td>The <b>3rd box</b>, because counting from the end the input is last and the third box is second to last.</td>
  </tr>
</table>

### 🧠 Good to Know

<table>
  <tr>
    <td>💡</td>
    <td><b>Double vs single colon:</b> <code>::</code> is for pseudo-<b>elements</b> (parts of an element), while <code>:</code> is for pseudo-<b>classes</b> (states or positions like <code>:hover</code>, <code>:first-child</code>).</td>
  </tr>
  <tr>
    <td>💡</td>
    <td><code>::before</code> and <code>::after</code> <b>do nothing without the <code>content</code> property</b>, even if it is just <code>content: ""</code>.</td>
  </tr>
  <tr>
    <td>💡</td>
    <td>Generated content is purely visual. It can't be selected as normal text and shouldn't carry important information.</td>
  </tr>
  <tr>
    <td>💡</td>
    <td><code>::selection</code> only allows a few properties, such as <code>color</code> and <code>background-color</code>.</td>
  </tr>
  <tr>
    <td>💡</td>
    <td>Pseudo-elements are not counted as children by <code>:nth-child()</code>.</td>
  </tr>
</table>

### 🔬 Try It Yourself

<details>
<summary><b>Click to expand the experiment steps</b></summary>

<br>

1. Select text on the page with your mouse and see the black background with aqua text from `::selection`.
2. Remove the `content` line from `.boxes::before` and watch the generated text disappear.
3. Set `content: ""` and give the pseudo-element a `display: block`, `width`, `height`, and background to make a decorative shape.
4. Change `.box::first-letter` to `.box::first-line` and see the whole first line styled.
5. Uncomment `.box:nth-child(odd)` and then `.box:nth-last-child(2)` and compare which boxes are highlighted.
6. Add `data-color="primary"` to one box, uncomment the attribute selector, and check that only that box changes.
7. Try `.box:not(:first-child)` to select every box except the first.

</details>

---

## 🚀 How to Run

No installation needed.

```bash
# 1. Clone the repository
git clone https://github.com/<your-username>/<your-repo-name>.git

# 2. Move into the project
cd <your-repo-name>

# 3. Open any project in your browser
open 12-modern-layout/index.html      # macOS
start 12-modern-layout/index.html     # Windows
xdg-open 12-modern-layout/index.html  # Linux
```

💡 **Tip:** Use the VS Code **Live Server** extension to see changes instantly as you edit.

---

## 🎓 Key Takeaways

<table>
  <tr>
    <td>✅</td>
    <td><code>position: sticky</code> with <code>top: 0</code> and a <code>z-index</code> makes a reliable, always-visible navbar.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td><code>flex-wrap: wrap</code> and <code>gap</code> make a flexible row of boxes that adapts to the screen.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>An <code>absolute</code> child needs a <code>relative</code> parent to be anchored where you expect.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Floated elements leave normal flow, so parents collapse. Use <code>display: flow-root</code> to fix it.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td><code>clear: both</code> pushes an element below any floats.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td><code>:nth-child()</code> counts <b>every</b> sibling, not just the ones with a matching class.</td>
  </tr>
  <tr>
    <td>✅</td>
    <td>Pseudo-elements add visual details without extra HTML, but they always need <code>content</code>.</td>
  </tr>
</table>

---

## 🗺️ Roadmap

- [x] `display` property
- [x] Viewport units and box model
- [x] CSS specificity
- [x] `overflow`
- [x] Lists and `list-style`
- [x] `box-shadow` and `text-shadow`
- [x] Positioning (`relative`, `absolute`, `fixed`, `sticky`)
- [x] Card component
- [x] Media queries
- [x] CSS variables
- [x] Landing page project
- [x] Float and clear
- [x] Pseudo-elements and advanced selectors
- [x] Full page layout with sticky navbar
- [ ] Flexbox in depth
- [ ] CSS Grid in depth
- [ ] Keyframe animations
- [ ] Mobile-first workflow

---

<div align="center">

### ⭐ If you found this helpful, consider giving the repo a star!

Made with ❤️ while learning CSS

</div>
