# robots.txt — Stellan Eoin Builders
# Deploy at site root: https://www.stellaneoin.com/robots.txt
# Goal: let search + AI crawlers read all public content; block Joomla system paths and utility pages.

User-agent: *
Allow: /

# Joomla system / non-public paths
Disallow: /administrator/
Disallow: /api/
Disallow: /bin/
Disallow: /cache/
Disallow: /cli/
Disallow: /components/
Disallow: /includes/
Disallow: /installation/
Disallow: /language/
Disallow: /layouts/
Disallow: /libraries/
Disallow: /logs/
Disallow: /modules/
Disallow: /plugins/
Disallow: /tmp/
Disallow: /index.php?

# Utility / low-value pages (also noindex these in-page)
Disallow: /login
Disallow: /forgot-password
Disallow: /component/tags/
Disallow: /*?view=
Disallow: /*&Itemid=

# Allow rendering assets (needed for Google to fairly render/score the page)
Allow: /templates/
Allow: /media/
Allow: /*.css$
Allow: /*.js$
Allow: /*.webp$
Allow: /*.png$
Allow: /*.jpg$
Allow: /*.svg$

# AI / answer-engine crawlers — explicitly welcomed (GEO/AEO is a goal)
User-agent: GPTBot
Allow: /

User-agent: OAI-SearchBot
Allow: /

User-agent: ChatGPT-User
Allow: /

User-agent: ClaudeBot
Allow: /

User-agent: Claude-User
Allow: /

User-agent: PerplexityBot
Allow: /

User-agent: Google-Extended
Allow: /

User-agent: Applebot-Extended
Allow: /

# Sitemap
Sitemap: https://www.stellaneoin.com/sitemap.xml
