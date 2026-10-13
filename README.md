# Efe Lorasdagi's academic homepage

A lightweight, responsive personal website for GitHub Pages. No build system or dependencies.

Live site: https://lorasdagi.com/

GitHub address: https://mefe06.github.io/ (redirects to the custom domain).

## Updating the site

- Edit `index.html` to change biography, research interests, updates, and experience.
- Edit `style.css` to change the appearance.
- The homepage is intentionally photo-free for now.
- Replace `assets/cv.pdf` with a current public CV. Keep private contact information out of the public copy.
- Update the footer date when making content changes.

The homepage is intentionally concise. Publication details are available through Google Scholar and the linked CV.

## GitHub Pages

Repository: `mefe06/mefe06.github.io`.

In repository **Settings → Pages**, select **Deploy from a branch**, **main**, and **/(root)**. This site uses plain HTML and CSS; `.nojekyll` disables Jekyll processing.

## Domain connection

You can replace the WordPress site at `lorasdagi.com`, or keep it and use a separate subdomain such as `research.lorasdagi.com` for this site. The site is configured to use `lorasdagi.com`.

1. Verify domain ownership in your GitHub account's Pages settings, using the TXT record GitHub provides.
2. Add the chosen custom domain in this repository's **Settings → Pages** before changing DNS.
3. At your DNS provider, use the appropriate configuration below. Preserve mail-related records.
4. Enable **Enforce HTTPS** in Pages settings when the certificate is ready.
5. Update the canonical URL and `og:url` in `index.html` to the chosen domain.

### Keep the current site; add a research subdomain

| Type | Name | Value |
| --- | --- | --- |
| CNAME | research | mefe06.github.io |

Set the GitHub Pages custom domain to `research.lorasdagi.com`. This leaves the root WordPress site in place.

### Replace the current root site

Set the GitHub Pages custom domain to `lorasdagi.com`. Replace the existing root web-hosting records with:

| Type | Name | Value |
| --- | --- | --- |
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | mefe06.github.io |

Remove conflicting root web-hosting A/AAAA records only when switching hosts. Do not remove unrelated DNS records. Domain configuration may take up to 24 hours to propagate. GitHub redirects the github.io address to the configured custom domain.

Official instructions: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site

## Existing hosting services

HayalHost retains the existing WordPress installation and mail services. The root and `www` website records point to GitHub Pages. `mail.lorasdagi.com` has a direct A record to the existing HayalHost server, and the domain MX record targets that mail hostname. Calendar/contact discovery records use the existing dedicated HayalHost hostnames. SPF authorizes the existing mail server and relay rather than the website host. Keep these mail records and the DKIM and MailChannels records when updating the website.
