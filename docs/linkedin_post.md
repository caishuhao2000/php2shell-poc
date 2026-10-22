78% of all websites run PHP.

Yesterday, PHP's security team made an emergency announcement: two critical vulnerabilities that have been hiding in PHP's source code since 2012.

That's 14 years. Unpatched. In a feature that's turned ON by default.

I spent the last 24 hours in a lab trying to understand how bad this really is. Short answer: very.

I built three separate ways to take over a PHP server — each starting from nothing more than a single HTTP request. No login. No credentials. No special access. Just a carefully crafted file upload to any PHP page.

The scariest part? The vulnerable code runs BEFORE your application even starts. Your firewall rules, your WAF, your application security — none of it matters. PHP processes the attack before your code gets a chance to defend itself.

Who's affected:
→ WordPress (43% of ALL websites)
→ Laravel, Symfony, Magento, Drupal
→ Every custom PHP application
→ Every PHP version released in the last 14 years

What to do RIGHT NOW:
1. Check your PHP version (php -v)
2. Update to PHP 8.2.35 / 8.3.36 / 8.4.27 / 8.5.12
3. If you can't update yet: add session.upload_progress.enabled = Off to php.ini

I published a full deep-dive with the technical analysis and a Docker lab so security teams can test their own systems.

Link in the comments 👇

#cybersecurity #php #vulnerability #wordpress #infosec #security
