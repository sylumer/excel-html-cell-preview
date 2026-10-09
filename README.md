# HTML Cell Preview for Excel

An Excel task-pane add-in for Windows and Mac desktop. Select a cell containing HTML and the pane renders it with the platform's modern browser engine (WebView2 on Windows, WebKit on Mac). Scripts and other active content are stripped with DOMPurify, and the result is shown in a sandboxed iframe with a restrictive Content Security Policy.

**Install instructions:** https://sylumer.github.io/excel-html-cell-preview/

Installation is per user and needs no administrator rights, store access or installer: a pasted PowerShell (Windows) or Terminal (Mac) command saves the manifest locally and registers it with Excel's developer add-in mechanism.

## Files

| File | Purpose |
|---|---|
| `manifest.xml` | Add-in manifest (Home tab button that opens the pane) |
| `taskpane.html` | The pane: reads the active cell, sanitises and renders it |
| `commands.html` | Required function file for the ribbon button |
| `index.html` | Install and uninstall page |
| `vendor/purify.min.js` | DOMPurify 3.2.6 |
| `assets/` | Icons |

Opening `taskpane.html` in an ordinary browser gives a paste box for testing the sanitiser and rendering outside Excel.

Changes to `taskpane.html` reach users automatically. Changes to `manifest.xml` require users to rerun the install command (bump `<Version>` when doing so).

Validate the manifest with `npx office-addin-manifest validate manifest.xml`.
