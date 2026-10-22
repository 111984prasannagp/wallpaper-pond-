# Security Policy

## Reporting a vulnerability

Do not publish credentials, session tokens, or exploitable details in a public issue. Contact the repository owner privately with reproduction steps and impact.

## Deployment checklist

- Set a unique, long ADMIN_PASSWORD as a server-side environment variable.
- Never commit real environment files, API keys, admin passwords, or session tokens.
- Serve the site and API over HTTPS.
- Use a Node-capable host for the Express API; static hosting alone cannot persist uploads.
- Use persistent object storage for production wallpaper uploads and configure backups.
- Review upload limits, allowed file types, and abuse protection before public launch.
