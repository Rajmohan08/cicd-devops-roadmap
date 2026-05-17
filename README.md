# CI/CD DevOps Roadmap Website

A static learning roadmap site for CI/CD and DevOps concepts, hosted on GitHub Pages and mapped to a custom domain.

Live URL
- https://cicd-devops-roadmap.rajmohan.dev/

Repository
- https://github.com/Rajmohan08/cicd-devops-roadmap

## Project Structure
- `index.html` - Main page content
- `styles.css` - Site styling
- `app.js` - Scroll reveal animation logic
- `CNAME` - GitHub Pages custom domain mapping
- `.github/workflows/pages.yml` - GitHub Pages deployment workflow
- `Jenkinsfile` - Starter Jenkins pipeline for release gate workflow

## Hosting and Deployment
This project is hosted on GitHub Pages.

Deploy behavior:
- Push to `main` triggers automatic GitHub Pages deployment.
- No manual deploy command is required for normal updates.

## Custom Domain
Configured domain:
- `cicd-devops-roadmap.rajmohan.dev`

DNS target:
- `rajmohan08.github.io`

## Jenkins and Datadog
The site content now includes:
- Jenkins in the CI/CD roadmap stages and implementation path
- Datadog in the monitoring/observability stages and learning links

`Jenkinsfile` included in this repo provides a starter pipeline that:
- checks required static files
- archives release artifacts
- uses an approval gate for main branch releases

## Local Preview
Open `index.html` directly in your browser, or run a simple local static server.

PowerShell example:
```powershell
cd C:\cicd-devops-roadmap
python -m http.server 8000
```
Then open:
- http://localhost:8000

## License
This project is for learning and portfolio usage.
