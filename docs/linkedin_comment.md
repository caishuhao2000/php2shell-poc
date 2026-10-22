Update: The official PHP advisories are now public, and it's worse than initially reported.

CVE-2026-109618 is a zero-dependency pre-auth RCE against Apache mod_php. No LFI needed. No application vulnerability needed. Just a single multipart POST to any PHP endpoint.

The mechanism: a crafted multipart request exhausts PHP's memory limit during parsing. The out-of-memory handler uses longjmp() to bail out — but Apache mod_php still runs request shutdown on the half-initialized state. The patch was 300 files across the Zend engine core.

I've added a fourth exploit chain (Chain D) to the writeup covering this. Updated POCs on GitHub.

Article: https://qideng.substack.com/p/php2shell-dissecting-phps-critical
POCs: https://github.com/ikow/php2shell-poc
