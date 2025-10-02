# Portfolio Website

A modern, single-page portfolio website built with React, TypeScript, and Vite.

## 🚀 Deployment

This site is automatically deployed to GitHub Pages when changes are pushed to the `main` branch.

**Live Site:** https://madhan-kumar-b.github.io/madhan.github.com/

### Automatic Deployment

The site uses GitHub Actions for continuous deployment:
- Push to `main` branch triggers automatic build and deployment
- Workflow builds the Vite app and deploys to GitHub Pages
- Deployment status can be viewed in the Actions tab

### Manual Deployment

To manually trigger deployment:
1. Go to the Actions tab in GitHub
2. Select "Deploy to GitHub Pages" workflow
3. Click "Run workflow"

## 🛠️ Local Development

### Prerequisites
- Node.js 20 or higher
- npm

### Setup

1. Clone the repository:
```bash
git clone https://github.com/madhan-kumar-b/madhan.github.com.git
cd madhan.github.com
```

2. Install dependencies:
```bash
npm install
```

3. Run development server:
```bash
npm run dev
```

4. Build for production:
```bash
npm run build
```

## 📦 Tech Stack

- **Frontend:** React with TypeScript
- **Build Tool:** Vite
- **Styling:** Tailwind CSS
- **UI Components:** shadcn/ui (Radix UI primitives)
- **Animations:** Framer Motion
- **Backend:** Express.js (for API routes)
- **Database:** PostgreSQL with Drizzle ORM

## 📝 Configuration

The deployment workflow is configured in `.github/workflows/deploy.yml`.

### GitHub Pages Settings

To enable GitHub Pages deployment:
1. Go to repository Settings → Pages
2. Under "Build and deployment", select "GitHub Actions" as the source
3. The workflow will handle the rest automatically

## 🔧 Build Output

- Frontend build outputs to `dist/public`
- Server build outputs to `dist`

## 📄 License

MIT
