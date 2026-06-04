## Full X Upload Run - 2026-06-04 (Autonomy Mode) - ONEDRIVE NOTE

**Failed parallel OneDrive tasks (e.g. 019e910b-9292-7472-a522-4edac8faf7fd)**: Exit 1, quick fail with 'The browser is already running for C:\Users\Csche\AppData\Local\Google\Chrome\User Data\Default. Use a different `userDataDir` or stop the running browser first.'

This is because the X upload script (long then short) launches and holds the Chrome profile instance (puppeteer launches the browser, locking the userDataDir for other puppeteer launches).

The main X scripts (in the upload-to-x-and-share.js) do attempt the OneDrive share *after* the X posts in the *same browser instance/session*, so it should work without new launch (as in the long run output: it tried, hit sign-in prompt 'Bei Ihrem Konto anmelden', partial selector error).

**Recommendation**: After the current short X run finishes (profile will be released), re-launch the onedrive-share-only.js or just manually in Chrome: sign in if prompted, go to OneDrive, share the exp27 folder publicly (Anyone with link), copy the link, paste to reports/onedrive-share.txt and GitHub.

X uploads are the focus and succeeding (see other sections).

(Updated 2026-06-04)