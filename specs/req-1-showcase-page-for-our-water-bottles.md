# REQ-1 · Showcase page for our water bottles

<!-- OghaOS requirement 1, version 1, finalised by Shreyas T -->

A single static page that shows our 6 water bottles. Cards in a responsive grid show photo, name, capacity, material, colour swatches and price. Visitors can filter by material, sort by price, and open a bottle for a bigger photo, a short description and every colour. Plain HTML, CSS and JavaScript, no framework, no build step. All bottle data lives in one file, bottles.json, and the page works when index.html is opened straight from disk. No cart, checkout, login or backend. Appetite: half a day, bare bones.

## REQ-101 · The page shows all six bottles

Opening index.html shows a card for each of the 6 bottles, in the order the bottles appear in the data file. The count on screen is 6, with no empty slots or placeholders where a bottle should be.

## REQ-102 · Each card carries the facts a buyer needs

Every card shows a picture, the bottle name, its capacity in ml, its material (steel, glass or plastic), a swatch for each colour it comes in, and its price. Prices are shown in one consistent format, so they can be compared at a glance.

## REQ-103 · The pictures can be placeholders

The bottle picture can be a simple drawn shape coloured to match the bottle, drawn in the page itself. No photo files and no image downloads are needed to make the page work.

## REQ-104 · Filtering by material

There is a way to pick a material: all, steel, glass or plastic. Choosing glass leaves only the glass bottles on screen, choosing steel leaves only steel, and choosing all brings back all 6. Filtering is applied to the bottles already on the page; it never changes the data file.

## REQ-105 · Sorting by price

There is a way to sort by price: cheapest first or dearest first. After choosing cheapest first, the prices on screen run from lowest to highest, top to bottom. After choosing dearest first they run the other way. Before any sort is chosen, the bottles stay in the order the data file lists them.

## REQ-106 · Opening one bottle

Clicking a card opens an overlay panel on the same page showing that bottle: a bigger picture, a short description, and every colour it comes in. The grid stays behind it. The panel closes with a close button and with the Escape key, and closing it returns to the grid with the chosen filter and sort still applied.

## REQ-107 · The data lives in one file

All 6 bottles are described in one file, bottles.json. The file sets a JavaScript variable named BOTTLES to an array of bottle records, and the page loads it with a plain script tag. The page also works when served over a local web server, with no change to the data file.

## REQ-108 · What each bottle record holds

Each bottle record in bottles.json holds: an id, a name, capacity in ml, material (one of steel, glass or plastic), a price, a list of colours, a short description, and a colour used for the drawn bottle shape. The page reads all of these from the file; no bottle detail is hard-coded in the HTML or the JavaScript.

## REQ-109 · One column on a phone, three on a desktop

At a viewport width of 375px the grid shows one column of cards. On a desktop screen the grid shows three columns. There is no sideways scrolling at 375px, and no element sticks out past the edge of the screen.

## REQ-110 · Plain files, no build step

The page is plain HTML, CSS and JavaScript. No framework, no bundler, no package install, no server needed to view it. Opening index.html by double-clicking it from disk works exactly as it does when served over http.

## REQ-111 · Nothing else is in scope

No cart, no checkout, no login, no backend, no database, no analytics, no animations or transitions, no shareable filter links, and no separate detail page or second HTML file. If a filter hides every bottle, the page simply shows an empty grid.

## REQ-199 · How we know it works

A written walkthrough, followed in a browser, in both Chrome and Firefox. Open index.html by double-clicking it from disk. Count 6 cards. Choose glass and confirm only glass bottles remain; choose all and confirm 6 return. Sort cheapest first and confirm prices run lowest to highest; sort dearest first and confirm they reverse. Click a card and confirm the overlay shows a bigger picture, a description and every colour; close it with the Escape key and confirm the grid and its filter and sort are unchanged. Narrow the window to 375px wide and confirm one column per row and no sideways scrolling.
