ROADTRIP LATEST CLEAN SETUP — A to Z

IMPORTANT:
Do NOT mix old index_v4.html, old upgrade_v4.sql, old V3 files.
Use ONLY the files in this folder.

FILES:
1. 01_SUPABASE_FULL_SETUP.sql  -> Run once in Supabase SQL Editor
2. config.js                   -> ONLY file you edit
3. 00_TEST_CONNECTION.html     -> Tests URL/key
4. index.html                  -> Main RoadTrip app
5. 02_CREATE_8D7N_TRIP.html    -> One-click importer for JB→Ipoh→Thailand→Cameron→JB
6. SOURCE_NOTES.md             -> Trip research source notes
7. trip_template_8d7n.json     -> Trip data backup

============================================================
A. SUPABASE DATABASE
============================================================
1. Open your existing Supabase project.
2. SQL Editor -> New query.
3. Open 01_SUPABASE_FULL_SETUP.sql.
4. Ctrl+A / Copy ALL.
5. Paste into SQL Editor.
6. Run.
7. Scroll to bottom. You should see:
   ROADTRIP_LATEST_SETUP_OK

The SQL is intended to work on both a fresh project and your existing project.

============================================================
B. SUPABASE API KEY
============================================================
1. Supabase project -> Connect
   OR Settings -> API Keys.
2. Copy Project URL.
3. Copy PUBLISHABLE key, normally starts:
   sb_publishable_...
4. DO NOT use:
   sb_secret_...
   service_role
   database password

============================================================
C. EDIT ONLY config.js
============================================================
Open config.js.

Change:
SUPABASE_URL: 'PASTE_PROJECT_URL_HERE'
to your Project URL.

Change:
SUPABASE_KEY: 'PASTE_PUBLISHABLE_KEY_HERE'
to your Publishable key.

Save.

============================================================
D. GITHUB
============================================================
In your GitHub repository:
1. Upload/replace ALL these public web files:
   index.html
   config.js
   00_TEST_CONNECTION.html
   02_CREATE_8D7N_TRIP.html

2. Commit changes.

3. Settings -> Pages:
   Source = Deploy from a branch
   Branch = main
   Folder = /(root)

4. Wait until Actions / Pages build and deployment is green.

============================================================
E. TEST FIRST
============================================================
Open:
https://YOUR-USERNAME.github.io/YOUR-REPO/00_TEST_CONNECTION.html

Click Test Connection.

You MUST get:
Connection OK

If it fails, DO NOT troubleshoot index.html yet.
Fix config.js first.

============================================================
F. OPEN APP
============================================================
Then open:
https://YOUR-USERNAME.github.io/YOUR-REPO/

You should see Login/Register, NOT “还差一步”.

============================================================
G. CREATE THE READY-MADE 8D7N TRIP
============================================================
Open:
https://YOUR-USERNAME.github.io/YOUR-REPO/02_CREATE_8D7N_TRIP.html

It automatically reads the same config.js.

1. Click Connect & Login
2. Login with your normal RoadTrip account
3. Click Create 8D7N Trip + Import All Items
4. It creates a NEW 8-day trip
5. Return to main index.html and refresh
6. Open the trip
7. Copy Invite Code to your 3 friends
8. Start voting

============================================================
H. AFTER IMPORT
============================================================
For cleanliness, you may delete 02_CREATE_8D7N_TRIP.html from GitHub after the trip is created.
The trip data stays in Supabase.

============================================================
I. PHOTOS
============================================================
The setup creates public bucket:
trip-photos

Only authenticated trip members can upload/update/delete files under their trip folder.
The resulting image URLs are public, so do NOT upload passports, IDs, invoices, or private documents.
Use it only for attraction/food/hotel inspiration photos.

============================================================
J. IF YOU SEE “还差一步”
============================================================
There are ONLY 3 things to check:
1. Is GitHub actually serving the NEW index.html?
2. Is config.js in the same root folder as index.html?
3. Does 00_TEST_CONNECTION.html say Connection OK?

Do not edit index.html to fix keys.
Only edit config.js.
