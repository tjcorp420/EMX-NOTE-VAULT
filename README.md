# EMX Notes / Vault
Static PWA for Vercel. No npm, backend, account, or environment variables needed.

## Deploy from your phone
1. Extract this ZIP using iOS Files.
2. In GitHub, create a new repository and upload the contents of the extracted folder to the repository root (index.html must be at root). GitHub's mobile website may require requesting the desktop site for bulk upload.
3. In Vercel, Add New > Project > Import Git Repository. Select the repo.
4. Framework Preset: Other. Build Command: leave empty. Output Directory: leave empty. Deploy.
5. Open the HTTPS URL in Safari. Share > Add to Home Screen.

## Use
- Add/edit/delete/search notes. Notes autosave in IndexedDB.
- Triple-tap the EMX logo to create/unlock a four-digit PIN.
- Upload photos, videos, PDFs and other supported files. Files are AES-GCM encrypted before IndexedDB storage, using a key derived from the PIN with PBKDF2 (600,000 rounds).
- Lock by leaving the vault, locking manually, or backgrounding the app.

## Security and limits
- A four-digit PIN has only 10,000 combinations. This is not high-security protection against a determined attacker with device access. The in-app delay is not tamper-resistant; for stronger protection use a longer passphrase or hardware-backed encryption.
- PIN is not recoverable; forgetting it makes vault contents inaccessible.
- Data is bound to browser/origin/storage container. Safari and an installed Home Screen PWA may have separate storage. Use the same installed app consistently.
- Browser/site data deletion, uninstall, storage eviction, private browsing, or changing domain may erase or orphan data. No backup or cloud sync is provided.
- File capacity depends on browser storage quotas; large videos may fail.
- Notes are not encrypted; only vault file contents are encrypted. Vault filenames, types, and sizes are stored unencrypted in IndexedDB.
- No media is uploaded to Vercel. The application source code is publicly accessible as with any website.
- This is an initial version, not independently security-audited. Test with disposable files before trusting it.


## v4.2 gallery update
- Decrypted, device-local photo thumbnails and video poster frames (where the browser supports decoding).
- Truncated long filenames in cards; original filenames preserved.
- Full-screen previous/next buttons, swipe navigation, and media position counter.
- Uses the same IndexedDB schema and encryption format.
