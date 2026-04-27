Dont Get Trapped
A browser-based, pixel-art social engineering awareness game set on a Lipscombs campus. Players navigate through nine rooms, each presenting a realistic phishing or social engineering scenario. The goal is to recognize the manipulation tactics — but the game is intentionally designed so most players fall for them the first time.

Setup
No installation, build tools, or server required.

Visit https://grayant04.github.io/Senior-Project/ on any browser

OR

Download Dont_Get_Trapped_v10.html from https://github.com/GrayAnt04/Senior-Project
Open it in any modern web browser (Chrome, Firefox, Safari, Edge)

The only external dependency is Google Fonts. An internet connection is needed for the fonts to display correctly but the game itself will still function offline, just with fallback fonts.

How to Play
Use your mouse to click on glowing NPCs and objects in each room. Talk to the NPCs to trigger dialogue. Fill in the forms they present to progress to the next room. A progress bar at the top tracks how far through the campus you have gotten.
Rooms in order:

Fields Engineering Center (exterior)
Fields — Lobby
Fields — Computer Lab

Beaman Library (exterior)
Front Desk
Library — Reading Room

Alumni Hall (exterior)
Alumni Hall — Starbucks
Student Dining Hall

Each room has one NPC or puzzle that must be solved before the exit unlocks

Project Structure
The project is organized into three sections:

CSS — all styles are written inline in the <head>, using CSS custom properties for the color palette and pixel art aesthetic
HTML rooms — each room is a <div class="room" id="roomN"> block so that only the active room is visible at a time
JavaScript — all game logic is contained in a <script> tag at the bottom, including the state machine, dialog builder, room transitions, and win/fail conditions

There are no external JavaScript libraries, no frameworks, and no asset files. Everything is drawn with HTML <div> elements and CSS.

Editing the Game

Moving or modifying NPCs
- Each NPC is a <div class="hotspot glow" id="hs-[name]"> element. Position is controlled by bottom and left CSS values within its style attribute.

Changing dialogue
- All dialogue is set up in the buildDialog(id) function in the <script> section. Each NPC has a key (e.g. receptionist, barista, cashier) that maps to an arrow function returning a title and HTML body string.
  
Adding a room
- Add a new <div class="room" id="roomN"> block in the HTML
- Add the room name to the names array inside setRoom()
- Add navigation hotspots that call goToRoom(N)
- Add any new NPC keys to the dialogs object in buildDialog()
- Add a corresponding state flag to the state object (e.g. roomNDone: false)

Changing room names
- Room display names are set in the names array inside the setRoom() function
- jsconst names = ['','FIELDS ENGINEERING CENTER','FIELDS — LOBBY', ...]
- Index 0 is unused; index 1 corresponds to room 1, and so on

Browser Compatibility
Tested in current versions of Chrome, Firefox, and Safari. Requires a browser with support for CSS custom properties, position: absolute stacking, and standard ES6 JavaScript.

Intended Use
This game is designed as an educational tool for cybersecurity awareness training, focused on social engineering, phishing, and pretexting. It is suitable for classroom use and self-guided learning. After completing the game, facilitators are encouraged to debrief players on what happened and why you shouldnt input sensitive information.
