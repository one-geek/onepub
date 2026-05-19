# onepub

Public-hosted release assets for distribution.

## Why this exists

Example: iOS OTA installs via `itms-services` must download both `manifest.plist` and the IPA over anonymous HTTPS.

Private GitHub release asset URLs require authentication (cookies or token). Private repo required those credentials, so requests to private assets typically fail with `401/403` (or `404`, depending on endpoint behavior).

## Possible alternatives

Host OTA artifacts on a public HTTPS endpoint, for example:

- Cloudflare R2
- Amazon S3 (public object URLs or CDN fronted)
- Azure Static Web Apps
- Azure Blob Storage
- Any other public HTTPS host or CDN
- Public Supabase buckets // may still be blocked by RLS/project policy 

## Notes

For now this is perfect as a public repository

### Build and Artifact Storage (GitHub Actions & Packages)

For automated builds and compiled assets, GitHub provides shared storage across GitHub Actions and GitHub Packages based on your plan:

- GitHub Free: 500 MB
- GitHub Pro: 2 GB
- GitHub Team: 2 GB
- GitHub Enterprise: 50 GB