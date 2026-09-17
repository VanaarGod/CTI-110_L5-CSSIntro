# CTI-110 L5 — CSS Intro

Welcome to your fifth web development assignment! You've built pages with structure and semantics — now it's time to make them look good. In this exercise, you'll pick a color palette, link an external stylesheet to your HTML page, and use CSS selectors to style your semantic elements.

## Step 1: Create Your Repository

1. Go to [GitHub](https://github.com) and log in.
2. Click **New repository**.
3. Name your repository exactly:
   ```
   CTI-110_L5-CSSIntro
   ```
4. Set the repository to **Public**
5. Check the box to **Add a README file**.
6. Click **Create repository**.

## Step 2: Clone Your Repository into VS Code

1. Open VS Code.
2. Click Clone Git Repository
3. Select your repository in the dropdown at the top of your screen.
4. Save it within a "GitHub" folder on your computer.
5. When prompted, click **Open** to open the cloned repository folder in VS Code.

> ‼️If you haven't already, navigate to your Extensions Store in VS Code and install "Live Server." You'll know you've found the right one if it has over 81,000,000 downloads!

## Step 3: Create Your Files

1. In the VS Code file explorer (left sidebar), create a new file named:
   ```
   index.html
   ```
2. Create a second new file named:
   ```
   styles.css
   ```
3. On the very first line of `index.html`, type `!` and then press the **Tab** key to generate the HTML boilerplate.
4. Update the `<title>` tag inside the `<head>` section with your **First and Last name**.

## Step 4: Choose Your Topic

Pick a topic of your choice for your page. You'll be building a new semantic page structure to style in this assignment.

## Step 5: Build Your Page with Semantic HTML

Just like L4, build your `<body>` using semantic elements — **no `<div>` tags allowed**:

- **`<header>`** with an `<h1>`
- **`<nav>`** with a list of links
- **`<main>`** wrapping your primary content
  - At least **two** `<section>` elements
  - At least **one** `<article>` element
  - An **`<aside>`** element
- **`<footer>`**

## Step 6: Pick a Color Palette from Colormind

1. Go to [colormind.io](https://colormind.io/bootstrap).
2. Click the palette generator and find a set of 5 colors you like for your topic.
3. Click the LOCK icon to lock down a color you like to prevent it from being lost on the reroll. 
4. Click on each color swatch to reveal its **hex code** (e.g., `#2E3440`).
5. Write down all 5 hex codes — you'll be using them in your CSS.

> ‼️A good rule of thumb: pick one color for your background, one or two for text, one for accents/links, and one for borders or highlights.
> ‼️Use CTRL+/ to toggle commenting on a line of code.

## Step 7: Link Your Stylesheet

Inside the `<head>` section of your `index.html`, add a `<link>` tag to connect your CSS file:

```html
<link rel="stylesheet" href="./styles.css">
```

> ‼️This tag must go inside `<head></head>`, not `<body></body>`. If your styles aren't showing up, this is the first thing to check — along with making sure `styles.css` is spelled exactly the same in both places.

## Step 8: Add Classes and IDs to Your HTML

Before you can style specific elements, you need to give them "hooks" for CSS to grab onto:

- A **class** (`class="..."`) is for styling a *group* of elements the same way. Classes can be reused on as many elements as you want.
- An **ID** (`id="..."`) is for styling *one specific, unique* element on the page. An ID should only be used once per page.

Example:

```html
<section class="topic-section">
  <h2 id="main-heading">Why I Love Hiking</h2>
  <p class="topic-section">Hiking gets me outside and off my screens.</p>
</section>
```

Add at least **3 classes** and **2 IDs** somewhere across your page's elements.

## Step 9: A Short Tutorial — CSS Selectors and Specificity

CSS works by **selecting** an HTML element and telling it how to look. Here are the three selector types you'll use in this assignment:

| Selector | Syntax | Targets |
|---|---|---|
| Element selector | `p { }` | Every `<p>` tag on the page |
| Class selector | `.topic-section { }` | Every element with `class="topic-section"` |
| ID selector | `#main-heading { }` | The one element with `id="main-heading"` |

Notice the punctuation: classes are written with a **period** (`.`) in front of them in your CSS, and IDs are written with a **pound sign / hashtag** (`#`) in front of them.

**Specificity** is the rulebook CSS uses when more than one rule tries to style the same element. From weakest to strongest:

1. **Element selectors** are the weakest (`p { color: blue; }`)
2. **Class selectors** beat element selectors (`.topic-section { color: red; }`)
3. **ID selectors** beat both (`#main-heading { color: green; }`)

So if a `<p class="topic-section" id="main-heading">` has all three rules above applied to it, the text will end up **green** — the ID selector wins because it's the most specific.

> ‼️A common bug: you write a CSS rule and nothing changes. Before assuming CSS is broken, check whether a more specific selector elsewhere is overriding you.

## Step 10: Style Your Page

In `styles.css`, use your Colormind hex codes to style your page. For this assignment, **only use the following properties** — we haven't covered the box model yet, so hold off on anything not in this list:

- `color`
- `background-color`
- `font-family`
- `font-size`
- `border`
- `padding`
- `margin`
- `a:hover`
- `a:visited`
- `opacity`
- `height`
- `width`

Example:

```css
body {
  background-color: #2E3440;
  font-family: Arial, sans-serif;
}

.topic-section {
  color: #ECEFF4;
  font-size: 18px;
  padding: 10px;
  margin: 15px;
  border: 2px solid #88C0D0;
}

#main-heading {
  color: #A3BE8C;
}

a {
  color: #EBCB8B;
}

a:hover {
  opacity: 0.7;
}

a:visited {
  color: #B48EAD;
}
```

> ‼️`a:hover` changes how a link looks while your mouse is over it. `a:visited` changes how a link looks after you've already clicked it once. Both go directly in your CSS file — no extra HTML needed.

## Step 11: Add Your Images

Make sure your page includes **2+ images**, each with an `alt` attribute. Use `height` and `width` in your CSS to control their size (no box model properties yet, so keep it simple).

## Step 12: Test Your Page

Test your site using the **Live Server** extension:

1. Right-click your `index.html` file in the VS Code file explorer.
2. Select **"Open with Live Server."**
3. Confirm your colors, fonts, and hover/visited link styles are all showing up correctly in the browser tab that opens.

## Step 13: Submit Your Work with Git

Once your page looks correct, submit it using Git:

1. Open a new **Terminal** in VS Code.
2. Run the following commands one at a time:

```bash
git add .
git commit -m "COMMIT MESSAGE GOES HERE"
git push
```

> ‼️Replace `"COMMIT MESSAGE GOES HERE"` with a short, descriptive message about what you did (e.g. `"Completed CSS Intro assignment"`).

## Step 14: Publish Your Site with GitHub Pages

Once your work is pushed to GitHub, turn your repository into a live website:

1. On GitHub, go to your `CTI-110_L5-CSSIntro` repository page.
2. Click the **Settings** tab.
3. In the left sidebar, click **Pages**.
4. Under **Build and deployment**, set the **Source** to **Deploy from a branch**.
5. Under **Branch**, select **main** (or **master**) and keep the folder set to **/ (root)**.
6. Click **Save**.
7. Wait a minute or two, then refresh the Pages settings screen. GitHub will display a link like:
   ```
   https://your-username.github.io/CTI-110_L5-CSSIntro/
   ```
8. Click the link to view your live site.

> ‼️Every time you `git push` new changes, GitHub Pages will automatically update your live site within a minute or two.

> ‼️GitHub Pages defaults to render your README.md file unless it finds an "index.html" file in the root folder. Always make sure your home page is set to "index.html"! This is case sensitive.

---

### Checklist Before You Submit
- [ ] Repository `CTI-110_L5-CSSIntro` created on GitHub
- [ ] Repository cloned into VS Code
- [ ] `index.html` and `styles.css` files created inside the cloned repo
- [ ] HTML boilerplate generated with `!` + `Tab`
- [ ] `<title>` updated with your First and Last name
- [ ] Page built with semantic elements (`header`, `nav`, `main`, `section` x2, `article`, `aside`, `footer`) — **no `<div>` tags**
- [ ] `./styles.css` properly linked inside `<head>` with a `<link>` tag
- [ ] Color palette generated from colormind.io with 5 hex codes recorded in the styles.css file (commented out)
- [ ] At least 3 classes and 2 IDs added to HTML elements
- [ ] CSS written using only: `color`, `background-color`, `font-family`, `font-size`, `border`, `padding`, `margin`, `a:hover`, `a:visited`, `opacity`, `height`, `width`
- [ ] Colormind hex codes actually implemented in the CSS
- [ ] At least 2 images included, sized using `height`/`width`
- [ ] Page tested with Live Server and styles confirmed working
- [ ] Work committed and pushed with Git commands in the VS Code Terminal
- [ ] GitHub Pages enabled in repository Settings
- [ ] Live site link verified and working
- [ ] ‼️YOU MUST SUBMIT CLICKABLE LINKS TO YOUR GITHUB REPOSITORY AND YOUR LIVE SITE THROUGH GITHUB PAGES. 2 LINKS. BOTH CLICKABLE OR YOU WILL RECEIVE A ZERO.
