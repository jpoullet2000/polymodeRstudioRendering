---
title: "How to generate RStudio good-looking html from polymode in emacs"
author: "Jean-Baptiste Poullet"
date: '2015-01-21'
output: html_document
---

This is a document to explain how to use emacs and its [polymode mode](https://github.com/vspinu/polymode) to generate RStudio-like HTML file. 

## <a name="convertHTML"></a> Generate your HTML file from Emacs/polymode mode. 

Polymode allows you to use knitr with Rmd files and export them to many output format (using the Pandoc exporter). To do so, one just type *alt-n e* and choose the output format in the list of available formats (HTML, Beamer tex, epub, md, etc). You need to select *HTML 5 (html)*.
Since you can use knitr, you can have R code embedded in your document.

```r
library(knitr)
kable(head(iris))
```



| Sepal.Length| Sepal.Width| Petal.Length| Petal.Width|Species |
|------------:|-----------:|------------:|-----------:|:-------|
|          5.1|         3.5|          1.4|         0.2|setosa  |
|          4.9|         3.0|          1.4|         0.2|setosa  |
|          4.7|         3.2|          1.3|         0.2|setosa  |
|          4.6|         3.1|          1.5|         0.2|setosa  |
|          5.0|         3.6|          1.4|         0.2|setosa  |
|          5.4|         3.9|          1.7|         0.4|setosa  |

## <a name="material"></a> Transform your ugly HTML file in a good-looking RStudio-like HTML file

To convert your HTML file, put the following files into the same directory (it is not per se needed but you might need to change the .sh script otherwise)

- RStudioHTML-style
- createNiceHTMLFromPolymode.sh

Then execute

./createNiceHTMLFromPolymode.sh <yourHTMLfile> <HTMLoutputfile>

That's it. You should have your nicely formatted HTML file.
Thanks to RStudio developers for providing this style and makes life nicer ;).

