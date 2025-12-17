# Scrubber

A simple, standalone HTML tool to **remove sensitive metadata** from Office documents – completely in your browser, with **no data leaving your computer**.

**Primary use case:**  
This program is designed to remove metadata from exam papers (text files) that are delivered to the teacher or examiner who will grade them. This ensures **100% anonymity** in situations where it is required that the person grading a student's exam does not know the identity of the student.

Supports:
- Microsoft Office formats: `.docx`, `.xlsx`, `.pptx`
- OpenDocument formats (LibreOffice/OpenOffice): `.odt`, `.ods`, `.odp`

Perfect for schools, universities, and any examination setting that requires blind grading.

## Where to donwload
that is easy -> [Click here to download Scrubber](https://github.com/rSignal86/Scrubber/archive/refs/heads/main.zip)

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
- Uses your custom JSZip build first, with automatic fallback to official CDN

## How to Use

1. Download or clone this repository.
2. Open `Scrubber.html` in any modern web browser (Chrome, Edge, Firefox, etc.).
3. Drag your exam files into the drop zone or click to select them.
4. Check/uncheck the metadata types you want to remove (recommended: leave all checked for full anonymity).
5. Click **"Scrub files and download as ZIP"**.
6. Extract the downloaded `scrubbed_files.zip` – the cleaned, anonymous files are ready for submission or grading.

> No internet connection required after the initial load (except for loading JSZip).

## Privacy & Security

- All processing happens **locally in your browser**.
- No files are uploaded anywhere.
- The tool uses JSZip to read and modify the ZIP-based document structure directly in memory.
- Ideal for protecting student privacy during anonymous grading.

## Technical Details

- Built with plain HTML, CSS, and vanilla JavaScript
- Uses [JSZip](https://stuk.github.io/jszip/) (custom minified version hosted in this repo)
- Modifies `docProps/core.xml` (OOXML) or `meta.xml` (ODF) to clear selected metadata fields

## Files

- `Scrubber.html` – The complete standalone application
- `data/jszi1p.min.js` – Custom minified JSZip library (used as primary source)

## License

This project is open source and free to use, modify, and distribute.

Feel free to fork, improve, or share!

---

Made with ❤️ for privacy and fair assessment by a dude that works in a school