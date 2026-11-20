# Deploy this project overview to Vercel (see also DEPLOY.md for Render)

This repository currently contains documentation and a project overview page. It does not contain the NestJS microservices, Kong configuration, Docker Compose setup, or a working food-ordering frontend/backend.

## Deploy

1. Push the contents of this `food-delivery` folder to a GitHub repository.
2. In Vercel, choose **Add New → Project** and import that repository.
3. Set **Root Directory** to `./` if this folder is the repository root. If the repository contains this folder inside another folder, set Root Directory to `food-delivery`.
4. Framework Preset: **Other**.
5. Build Command: leave empty.
6. Output Directory: leave empty (or `.` if the dashboard requires a value).
7. Install Command: leave empty.
8. Click **Deploy**. Vercel serves the root `index.html` as a static site.

## Important

This deployment publishes the project overview and links to the Markdown documentation. It does not run the backend architecture. To deploy the actual food delivery system, implement the NestJS services and infrastructure described in `README.md`, then host the long-running services and message broker on suitable backend/container infrastructure. A Vercel deployment URL returning `404 DEPLOYMENT_NOT_FOUND` is a missing/invalid deployment URL; after a successful deployment, use the URL shown on the latest **Ready** deployment in the Vercel dashboard.
