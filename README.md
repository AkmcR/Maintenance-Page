The down step is not neccessary if your server is a self hosting server.


For Hosting server like cPanel/whm.

Open File Manager, go to public_html (or the folder of the domain you want), and turn on Settings → Show Hidden Files so you can see .htaccess.
Upload maintenance.html.
Add the .htaccess rules:
If the folder has no .htaccess, upload this one.
If it already has one (WordPress and similar sites do), don’t overwrite it. Paste the contents of mine at the top of the existing file.
Open your domain. You should see the maintenance page.
To turn maintenance off, delete or comment out the lines you added.

Letting yourself see the real site: in .htaccess, remove the # in front of the RewriteCond %{REMOTE_ADDR} line and put your own IP address in it.

In WHM (server-wide): put maintenance.html in /usr/local/apache/htdocs/ to use it as a default or fallback page. For one account, use the cPanel steps above.

503 status: the .htaccess returns a 503 “temporarily unavailable” status, so Google knows the downtime is temporary and won’t drop your pages from search.
Internet needed: because the page uses React and Tailwind from a CDN, visitors need an internet connection to see it properly.
