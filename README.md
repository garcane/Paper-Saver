# Paper Saver

Turn scanned PDFs into genuinely editable, structured documents while preserving the original document's content, structure, and layout as closely as practical.

Paper Saver is designed for document-reconstruction workflows where ordinary OCR is not enough. The goal is to recover **editable text and document structure**, rather than simply placing OCR text on top of scanned page images.

## What it does

The included skill instructs an AI document-processing workflow to:

- Reconstruct reliably readable text as editable text.
- Preserve page order and meaningful page boundaries.
- Maintain heading hierarchy, paragraphs, lists, tables, captions, and references.
- Preserve columns and reading order where relevant.
- Reconstruct footnotes, endnotes, headers, and footers where possible.
- Recreate diagrams, charts, flowcharts, and schematics as editable SVG where practical.
- Keep photographs and inherently raster imagery as raster images rather than forcing them into SVG.
- Prioritise fidelity to the scanned PDF and avoid inventing unreadable content.
- Produce a Microsoft Word `.docx` document where the required structure can be supported.
- Keep the resulting document machine-readable and suitable for downstream language-model processing.

## Repository structure

```text
Paper-Saver/
├── README.md
└── SKILL.MD
```

### `SKILL.MD`

The core instruction set for the document-reconstruction workflow. It defines the expected behaviour, fidelity requirements, treatment of images and diagrams, and output requirements.

## Installation

Paper Saver is a prompt/skill definition rather than a conventional Python package, so there is no `pip install` step and no dependency file is required.

### Option 1 — Claude / compatible AI skill workflow

1. Clone or download this repository.
2. Open `SKILL.MD`.
3. Add the skill to your AI assistant's supported skills/instructions location, following that platform's skill-import process.
4. Provide the scanned PDF as the input document.
5. Ask the assistant to reconstruct the PDF into an editable document using the Paper Saver skill.
6. Review the generated `.docx` for OCR errors, layout differences, equations, tables, and figures before treating it as a final archival copy.

### Option 2 — Use the instructions directly

If your AI platform does not support a formal skill system:

1. Download or copy the contents of `SKILL.MD`.
2. Supply those instructions as the system/context prompt for your document-processing workflow.
3. Upload the scanned PDF.
4. Request an editable `.docx` reconstruction.
5. Validate the output against the original PDF.

## Usage

A typical request is:

> Reconstruct the attached scanned PDF into a genuinely editable Word document using the Paper Saver instructions. Preserve the text, page structure, tables, figures, references, equations, and layout as faithfully as possible. Do not invent unreadable content.

The scanned PDF should always be treated as the authoritative source.

## Recommended workflow

```text
Scanned PDF
    ↓
Paper Saver instructions
    ↓
OCR + document understanding
    ↓
Structure reconstruction
    ↓
Figure / diagram reconstruction
    ↓
Editable .docx
    ↓
Visual + content quality check
```

## Quality-control checklist

Before considering a reconstruction complete, check:

- [ ] Every page is present and in the correct order.
- [ ] Headings and subheadings retain their hierarchy.
- [ ] Paragraphs and line breaks are sensible.
- [ ] Multi-column pages follow the correct reading order.
- [ ] Tables retain their rows, columns, and labels.
- [ ] Captions are associated with the correct figures.
- [ ] Footnotes/endnotes are retained where possible.
- [ ] References and citations have not been silently dropped.
- [ ] Equations and mathematical notation are accurate.
- [ ] Diagrams and vector-like figures are reconstructed where practical.
- [ ] Photographs and raster imagery remain appropriately represented.
- [ ] Unreadable material has not been fabricated.
- [ ] The resulting Word document contains actual editable text rather than page-sized screenshots wherever reconstruction is possible.
- [ ] The final document has been visually compared with the source PDF.

## Important limitations

Paper Saver is intended to improve document reconstruction, not guarantee perfect recovery of every scanned document. Results can be affected by scan quality, handwriting, unusual fonts, complex page layouts, damaged pages, mathematical notation, and low-resolution figures.

When an element cannot be reconstructed reliably, preserving the original element as an image is preferable to guessing its content.

## Contributing

Improvements are welcome, particularly around:

- OCR accuracy
- complex table reconstruction
- mathematical notation
- SVG diagram reconstruction
- multi-column layouts
- document validation
- compatibility with additional AI skill platforms

When modifying `SKILL.MD`, preserve its core principle: **fidelity to the source document takes priority over filling gaps with assumptions.**

## License

No license has currently been specified for this repository. If you intend to allow reuse, modification, or redistribution, add an appropriate open-source license file.
