PDF Annotation Tool
This is a simple Python script for annotating PDF files by highlighting specified keywords. The script uses the fitz module from PyMuPDF to open, search, and annotate PDF documents.

Requirements
Python 3.x
PyMuPDF (fitz)

pip install PyMuPDF

import fitz  # PyMuPDF

def process_pdf_anno(pdf_path, keywords):
    doc = fitz.open(pdf_path)
    for page_num in range(doc.page_count):
        page = doc[page_num]
        text_instances = []
        for keyword in keywords:
            text_instances.extend(page.search_for(keyword.strip()))

        for inst in text_instances:
            highlight = page.add_highlight_annot(inst)
            highlight.set_colors(stroke=(1, 1, 0))
            highlight.update()
    output_path = pdf_path.replace(".pdf", "_annotated.pdf")
    doc.save(output_path)
    doc.close()

    print(f"Annotated PDF saved as: {output_path}")

if __name__ == "__main__":
    pdf_path = "sem.pdf"
    keywords = ["syed Abjimiah"]
    process_pdf_anno(pdf_path, keywords)
Output
The script will generate an annotated PDF file with the _annotated.pdf suffix added to the original filename (e.g., sem_annotated.pdf).

Customization
PDF Path: Change the pdf_path variable to point to your PDF file.
Keywords: Modify the keywords list to include the words or phrases you want to highlight.
