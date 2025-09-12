# How to Customize Pages in Your Hugo Project

This guide explains how to customize each page in your Hugo site, including content, layout, and style.

---

## 1. Customize Page Content
- **Location:** `content/<language>/<section>/<page>.md`
- **Action:** Edit the Markdown files to change text, images, front matter (title, description, etc.).
- **Tip:** Use [front matter](https://gohugo.io/content-management/front-matter/) to set custom parameters for each page.

---

## 2. Customize Page Layouts
- **Location:** `layouts/`
- **Action:**
  - Edit `layouts/_default/single.html` for single pages.
  - Edit `layouts/_default/list.html` for list pages.
  - Create or edit `layouts/<section>/single.html` or `list.html` for section-specific layouts.
  - Edit `layouts/index.html` for the homepage.
- **Tip:** Use [Hugo templating](https://gohugo.io/templates/) to control page structure and display custom parameters.

---

## 3. Use Partials and Components
- **Location:** `layouts/partials/`
- **Action:** Edit reusable components (header, footer, widgets, etc.) to change shared elements across pages.
- **Tip:** Call partials in your templates using `{{ partial "<name>" . }}`.

---

## 4. Add Custom Styles and Scripts
- **Location:** `assets/css/`, `assets/js/`
- **Action:** Add or modify CSS and JS files to change the look and behavior of your site.
- **Tip:** Reference custom assets in your templates or via the `head.html` partial.

---

## 5. Advanced Customization
- **Custom Parameters:**
  - Set custom parameters in page front matter and access them in templates with `.Params`.
- **Conditional Layouts:**
  - Use [Hugo's conditional logic](https://gohugo.io/templates/introduction/#conditionals) to display different content/layouts based on page type, section, or parameters.
- **Multilingual Support:**
  - Add content for each language in separate folders and configure languages in your config files.

---

## References
- [Hugo Documentation](https://gohugo.io/documentation/)
- [Content Management](https://gohugo.io/content-management/)
- [Templates](https://gohugo.io/templates/)
- [Multilingual Sites](https://gohugo.io/content-management/multilingual/)

---

**Tip:** After making changes, rebuild your site to see updates.
