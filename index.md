---
title: "[Lesson 2: Your Practical Page](https://github.com/stri-con/dc-single/blob/master/index.Rmd)"
author: "by Jarrod"
date: "14 April, 2020"
smart: true
output:
  html_document:
    theme: journal
    toc: true
    toc_float: true
    toc_depth: 3
    highlight: tango
    keep_md: true
    self_contained: true
#output:
#  epuRate::epurate:
#    toc: TRUE
#    number_sections: FALSE
#    code_folding: "show"
editor_options: 
  chunk_output_type: inline
---



## Overview

Welcome to the hands-on, practical learning portion of [Lesson 2](https://stri-con.github.io/data-curation/2020/04/09/lesson-2/) where you will create a single page R Markdown document. I made this page to help guide you in the process. The material below contains a series of assignments and challenges designed to get you comfortable utilizing [YAML metadata](https://stri-con.github.io/data-curation/2020/04/09/lesson-2/#the-yaml-header-1), [Markdown syntax](https://stri-con.github.io/data-curation/2020/04/09/lesson-2/#markdown-formatted-text-1), and [R code chunks](https://stri-con.github.io/data-curation/2020/04/09/lesson-2/#r-code-chunks-1). 

The page itself is written almost entirely in R Markdown, meaning there is no extensive use of anything fancy like complicated  CSS or HTML. I will introduce some simple HTML code you can use to jazz up your document a little. You should be able to solve any problem I present by digging around in the raw code on GitHub, consulting the [Resources page](https://stri-con.github.io/data-curation/page/resources/), using one of the targeted search strategies described in the [Problem Solving post](https://stri-con.github.io/data-curation/2020/04/03/help/), and/or posting a question to the Slack channel.

## Some Keys to Success

> **Knit often**. Whenever you make a change to the YAML header, add a new code chunk, etc., re-knit (or render) your document. This is very important. Regular knitting allows you to **a**) see the effects of a change and **b**) track down (troubleshoot) issues more easily. 
>
> Simply hit the knit button or use the shortcut keys---on MacOS `Cmd`+`Shift`+`K` and Windows `Ctrl`+`Shift`+`K`. Learn to love these shortcut keys. They will save you time. 

You can choose how your document is previewed using the dropdown menu in the document settings. `Preview in Window` opens the document in a separate RStudio window and `Preview in Viewer Pane` lets you see the document in the main RStudio IDE. These are good for *quick* looks. You should **always** double-check the actual HTML file because sometimes things look different in RStudio. 
<br/>

![](files/preview.png)

Something to consider while you create your page is *readability*. This not only applies to the final document but also the raw R Markdown code itself. Think about someone digging through your code to figure out how you did something. Or think about yourself coming back to the code after a few years. The better your document is formatted, the easier it will be to understand. In future lessons we will return to some best practices but for now remember, part of what we are doing here is making your science more *transparent* and *reproducible*. If your document is confusing to follow then it serves neither of these purposes.

## Assignment 1: The Basics

In the first assignment, you will employ some basic techniques to control the look of your document and how R code chunks are rendered. We will cover YAML metadata modifications, setting global chunk options, and writing Markdown content. You will also learn about testing R code first before rendering the final document.

### 1.1 Make a Document

If you have not already done so, your first task is to create an R Markdown document. Open R Studio and go to `File > New File > R Markdown`. A window should pop up where you can fill in the details. It is not important what you put here since you can change it at any time. What is important is that **Document** and **HTML** are both selected. We will cover other document types in the future. Hit `Ok` and follow the steps in this graphic. Remember, you do not need to add a file extension when you save the document. 

<br/>

![Building your initial R Markdown document.](files/make-rmd.gif)

<br/>

Once you have a document built and saved, there should be a `.html` file in your working directory. Double-click that file---it should open in your default browser. Each time you re-knit the `.Rmd` file, you can just refresh the browser page or double-click the file again. 

### 1.2 Add Markdown Text

Your first task is to add some content and format the content with Markdown. This doesn't need to be anything fancy to start. You can either add text as you go or paste a large amount of text in at once. Dealers choice. You can use the [Markdown](https://stri-con.github.io/data-curation/2020/03/28/lesson-0/#markdown-3) section of Lesson 0 or the [Markdown](https://stri-con.github.io/data-curation/page/resources/#markdown) section from the Resources page for reference. 

1) Add headers to give the document structure. Use different header levels.
2) Add hyperlinks. We will learn about *internal* links later. For now, just link to outside websites.
3) Add emphasis formatting like bold, italics, and block text. 
4) Mix and match formatting, like make a hyperlink bold or add italics to block text. 
5) Make a list of items. 

### 1.3 Modify & Test R Code Chunks

Now it is time to get some practice modifying code chunk options so you can gain more control over the behavior of code and result display. If you have your own R code you are more than welcome to use it here. I will use the default code chunks that were added to the `.Rmd` file. Please see the section on [Chunk structure & options](https://stri-con.github.io/data-curation/2020/04/09/lesson-2/#chunk-structure-options-1) from Lesson 2 for more details. 

Here are the two default code chunks. As you can see, both have names and the second chunk has a single option. 

````
```{r cars}
summary(cars)
```
````

````
```{r pressure, echo=FALSE}
plot(pressure)
```
````

There are many code chunk options you can control. Which options you use and how you set them will be determined by your needs. Test the behavior of the following options by setting each equal to either `TRUE` or `FALSE`. Render the document and see if you can figure out what changed. Each of these has a default value so you may not see a change until you set the alternative value. 

1) `echo`
2) `collapse`
3) `eval`
4) `prompt`
5) `highlight`
6) `include`

Next, it is a really good habit to check code chunks as you add them. This will ensure that each chunk works, making it easier to track down problems. If you refer to the first image on this page, you can you have options for **Chunk Output**---*Inline* and *Console*. This controls where the output is displayed. Let's take a quick look at a code chunk in RStudio and see how you test chunks before rendering. 

![](files/run-chunk.png)

Take a look at the tool bar on the far right. **Option 1** is a dropdown menu that gives you an alternative way to set code chunk options. **Option 2** will *Run all Code Chunks Above* meaning that RStudio will run all code chunks above the current chunk but not the current chunk itself. And **Option 3** will *Run the Current Chunk*. Incidentally, if you do not see these options it means something is wrong with the chunk. 

Go ahead and run the chunk. 

### 1.4 Modify YAML Metadata

You last task is to modify the YAML header to suit your needs and tastes. I would like you to experiment with different options and settings to see what happens in the final document. 

1) Run `?rmarkdown::html_document` or `?html_document` in the Console to see the header options for an HTML document.
2) Add a table of contents and include options that modify the behavior of the table of contents.
3) Add the option to keep the Markdown document. This will save a `.md` copy of your file. 
4) Open the `.md` file in a text editor. This is the output from `knitr`---after all R code has been processed---and what PanDoc uses to generate an HTML file. Keep this file open as you build your document. Pay attention to how your R code is converted to Markdown syntax.
5) Change the theme. Options are listed on the *Convert to an HTML document* help page you opened in RStudio. Try a few options and see what happens.
6) Change the code highlight option. These too are listed on the help page. Try a few options and see what happens.

### The End

...of Assignment 1 that is. These exercises should give you an idea of some techniques you can use to tweak the behavior of your document. Assignment 2 will be similar in structure and released in a day or so. More on that soon. 
