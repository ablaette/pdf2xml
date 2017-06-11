Turn pdf document into XML
==========================

This is an experimental package to turn a pdf document document into a XML document
for further processing in a corpus preparation pipeline.

The class PDF includes a set of methods to handle somewhat tricky problems that may 
arise when processing pdf documents:
- Text outside a region (such as page numbers) can be removed based in coordinates;
- Two columns can be rearranged so that a two-column-layout can be managed;
- If the document has been scanned in tilted fashion, lines are reconstructed;
- Paragraphs can be reconstructed based on a simple heuristic.

Comparing pdf2xml to other packages such as poppleR or pdftools, the existing packages
do not offer the aforementioned pruning and reconstruction capability.
