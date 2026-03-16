# Pressings App Dashboard

Production management dashboard for the Pressings app with Vercel & Sentry integration.

## Features

- 🚀 **Vercel Integration**: Deployment status, build history, bandwidth tracking
- 🐛 **Sentry Monitoring**: Error tracking, issue count, performance metrics
- 📊 **Business Metrics**: Revenue, conversions, user growth (placeholder for your analytics)
- ⚡ **Real-time Updates**: Auto-refresh every 2 minutes
- 🎨 **Dark/Light Mode**: Persisted theme preference
- 📱 **Mobile Responsive**: Works on all devices

## Setup

### 1. Configure Vercel API

1. Go to https://vercel.com/account/tokens
2. Create a new token with read access
3. Click **⚙️ Configure APIs** in the dashboard
4. Enter:
   - **Vercel Token**: Your API token
   - **Vercel Project ID**: Find in your project settings (e.g., `prj_xxxxx`)

### 2. Configure Sentry API

1. Go to https://sentry.io/settings/account/api/auth-tokens/
2. Create a new auth token with `project:read` and `event:read` scopes
3. Enter in dashboard:
   - **Sentry Auth Token**: Your auth token
   - **Sentry Project**: Format `org-name/project-name`

### 3. Add Analytics (Optional)

To track revenue and business metrics:
- Modify the `loadDashboard()` function to fetch from your analytics endpoint
- Update the business metrics section with real data

## API Endpoints Used

**Vercel API:**
- `GET /v9/projects/{projectId}/deployments` - Recent deployments
- `GET /v6/deployments/{deploymentId}` - Deployment details

**Sentry API:**
- `GET /api/0/projects/{org}/{project}/issues/` - Error tracking
- `GET /api/0/projects/{org}/{project}/stats/` - Performance metrics

## Customization

All configuration is stored in localStorage:
- `pressings_vercel_token`
- `pressings_vercel_project`
- `pressings_sentry_token`
- `pressings_sentry_project`
- `pressings_theme` (dark/light)

## Security Notes

- API tokens are stored in browser localStorage (client-side only)
- For production, consider using a backend proxy to avoid exposing tokens
- Never commit tokens to git

## Next Steps

1. Configure your API tokens
2. Connect analytics for business metrics
3. Customize the metrics you want to track
4. Set up alerts for critical errors

---

Built with ❤️ for Pressings App monetization tracking
