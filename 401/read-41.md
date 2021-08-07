## Next.js - Deployment

**Next.js and Vercel**

- Vercel is made by the creators of Next.js and has first-class support for Next.js. When you deploy your Next.js app to Vercel, the following happens by default:

1. Pages that use Static Generation and assets (JS, CSS, images, fonts, etc) will automatically be served from the Vercel Edge Network, which is blazingly fast.
2. Pages that use Server-Side Rendering and API routes will automatically become isolated Serverless Functions. This allows page rendering and API requests to scale infinitely.

Vercel has many more features, such as:

- Custom Domains: Once deployed on Vercel, you can assign a custom domain to your Next.js app.
- Environment Variables: You can also set environment variables on Vercel.
- Automatic HTTPS: HTTPS is enabled by default (including custom domains) and doesn't require extra configuration. We auto-renew SSL certificates.

**Develop, Preview, Ship**

- **Develop**: We’ve written code in Next.js and used the Next.js development server running to take advantage of its hot reloading feature.
- **Preview**: We’ve pushed changes to a branch on GitHub, and Vercel created a preview deployment that’s available via a URL. We can share this preview URL with others for feedback. In addition to doing code reviews, you can do deployment previews.
- **Ship**: We’ve merged the pull request to main to ship to production.

### **Deploy to Vercel**

The easiest way to deploy Next.js to production is to use the Vercel platform developed by the creators of Next.js.

1. Create a Vercel Account

2. Import your repository

3. Install Vercel for GitHub.
*You can give it access to All Repositories.*

Once you’ve installed Vercel, import your repo.

- You can use default values for the following settings — no need to change anything. Vercel automatically detects that you have a Next.js app and chooses optimal build settings for you.
