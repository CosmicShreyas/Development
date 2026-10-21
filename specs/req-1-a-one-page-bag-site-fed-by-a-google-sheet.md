# REQ-1 · A one-page bag site fed by a Google Sheet

<!-- OghaOS requirement 1, version 2, finalised by Shreyas T -->

She sells handmade bags through Instagram DMs and answers "what do you have?" with a 20-photo dump. This gives her a single public page that lists her current bags with photo, fabric, size and price, marks them available or sold, and sends each buyer to WhatsApp with the bag name already in the message. The bag list is a Google Sheet she already knows, and the site reads it live, so a sold bag shows as sold without a developer. Appetite: one day of build. No payments, no admin screen.

## REQ-101 · One page, no detail pages

The site is a single public page. Every bag appears as a card on that page. There is no second page per bag and no way to reach one. Clicking a card's contact button never opens a bag detail page.

## REQ-102 · Each card shows one photo, fabric, size and price

A card shows exactly one photo of the bag, the fabric, the size, and the price. The photo is the one she chose, and it fills the card without being cropped awkwardly. The price is shown as she wrote it in the sheet, including the currency.

## REQ-103 · Available and sold are both visible

Each card shows whether the bag is available or sold. A sold bag still appears on the page, visibly marked sold, and a buyer can still read its details. Sold bags do not disappear. A bag whose status cell is empty, or holds anything other than sold, is treated as available.

## REQ-104 · The Google Sheet is the bag list

The bags come from a Google Sheet. The sheet has one row per bag with columns for name, photo, fabric, size, price and status. The site reads that sheet. The bag list is not stored in the site's code, and no person has to edit code or a data file to add a bag or mark one sold.

## REQ-105 · The page reads the sheet on every visit

Each time someone opens the page, the site reads the current sheet. A change she makes in the sheet, including marking a bag sold, is visible the next time the page loads, without a rebuild or a message to anyone.

## REQ-106 · Photos live in Google Drive

Photos live in a Google Drive folder in her account. The sheet holds the photo's Drive file id, and the site turns that into the image URL itself. The folder is set to anyone with the link can view. If a photo fails to load, the card still shows the bag's name, fabric, size and price, with a plain placeholder where the image would be.

## REQ-107 · Each card contacts her on WhatsApp

Each card has a button that opens WhatsApp with a message already filled in, naming that bag. The message says the bag name and asks about it. The button works on a phone and on a desktop, and it does not need a form, an account, or a login.

## REQ-108 · Missing values do not break the page

If the sheet is empty, the page loads and says there are no bags yet, rather than showing an error. If a row is missing a photo, a fabric, a size, a price or a name, the card shows what is there and leaves out what is not. One incomplete row does not stop the other bags from appearing.



The page stays usable on a phone with a slow connection: it shows the bag cards as soon as the sheet is read, and photos fill in as they arrive.

## REQ-109 · No payments, no admin

The site takes no payments and has no cart or checkout. There is no admin screen, no login for her, and no edit button on the page. Editing happens only in the sheet.

## REQ-199 · How we know it works

She adds a test row to her sheet with a name, a Drive photo, fabric, size, price and status available. On her phone she opens the site and sees the card with the photo and all four values, and sees the sold test bag from the same sheet marked sold. She taps the card's WhatsApp button and the WhatsApp chat opens with the test bag's name in the message. She then changes the test bag's status to sold, reloads the page, and the card shows sold.
