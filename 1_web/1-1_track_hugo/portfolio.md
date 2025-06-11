# 4. Portfolio Lab — Build a Personal Website Without Code

> 🎯 **Goal**  
> In this lab, you’ll build a beautiful, professional-looking personal website using the **Paige** theme for Hugo — no coding, no design skills, no stress.

You’ll:

- Set up your Hugo project
- Choose and apply a theme
- Add your profile picture and a banner image
- Customize your name, bio, and social media links
- Preview your site live in a browser

Let’s get started.

---

## 4.1 What is the Paige Theme?

**Paige** is a minimalist and elegant theme for Hugo. It focuses on simplicity, fast loading, and a great mobile experience.

✅ **Why use it for your portfolio?**

- It comes with a **homepage** and content structure built in — no need to design anything from scratch
- It supports **social media icons** in the top-right corner (LinkedIn, GitHub, email, etc.)
- You can use **images** (like your background banner and avatar) to personalize it
- You only need to edit **Markdown** and one small configuration file (`config.toml`)

🔗 Demo: [https://themes.gohugo.io/themes/paige](https://themes.gohugo.io/themes/paige)

---

## 4.2 Set Up Your Hugo Site

Let’s set up the Hugo site and install the Paige theme.

### Step 1: Create a new Hugo site

---

In your terminal, run:

```bash
hugo new site my-portfolio
cd my-portfolio
```

This creates a new folder called `my-portfolio` with the Hugo folder structure.

### Step 2 : Add the Paige theme

---

We'll add the Paige theme from GitHub using Git:

``` bash
git init
git submodule add git@github.com:willfaught/paige.git themes/paige
```

!!! tip "Reminder"

    A Git submodule is a way of including another Git repository inside your project. This lets you keep the theme up to date easily.

### Step 3 : Copy example content

---

The theme comes with example content (Markdown pages and configuration) that we'll use as a starting point:

``` bash
cp -r themes/paige/example/* .
```

> Now your project has some real content and a working layout.

## 4.3 Add Your Images

### 🎨 What You Need:

---

* A **background image** that represents you or your style (e.g. landscape, city, abstract)

* A **profile photo** (preferebly square)

### ✅ Where to place them:

---

1. Save your backgroun image as:

```
static/images/bg.jpg
```
---

2. Save your avatar/profile picture as:

```
static/images/avatar.jpg
```
---

!!! tip "Reminder"

    The `static/` folder is where you put any images or assets you want to appear on your website exactly as-is.

---

## 4.4 Customize the Site Content

Now let's make the website yours!

### Step 1 : Edit your homepage content

---

Open this file in your code editor: `content/_index.md`.

At the top, you'll see the front matter (a section between `+++` symbols):

``` toml
+++
title = "Hi, I'm [Your Name]"
description = "Short description or tagline about you"
keywords = ["portfolio", "developer", "hugo"]
+++
```

Update the following informations:
- `title` with your name or greeting
- `description` with a one-liner about who you are or what you do

Then scroll down and look for the **image shortcodes**.

### Step 2 : Replace the banner image

---

Find and replace the hero image shortcode with this:

``` markdown
{{< paige/image
     src="images/bg.jpg"
     alt="Banner"
     width="100%"
     height="20rem"
     class="object-fit-cover rounded-4 shadow"
     breakpoints="true"
     fetchpriority="high"
     loading="eager"
>}}
```

> This tells Hugo to show your custom banner image across the top of your site.

### Step 3 : Add your profile picture

---

Below that, paste this shortcode to show your circular profile image:

``` markdown
{{< paige/image
     src="images/avatar.jpg"
     alt="Profile"
     width="8rem"
     height="8rem"
     class="rounded-circle shadow d-block mx-auto mt-n6"
     loading="lazy"
>}}
```
> This will place your profiule image on top of the banner - giving your site a bold, modern personal touch.

!!! hint "Note"

    If you want the avatar higher or lower, tweak the `mt-n6` to `mt-n4` or `mt-n8` (that’s margin-top negative spacing).


### Step 4 : Add a short intro below the image

---

You can use regular Markdown:

``` markdown
### Hello! 👋

I'm a curious developer and lifelong learner, building fast and clean web experiences.
```

Obviously, you can tweak to your own preferences. Up to you!

## 4.5 Add Your Social Icons

We'll now add GitHub, LinkedIn, and email icons that appear at the **top right of your site**.

### Step 1 : Open `hugo.toml`

---

This file controls global settings for your site.

Find (or add) th esection for menu.main and add:

``` toml
[[menu.main]]
  name   = ""
  url    = "https://github.com/YOUR-USERNAME"
  weight = 1
  pre    = "<i class='bi bi-github fs-4'></i>"

[[menu.main]]
  name   = ""
  url    = "https://linkedin.com/in/YOUR-LINKEDIN"
  weight = 2
  pre    = "<i class='bi bi-linkedin fs-4'></i>"

[[menu.main]]
  name   = ""
  url    = "mailto:you@example.com"
  weight = 3
  pre    = "<i class='bi bi-envelope fs-4'></i>"
```

> These are Bootstrap icons already supported by the Paige theme. The icons will appear neatly on the top-right of your site.

You can add more icons for other social platforms if you like - check the [Bootstrap Icons](https://icons.getbootstrap.com) site for names.

## 4.6 Preview Your Site in the Browser

You're ready to view your site!

In your terminal:

``` bash
hugo server
```

Then open your browser and go to:

    http://localhost:1313

> Or whatever is printed in the terminal once you run the `hugo server` command.


**🎉 You should now see:**

* Your custom background image
* Your profile photo, overlaid on the banner
* Your name and bio
* Social media icons (GitHub, LinkedIn, Email) in the top-right

!!! hint "Reminder"

    Hugo will automatically reload your browser as you edit files - so you can keep tweaking and see updates in real time.

## 4.7 What You Built

You just created a clean, professional site using:

* Zero HTML (ew), CSS (ewwwwww), or JS (ewwwwwwwwwwww brother)
* Just Markdown, images, and a config file
* A modern, mobile-ready (THAT IS CRAZY IF YOU KNOW WHAT IT IMPLIES) Hugo theme.

This is now your web presence - and it already looks amazing.