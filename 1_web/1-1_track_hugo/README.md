# 1.1 - Track Hugo
## Introduction

Welcome to the Hugo Portfolio Lab! In this lab, you'll create a portfolio website using Hugo, a powerful and flexible static site generator. This portfolio will not only serve as a showcase of your skills and projects but also lay the groundwork for your onboarding journey with the club. This lab will guide you through the process of setting up Hugo, choosing a template, and ultimately building a website that represents your professional self.

If you haven't read the formal introduction to this onboarding series, we recommend starting there. If you're ready and have chosen Hugo as your web development framework, let's proceed!

This lab is structured to accommodate different levels of engagement:

- **Green (Essentials):** 🟢 Read and complete the essential parts to set up your basic website.
- **Yellow (Intermediate):** 🟡 Learn about more advanced concepts and make small customizations.
- **Red (Advanced):** 🔴 Dive deep into Hugo and customize every part of your website.

No matter your level of interest, you'll leave this lab with a working portfolio. The only difference is how deep you decide to explore the Hugo ecosystem.

## Lab Structure

### 1. Getting Started with Hugo

#### 🟢 Introduction to Hugo

- **What is Hugo?**: Hugo is an open-source static site generator designed for speed and simplicity. It is highly suitable for creating lightweight, fast-loading websites.
- **Why Hugo?**: Hugo is renowned for its speed and ease of use, thanks to its foundation in Go. It allows developers to create fast, secure websites by quickly transforming Markdown-based content into static HTML files. With its simple setup, customizable templates, and instant builds, Hugo streamlines the website development process—ideal for blogs, documentation, and any content-driven site.

#### 🟢 Installing Hugo

- **Option 1: Using Docker** (Recommended for Beginners)
  - **Why Docker?**: Docker is a better choice, as it simplifies setup, ensures consistency, and helps build foundational knowledge for later labs. Docker will aslo be used to ultimately deploy your website on the club's infrastructure.
    - Here is a link to the club’s ["Learn Docker" wiki article](https://wiki.omni.cedille.club/onboarding/tracks/learn-docker/) for first timers.
  - **Installation Steps**: Explain the steps to pull an image from the docker hub and run it.
    - pull the docker image of hugo from [Docker Hub](https://hub.docker.com/r/floryn90/hugo)
     ```sh
     docker pull floryn90/Hugo
     ```
    - Run a container with the image
- **Option 2: Native Installation**
  - Provide installation instructions for different operating systems:
    - [Linux Installation Guide](https://gohugo.io/installation/linux/)
    - [Windows Installation Guide](https://gohugo.io/installation/windows/)

### 2. Setting Up Your Site

#### 🟢 Creating Your First Hugo Site

- Run the following commands to get started:
  ```sh
  hugo version
  hugo new site ./ --force
  ```
- **Creating Your Own Repository**: Be sure to create your own repository using the provided template, and remember to set it up in your personal GitHub account, not the club’s organization account. If you need a refresher on GitHub or Git, refer back to the Git track, which is a prerequisite for this module, for detailed guidance and tips.

### 3. Choosing Your Path: Template vs. Custom Theme

#### 🟢 Using an Existing Template (Recommended)

- **Template Introduction**: Starting with an existing template is the easiest way for beginners to get up and running, as it provides a pre-built structure and layout. This lets you focus on content creation rather than design details, making the process smoother and more manageable.
- **Gallery of Themes**: Here is a link to Hugo’s [official themes gallery](https://themes.gohugo.io/).
- **Setup Instructions**:
  - Once you find a theme you like click on it and navigate to its GitHub repository by clicking the download button on hugo's website.
  - Read the readme of the theme.
  - clone the theme's github repository into the 'themes' directory of your website.
  - Open your project’s `config.toml` file.
   - Set the theme by adding (or editing) the line:
     ```toml
     theme = "<the-name-of-your-theme>"
     ```
   - Save the file, then run on your terminal:
   ```bash
   hugo server
   ```
   - Open `http://localhost:1313` in your browser to see your site with the theme applied.
### Summary of Hugo’s File Layout

Hugo uses a well-defined folder structure to separate content, templates, static assets, and other site elements. Here’s a detailed explanation of each folder and its purpose.

| Folder        | Purpose                                                                                              | Key Details                                      |
|---------------|------------------------------------------------------------------------------------------------------|--------------------------------------------------|
| `content/`    | Stores the main content of the website (Markdown files)                                              | Markdown files with front matter metadata        |
| `layouts/`    | Holds templates that control how content is rendered on the site                                     | HTML templates and reusable partials             |
| `static/`     | Stores static files like images, CSS, and JavaScript                                                 | Directly served as-is without processing         |
| `data/`       | Contains structured data files (YAML, TOML, JSON) used throughout the site                           | Useful for configuration and structured content  |
| `assets/`     | Holds files processed by Hugo’s asset pipeline (e.g., SCSS, minified JS, resized images)             | Allows preprocessing of assets before inclusion  |
| `config/`     | Stores site configuration files (`config.toml`, `config.yaml`, etc.)                                 | Defines global site settings and configurations  |
| `themes/`     | Contains theme files if you are using a theme                                                        | Holds templates, styles, and assets for themes   |

---

#### 🟡 Customizing an Existing Template

- **Intermediate Customization**: Guide users on how to make small customizations, such as editing CSS or modifying the layouts to personalize their site further.
- pointwer vers la doc pour voir comment faire  pas un step by step
- **Tips**: Provide links to Hugo's documentation to learn more about customizing templates.

#### 🔴 Creating Your Own Theme from Scratch (Advanced)

- **Warning**: Let users know that building a custom theme is challenging.
  - Provide some background about your club's attempt to do this and what we learned.
  - Explain why we don't recommend it given the challenges we faced with making the UI look good.
- **Basic Setup**: If you are sure you want to continue, walk through the command to create a new theme:
  ```sh
  hugo new theme your-theme-name
  ```
- **Theme Building Blocks**: Introduce users to Hugo-specific concepts, such as shortcodes, archetypes, and layouts.
- **Documentation Links**: Provide links to the appropriate documentation for each concept.

### 4. Content Creation

#### 🟢 Customizing Existing Pages

- **Essential Customizations**: Create the about, porjects and blog pages as well as a navigation bar.
  - Create the following folders inside /content. this folders will have the contents of the about, projects and blog page.
  ```sh
  cd /content
  mkdir projecs about posts
  ```
  - Paste the following into your hugo.toml or config.toml. This will create the navigation bar.
  ``` toml
  [menus]
  [[menus.main]]
    name = 'blog'
    pageRef = '/posts'
    weight = 1
  [[menus.main]]
    name = 'projects'
    pageRef = '/projects'
    weight = 2
  [[menus.main]]
    name = 'About'
    pageRef = '/about'
    weight = 3
  ```
  - To add a content on the different pages you just created follow [this tutorial](https://gohugo.io/getting-started/quick-start/#add-content)
  - **About page**: Introduce yourself. Share who you are, what you do, your background, and what makes you unique. Include a brief bio, mission, and links to social media or contact info.
  - **Blog/Case Studies**: Share articles, updates, and insights. Use the Blog page to connect with your audience by posting tutorials, news, and opinions. Include recent posts and tags!
  - **Projects**: Showcase your work or portfolio. Highlight key projects with a brief description, the technologies used, and the outcomes. Include visuals, links to live demos, or code repositories for extra context.
- **Rebuild and Test**: The hugo web server should reflect the changes done to the website in real time. You can always stop it and restart it if you don't see the changes made in your code.
  Walk through the steps to rebuild the project after changes and verify that the modifications are correct.

#### 🟡 Enhancing Content

  - **Intermediate Customization**: Provide additional ideas for intermediate customizations, such as modifying the layout of a page by moving sections arround, adding new sections, or editing existing components to fit their brand.

#### 🔴 Creating New Pages from Scratch (Advanced)

- **Creating New Pages**: Explain that creating entirely new pages not present in the original template while masterfully staying consistent with the original UI design can be complex and is intended for advanced users. Provide guidance on the basics of creating new page layouts and adding them to the site.
- **Hugo File Structure Deep Dive**: Offer a deeper understanding of the Hugo file structure, including how new content types can be added effectively.

### 5. Acceptance Criteria for Completion

#### 🟢 Minimum Requirements

The minimum requirement is to have the following two pages in ones portfolio website:

- **About**
- **Projects**

#### 🟡 Documenting Your Experience

- **First Blog Post**: Encourage members to write a blog post about their experience building in this training tutorial walking them through making their own Hugo portfolio and learning all the steps needed to eventually deploy it - focusing on what they learn, the challenge they faced and how they resolved them.

### 7. Next Steps

- **DevOps Lab**: After completing the Hugo Lab, the next step will be to set up Continuous Integration and Continuous Deployment (CI/CD) for your website using Docker in the upcoming DevOps Lab. This will automate the build and deployment process, making your site updates faster and more reliable.

- **Foster a Knowledge Transfer Mindset**: Sharing your experiences is valuable for the community. Document the feedback you have about the Hugo Lab, including any challenges or pain points you faced. This will help improve the lab experience for future members and create a stronger foundation for collective learning.


## Conclusion

This multi stage training project is the beginning of your journey with CEDILLE. By the end of this experience, you’ll not only have a portfolio that showcases your skills but also foundational experience in DevOps, SRE, and application development through subsequent labs. Take your time, experiment, and make the most out of it. We’re here to help you slowly get ready for the industry, one project at a time!

---
