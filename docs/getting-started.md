# Must-haves

Before you start, the first thing to do is set up your workspace:

> [!WARNING]
> To have links update automatically when you rename files, go to `Files and links` in Settings and turn on `Automatically update internal links`.

> [!IMPORTANT]
> To show all files, regardless of type, in the file tree on the left, go to `Files and links` in Settings and turn on `Show all file types`.

> [!NOTE]
> To keep `PNG`, `GIF`, and other files out of the way and together in one folder, go to `Files and links` -> `Default location for new attachments` in Settings.
> Then choose how you want to store attachments.
>
> I usually keep attachments in a folder created in the same folder I am working in. To do that, choose `In the folder specified below` under `Default location for new attachments`. The `Attachment folder path` field that appears contains `Attachments` by default. You can change it, but the capital `A` is convenient because the folder appears near the top of the list (unless you have folders starting with `!`, `#`, `_`, or similar characters).

> [!CAUTION]
> If you use `.md` files not only for GitHub but also for simple notes in folders on Google Drive, you may have noticed `desktop.ini` files appearing all over the place, sometimes in almost every folder.
>
> One way to hide them from your Vault is to install the `Advanced Exclude` plugin (described below).

# Plugins

Obsidian has a large plugin store. Here are some plugins I have tried and found useful:
- `Link Converter`
	Converts all wiki links (`[[file]]`) in every note in your Vault to relative Markdown links (`[file](some_path/file.md)`) with one command. This is very useful before publishing `.md` files on GitHub.
- `Better Export PDF`
	An improved PDF exporter for notes. It can export entire folders and supports images with `![file_name](file_name)`, tags, and more. It is easy to configure: you can choose A4, A5, or another page size, create your own, choose whether to show the note title in the PDF, and more.
- `Docxer`
	A plugin for working with Microsoft Word. It lets you:
	1. Read documents without opening Word (opening one in Obsidian takes less than a second, while Word takes 5-10 seconds).
	2. Convert documents to Markdown while keeping all the images from the document.
- `Excel to Markdown Table`
	A plugin for Microsoft Excel, Google Sheets, and other non-Markdown spreadsheets. It lets you paste copied tables or parts of tables into notes as Markdown tables without formatting problems. Try pasting without the plugin: the `|-|-|` separators between the header and data rows break.
- `Templater`
	For inserting text from templates, including generated values such as the current date. I only needed it for daily notes (the built-in `Daily Notes` plugin, represented by the calendar icon on the left toolbar in Obsidian).
- `Kanban`
	Displays task cards by status, for example, to do, in progress, doing now, and done.
- `Minimal Theme Settings`
	For customizing the `Minimal` theme. I use `Colorful window frame` (highlights the tab bar), `Colorful active states` (highlights the current note), and `Colorful headings` (colors headings from red for level 1 to purple for level 6).
- `Advanced Exclude`
	Excludes files or folders from your Vault. It works like `.gitignore`, although, as far as I understand, it does not care about letter case. I use it to hide Google's `desktop.ini` files and a couple of my `*.gscript` files for automating work with Google Calendar. ^6ef345
- `Gemini Scribe`
	Connects the Gemini AI assistant using an API key.
	- Plugin repository: [allenhutchison/obsidian-gemini](https://github.com/allenhutchison/obsidian-gemini/)
	- Documentation site: [Gemini Scribe](https://allenhutchison.github.io/obsidian-gemini/)
	Important: if you use `Advanced Exclude` to exclude folders or files from your Vault, `Gemini Scribe` will not see them. This can be useful for keeping sensitive information away from AI, but those files will also be hidden when you open this Vault.
- `Plugin Update Tracker`
	Tracks updates to other plugins. When one is available, a small green indicator appears in the upper-right corner.

> [!IMPORTANT]
> If you ever need to save a website as Markdown, there is a browser extension for that: [Obsidian Web Clipper - Chrome Web Store](https://chromewebstore.google.com/detail/obsidian-web-clipper/cnjifjpddelmedmihgijeibhnjfabmlf).
>
> It works with YouTube too: it downloads all timestamps and subtitles.

# Themes

Many people think the main and only benefit of themes is that they look good.

But if you have several Vaults, especially if some contain similar notes, you have to switch context in your head, which takes time and effort. Different themes can make that easier by signaling to your brain which Vault you are in.

The themes I use:
- `GitHub` - for opening a Vault with a folder for GitHub (handy for writing `README` files), with a blue background and green topics like the site
- `Primary` - great for writing textbooks and other book-like content. It might also work as a main Vault theme. I recommend taking a look because it offers many customizations
- `Minimal` - a calm theme and the best option for my main Vault
