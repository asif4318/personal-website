+++
title = 'UF Student Government Legislative Tracker'
date = 2023-08-19T18:46:59-04:00
type = 'project'
draft = false
+++

## Improving the transparency of UF Student Government Senate

UF’s Student Government (SG) Senate authors many pieces of legislation each semester, yet students often have no idea of the status of these bills or even what the details of these bills are. The SG website displays legislation only by bill number, causing students to tediously download files and individually check the subject of each bill.

Therefore, I created a web app to address these issues with transparency and accessibility: UF SG Legislative Tracker

My project adddresses this inconvenience. Using Python I automatically scrape the SG website of the PDFs of current legislation. From that, I ensure each PDF is searchable, using optical character recognition, a form of machine learning that converts images to text.

Next, I use a script that uses OpenAI’s GPT API to automatically scrape relevant data such as authors, sponsors, and a brief summary from each of these PDFs and output the data into a JSON file. The text searchable PDFs allow for easy text and quick text extraction such that GPT can be run on the data.

Finally, this organized data is pushed to a Google FireStore database from which the React frontend pulls data from.

As alluded to earlier, the frontend is made using Meta’s React JavaScript library along with the Chakra UI library. Additionally, fuzzy search was implemented to allow users to quickly find specific legislation.

Additionally, I took the voter records spreadsheet and wrote another Python script that parses and uploads the data to FireStore. Voter records log each vote cast within Senate by a Senator. Therefore making the data easily searchable and viewable on the web enables greater transparency.
