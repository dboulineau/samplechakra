# GitHub Pages Deployment Guide

## Automatic Deployment (Recommended)

This project is configured for automatic deployment to GitHub Pages using GitHub Actions.

### Setup Steps:

1. **Push to GitHub:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/yourusername/samplechakra.git
   git push -u origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository on GitHub
   - Navigate to Settings → Pages
   - Under "Source", select "GitHub Actions"
   - The workflow will automatically trigger on push to main branch

3. **Access your site:**
   - Your app will be available at: `https://yourusername.github.io/samplechakra/`
   - Replace `yourusername` with your actual GitHub username

## Manual Deployment

If you prefer manual deployment, you can use the gh-pages package:

1. **Build and deploy:**
   ```bash
   npm run deploy
   ```

2. **Enable GitHub Pages (if not already done):**
   - Go to repository Settings → Pages
   - Under "Source", select "Deploy from a branch"
   - Select "gh-pages" branch and "/ (root)" folder

## Important Notes

- The `base` path in `vite.config.ts` is set to `/samplechakra/` for production
- Change this to match your repository name if different
- The app will work locally with `npm run dev` regardless of the base path setting
- GitHub Actions workflow requires Pages to be enabled in repository settings

## Troubleshooting

- **404 errors:** Make sure the base path in `vite.config.ts` matches your repository name
- **Blank page:** Check browser console for path-related errors
- **Build fails:** Ensure all dependencies are properly installed and TypeScript compiles without errors

## Custom Domain

To use a custom domain:
1. Add a `CNAME` file to the `public/` directory with your domain name
2. Configure DNS settings at your domain provider
3. Enable custom domain in GitHub Pages settings
