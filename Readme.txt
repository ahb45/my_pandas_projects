
Difference between original version and RTL version is  def set_cell_alignment_right

in only make word files

******************* in original version   ****************
def set_cell_alignment_right(cell):
    for paragraph in cell.paragraphs:
        paragraph.alignment = WD_ALIGN_PARAGRAPH.RIGHT

*******************  in RTL version  ********************
def set_cell_alignment_right(cell):
    for paragraph in cell.paragraphs:
        paragraph.alignment = WD_ALIGN_PARAGRAPH.RIGHT
        pPr = paragraph._element.get_or_add_pPr()
        bidi = OxmlElement('w:bidi')
        bidi.set(qn('w:val'), '1')
        pPr.append(bidi)