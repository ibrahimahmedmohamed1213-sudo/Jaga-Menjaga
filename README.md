# Jaga-Menjaga

Our prototype for the SDP University Hackathon 2026 (People track). Team from IIUM.

Try it here: https://courageous-cactus-b5928b.netlify.app

## What it is

Most of us live a few metres from our neighbours but don't really know them. Jaga-Menjaga ("we look after each other") puts neighbours on the same street into small groups called Street Circles. If you need help, your request goes to the people closest to you. Helping out builds your trust level, which unlocks more features.

The demo is set in Elmina Green One, City of Elmina (Shah Alam), our proposed pilot neighbourhood.

There are four parts:

- **Care** - say Salam Pagi to your buddies every morning. If an older neighbour doesn't check in, their buddy gets a gentle reminder to check on them. You can start a Meal Train if someone is sick, find someone to look after your pet (Jaga Pet), get a neighbour who's home to take in your parcel (Jaga Parcel), and plan meet-ups like picnics, town halls or gotong-royong (Jom Kumpul) - neighbours vote on a date, and you can join in person or online.
- **Share** - borrow things from neighbours instead of buying (Pinjam Library), swap skills, and share extra food (Lebihan).
- **Safe** - SOS button that alerts your buddies, family and the guardhouse at the same time. Also Safe Journey for walking home, and alerts that only spread once neighbours confirm them.
- **Comfort** - give neighbours a heads-up before renovations or a kenduri, and report broken things like streetlights.

There's also a Guardhouse screen for the guards and a Care Index page for township managers (only shows patterns, not personal info).

## How to run it

Just open `index.html` in Chrome or any browser. Nothing to install. Works on phone and laptop. On a phone the menu is at the bottom.

## How it works

Everything is in one file, `index.html`:

- **HTML** - the layout of each page (Street, Care, Share, Safe, Comfort, Live street, You, Guardhouse, Care Index)
- **CSS** - colours, fonts, and making it fit on phones
- **JavaScript** - all the buttons and logic. The main parts are:
  - the sample data (residents, requests, items, parcels, meet-ups, alerts), saved in the browser with `localStorage`
  - a simple sorter that reads what you type (Malay, English or rojak) and decides if it's help, borrowing, a parcel, a repair or an alert
  - one render function for each section that redraws it when something changes
  - the drawings (people and the township) are made with SVG and canvas code, so there are no image files

The "Live street" page lets real phones join the same street. Salam Pagi, requests, SOS, repair reports, meet-up votes and parcels all show up on everyone's phone live. It sends small messages through ntfy.sh, a free relay. If the relay can't be reached, it switches to a demo that works between tabs on one device.

## Limitations

This is a prototype, so:

- the residents and numbers are sample data
- the sorting uses keyword rules, not real AI
- the live demo uses a free public relay - a real version would need a proper database and guardhouse verification

## Team

- Ibrahim - Architecture (concept and prototype)
- Adam - Quantity Surveying (costing and feasibility)
- Nurin - Urban Planning (township mapping)
