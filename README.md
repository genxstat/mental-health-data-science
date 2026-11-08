# Mental Health Data Science with Melanie Wall

Source for the blog at <https://genxstat.github.io/mental-health-data-science/>, built with [Quarto](https://quarto.org).

## Writing a new post

1. Make a folder named for the date and a short slug, e.g. `2026/11/15/my-new-post/`, so it sits alongside the older posts and keeps the same URL style.
2. Inside it, create `index.qmd`:

   ````markdown
   ---
   title: "My new post"
   date: 2026-11-15
   categories: [R, methods]
   ---

   Some text.

   ```{r}
   summary(lm(mpg ~ wt, data = mtcars))
   ```
   ````

3. Preview it in RStudio (**Render** button) or from a terminal: `quarto preview`.
4. Commit and push. If the post runs R code, also commit the `_freeze/` folder that rendering creates. That way GitHub doesn't need R to rebuild the site.

GitHub Actions rebuilds and publishes the site on every push to `main` (see `.github/workflows/publish.yml`). It takes about a minute.

## Layout

- `_quarto.yml`: site settings (title, navbar, theme)
- `index.qmd`: home page listing of all posts, with categories and an RSS feed (`index.xml`)
- `about-me/index.qmd`: About page
- `YYYY/MM/DD/slug/index.qmd`: posts (same URLs as the old WordPress blog)
- `wp-content/uploads/`: original images, slides and documents from the WordPress blog, kept at their old addresses
- `styles.css`: small style tweaks
