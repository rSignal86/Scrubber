# Scrubber

A simple, standalone HTML tool to **remove sensitive metadata** from Office documents – completely in your browser, with **no data leaving your computer**.

**Primary use case:**  
This program is designed to remove metadata from exam papers that are delivered to the teacher or examiner who will grade them. This ensures **100% anonymity** in situations where it is required that the person grading a student's exam does not know the identity of the student.

Supports:
- Microsoft Office formats: `.docx`, `.xlsx`, `.pptx`
- OpenDocument formats (LibreOffice/OpenOffice): `.odt`, `.ods`, `.odp`

Perfect for schools, universities, and any examination setting that requires blind grading.

## Download

Easy to get started – [Click here to download Scrubber](https://github.com/rSignal86/Scrubber/archive/refs/heads/main.zip)

## Features

- **100% client-side** – No uploads, no servers, no tracking
- Drag & drop or click to select multiple files (up to 50 at once)
- Choose exactly which metadata to remove:
  - Author / Creator
  - Last Modified By
  - Created Date
  - Modified Date
  - Title
  - Subject
- Automatically adds `_SCRUBBED` to cleaned filenames (e.g., `exam.docx` → `exam_SCRUBBED.docx`)
- Downloads all cleaned files in a single `.zip` archive
- Uses a custom JSZip build first, with automatic fallback to the official CDN

## How to Use

1. Download or clone this repository.
2. Open `Scrubber.html` in any modern web browser.
3. Drag your exam files into the drop zone or click to select them.
4. Check/uncheck the metadata types you want to remove (recommended: leave all checked for full anonymity).
5. Click **"Scrub files and download as ZIP"**.
6. Extract the downloaded `scrubbed_files.zip` – the cleaned, anonymous files are ready for submission or grading.


## Privacy and GDPR Compatibility

**Privacy has been the highest priority throughout the entire development of Scrubber.**  
The tool is deliberately designed to keep all processing local to your device, ensuring that no document content or personal data ever leaves your browser.

For full details on how Scrubber handles privacy, external requests, and its alignment with GDPR requirements, please see the dedicated documents:

- [Data Processing Statement - English](DataProcessingStatement.md) – Explains the roles under GDPR and why Scrubber is **not** a data processor (no Data Processing Agreement required).
- [Privacy Notice and GDPR Compatibility](PrivacyAndGDPRCompatibility.md) – Detailed information about client-side processing, minimal external requests (JSZip loading and version check), and how the tool supports GDPR principles such as data minimization, transparency, and privacy by design.

These documents confirm that:
- No file contents or metadata are transmitted anywhere.
- The only external requests are for loading a public JavaScript library and checking for updates – neither includes any user or document data.
- The risk of a personal data breach originating from Scrubber is effectively zero.

## Technical Details

- Built with plain HTML, CSS, and vanilla JavaScript
- Uses [JSZip](https://stuk.github.io/jszip/) (custom minified version hosted in this repo as primary source)
- Modifies `docProps/core.xml` (OOXML) or `meta.xml` (ODF) to clear selected metadata fields

## Files in the Repository

- `Scrubber.html` – The complete standalone application
- `data/jszi1p.min.js` – Custom minified JSZip library (primary source)
- `DataProcessingStatement.md` – Data processing statement in english
- `DatabehandlerAvtale.md` – Data processing statement in Norwegian
- `PrivacyAndGDPRCompatibility.md` – Detailed privacy notice and GDPR compatibility
- `README.md` – This file

## License

This project is open source and free to use, modify, and distribute.

Feel free to fork, improve, or share!

---

Made with ❤️ for privacy by someone who works in a school
