# Etienne Phillips website

Plain HTML and CSS. No installation or build step is required. Open `index.html` in a browser to view the site.

## Quick editing guide

| Change | File |
| --- | --- |
| Biography, recognition, interviews, reading recommendation | index.html |
| Music captions and chart order | music.html |
| CV introduction and displayed pages | cv.html |
| Colors, spacing, typography, phone layout | styles.css |
| Replace the CV | assets/cv.pdf |
| Replace the portrait | assets/portrait.jpg |

The HTML is indented and contains comments identifying editable areas. The sidebar appears in each page: update all three if you change contact details or navigation. The stylesheet is shared, so design changes apply to every page.

### Edit text or links

Open the appropriate HTML file in a text editor, search for the text you want to change, and edit it between the tags. Link destinations are inside `href="..."`; visible labels are between `<a>` and `</a>`. Save and refresh your browser. Keep surrounding tags intact.

### Reorder or add music charts

Each chart is one `<figure> ... </figure>` block. Move the entire block to reorder it. To add a chart, copy a block, give its `id` a unique name, and update both links, the image path, the caption, and the image's alt description. Put the new image in assets/.

Charts have descriptive filenames such as top-albums-2024.png. The all-time top 100 comes first, followed immediately by 2024. Album rankings remain in the original chart images.

### Change the design

The top of styles.css defines the main colors in :root. Mobile layout rules are near the bottom. Each declaration is on its own line.

## Plain CV pages

The CV displays three high-resolution page images, with no viewer toolbar or thumbnails. Screen readers receive extracted document text. The “Download CV PDF” button points to assets/cv.pdf.

When updating your CV, replace assets/cv.pdf and regenerate the page images with Poppler:

```text
pdftoppm -png -r 180 assets/cv.pdf assets/cv-page
```

This command produces cv-page-1.png, cv-page-2.png, and cv-page-3.png. If the page count changes, update the page blocks in cv.html. Update the hidden text in each block for screen readers as well. Ordinary website text edits still require no build step.

## Publish on GitHub Pages

Upload this folder's contents to a repository, with index.html at its root. Configure GitHub Pages to publish the branch's root folder. Relative links allow the site to work under a repository URL. The .nojekyll file is included.

Content was copied from https://sites.google.com/view/ephil on October 6, 2026. Your original website has not been changed.

## Homepage photos

The three original homepage photos are in assets/category-theory-talk.jpg, assets/conference-photo.jpg, and assets/mathematics-event.jpg. Their image tags are in the commented HOMEPAGE PHOTOS section at the end of index.html. Images display fully without cropping.
