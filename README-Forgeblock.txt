FORGEBLOCK LEGENDS — WORLD UPDATE
=================================

FILES
-----
index.html       Main game
manifest.json    Installable web-app settings
sw.js            Service worker for caching the app shell
icon-192.png     App icon
icon-512.png     App icon

INSTALL / DEPLOY
----------------
1. Put all five files in the same folder in your GitHub Pages repository.
2. Keep the names exactly as listed above.
3. Commit/publish the changes and open the HTTPS GitHub Pages website.
4. On a phone, open the page in the browser and use the browser's Add to Home Screen / Install option.
5. Refresh the page fully after replacing the old files. If an old version remains, clear the site's cached data or change the cache version in sw.js.

CONTROLS
--------
Desktop:
  WASD move, mouse look, Shift sprint, Space jump
  Left-click attack, right-click mine
  G place the selected block, V cycle block type
  E talk to a villager / collect from a nearby animal
  Q cast power, Z next power, F cycle style
  B summon boss, R start raid, C open menu, X swap weapon
  1–9 select hotbar item

Mobile:
  Use landscape orientation, left joystick to move, drag the right side to look,
  and tap the on-screen buttons. Talk is the speech-bubble button.

NEW GAMEPLAY
------------
- More gently rolling terrain and a clouded day/night sky.
- Procedural surface, wood, leaf, and creature texture improvements.
- Mining takes multiple hits on tougher blocks, animates the held tool, and
  drops Grass, Dirt, Stone, and ore resources into inventory.
- Inventory lets you choose a block type; G places it on an exposed surface.
- Village structures, smith station, and villagers.
- Peaceful daytime cows, sheep, and pigs; E collects wool or raw meat nearby.
- Forge menu for melee weapons, ranged weapons, and armour. Forged gear gets a
  quality tier (Common, Rare, Epic, Legendary, or Mythic) that changes stats.
- Village trades for materials, wool, and building blocks.
- Local saves now include block inventory, drops, forge quality, placed blocks,
  and a limited set of terrain edits.
- Google sign-in and room-code friend PvP setup panel.

GOOGLE LOGIN + FRIEND PvP SETUP
-------------------------------
These online features need a Firebase project. They cannot work until you
configure your own project; do not use anyone else's private credentials.

1. Create a Firebase project and register a Web app.
2. In Authentication, enable the Google sign-in provider.
3. In Authentication settings, add your GitHub Pages domain to Authorized
   domains (for example, username.github.io).
4. Create a Realtime Database and copy its database URL.
5. Open the game, choose Online, paste the Firebase Web app config values, then
   choose Save & connect and Sign in with Google.
6. Create a friend room and share its code. Your friend needs the same Firebase
   project config, signs in, and joins that code.
7. In Realtime Database Rules, use the starter rules shown inside the game's
   Online tab. Review and strengthen them before making a public game.

IMPORTANT ONLINE LIMITS
-----------------------
- Firebase Web config values are public client configuration, not admin secrets.
  Never put a service-account key or admin credential in this game.
- The room syncs player positions and simple PvP hit events. It is a casual
  prototype, not an authoritative anti-cheat server or ranked PvP system.
- Google login and online play require HTTPS hosting, internet access, and a
  correctly configured Firebase project.
- The 3D engine and Firebase SDKs load from CDNs, so the game still needs an
  internet connection even though the app shell is cached by the service worker.

TESTING NOTE
------------
The updated inline JavaScript passed a Node syntax check. A full interactive
browser test was not available in the build environment, so test the published
version on your phone/desktop before sharing it widely. No software can honestly
be guaranteed to contain zero bugs.
