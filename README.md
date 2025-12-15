# Website Content Management Guide

This website is built with Jekyll and hosted on GitHub Pages.

## How to Edit Content

### Editing Existing Pages

1. Navigate to the file you want to edit (e.g., `index.md` or files in the `pages/` folder)
2. Click the pencil icon (Edit) on GitHub
3. Make your changes using Markdown syntax
4. Scroll down and click "Commit changes"
5. The website will automatically rebuild (takes 1-2 minutes)

### Adding a New Page

1. Go to the `pages/` folder
2. Click "Add file" → "Create new file"
3. Name your file (e.g., `contact.md`)
4. Add this header at the top:
   ```
   ---
   layout: page
   title: Contact
   permalink: /contact/
   ---
   ```
5. Write your content below the header using Markdown
6. Commit the file

### Adding Images

1. Go to the `assets/images/` folder
2. Click "Add file" → "Upload files"
3. Upload your image(s)
4. In your markdown file, reference the image:
   ```
   ![Image description](/assets/images/your-image.jpg)
   ```

### Adding a Blog Post (Optional)

1. Go to the `_posts/` folder
2. Create a new file named: `YYYY-MM-DD-title.md` (e.g., `2024-01-15-hello-world.md`)
3. Add this header:
   ```
   ---
   layout: post
   title: "Your Post Title"
   date: 2024-01-15
   ---
   ```
4. Write your content below

## Markdown Basics

- `# Heading 1` → Large heading
- `## Heading 2` → Medium heading
- `**bold text**` → **bold text**
- `*italic text*` → *italic text*
- `[Link text](https://example.com)` → Clickable link
- `![Image alt text](/path/to/image.jpg)` → Image

## Folder Structure

- `index.md` - Homepage
- `pages/` - Static pages (About, Contact, etc.)
- `_posts/` - Blog posts (optional)
- `assets/images/` - Upload images here
- `design/` - Design mockups and screenshots (not published)
- `_config.yml` - Site configuration (title, description, etc.)

## Need Help?

If something breaks or you need assistance, contact the site administrator.
