# Simple exercise template
Very simple LaTeX template for simple assignments or homework

## Tricks

`sed` oneliner for replacing figure markers (such as `(1.2)`) with latex which include an image (named 1\_2.png)

`sed '/([[:digit:]].[[:digit:]])/ {s/\./_/;s/(/\n% <autoincludegraphics>\n\\begin{figure}\n\t\\centering\n\t\\includegraphics[width=0.7\\textwidth]{/; s/)/.png}\n\\end{figure}\n% <\/autoincludegraphics>\n/}'`

Same, but for images in a subfolder named FOLDER
`sed '/([[:digit:]].[[:digit:]])/ {s/\./_/;s/(/\n% <autoincludegraphics>\n\\begin{figure}\n\t\\centering\n\t\\includegraphics[width=0.7\\textwidth]{FOLDER\//; s/)/.png}\n\\end{figure}\n% <\/autoincludegraphics>\n/}'`

When replacing the FOLDER in this oneliner make sure to escape special characters and whitespaces. If you're not sure if it's a special character it probably is. It's easier if the folder name doesn't contain spaces or special characters.
