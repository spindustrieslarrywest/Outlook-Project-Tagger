# Project Tagger — Outlook add-in

Adds a **Project** button to Outlook when you're reading an email. It opens a panel beside the email with:

- A project dropdown. Picking a project tags the email with an Outlook category of the same name. Picking "No project" removes the tag.
- A New project box. Adds a project and, with the box ticked, tags the open email with it.
- Manage projects. Removes a project from the dropdown. Emails already tagged keep their category.

One project per email. Choosing a different project replaces the old project tag, and any other categories on the email are left alone.

Pin the panel with the pin icon and it stays open, following each email you click.

## Hosting (one time)

1. On GitHub, create a **public** repository named exactly `Outlook-Project-Tagger` under `spindustrieslarrywest`.
2. Put these files at the top level of the repo: `index.html`, `taskpane.html`, `commands.html`, `manifest.xml`, `README.md`, and the `assets` folder.
3. Settings → Pages → Build and deployment → Source: **Deploy from a branch** → Branch: `main`, folder `/ (root)` → Save.
4. After a minute or two, https://spindustrieslarrywest.github.io/Outlook-Project-Tagger/ should show the Project Tagger page.

The manifest points at that exact address. A different repo name means the manifest URLs must change to match.

## Installing in Outlook

1. Sign in to your SP Microsoft 365 account in a browser and open https://aka.ms/olksideload
2. In the Add-ins dialog: **My add-ins** → **Custom** → **Add a custom add-in** → **Add from file** → choose `manifest.xml`
3. Accept the permission prompt, close the dialog, and refresh.
4. Open any email and choose **Apps** (or the **...** menu) → **Project Tagger**. In classic Outlook the **Project** button sits on the Home ribbon.

If **Custom** / **Add a custom add-in** is missing, SP's Microsoft 365 admin has turned off user-installed add-ins. The admin can deploy the same `manifest.xml` centrally instead.

## Notes

- Requires Outlook that supports Mailbox requirement set 1.8: Outlook on the web, new Outlook, and current classic Outlook on Windows.
- Asks for "read/write mailbox" permission because creating a new Outlook category needs it.
- The project list is stored in your mailbox (add-in roaming settings), not in this repo. The repo holds code only.
- To find everything for a project, filter or search by its category in Outlook.
