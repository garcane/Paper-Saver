This is a scanned PDF that needs to be reconstructed into a genuinely editable, structured document.

The objective is not simply to OCR the PDF and extract its text. Instead, reconstruct the document as faithfully as possible, preserving both its semantic structure and its visual/layout structure.

Text and document structure

Convert all reliably readable text into actual editable text rather than leaving it as part of a scanned page image.

Preserve, as closely as possible:

* page order and page boundaries
* headings and heading hierarchy
* paragraphs and paragraph breaks
* columns and reading order
* numbered and bulleted lists
* tables
* captions
* footnotes/endnotes
* headers and footers
* references and citations
* equations and mathematical notation
* section breaks and other meaningful document structure

Where the original layout is important to understanding the content, reproduce that layout rather than simply placing all text into a linear sequence.

Images, figures, and diagrams

Where possible, reconstruct diagrams, charts, flowcharts, schematics, line drawings, symbols, and other vector-like graphics as editable SVG files and embed them in the resulting document.

Preserve the original figures as closely as possible, including:

* geometry and proportions
* labels and text
* arrows and connectors
* shapes
* lines
* colours
* symbols
* relative positioning

Do not force photographs or inherently raster-based imagery into SVG. Where an image is better represented as raster content, preserve it in an appropriate image format instead.

Fidelity and accuracy

The priority is to preserve the information and structure of the original PDF.

Do not invent, infer, or substantially alter content that cannot be reliably read or reconstructed. If a particular element cannot be reconstructed accurately, preserve the original element as an embedded image where possible rather than guessing.

Maintain the original page sequence and aim for a visually faithful reconstruction while ensuring that the underlying text remains genuinely editable and machine-readable.

Output

Prefer a Microsoft Word .docx document as the final output, provided it can adequately support the required structure and embedded SVGs.

The final document should therefore be:

1. genuinely editable,
2. machine-readable,
3. structurally faithful to the source PDF,
4. visually faithful where practical, and
5. usable by downstream language models for extracting and understanding the document’s information.

The scanned PDF should be treated as the authoritative source. Do not add information that is not present in the source.
