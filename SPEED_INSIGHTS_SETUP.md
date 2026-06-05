# Vercel Speed Insights Setup

This project has been configured with Vercel Speed Insights to monitor real-user performance metrics.

## What was installed

- **Package**: `@vercel/speed-insights` (latest version)
- **Integration**: Added to `index.html` in the `<head>` section

## How it works

Speed Insights has been integrated using the official Vercel approach for static HTML sites:

1. A tracking script initialization is added to set up the `window.si` function
2. The Speed Insights script is loaded from `/_vercel/speed-insights/script.js`
3. When deployed to Vercel, this path will automatically resolve to the correct Speed Insights tracking script

## Requirements

For Speed Insights to work properly, you must:

1. **Deploy to Vercel**: The project must be deployed to Vercel's platform
2. **Enable Speed Insights**: In your Vercel dashboard, go to your project settings and enable Speed Insights
3. **Wait for traffic**: After deployment, Speed Insights will start collecting data as users visit your site

## Viewing the data

After deployment and once users start visiting your site:

1. Go to your Vercel dashboard
2. Navigate to your project
3. Click on "Speed Insights" in the sidebar
4. View real-user performance metrics including:
   - Core Web Vitals (LCP, FID, CLS)
   - Page load times
   - Performance scores by device and location

## Local Development

Speed Insights does **not** track data in development mode. The tracking only activates when:
- The site is deployed to Vercel production or preview environments
- Speed Insights is enabled in the Vercel dashboard

## Documentation

For more information, visit:
- [Vercel Speed Insights Quickstart](https://vercel.com/docs/speed-insights/quickstart)
- [Speed Insights Documentation](https://vercel.com/docs/speed-insights)

## Implementation Details

The following code was added to `index.html`:

```html
<!-- Vercel Speed Insights -->
<script>
  window.si = window.si || function () { (window.siq = window.siq || []).push(arguments); };
</script>
<script defer src="/_vercel/speed-insights/script.js"></script>
```

This is the recommended approach from the official Vercel documentation for static HTML sites.
