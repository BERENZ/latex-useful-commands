# Sort bibliograhy file

```
bibtool -s -i input.bib -o output.bib
```

# Insert bibliograhy entry into text
```
\usepackage{bibentry} % enter bibentry into text
\nobibliography*
\bibentry{laney2001}
\bibliographystyle{apalike}
\nobibliography{../reports/bibliography.bib}
```
