# Deployment Guide

## Setting Up GitHub Pages Deployment

This guide will help you deploy your portfolio website to GitHub Pages using the automated GitHub Actions workflow.

## Prerequisites

Before deployment, ensure:
- You have admin access to the repository
- The repository contains your source code (client, server, shared directories)
- All dependencies are listed in package.json

## Step 1: Enable GitHub Pages

1. Navigate to your repository on GitHub: `https://github.com/madhan-kumar-b/madhan.github.com`
2. Click on **Settings** tab
3. Scroll down to **Pages** section in the left sidebar
4. Under "Build and deployment":
   - **Source**: Select "GitHub Actions" (not "Deploy from a branch")
5. Save the settings

## Step 2: Merge to Main Branch

The deployment workflow is configured to run automatically when code is pushed to the `main` branch.

1. Create a pull request to merge your changes to `main`
2. Review and approve the PR
3. Merge the PR

## Step 3: Monitor Deployment

1. Go to the **Actions** tab in your repository
2. You should see a workflow run called "Deploy to GitHub Pages"
3. Click on the workflow run to see detailed logs
4. Wait for both "build" and "deploy" jobs to complete (usually 2-5 minutes)

## Step 4: Access Your Site

Once deployment is complete, your site will be available at:
- **URL**: `https://madhan-kumar-b.github.io/madhan.github.com/`

You can also find the URL in:
- The Actions workflow run under the "deploy" job
- Repository Settings → Pages

## Troubleshooting

### Build Fails

If the build step fails:
1. Check the workflow logs in the Actions tab
2. Ensure all dependencies are correctly listed in package.json
3. Verify that `npm run build` works locally
4. Check for TypeScript errors or linting issues

### Deployment Fails

If deployment fails but build succeeds:
1. Verify GitHub Pages is enabled in repository settings
2. Check that the source is set to "GitHub Actions"
3. Ensure the workflow has proper permissions (already configured)

### Site Shows 404

If the deployed site shows a 404 error:
1. Wait a few minutes for DNS propagation
2. Verify the build output directory is correct (`dist/public`)
3. Check that the Vite base path is correctly configured

### Manual Deployment

To manually trigger a deployment:
1. Go to the **Actions** tab
2. Click "Deploy to GitHub Pages" workflow
3. Click "Run workflow" button
4. Select the `main` branch
5. Click "Run workflow"

## Configuration Files

The deployment uses these files:
- `.github/workflows/deploy.yml` - GitHub Actions workflow configuration
- `vite.config.ts` - Vite build configuration with base path
- `package.json` - Dependencies and build scripts

## Updating Your Site

Every time you push to the `main` branch, the site will automatically rebuild and redeploy:
1. Make your changes in a feature branch
2. Test locally with `npm run dev`
3. Create a PR to `main`
4. Merge the PR
5. Wait for automatic deployment

## Environment Variables

If your application requires environment variables:
1. Go to Settings → Secrets and variables → Actions
2. Add your secrets (e.g., DATABASE_URL, API keys)
3. Update the workflow to include these secrets in the build step

## Notes

- The workflow uses Node.js 20
- Build artifacts are cached for faster subsequent builds
- Only the frontend (`dist/public`) is deployed to GitHub Pages
- The backend server code is not deployed (GitHub Pages is static hosting only)

For the backend API, consider deploying to:
- Vercel
- Netlify Functions
- Railway
- Heroku
- Any Node.js hosting platform

## Support

If you encounter issues:
1. Check the Actions workflow logs
2. Verify your source code is complete
3. Test the build locally
4. Review the GitHub Pages documentation: https://docs.github.com/en/pages
