Crossfuze Autonomous Enterprise campaign map — encrypted CARS files

This package contains:
- index.html — the entire campaign map, with the correct Crossfuze logo embedded
- RoadToZero-v32-standalone.html — the Track A master
- assets/CARS_First_Call_Recording.enc.part01 through part04 — encrypted CARS recording, split for GitHub browser upload
- assets/CARS_First_Call_Deck.enc.part01 — encrypted preliminary-pricing PowerPoint
- assets/Crossfuze-Logo_Vibrant-White-Gradient.png — logo backup

1. Extract the ZIP.
2. Upload index.html, RoadToZero-v32-standalone.html, and the assets folder to the root of the appropriate GitHub Pages repository. Preserve filenames and exact folder hierarchy. 
3. IMPORTANT: GitHub's browser uploader accepts only files up to 25 MiB each. Each encrypted CARS segment is no more than 20 MiB, so you can upload them through GitHub's web UI. You can also use Git or GitHub Desktop.
4. Visit the GitHub Pages URL on HTTPS. Open the CARS campaign section and click either resource, then enter the password shared separately through an internal channel.
5. Never commit the clear MP4/PPTX or the password to the public repository, and never include the password in HTML, JavaScript, or README files.

Security: The actual recording and deck bytes are AES-256-GCM encrypted with independent per-file salts and nonces, and the key is derived from a high-entropy password using PBKDF2-SHA-256 (310,000 iterations). The site does not contain a password or stored decryption key. Anyone can download ciphertext, but cannot decrypt it without the password. Anyone with the password can decrypt and share files; password-only access is not identity-based authorization, and there are no per-user revocation or audit logs. For strict individual access control, move these assets to your Microsoft 365 tenant and link them from the same page, or host the entire page behind managed authentication.

Local testing: Decryption uses browser fetch and Web Crypto. It works from the published HTTPS site. Opening index.html directly from disk (file://) may not work for encrypted-file fetches. You may test locally with python3 -m http.server 8000 and visit http://localhost:8000.

Note: Do not upload this ZIP itself as a single file to GitHub Pages; upload its extracted contents.

UPDATE: 23 October 2026
Campaign Resources now includes 01 Preparing for the Autonomous Enterprise and 03 Road to Zero Master v32.
Sales Enablement retains 02 AI Readiness Gap, linking to Crossfuze-AI-Maturity-Document.html (included in root).
Upload this new HTML file to the same folder as index.html. Keep the encrypted CARS assets.

STATUS CLARIFICATION: 23 October 2026
All listed campaign guides, campaign hubs and supporting resources are LIVE except Road to Zero Master v32, which is an unpublished working master. The Road to Zero Campaign Hub is live and separate.
IMPORTANT: The working master is still included as an unencrypted HTML file in this GitHub package; uploading it to a public GitHub Pages repository makes the file publicly accessible even though it is not an officially published campaign. Do not upload it if it must remain restricted.
