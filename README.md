# Breeze.bio
A runnable early-stage profile host with Node.js, Express and PostgreSQL. No fixed domain.

## Run
Use Node.js 22+, provision PostgreSQL, set DATABASE_URL, PORT and NODE_ENV=production on your hosting platform, then run npm install and npm start. Production requires HTTPS. Configure the reverse proxy and rate limiting for your hosting topology. For local HTTP omit NODE_ENV=production.

Register your own account, then using your private database console promote it: `UPDATE users SET role='admin' WHERE username='your_username';` Never expose database credentials or make a public promotion endpoint.

Features: password accounts, public profiles, external HTTPS asset URLs, themes, links, daily view counters, badge grants/revocation, bans and audit records. Badge symbols are text, not registered artwork. No uploads, OAuth, password reset, email verification, billing or content reporting yet. External media can reveal visitor IPs to its host; use trusted media only. Add reporting, content moderation, age-appropriate privacy controls, account deletion and recovery before opening public registration.

Scale target: 1 million registered accounts, not 1 million concurrent connections. Indexed PostgreSQL usernames and sessions, daily aggregates and cursor pagination are a starting point. Before production use distributed rate limits, shared object storage with scanning, CDN, connection pooling, backups, monitoring, session expiry cleanup, security review and representative load tests. Capacity is not verified. View counts are approximate and not unique visitors.
