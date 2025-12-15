# Setup and Deployment Guide

## Running Locally

To run the Jekyll site locally on your machine:

1. **Install Ruby** (if not already installed)
   - On macOS: Ruby comes pre-installed
   - On Linux: `sudo apt-get install ruby-full` (Ubuntu/Debian)
   - On Windows: Use [RubyInstaller](https://rubyinstaller.org/)

2. **Install Jekyll and dependencies**
   ```bash
   gem install bundler
   bundle install
   ```

3. **Run the local server**
   ```bash
   bundle exec jekyll serve
   ```

4. **View the site**
   - Open your browser and go to: `http://localhost:4000`
   - The site will auto-reload when you make changes

## Deploying to GitHub Pages

### Option 1: Automatic Deployment (Recommended)

1. **Create a GitHub repository**
   - Go to GitHub and create a new repository
   - Name it something like `haensel-gretel-website`

2. **Push your code**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**
   - Go to your repository settings on GitHub
   - Navigate to "Pages" in the left sidebar
   - Under "Source", select "Deploy from a branch"
   - Select branch: `main` and folder: `/ (root)`
   - Click "Save"

4. **Wait for deployment**
   - GitHub will automatically build and deploy your site
   - After a few minutes, your site will be available at:
     `https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/`

5. **Update the URL in _config.yml**
   - Edit `_config.yml` and set:
     ```yaml
     url: "https://YOUR_USERNAME.github.io"
     baseurl: "/YOUR_REPO_NAME"
     ```
   - Commit and push the changes

### Option 2: Custom Domain

If you want to use a custom domain (e.g., www.haensel-gretel.de):

1. Follow steps 1-3 from Option 1
2. In your repository, create a file named `CNAME` with your domain:
   ```
   www.haensel-gretel.de
   ```
3. Configure your domain's DNS settings to point to GitHub Pages
4. Enable "Enforce HTTPS" in GitHub Pages settings

## Folder Structure

```
/
├── _config.yml          # Site configuration
├── _layouts/            # HTML layouts
├── _includes/           # Reusable components (header, footer)
├── assets/
│   ├── css/            # Stylesheets
│   └── images/         # Images
├── pages/              # Additional pages
├── design/             # Design references (not published)
├── index.md            # Homepage
├── Gemfile             # Ruby dependencies
└── README.md           # Content editing guide
```

## Troubleshooting

### Build fails on GitHub
- Check the "Actions" tab in your repository for error messages
- Make sure all file paths are correct
- Verify that `_config.yml` is valid YAML

### Images not showing
- Make sure image paths start with `/assets/images/`
- Check that images are committed to the repository
- Verify image file extensions are correct

### Styling not applied
- Clear your browser cache
- Make sure `assets/css/style.css` exists
- Check browser developer console for errors

## Need Help?

- Jekyll Documentation: https://jekyllrb.com/docs/
- GitHub Pages Documentation: https://docs.github.com/en/pages
