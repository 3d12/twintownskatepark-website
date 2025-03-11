# Twin Town Skate Park Website

A website for the Twin Town Skate Park, powered by [11ty](https://www.11ty.dev/) using the [Eleventy Duo](https://eleventyduo.netlify.app/) template written by yinkakun

## Updating

If editing content, edits should only be needed in `src/data/site.json`.

Current layout will parse all the JSON objects out of the `infoSections` array and create a new "info section" element for the contents of the object.

The layout will parse these in order, so to change the order of how things appear on the page, cut/paste them into the correct order in `site.json`.

For more advanced changes to layout, check the templates in the `src/layouts/` folder or consult your web admin for assistance.

**Structure of an infoSection object**
- id: Each infoSection needs one of these. This can be anything you want, but this is how you can target the specific infoSection for styling (using CSS class selectors) if needed.
- header: (Optional) Will create a large header atop the text part of the infoSection, with a highlighted border underneath. Text put in this element is what will be displayed for the header text.
- text: (Optional) Will place text into the infoSection. In order to break up text into multiple lines, use `\n` as a newline separator. HTML is acceptable in this field and will be parsed appropriately.
- image: (Optional) Path to an image to be displayed in the infoSection, must be relative to the `src/` directory.
- author: (Optional) Prepended with a hyphen and offset to the end (right, by default) -- used to attribute quotes

An infoSection object will be laid out across the horizontal axis according to which elements are present:
- If there is only an image defined but no text, the image will cross most of the horizontal axis.
- Similarly, if text is defined but no image, the text will reach over halfway across the horizontal axis.
- However, if both text and image are present, they will take a more balanced layout, splitting the horizontal axis roughly 60/40 with the image getting the larger share by default.

## Design

Most editable CSS will be in `src/css/main.css`. This is where tweaks to specific info sections can be grouped together.

Other notable CSS files:
- `info-section.css`: Contains stylings for the infoSection elements on the main page.
- `typography.css`: Contains details about fonts, including the available font size variables
- `variable.css`: Contains other variables, including viewport breakpoint and color variables.
- `global.css`: Contains styles which are inherited throughout the entire website. Probably won't need many changes, but if you wanted to change anything outside the boundaries of the `main` div, this is probably where it will be.

## License

Copyright (c) 2025 Twin Town Skate Park Committee, All Rights Reserved

This website was constructed in part from a template which is distributed under the MIT license.

Template eleventy-duo Copyright (c) 2020 Yinka Adedire, MIT License
