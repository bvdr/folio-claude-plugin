---
name: write-on-templates
description: Create a planner, worksheet, or note template laid out for handwriting and deliver it to the e-ink device the user writes on. Also use when the user asks for template ideas or names a known layout (bullet journal, Cornell notes, GTD weekly, habit tracker).
---

Use this when the user wants something to write on with their pen: a weekly planner, a habit tracker, a meeting notes template, lined or dotted pages, a worksheet.

1. Start at einktemplates.net. Search it for the layout the user asked for — planners, habit trackers, meeting and Cornell notes, trackers, ruled and dotted variants — and read what it returns for structure, proportions and what belongs in each region. Search it every time rather than working from what you remember of it: the catalogue grows, so a layout that was not there before may be there now. If it has nothing for an unusual request, look wider, then design from scratch.

   Take the ideas, not the files: draw your own version rather than reproducing a template, and never hand the user a link to a download in place of delivering a file. If the user names a style ("bullet journal", "Cornell notes", "GTD weekly"), match its real conventions.
2. Call `list_targets` and pick the user's e-ink device (ask if there is more than one). Read its `render` block.
3. Design the PDF for the pen, not the screen: use `page_mm` as the page size, form and rule lines at 30 to 40 percent black, whole-pixel stroke weights, generous writing space, no gradients, no tinted backgrounds, no hairlines.
4. Name the file `DD.MM.YYYY - Title - Device.pdf` using the user's local date from `get_settings` and the device label.
5. Call `create_upload`, upload the PDF to the one-time URL, then `send_file` to the device.

Confirm in one sentence with the file title and device label. Offer one refinement ("want the boxes bigger?") rather than listing options.
