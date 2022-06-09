# Penguin practice  

Some instructions for exploring R Markdown using the `penguins_demo.Rmd` file.  

To work through these exerciese, you will need `knitr` and `tinytex` installed on your computer. Also note, the excersises assume you are using R Studio. 

## Getting started  
- Download the file `penguins_demo.Rmd` from this repo. Right-click the file name to save. Make sure to save in a reasonable location on your machine - a directory named `temp` or `penguin exercise` for example.    
- Open the file in R Studio. Note that I usually suggest using an R Project, but for this simple demo that's not necessary  
- Click the 'knit' button at the top of the document pane. This should knit the document to an HTML file. Rendering the document now will verify that you are not missing any packages or other errors.  
- Verify that the HTML file was created in the directory where you saved the .Rmd file. Open the HTML file in a browser and take a quick look at the output.   

For the next exercises, you can make one change and re-knit the file, or you can make several changes and see how the output changes.

## Modify the HTML output
- Add a table of contents by modifying the YAML header
```yaml
output: 
  html_document:
    toc: true
```
- Add the following text in a block quote before the first section (Penguin mass vs. flipper length)  
```markdown
> The goal of palmerpenguins is to provide a great dataset for data exploration & visualization. 
> Data were collected and made available by Dr. Kristen Gorman and the Palmer Station, Antarctica LTER, a member of the Long Term Ecological Research Network.
```


