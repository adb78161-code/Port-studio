ADII STUDIO V9 — COMPLETE RELEASE

FILES
- index.html: public portfolio
- manage.html: admin dashboard at /manage.html
- config.js: Supabase URL + public publishable key
- projects.json: fallback content
- supabase-setup.sql: safe setup/migration SQL (does not drop tables)
- admin-role.sql: separate SQL to grant the admin role to your Auth user
- assets/ and logo images: visual assets

GITHUB PAGES DEPLOYMENT
1. Create a new GitHub repository.
2. Upload every item inside this folder to the repository ROOT (not an extra nested folder).
3. Commit to branch main.
4. Repository Settings > Pages > Deploy from a branch > main > /(root) > Save.
5. Wait for deployment, then open the GitHub Pages URL.

SUPABASE
1. Check config.js. It contains the browser-safe project URL and publishable key. Never add a service_role key or database password.
2. In Supabase SQL Editor, run supabase-setup.sql. It is designed to be re-runnable and does not drop existing tables or rows. Review the SQL before running it on a production database.
3. Create/sign in to the intended admin user in Authentication > Users.
4. Open admin-role.sql, replace YOUR-ADMIN-EMAIL@example.com in BOTH places with the exact email of your Auth user, then run the full file separately in SQL Editor.
5. Sign out and sign back in so the refreshed JWT contains app_metadata.role=admin.
6. Admin page: https://YOUR-USERNAME.github.io/YOUR-REPOSITORY/manage.html

IMPORTANT
- Do not delete your old Supabase project if it contains portfolio content or enquiries.
- Existing project rows remain in place. Only rows with published=true appear publicly.
- The public publishable key is intended for browser use; database security depends on RLS policies.
- Test login, project save/upload, public project display and enquiry submission after deployment.
