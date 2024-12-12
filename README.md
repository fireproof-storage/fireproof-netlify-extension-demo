# Fireproof + Netlify Extension Demo

The purpose of this application is to demonstrate that the Fireproof Netlify extension is installed and functioning correctly.

## Deploying this to Netlify

- Enable the Fireproof Netlify extension within the Netlify UI
- Create a new site using an existing project, pointing to this repo

## Veryifying two-way sync works

Verifying two-way sync requires to separate browser instances (not just separate tabs), referred to below as A and B:

- Browser A
  - Open the newly deployed site
  - Open the dev tools console
  - Press the `Check All Docs Count` button, and expect to see `All Docs Length 0`

- Repeat the same in Browser B
  - Open the newly deployed site
  - Open the dev tools console
  - Press the `Check All Docs Count` button, and expect to see `All Docs Length 0`

- Browser A
  - Press the `Create Document` button
  - Press the `Check All Docs Count` button, and expect to see `All Docs Length 1`

- Back to Browser B
  - Keep pressing the `Check All Docs Count` button, and eventually (often over 1m later) the `All Docs Length` will increase from 0 to 1
  - Now, press the `Create Document` button

- Back to Browser A
  - Keep pressing the `Check All Docs Count` button, and eventually (often over 1m later) the `All Docs Length` will increase from 1 to 2

You have now verified that documents created in one browser are eventually synced and visible on the other browser.
