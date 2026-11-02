To run VulnLab-PHP:
***
first install 
sudo apt install php-sqlite3

Debian/Ubuntu/Kali
1. Start it

cd vulnlab-php
php -S 127.0.0.1:8000 -t public

(or docker compose up --build if you’d rather containerize it)

2. Open it — go to http://127.0.0.1:8000/ in your browser. That’s the challenge dashboard.

3. Log in — either register a new account, or use a seed login: alice / alice123 or bob / bobpass.

4. Work through challenges — click into any of the 9 cards (SQLi, reflected/stored XSS, IDOR, broken access control, exposed backup, SSRF, file upload, CSRF). Each has:

A description of what to achieve
A Hint link if you’re stuck
A Solution link with the full exploit steps and the real-world fix

5. For the CSRF challenge specifically — you also need a second, separate server: cd csrf-poc && php -S localhost:9000, then open http://localhost:9000/evil-page.html in a new tab while logged into the main app, to see the cross-origin attack fire.

6. Resetting — delete data/vulnlab.sqlite and anything in public/uploads/ to wipe progress and start over.
