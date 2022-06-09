# Penguin practice  

Some instructions for exploring R Markdown using the `penguins_demo_clean.Rmd` file.  

To work through these exerciese, you will need `knitr` and `tinytex` installed on your computer. Also note, the excersises assume you are using R Studio. 

## Getting started  

- Download the file `penguins_demo_clean.Rmd` from this repo. Right-click the file name above to save. Make sure to save in a reasonable location on your machine - a directory named `temp` or `penguin exercise` for example.    
- Open the file in R Studio. Note that I usually suggest using an R Project, but for this simple demo that's not necessary  
- Click the 'knit' button at the top of the document pane. This should knit the document to an HTML file. Rendering the document now will verify that you are not missing any packages or other errors.  
- Verify that the HTML file was created in the directory where you saved the .Rmd file. Open the HTML file in a browser and take a quick look at the output.   

For the next exercises, you can make one change and re-knit the file, or you can make several changes and see how the output changes.  

If you get stuck, open the Markdown Quick Reference in R Studio under 'Help'  

## Adjust chunk settings

- In the initial chunk, `knitr::opts_chunk$set()` sets several options for the entire document (although these options can be modified in individual chunks later on). Change `collapse = TRUE` to `collapse = FALSE` and re-knit the file. What changes?  
- Add the option `echo = FALSE` and re-run the file. What changes? When might this option be useful?  
- Run the chunk `mass-flipper` without knitting the document. Notice that a warning appears along with the plot. Use the option `warning` to suppress this output for this chunk only.  
- Change the dimensions of the plots by altering the `fig.width`, `fig.height`, and `fig.asp` options for a specific chunk. Note that it's best to change only two of these at a time, for example change `fig.width=6` and `fig.height=4`. Knit the file and see how it looks.   
- Now change the plot dimensions using the following options: `out.width="90%"`. How is this different from what you saw before? 

## Add inline code

- Calculate the mean bill length of all penguins. Write a sentence that includes this number, with the R code for the calculation inline with the text. 
```markdown
The average bill length of all penguins is `r mean(penguins$bill_depth_mm, na.rm=TRUE)` mm. Huh, I would've thought it was longer.
```
What happens if you do not include `na.rm = TRUE` in the function? 
How can you evaluate this function without rendering the file?  

## Modify the HTML output

- Add a table of contents by modifying the YAML header  

```yaml
title: "Example graphs using the penguins data"
output: 
  html_document:
    toc: true
```
- Make the TOC float, then open the file in a browser and test it out  

```yaml
title: "Example graphs using the penguins data"
output: 
  html_document:
    toc: true
    toc_float: true
```
- Add the following text in a block quote before the first section (Penguin mass vs. flipper length)  

```markdown
> The goal of palmerpenguins is to provide a great dataset for data exploration & visualization. Data were collected and made available by Dr. Kristen Gorman and the Palmer Station, Antarctica LTER, a member of the Long Term Ecological Research Network.
```
- Create tabs by adding a top-level header with `tabset`. Add this code immediately after the blockquote you added above.  

```markdown
# Penguin Plots {.tabset}
```
- You can also add HTML tags into an R Markdown document. Add a line of text to the document, and use HTML tags to make the font bigger. If you know HTML, you can incorporate into R Markdown.  

```markdown
<font size="+20">
The most amazing penguin data ever!
</font>
```

## Try different outputs
- Change the YAML header output setting to a Word document and render the file. How does it look?  
```yaml
title: "Example graphs using the penguins data"
output: 
  word_document:
    toc: true
```
- Change the YAML header output setting to a PDF (make sure you have tinytex installed). Add your name as an author and the date.  
```yaml
title: "Example graphs using the penguins data"
author: Your Name
date: Today's date
output: 
  pdf_document:
    toc: true
```
- Try rendering to multiple output formats at once! 
- Try removing the `output` option from the YAML header. What happens if you knit the file?  

## Add a table
- Create a new R chunk and name it `table`. Subset the `penguins` dataset to only Chinstrap penguins and create a table of only the first 10 entries in the Chinstrap dataset.  
```markdown
'``{r table}
chinstrap <- subset(penguins, species=="Chinstrap")
kable(head(chinstrap, 10), caption = "Penguin data")
'``
```  
- Many additional packages exist for formatting tables in PDF, HTML, etc. Check out options in the [R Markdown Cookbook](https://bookdown.org/yihui/rmarkdown-cookbook/table-other.html)

This is just scratching the surface of what R Markdown can do! 
