---
title: "[Lesson 2: Your Practical Page](https://github.com/stri-con/dc-single/blob/master/index.Rmd)"
author: "by Jarrod"
date: "22 April, 2020"
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
    code_download: true
    code_folding: hide
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

You can choose how your document is previewed using the drop down menu in the document settings. `Preview in Window` opens the document in a separate RStudio window and `Preview in Viewer Pane` lets you see the document in the main RStudio IDE. These are good for *quick* looks. You should **always** double-check the actual HTML file because sometimes things look different in RStudio.
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

Take a look at the tool bar on the far right. **Option 1** is a drop down menu that gives you an alternative way to set code chunk options. **Option 2** will *Run all Code Chunks Above* meaning that RStudio will run all code chunks above the current chunk but not the current chunk itself. And **Option 3** will *Run the Current Chunk*. Incidentally, if you do not see these options it means something is wrong with the chunk.

Go ahead and run the chunk.

### 1.4 Modify YAML Metadata

You last task is to modify the YAML header to suit your needs and tastes. I would like you to experiment with different options and settings to see what happens in the final document.

1) Run `?rmarkdown::html_document` or `?html_document` in the Console to see the header options for an HTML document.
2) Add a table of contents and include options that modify the behavior of the table of contents.
3) Add the option to keep the Markdown document. This will save a `.md` copy of your file.
4) Open the `.md` file in a text editor. This is the output from `knitr`---after all R code has been processed---and what PanDoc uses to generate an HTML file. Keep this file open as you build your document. Pay attention to how your R code is converted to Markdown syntax.
5) Change the theme. Options are listed on the *Convert to an HTML document* help page you opened in RStudio. Try a few options and see what happens.
6) Change the code highlight option. These too are listed on the help page. Try a few options and see what happens.

## Assignment 2: Tables

In this assignment, you will explore different methods of incorporating tables in your document. The choice of method depends on **a**) the type of data, **b**) the amount of data, and **c**) the desired output. I will cover a few tools for creating tables but please note there are [many options](https://rfortherestofus.com/2019/11/how-to-make-beautiful-tables-in-r/) out there, so look around and let us know if you find a tool you like.

For each example, I will use the `mtcars` data set from the `datasets` package. The `mtcars` data set has 32 rows and 11 columns. Feel free to load your own data table or use the `mtcars` data set.

### Tools

You will use four different tools in this assignment for making tables. Here is a summary table of of each tool. 

| Table type                    | Table size       |  Formatting Options  | Skill Level      |
|-------------------------------|:----------------:|:--------------------:|:----------------:|
| `markdown`                    | small            | minimal              | beginner         |
| `rmarkdown::paged_table`      | large            | minimal              | beginner         |
| `knitr::kable` + `kableExtra` | small            | extensive            | intermediate     |
| `DT` + `DataTables`           | large            | extensive            | advanced         |
Table: *Table types and recommended uses.*

<br/>

### 2.1 Markdown

The simplest method of building a table is with Markdown syntax. This is a nice option because you can hard code the table right into the document---no need to install and load libraries or write code chunks---and it is easy to implement. The downside is there is minimal functionality available in a Markdown table.

Markdown does not work well for large tables. So I will first grab a subset of `mtcars`, specifically the first 4 rows and 3 columns. In my code chunk I add the chunk option `comment=""`. This prevents knit from appending a string (default is `##`) to the start of each line of results in the final document.


```r
mtcars_sub <- mtcars[1:4,1:3]
mtcars_sub
```

```
                mpg cyl disp
Mazda RX4      21.0   6  160
Mazda RX4 Wag  21.0   6  160
Datsun 710     22.8   4  108
Hornet 4 Drive 21.4   6  258
```

<br/>

*Incidentally, the results box above is technically the simplest table you can make, either by calling the data frame `mtcars_sub` directly or running `print.data.frame(mtcars_sub)`.*

Anyway, run this code chunk, copy the results, and make a Markdown table. You can either run the chunk in RStudio without rendering the document (described above) or render the document and copy the results from HTML page. I added a header to the first column. And here is the Markdown table.

<br/>

| model                                                             |  mpg   |  cyl |  disp     |
|:------------------------------------------------------------------|:------:|:----:|----------:|
| [Mazda RX4](https://sco.wikipedia.org/wiki/Mazda_RX-4)            | *21.0* | **6**|    160    |
| `Mazda RX4 Wag`                                                   | *21.0* |   6  |    160    |
| [Datsun 710](https://en.wikipedia.org/wiki/Nissan_Violet#710)     | *22.8* |   4  |    108    |
| [Hornet 4 Drive](https://en.wikipedia.org/wiki/AMC_Hornet)        | 21.4   |   6  |  **258**  |
Table:  *Demonstration of the output from `pipe_tables` Markdown syntax.*

<br/>

Since this is a Markdown table, you can add additional Markdown syntax for formatting. See if you can figure out what syntax I added to my table and add some to your table. Also check out the *Tables* section of [PanDoc User's Guide](https://pandoc.org/MANUAL.html#tables) for other Markdown table options, including how to add a caption. In addition to `pipe_tables`, you can create `multiline_tables` `grid_tables`, and `simple_tables`.

Something to notice is that the Markdown table spans the entire width of the page---even though it does not need all of that space. As far as I know, there is no way to control this behavior without adding additional HTML formatting.

> **Recommendation** Use `Markdown` for small, simple tables where styling is not a concern.

### 2.2 R Markdown Paged Tables

With larger tables, it may not be practical to display the full table inline. So we need a way to shrink a large table so it looks good while still allowing access to the full table.

The next type of table I want you to try are Paged Tables. R Markdown comes with its own built in table function called `paged_table`. The `paged_table` function allows pagination of rows and columns making it possible to render a large table in a small space.

It is easy to code `paged_table` but that ease comes with a small price---limited functionality. Here are the options you do have with `paged_table` function.

| Option           | Description                                    |
|------------------|------------------------------------------------|
| `rows.print`     | Maximum rows to print per page.                |
| `max.print`      | Maximum rows in the table (defaults to 1000).  |
| `cols.print`     | Maximum columns in the table (defaults to 10). |
| `rownames.print` | Print row names as part of the table.          |
Table: *A Markdown table listing the Options for the `paged_table` function. *

***A quick side note***. You actually need to load the `rmarkdown` package for `paged_table` to work. Anyway, this is a good time to return to the first code chunk in your `.Rmd` file---the chunk called `setup` that R Markdown added by default.

I like to use this chunk to load all of the packages I need for my document. Using a single chunk for all of my packages helps me keep my document organized. Notice the `setup` chunk has the option `include=FALSE`. This prevents the content of the chunk from appearing in the final document, which for me is more stylistically appealing.  I can add a `sessionInfo()` chunk at the end of my document to report all of the packages so this information is available to the reader. We will cover `sessionInfo()` when we get into more depth on the subject of *reproducible*. If you do not want to load the library you can run the command like this: `rmarkdown::paged_table()`.

***OK, back to the table***. Now I can create a table of `mtcars` with the `paged_table` function and use an option to limit the number of printed rows to `5` for each page. I used `echo=FALSE` in my code chunk to hide the code :). By now you should know where to look for a solution.

<br/>

<div data-pagedtable="false">
  <script data-pagedtable-source type="application/json">
{"columns":[{"label":[""],"name":["_rn_"],"type":[""],"align":["left"]},{"label":["mpg"],"name":[1],"type":["dbl"],"align":["right"]},{"label":["cyl"],"name":[2],"type":["dbl"],"align":["right"]},{"label":["disp"],"name":[3],"type":["dbl"],"align":["right"]},{"label":["hp"],"name":[4],"type":["dbl"],"align":["right"]},{"label":["drat"],"name":[5],"type":["dbl"],"align":["right"]},{"label":["wt"],"name":[6],"type":["dbl"],"align":["right"]},{"label":["qsec"],"name":[7],"type":["dbl"],"align":["right"]},{"label":["vs"],"name":[8],"type":["dbl"],"align":["right"]},{"label":["am"],"name":[9],"type":["dbl"],"align":["right"]},{"label":["gear"],"name":[10],"type":["dbl"],"align":["right"]},{"label":["carb"],"name":[11],"type":["dbl"],"align":["right"]}],"data":[{"1":"21.0","2":"6","3":"160.0","4":"110","5":"3.90","6":"2.620","7":"16.46","8":"0","9":"1","10":"4","11":"4","_rn_":"Mazda RX4"},{"1":"21.0","2":"6","3":"160.0","4":"110","5":"3.90","6":"2.875","7":"17.02","8":"0","9":"1","10":"4","11":"4","_rn_":"Mazda RX4 Wag"},{"1":"22.8","2":"4","3":"108.0","4":"93","5":"3.85","6":"2.320","7":"18.61","8":"1","9":"1","10":"4","11":"1","_rn_":"Datsun 710"},{"1":"21.4","2":"6","3":"258.0","4":"110","5":"3.08","6":"3.215","7":"19.44","8":"1","9":"0","10":"3","11":"1","_rn_":"Hornet 4 Drive"},{"1":"18.7","2":"8","3":"360.0","4":"175","5":"3.15","6":"3.440","7":"17.02","8":"0","9":"0","10":"3","11":"2","_rn_":"Hornet Sportabout"},{"1":"18.1","2":"6","3":"225.0","4":"105","5":"2.76","6":"3.460","7":"20.22","8":"1","9":"0","10":"3","11":"1","_rn_":"Valiant"},{"1":"14.3","2":"8","3":"360.0","4":"245","5":"3.21","6":"3.570","7":"15.84","8":"0","9":"0","10":"3","11":"4","_rn_":"Duster 360"},{"1":"24.4","2":"4","3":"146.7","4":"62","5":"3.69","6":"3.190","7":"20.00","8":"1","9":"0","10":"4","11":"2","_rn_":"Merc 240D"},{"1":"22.8","2":"4","3":"140.8","4":"95","5":"3.92","6":"3.150","7":"22.90","8":"1","9":"0","10":"4","11":"2","_rn_":"Merc 230"},{"1":"19.2","2":"6","3":"167.6","4":"123","5":"3.92","6":"3.440","7":"18.30","8":"1","9":"0","10":"4","11":"4","_rn_":"Merc 280"},{"1":"17.8","2":"6","3":"167.6","4":"123","5":"3.92","6":"3.440","7":"18.90","8":"1","9":"0","10":"4","11":"4","_rn_":"Merc 280C"},{"1":"16.4","2":"8","3":"275.8","4":"180","5":"3.07","6":"4.070","7":"17.40","8":"0","9":"0","10":"3","11":"3","_rn_":"Merc 450SE"},{"1":"17.3","2":"8","3":"275.8","4":"180","5":"3.07","6":"3.730","7":"17.60","8":"0","9":"0","10":"3","11":"3","_rn_":"Merc 450SL"},{"1":"15.2","2":"8","3":"275.8","4":"180","5":"3.07","6":"3.780","7":"18.00","8":"0","9":"0","10":"3","11":"3","_rn_":"Merc 450SLC"},{"1":"10.4","2":"8","3":"472.0","4":"205","5":"2.93","6":"5.250","7":"17.98","8":"0","9":"0","10":"3","11":"4","_rn_":"Cadillac Fleetwood"},{"1":"10.4","2":"8","3":"460.0","4":"215","5":"3.00","6":"5.424","7":"17.82","8":"0","9":"0","10":"3","11":"4","_rn_":"Lincoln Continental"},{"1":"14.7","2":"8","3":"440.0","4":"230","5":"3.23","6":"5.345","7":"17.42","8":"0","9":"0","10":"3","11":"4","_rn_":"Chrysler Imperial"},{"1":"32.4","2":"4","3":"78.7","4":"66","5":"4.08","6":"2.200","7":"19.47","8":"1","9":"1","10":"4","11":"1","_rn_":"Fiat 128"},{"1":"30.4","2":"4","3":"75.7","4":"52","5":"4.93","6":"1.615","7":"18.52","8":"1","9":"1","10":"4","11":"2","_rn_":"Honda Civic"},{"1":"33.9","2":"4","3":"71.1","4":"65","5":"4.22","6":"1.835","7":"19.90","8":"1","9":"1","10":"4","11":"1","_rn_":"Toyota Corolla"},{"1":"21.5","2":"4","3":"120.1","4":"97","5":"3.70","6":"2.465","7":"20.01","8":"1","9":"0","10":"3","11":"1","_rn_":"Toyota Corona"},{"1":"15.5","2":"8","3":"318.0","4":"150","5":"2.76","6":"3.520","7":"16.87","8":"0","9":"0","10":"3","11":"2","_rn_":"Dodge Challenger"},{"1":"15.2","2":"8","3":"304.0","4":"150","5":"3.15","6":"3.435","7":"17.30","8":"0","9":"0","10":"3","11":"2","_rn_":"AMC Javelin"},{"1":"13.3","2":"8","3":"350.0","4":"245","5":"3.73","6":"3.840","7":"15.41","8":"0","9":"0","10":"3","11":"4","_rn_":"Camaro Z28"},{"1":"19.2","2":"8","3":"400.0","4":"175","5":"3.08","6":"3.845","7":"17.05","8":"0","9":"0","10":"3","11":"2","_rn_":"Pontiac Firebird"},{"1":"27.3","2":"4","3":"79.0","4":"66","5":"4.08","6":"1.935","7":"18.90","8":"1","9":"1","10":"4","11":"1","_rn_":"Fiat X1-9"},{"1":"26.0","2":"4","3":"120.3","4":"91","5":"4.43","6":"2.140","7":"16.70","8":"0","9":"1","10":"5","11":"2","_rn_":"Porsche 914-2"},{"1":"30.4","2":"4","3":"95.1","4":"113","5":"3.77","6":"1.513","7":"16.90","8":"1","9":"1","10":"5","11":"2","_rn_":"Lotus Europa"},{"1":"15.8","2":"8","3":"351.0","4":"264","5":"4.22","6":"3.170","7":"14.50","8":"0","9":"1","10":"5","11":"4","_rn_":"Ford Pantera L"},{"1":"19.7","2":"6","3":"145.0","4":"175","5":"3.62","6":"2.770","7":"15.50","8":"0","9":"1","10":"5","11":"6","_rn_":"Ferrari Dino"},{"1":"15.0","2":"8","3":"301.0","4":"335","5":"3.54","6":"3.570","7":"14.60","8":"0","9":"1","10":"5","11":"8","_rn_":"Maserati Bora"},{"1":"21.4","2":"4","3":"121.0","4":"109","5":"4.11","6":"2.780","7":"18.60","8":"1","9":"1","10":"4","11":"2","_rn_":"Volvo 142E"}],"options":{"columns":{"min":{},"max":[10]},"rows":{"min":[5],"max":[5]},"pages":{}}}
  </script>
</div>

Notice that for each column, the column *class* is printed below the name (text enclosed in < >). This is irritating and related to printing a table from a built-in data frame. I have no idea how to fix this (within the confines of R Markdown) but I will work on a solution.

> **Recommendation** Use `paged_table` for large tables where extensive styling is not a concern.

### 2.3 Kable Tables

Knitr comes with its own tool for rendering simple tables called `kable`. The documentation for `kable` can be found [here](https://cran.r-project.org/web/packages/kableExtra/index.html) or by running `?knitr::kable()` in the Console. By itself, kable  comes with *almost no options*. We can extend its functionality with the `kableExtra` package and piping syntax from `magrittr`. The features of `kableExtra`  are extensive and I will only touch on a few here. The documentation for `kableExtra` can be found [here](https://cran.r-project.org/web/packages/kableExtra/index.html) or by running `?kableExtra` in the Console after the package has been installed and loaded.

> I highly recommend you [learn how to use these packages](https://cran.r-project.org/web/packages/kableExtra/vignettes/awesome_table_in_html.html) for making tables.

Again, you will need to load `kableExtra` and either load the `knitr` package or run the command like this: `knitr::kable()`.

First, let’s look at the default `kable` table output. We will use the head of the `mtcars` data set.

<br/>


```r
kable(head(mtcars), caption = "*Wow, this table looks terrible.*")
```

<table>
<caption>*Wow, this table looks terrible.*</caption>
 <thead>
  <tr>
   <th style="text-align:left;">   </th>
   <th style="text-align:right;"> mpg </th>
   <th style="text-align:right;"> cyl </th>
   <th style="text-align:right;"> disp </th>
   <th style="text-align:right;"> hp </th>
   <th style="text-align:right;"> drat </th>
   <th style="text-align:right;"> wt </th>
   <th style="text-align:right;"> qsec </th>
   <th style="text-align:right;"> vs </th>
   <th style="text-align:right;"> am </th>
   <th style="text-align:right;"> gear </th>
   <th style="text-align:right;"> carb </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Mazda RX4 </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.90 </td>
   <td style="text-align:right;"> 2.620 </td>
   <td style="text-align:right;"> 16.46 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 4 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Mazda RX4 Wag </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.90 </td>
   <td style="text-align:right;"> 2.875 </td>
   <td style="text-align:right;"> 17.02 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 4 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Datsun 710 </td>
   <td style="text-align:right;"> 22.8 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 108 </td>
   <td style="text-align:right;"> 93 </td>
   <td style="text-align:right;"> 3.85 </td>
   <td style="text-align:right;"> 2.320 </td>
   <td style="text-align:right;"> 18.61 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet 4 Drive </td>
   <td style="text-align:right;"> 21.4 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 258 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.08 </td>
   <td style="text-align:right;"> 3.215 </td>
   <td style="text-align:right;"> 19.44 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet Sportabout </td>
   <td style="text-align:right;"> 18.7 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 360 </td>
   <td style="text-align:right;"> 175 </td>
   <td style="text-align:right;"> 3.15 </td>
   <td style="text-align:right;"> 3.440 </td>
   <td style="text-align:right;"> 17.02 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Valiant </td>
   <td style="text-align:right;"> 18.1 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 225 </td>
   <td style="text-align:right;"> 105 </td>
   <td style="text-align:right;"> 2.76 </td>
   <td style="text-align:right;"> 3.460 </td>
   <td style="text-align:right;"> 20.22 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
</tbody>
</table>

<br/>

If we tried to render the entire table by omitting `head`, we would just get a long, crappy table in our document. Not cool. Lets see if we can jazz this up a bit with `kableExtra`.


```r
kable(head(mtcars), caption = "*This table looks better*") %>%
  kable_styling()
```

<table class="table" style="margin-left: auto; margin-right: auto;">
<caption>*This table looks better*</caption>
 <thead>
  <tr>
   <th style="text-align:left;">   </th>
   <th style="text-align:right;"> mpg </th>
   <th style="text-align:right;"> cyl </th>
   <th style="text-align:right;"> disp </th>
   <th style="text-align:right;"> hp </th>
   <th style="text-align:right;"> drat </th>
   <th style="text-align:right;"> wt </th>
   <th style="text-align:right;"> qsec </th>
   <th style="text-align:right;"> vs </th>
   <th style="text-align:right;"> am </th>
   <th style="text-align:right;"> gear </th>
   <th style="text-align:right;"> carb </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Mazda RX4 </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.90 </td>
   <td style="text-align:right;"> 2.620 </td>
   <td style="text-align:right;"> 16.46 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 4 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Mazda RX4 Wag </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.90 </td>
   <td style="text-align:right;"> 2.875 </td>
   <td style="text-align:right;"> 17.02 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 4 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Datsun 710 </td>
   <td style="text-align:right;"> 22.8 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 108 </td>
   <td style="text-align:right;"> 93 </td>
   <td style="text-align:right;"> 3.85 </td>
   <td style="text-align:right;"> 2.320 </td>
   <td style="text-align:right;"> 18.61 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet 4 Drive </td>
   <td style="text-align:right;"> 21.4 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 258 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.08 </td>
   <td style="text-align:right;"> 3.215 </td>
   <td style="text-align:right;"> 19.44 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet Sportabout </td>
   <td style="text-align:right;"> 18.7 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 360 </td>
   <td style="text-align:right;"> 175 </td>
   <td style="text-align:right;"> 3.15 </td>
   <td style="text-align:right;"> 3.440 </td>
   <td style="text-align:right;"> 17.02 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 2 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Valiant </td>
   <td style="text-align:right;"> 18.1 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 225 </td>
   <td style="text-align:right;"> 105 </td>
   <td style="text-align:right;"> 2.76 </td>
   <td style="text-align:right;"> 3.460 </td>
   <td style="text-align:right;"> 20.22 </td>
   <td style="text-align:right;"> 1 </td>
   <td style="text-align:right;"> 0 </td>
   <td style="text-align:right;"> 3 </td>
   <td style="text-align:right;"> 1 </td>
  </tr>
</tbody>
</table>

Here I used the [pipe operator](https://riptutorial.com/r/topic/652/pipe-operators------and-others-) (`%>%`) to pass the results of `kable` to the function `kable_styling`---a part of the `kableExtra` package. By running  `kable_styling` *as is*, I am using defaults for all of the options.

> The pipe operator is a powerful tool worth learning.

Back to the table. It certainly looks better than the default `kable` version but we are missing the ability to *page* the table. I would like you to run these two commands and look at the output.

This command will include the whole table.

```
kable(mtcars) %>%
  kable_styling()
```

And this command will transpose the table (swap rows and columns) using the transpose (`t`) function. Remember, `mtcars` has 32 rows and 11 columns but when you transpose the table, it has 11 rows and 32 columns. So it is really wide in the transposed state.

```
kable(head(t(mtcars))) %>%
  kable_styling()
```

I hope you agree that neither of these tables are acceptable, especially the second one. Unfortunately, the `kableExtra` package does not come with an option to add pagination. You can however put the table in a fixed-height, fixed-width (or both) box, and make it scrollable. We can do this by using a pipe operator and the `scroll_box` function. While we are at it, lets also add tweak some options in `kable_styling` to make a more handsome table.


```r
kable(t(mtcars), caption = "*Scrollable kable table.*") %>%
  kable_styling(bootstrap_options = c("striped", "hover",
                                      "condensed", "responsive")) %>%
  scroll_box(width = "100%", height = "300px")
```

<div style="border: 1px solid #ddd; padding: 0px; overflow-y: scroll; height:300px; overflow-x: scroll; width:100%; "><table class="table table-striped table-hover table-condensed table-responsive" style="margin-left: auto; margin-right: auto;">
<caption>*Scrollable kable table.*</caption>
 <thead>
  <tr>
   <th style="text-align:left;position: sticky; top:0; background-color: #FFFFFF;">   </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Mazda RX4 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Mazda RX4 Wag </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Datsun 710 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Hornet 4 Drive </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Hornet Sportabout </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Valiant </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Duster 360 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Merc 240D </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Merc 230 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Merc 280 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Merc 280C </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Merc 450SE </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Merc 450SL </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Merc 450SLC </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Cadillac Fleetwood </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Lincoln Continental </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Chrysler Imperial </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Fiat 128 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Honda Civic </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Toyota Corolla </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Toyota Corona </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Dodge Challenger </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> AMC Javelin </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Camaro Z28 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Pontiac Firebird </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Fiat X1-9 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Porsche 914-2 </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Lotus Europa </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Ford Pantera L </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Ferrari Dino </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Maserati Bora </th>
   <th style="text-align:right;position: sticky; top:0; background-color: #FFFFFF;"> Volvo 142E </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> mpg </td>
   <td style="text-align:right;"> 21.00 </td>
   <td style="text-align:right;"> 21.000 </td>
   <td style="text-align:right;"> 22.80 </td>
   <td style="text-align:right;"> 21.400 </td>
   <td style="text-align:right;"> 18.70 </td>
   <td style="text-align:right;"> 18.10 </td>
   <td style="text-align:right;"> 14.30 </td>
   <td style="text-align:right;"> 24.40 </td>
   <td style="text-align:right;"> 22.80 </td>
   <td style="text-align:right;"> 19.20 </td>
   <td style="text-align:right;"> 17.80 </td>
   <td style="text-align:right;"> 16.40 </td>
   <td style="text-align:right;"> 17.30 </td>
   <td style="text-align:right;"> 15.20 </td>
   <td style="text-align:right;"> 10.40 </td>
   <td style="text-align:right;"> 10.400 </td>
   <td style="text-align:right;"> 14.700 </td>
   <td style="text-align:right;"> 32.40 </td>
   <td style="text-align:right;"> 30.400 </td>
   <td style="text-align:right;"> 33.900 </td>
   <td style="text-align:right;"> 21.500 </td>
   <td style="text-align:right;"> 15.50 </td>
   <td style="text-align:right;"> 15.200 </td>
   <td style="text-align:right;"> 13.30 </td>
   <td style="text-align:right;"> 19.200 </td>
   <td style="text-align:right;"> 27.300 </td>
   <td style="text-align:right;"> 26.00 </td>
   <td style="text-align:right;"> 30.400 </td>
   <td style="text-align:right;"> 15.80 </td>
   <td style="text-align:right;"> 19.70 </td>
   <td style="text-align:right;"> 15.00 </td>
   <td style="text-align:right;"> 21.40 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> cyl </td>
   <td style="text-align:right;"> 6.00 </td>
   <td style="text-align:right;"> 6.000 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 6.000 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 6.00 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 6.00 </td>
   <td style="text-align:right;"> 6.00 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 8.000 </td>
   <td style="text-align:right;"> 8.000 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 8.000 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 8.000 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 6.00 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 4.00 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> disp </td>
   <td style="text-align:right;"> 160.00 </td>
   <td style="text-align:right;"> 160.000 </td>
   <td style="text-align:right;"> 108.00 </td>
   <td style="text-align:right;"> 258.000 </td>
   <td style="text-align:right;"> 360.00 </td>
   <td style="text-align:right;"> 225.00 </td>
   <td style="text-align:right;"> 360.00 </td>
   <td style="text-align:right;"> 146.70 </td>
   <td style="text-align:right;"> 140.80 </td>
   <td style="text-align:right;"> 167.60 </td>
   <td style="text-align:right;"> 167.60 </td>
   <td style="text-align:right;"> 275.80 </td>
   <td style="text-align:right;"> 275.80 </td>
   <td style="text-align:right;"> 275.80 </td>
   <td style="text-align:right;"> 472.00 </td>
   <td style="text-align:right;"> 460.000 </td>
   <td style="text-align:right;"> 440.000 </td>
   <td style="text-align:right;"> 78.70 </td>
   <td style="text-align:right;"> 75.700 </td>
   <td style="text-align:right;"> 71.100 </td>
   <td style="text-align:right;"> 120.100 </td>
   <td style="text-align:right;"> 318.00 </td>
   <td style="text-align:right;"> 304.000 </td>
   <td style="text-align:right;"> 350.00 </td>
   <td style="text-align:right;"> 400.000 </td>
   <td style="text-align:right;"> 79.000 </td>
   <td style="text-align:right;"> 120.30 </td>
   <td style="text-align:right;"> 95.100 </td>
   <td style="text-align:right;"> 351.00 </td>
   <td style="text-align:right;"> 145.00 </td>
   <td style="text-align:right;"> 301.00 </td>
   <td style="text-align:right;"> 121.00 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> hp </td>
   <td style="text-align:right;"> 110.00 </td>
   <td style="text-align:right;"> 110.000 </td>
   <td style="text-align:right;"> 93.00 </td>
   <td style="text-align:right;"> 110.000 </td>
   <td style="text-align:right;"> 175.00 </td>
   <td style="text-align:right;"> 105.00 </td>
   <td style="text-align:right;"> 245.00 </td>
   <td style="text-align:right;"> 62.00 </td>
   <td style="text-align:right;"> 95.00 </td>
   <td style="text-align:right;"> 123.00 </td>
   <td style="text-align:right;"> 123.00 </td>
   <td style="text-align:right;"> 180.00 </td>
   <td style="text-align:right;"> 180.00 </td>
   <td style="text-align:right;"> 180.00 </td>
   <td style="text-align:right;"> 205.00 </td>
   <td style="text-align:right;"> 215.000 </td>
   <td style="text-align:right;"> 230.000 </td>
   <td style="text-align:right;"> 66.00 </td>
   <td style="text-align:right;"> 52.000 </td>
   <td style="text-align:right;"> 65.000 </td>
   <td style="text-align:right;"> 97.000 </td>
   <td style="text-align:right;"> 150.00 </td>
   <td style="text-align:right;"> 150.000 </td>
   <td style="text-align:right;"> 245.00 </td>
   <td style="text-align:right;"> 175.000 </td>
   <td style="text-align:right;"> 66.000 </td>
   <td style="text-align:right;"> 91.00 </td>
   <td style="text-align:right;"> 113.000 </td>
   <td style="text-align:right;"> 264.00 </td>
   <td style="text-align:right;"> 175.00 </td>
   <td style="text-align:right;"> 335.00 </td>
   <td style="text-align:right;"> 109.00 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> drat </td>
   <td style="text-align:right;"> 3.90 </td>
   <td style="text-align:right;"> 3.900 </td>
   <td style="text-align:right;"> 3.85 </td>
   <td style="text-align:right;"> 3.080 </td>
   <td style="text-align:right;"> 3.15 </td>
   <td style="text-align:right;"> 2.76 </td>
   <td style="text-align:right;"> 3.21 </td>
   <td style="text-align:right;"> 3.69 </td>
   <td style="text-align:right;"> 3.92 </td>
   <td style="text-align:right;"> 3.92 </td>
   <td style="text-align:right;"> 3.92 </td>
   <td style="text-align:right;"> 3.07 </td>
   <td style="text-align:right;"> 3.07 </td>
   <td style="text-align:right;"> 3.07 </td>
   <td style="text-align:right;"> 2.93 </td>
   <td style="text-align:right;"> 3.000 </td>
   <td style="text-align:right;"> 3.230 </td>
   <td style="text-align:right;"> 4.08 </td>
   <td style="text-align:right;"> 4.930 </td>
   <td style="text-align:right;"> 4.220 </td>
   <td style="text-align:right;"> 3.700 </td>
   <td style="text-align:right;"> 2.76 </td>
   <td style="text-align:right;"> 3.150 </td>
   <td style="text-align:right;"> 3.73 </td>
   <td style="text-align:right;"> 3.080 </td>
   <td style="text-align:right;"> 4.080 </td>
   <td style="text-align:right;"> 4.43 </td>
   <td style="text-align:right;"> 3.770 </td>
   <td style="text-align:right;"> 4.22 </td>
   <td style="text-align:right;"> 3.62 </td>
   <td style="text-align:right;"> 3.54 </td>
   <td style="text-align:right;"> 4.11 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> wt </td>
   <td style="text-align:right;"> 2.62 </td>
   <td style="text-align:right;"> 2.875 </td>
   <td style="text-align:right;"> 2.32 </td>
   <td style="text-align:right;"> 3.215 </td>
   <td style="text-align:right;"> 3.44 </td>
   <td style="text-align:right;"> 3.46 </td>
   <td style="text-align:right;"> 3.57 </td>
   <td style="text-align:right;"> 3.19 </td>
   <td style="text-align:right;"> 3.15 </td>
   <td style="text-align:right;"> 3.44 </td>
   <td style="text-align:right;"> 3.44 </td>
   <td style="text-align:right;"> 4.07 </td>
   <td style="text-align:right;"> 3.73 </td>
   <td style="text-align:right;"> 3.78 </td>
   <td style="text-align:right;"> 5.25 </td>
   <td style="text-align:right;"> 5.424 </td>
   <td style="text-align:right;"> 5.345 </td>
   <td style="text-align:right;"> 2.20 </td>
   <td style="text-align:right;"> 1.615 </td>
   <td style="text-align:right;"> 1.835 </td>
   <td style="text-align:right;"> 2.465 </td>
   <td style="text-align:right;"> 3.52 </td>
   <td style="text-align:right;"> 3.435 </td>
   <td style="text-align:right;"> 3.84 </td>
   <td style="text-align:right;"> 3.845 </td>
   <td style="text-align:right;"> 1.935 </td>
   <td style="text-align:right;"> 2.14 </td>
   <td style="text-align:right;"> 1.513 </td>
   <td style="text-align:right;"> 3.17 </td>
   <td style="text-align:right;"> 2.77 </td>
   <td style="text-align:right;"> 3.57 </td>
   <td style="text-align:right;"> 2.78 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> qsec </td>
   <td style="text-align:right;"> 16.46 </td>
   <td style="text-align:right;"> 17.020 </td>
   <td style="text-align:right;"> 18.61 </td>
   <td style="text-align:right;"> 19.440 </td>
   <td style="text-align:right;"> 17.02 </td>
   <td style="text-align:right;"> 20.22 </td>
   <td style="text-align:right;"> 15.84 </td>
   <td style="text-align:right;"> 20.00 </td>
   <td style="text-align:right;"> 22.90 </td>
   <td style="text-align:right;"> 18.30 </td>
   <td style="text-align:right;"> 18.90 </td>
   <td style="text-align:right;"> 17.40 </td>
   <td style="text-align:right;"> 17.60 </td>
   <td style="text-align:right;"> 18.00 </td>
   <td style="text-align:right;"> 17.98 </td>
   <td style="text-align:right;"> 17.820 </td>
   <td style="text-align:right;"> 17.420 </td>
   <td style="text-align:right;"> 19.47 </td>
   <td style="text-align:right;"> 18.520 </td>
   <td style="text-align:right;"> 19.900 </td>
   <td style="text-align:right;"> 20.010 </td>
   <td style="text-align:right;"> 16.87 </td>
   <td style="text-align:right;"> 17.300 </td>
   <td style="text-align:right;"> 15.41 </td>
   <td style="text-align:right;"> 17.050 </td>
   <td style="text-align:right;"> 18.900 </td>
   <td style="text-align:right;"> 16.70 </td>
   <td style="text-align:right;"> 16.900 </td>
   <td style="text-align:right;"> 14.50 </td>
   <td style="text-align:right;"> 15.50 </td>
   <td style="text-align:right;"> 14.60 </td>
   <td style="text-align:right;"> 18.60 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> vs </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 1.00 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> am </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 0.00 </td>
   <td style="text-align:right;"> 0.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.00 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> gear </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 3.000 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.000 </td>
   <td style="text-align:right;"> 3.000 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 3.000 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.000 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.000 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 5.00 </td>
   <td style="text-align:right;"> 5.000 </td>
   <td style="text-align:right;"> 5.00 </td>
   <td style="text-align:right;"> 5.00 </td>
   <td style="text-align:right;"> 5.00 </td>
   <td style="text-align:right;"> 4.00 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> carb </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 2.00 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 2.00 </td>
   <td style="text-align:right;"> 2.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 3.00 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 4.000 </td>
   <td style="text-align:right;"> 1.00 </td>
   <td style="text-align:right;"> 2.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 2.00 </td>
   <td style="text-align:right;"> 2.000 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 2.000 </td>
   <td style="text-align:right;"> 1.000 </td>
   <td style="text-align:right;"> 2.00 </td>
   <td style="text-align:right;"> 2.000 </td>
   <td style="text-align:right;"> 4.00 </td>
   <td style="text-align:right;"> 6.00 </td>
   <td style="text-align:right;"> 8.00 </td>
   <td style="text-align:right;"> 2.00 </td>
  </tr>
</tbody>
</table></div>

<br/>

For the `scroll_box` function I set the `width = "100%"` rather than specifying a dimension. This ensures the box will always be the width of the page no matter how small the window is.

Even though you cannot make a paged table with `kable`, there are  many styling options available in the `kableExtra` package that makes this method  extremely useful and worth learning. Plus, the code is relatively simple to write.

I want to show you one more feature that is not available the other table methods we cover in this Assignment---*floating*. Let's first subset the `mtcars` data set so we can make a small table. Next we use the `full_width` and `position` options to control the size and position of the table. 

Here is our code chunk.


```r
mtcars_sub <- mtcars[1:7,1:6]
kable(mtcars_sub) %>%
  kable_styling(bootstrap_options = "striped",
                full_width = FALSE,
                position = "float_right")
```

<table class="table table-striped" style="width: auto !important; float: right; margin-left: 10px;">
 <thead>
  <tr>
   <th style="text-align:left;">   </th>
   <th style="text-align:right;"> mpg </th>
   <th style="text-align:right;"> cyl </th>
   <th style="text-align:right;"> disp </th>
   <th style="text-align:right;"> hp </th>
   <th style="text-align:right;"> drat </th>
   <th style="text-align:right;"> wt </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> Mazda RX4 </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.90 </td>
   <td style="text-align:right;"> 2.620 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Mazda RX4 Wag </td>
   <td style="text-align:right;"> 21.0 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 160 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.90 </td>
   <td style="text-align:right;"> 2.875 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Datsun 710 </td>
   <td style="text-align:right;"> 22.8 </td>
   <td style="text-align:right;"> 4 </td>
   <td style="text-align:right;"> 108 </td>
   <td style="text-align:right;"> 93 </td>
   <td style="text-align:right;"> 3.85 </td>
   <td style="text-align:right;"> 2.320 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet 4 Drive </td>
   <td style="text-align:right;"> 21.4 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 258 </td>
   <td style="text-align:right;"> 110 </td>
   <td style="text-align:right;"> 3.08 </td>
   <td style="text-align:right;"> 3.215 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Hornet Sportabout </td>
   <td style="text-align:right;"> 18.7 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 360 </td>
   <td style="text-align:right;"> 175 </td>
   <td style="text-align:right;"> 3.15 </td>
   <td style="text-align:right;"> 3.440 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Valiant </td>
   <td style="text-align:right;"> 18.1 </td>
   <td style="text-align:right;"> 6 </td>
   <td style="text-align:right;"> 225 </td>
   <td style="text-align:right;"> 105 </td>
   <td style="text-align:right;"> 2.76 </td>
   <td style="text-align:right;"> 3.460 </td>
  </tr>
  <tr>
   <td style="text-align:left;"> Duster 360 </td>
   <td style="text-align:right;"> 14.3 </td>
   <td style="text-align:right;"> 8 </td>
   <td style="text-align:right;"> 360 </td>
   <td style="text-align:right;"> 245 </td>
   <td style="text-align:right;"> 3.21 </td>
   <td style="text-align:right;"> 3.570 </td>
  </tr>
</tbody>
</table>

<br/><br/>

Let’s say we have a bunch of text that we want to put side-by-side with this small table. Our subsetted `mtcars` data set now has 7 rows and 6 columns. We can make our table smaller by setting `full_width = FALSE` in `kable_styling` and float the table by setting `position = "float_right"`

Please study the [extensive options available in `kable` and `kableExtra`](https://cran.r-project.org/web/packages/kableExtra/vignettes/awesome_table_in_html.html) and create tables that implement some of the options.

<br/><br/>

> **Recommendation** Use `kable` + `kableExtra` for small tables where extensive styling is desired.

### 2.4 DT Tables

The last option I want to cover for building tables is implemented using the `datatable` function from the [DT](https://rstudio.github.io/DT/) package, an interface to the JavaScript library *[DataTables](https://datatables.net/)*. To demonstrate the functionality, I will use a larger data set called `USJudgeRatings` from the `datasets` package. `USJudgeRatings` has 43 rows and 12 columns. This table is too big---horizontally and vertically---to fit on a standard page.

The syntax for the `DT::datatable` is more complicated than the other methods but that comes with  more extensive functionality.

> Working with `DT::datatable` is an advanced level skill. I highly recommend you learn how to use the package, but it will take  practice.

Please make sure you are comfortable with the other methods first before trying to use `DT::datatable`. I promise, if you do not know what you are doing, this package will cause a lot of frustration. That said, I use it all the time because it is awesome.

Moving on. If we run `DT` on the `USJudgeRatings` data set without any options the table will spill off the side of the page. Again, not cool. Try to run this command and see what happens.

```
datatable(USJudgeRatings)
```

`DT::datatable` *does not page tables horizontally* like the `paged_table` command does (described above). We can set the width of the table and add an option that allows horizontal scrolling. For this we use the `options` argument. The syntax is to add `width = "100%"` followed by `options = list()`, where we put a comma separated list of options. For now, we just include `scrollX` in our list of options.


```r
datatable(USJudgeRatings, width = "100%",
          options = list(scrollX = TRUE))
```

<!--html_preserve--><div id="htmlwidget-2dc24d8cbe92d410b136" style="width:100%;height:auto;" class="datatables html-widget"></div>
<script type="application/json" data-for="htmlwidget-2dc24d8cbe92d410b136">{"x":{"filter":"none","data":[["AARONSON,L.H.","ALEXANDER,J.M.","ARMENTANO,A.J.","BERDON,R.I.","BRACKEN,J.J.","BURNS,E.B.","CALLAHAN,R.J.","COHEN,S.S.","DALY,J.J.","DANNEHY,J.F.","DEAN,H.H.","DEVITA,H.J.","DRISCOLL,P.J.","GRILLO,A.E.","HADDEN,W.L.JR.","HAMILL,E.C.","HEALEY.A.H.","HULL,T.C.","LEVINE,I.","LEVISTER,R.L.","MARTIN,L.F.","MCGRATH,J.F.","MIGNONE,A.F.","MISSAL,H.M.","MULVEY,H.M.","NARUK,H.J.","O'BRIEN,F.J.","O'SULLIVAN,T.J.","PASKEY,L.","RUBINOW,J.E.","SADEN.G.A.","SATANIELLO,A.G.","SHEA,D.M.","SHEA,J.F.JR.","SIDOR,W.J.","SPEZIALE,J.A.","SPONZO,M.J.","STAPLETON,J.F.","TESTO,R.J.","TIERNEY,W.L.JR.","WALL,R.A.","WRIGHT,D.B.","ZARRILLI,K.J."],[5.7,6.8,7.2,6.8,7.3,6.2,10.6,7,7.3,8.2,7,6.5,6.7,7,6.5,7.3,8,7.7,8.3,9.6,7.1,7.6,6.6,6.2,7.5,7.8,7.1,7.5,7.5,7.1,6.6,8.4,6.9,7.3,7.7,8.5,6.9,6.5,8.3,8.3,9,7.1,8.6],[7.9,8.9,8.1,8.8,6.4,8.8,9,5.9,8.9,7.9,8,8,8.6,7.5,8.1,8,7.6,7.7,8.2,6.9,8.2,7.3,7.4,8.3,8.7,8.9,8.5,9,8.1,9.2,7.4,8,8.5,8.9,6.2,8.3,8.3,8.2,7.3,8.2,7,8.4,7.4],[7.7,8.8,7.8,8.5,4.3,8.7,8.9,4.9,8.9,6.7,7.6,7.6,8.2,6.4,8,7.4,6.6,6.7,7.4,5.7,7.7,6.9,6.2,8.1,8.5,8.7,8.3,8.9,7.7,9,6.9,7.9,7.8,8.8,5.1,8.1,8,7.7,7,7.8,5.9,8.4,7],[7.3,8.5,7.8,8.8,6.5,8.5,8.7,5.1,8.7,8.1,7.4,7.2,6.8,6.8,8,7.7,7.2,7.5,7.8,6.6,7.1,6.8,6.2,7.7,8.6,8.9,8,8.7,8.2,9,8.4,7.9,8.5,8.7,5.6,8.3,8.1,7.8,6.8,8.3,7,7.7,7.5],[7.1,7.8,7.5,8.3,6,7.9,8.5,5.4,8.6,7.9,7.3,7,6.9,6.5,7.9,7.3,6.5,7.4,7.7,6.9,6.6,6.7,5.4,7.4,8.5,8.7,7.9,8.4,8,8.4,8,7.8,8.1,8.4,5.6,8.4,7.9,7.6,7,8.4,7,7.5,7.5],[7.4,8.1,7.6,8.5,6.2,8,8.5,5.9,8.5,8,7.5,7.1,6.6,7,8,7.3,6.5,7.5,7.7,6.6,6.6,6.8,5.7,7.3,8.4,8.8,7.9,8.5,8.1,8.6,7.9,7.8,8.2,8.5,5.9,8.2,7.9,7.7,7.1,8.3,7.2,7.7,7.7],[7.1,8,7.5,8.7,5.7,8.1,8.5,4.8,8.4,7.9,7.1,6.9,7.1,6.6,7.9,7.3,6.8,7.1,7.7,6.2,6.7,6.4,5.8,7.3,8.5,8.9,7.8,8.4,8.2,9.1,8.2,7.6,8.4,8.5,5.6,8.2,7.9,7.7,6.7,7.7,6.9,7.8,7.4],[7.1,8,7.5,8.7,5.7,8,8.5,5.1,8.4,8.1,7.2,7,7.3,6.8,7.8,7.2,6.7,7.3,7.8,6,6.7,6.3,5.9,7.3,8.5,9,7.8,8.3,8.4,9.1,8.4,7.4,8.5,8.5,5.6,8.1,7.7,7.7,6.7,7.6,6.9,8.2,7.2],[7.1,7.8,7.3,8.4,5.1,8,8.6,4.7,8.4,7.7,7.1,7,7.2,6.3,7.8,7.1,6.4,7.1,7.5,5.8,6.8,6.3,5.2,7.2,8.4,8.8,7.8,8.3,8,8.9,7.7,7.4,8.1,8.4,5.3,7.9,7.6,7.5,6.7,7.5,6.5,8,6.9],[7,7.9,7.4,8.5,5.3,8,8.4,4.9,8.5,7.8,7.2,7.1,7.2,6.6,7.8,7.2,6.5,7.3,7.6,5.8,6.8,6.3,5.8,7.3,8.4,8.9,7.7,8.3,8.1,9,7.9,7.4,8.3,8.4,5.5,8,7.7,7.6,6.7,7.7,6.6,8.1,7],[8.3,8.5,7.9,8.8,5.5,8.6,9.1,6.8,8.8,8.5,8.4,6.9,8.1,6.2,8.4,8,6.9,8.1,8,7.2,7.5,7.4,4.7,7.8,8.7,9,8.3,8.8,8.4,8.9,8.4,8.1,8.7,8.8,6.3,8,8.1,8.5,8,8.1,7.6,8.3,7.8],[7.8,8.7,7.8,8.7,4.8,8.6,9,5,8.8,7.9,7.7,7.2,7.7,6.5,8,7.6,6.7,7.4,8,6,7.3,6.6,5.2,7.6,8.7,9,8.2,8.7,8.1,9.2,7.5,7.9,8.3,8.8,5.3,8.2,8,7.7,7,7.9,6.6,8.1,7.1]],"container":"<table class=\"display\">\n  <thead>\n    <tr>\n      <th> <\/th>\n      <th>CONT<\/th>\n      <th>INTG<\/th>\n      <th>DMNR<\/th>\n      <th>DILG<\/th>\n      <th>CFMG<\/th>\n      <th>DECI<\/th>\n      <th>PREP<\/th>\n      <th>FAMI<\/th>\n      <th>ORAL<\/th>\n      <th>WRIT<\/th>\n      <th>PHYS<\/th>\n      <th>RTEN<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"scrollX":true,"columnDefs":[{"className":"dt-right","targets":[1,2,3,4,5,6,7,8,9,10,11,12]},{"orderable":false,"targets":0}],"order":[],"autoWidth":false,"orderClasses":false}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->

<br/>

Play around with the table a little. As you can see

* the table now fits in the window,
* horizontal scrolling in enabled,
* the page is vertically paged,
* there is a *Show entries* drop down, and
* there is a *Search* box.

The *Show entries* and *Search* box are added by default. We can decide whether to show these options or not. I will save that for later. For now, I want to leave you with a more stylized DT data table to give you a sense of the possibilities. Don't worry so much about the code---pay attention to the functionality.


```r
datatable(USJudgeRatings, width = "100%",
          extensions = 'Buttons', options = list(
            scrollX = TRUE,
            dom = 'lfrtipB',
            buttons = c('copy', 'csv', 'excel', 'pdf', 'print'),
            pageLength = 5,
            lengthMenu = c(5, 10, 20, 45)
            )
          )
```

<!--html_preserve--><div id="htmlwidget-9277e86fe22b48ad32b8" style="width:100%;height:auto;" class="datatables html-widget"></div>
<script type="application/json" data-for="htmlwidget-9277e86fe22b48ad32b8">{"x":{"filter":"none","extensions":["Buttons"],"data":[["AARONSON,L.H.","ALEXANDER,J.M.","ARMENTANO,A.J.","BERDON,R.I.","BRACKEN,J.J.","BURNS,E.B.","CALLAHAN,R.J.","COHEN,S.S.","DALY,J.J.","DANNEHY,J.F.","DEAN,H.H.","DEVITA,H.J.","DRISCOLL,P.J.","GRILLO,A.E.","HADDEN,W.L.JR.","HAMILL,E.C.","HEALEY.A.H.","HULL,T.C.","LEVINE,I.","LEVISTER,R.L.","MARTIN,L.F.","MCGRATH,J.F.","MIGNONE,A.F.","MISSAL,H.M.","MULVEY,H.M.","NARUK,H.J.","O'BRIEN,F.J.","O'SULLIVAN,T.J.","PASKEY,L.","RUBINOW,J.E.","SADEN.G.A.","SATANIELLO,A.G.","SHEA,D.M.","SHEA,J.F.JR.","SIDOR,W.J.","SPEZIALE,J.A.","SPONZO,M.J.","STAPLETON,J.F.","TESTO,R.J.","TIERNEY,W.L.JR.","WALL,R.A.","WRIGHT,D.B.","ZARRILLI,K.J."],[5.7,6.8,7.2,6.8,7.3,6.2,10.6,7,7.3,8.2,7,6.5,6.7,7,6.5,7.3,8,7.7,8.3,9.6,7.1,7.6,6.6,6.2,7.5,7.8,7.1,7.5,7.5,7.1,6.6,8.4,6.9,7.3,7.7,8.5,6.9,6.5,8.3,8.3,9,7.1,8.6],[7.9,8.9,8.1,8.8,6.4,8.8,9,5.9,8.9,7.9,8,8,8.6,7.5,8.1,8,7.6,7.7,8.2,6.9,8.2,7.3,7.4,8.3,8.7,8.9,8.5,9,8.1,9.2,7.4,8,8.5,8.9,6.2,8.3,8.3,8.2,7.3,8.2,7,8.4,7.4],[7.7,8.8,7.8,8.5,4.3,8.7,8.9,4.9,8.9,6.7,7.6,7.6,8.2,6.4,8,7.4,6.6,6.7,7.4,5.7,7.7,6.9,6.2,8.1,8.5,8.7,8.3,8.9,7.7,9,6.9,7.9,7.8,8.8,5.1,8.1,8,7.7,7,7.8,5.9,8.4,7],[7.3,8.5,7.8,8.8,6.5,8.5,8.7,5.1,8.7,8.1,7.4,7.2,6.8,6.8,8,7.7,7.2,7.5,7.8,6.6,7.1,6.8,6.2,7.7,8.6,8.9,8,8.7,8.2,9,8.4,7.9,8.5,8.7,5.6,8.3,8.1,7.8,6.8,8.3,7,7.7,7.5],[7.1,7.8,7.5,8.3,6,7.9,8.5,5.4,8.6,7.9,7.3,7,6.9,6.5,7.9,7.3,6.5,7.4,7.7,6.9,6.6,6.7,5.4,7.4,8.5,8.7,7.9,8.4,8,8.4,8,7.8,8.1,8.4,5.6,8.4,7.9,7.6,7,8.4,7,7.5,7.5],[7.4,8.1,7.6,8.5,6.2,8,8.5,5.9,8.5,8,7.5,7.1,6.6,7,8,7.3,6.5,7.5,7.7,6.6,6.6,6.8,5.7,7.3,8.4,8.8,7.9,8.5,8.1,8.6,7.9,7.8,8.2,8.5,5.9,8.2,7.9,7.7,7.1,8.3,7.2,7.7,7.7],[7.1,8,7.5,8.7,5.7,8.1,8.5,4.8,8.4,7.9,7.1,6.9,7.1,6.6,7.9,7.3,6.8,7.1,7.7,6.2,6.7,6.4,5.8,7.3,8.5,8.9,7.8,8.4,8.2,9.1,8.2,7.6,8.4,8.5,5.6,8.2,7.9,7.7,6.7,7.7,6.9,7.8,7.4],[7.1,8,7.5,8.7,5.7,8,8.5,5.1,8.4,8.1,7.2,7,7.3,6.8,7.8,7.2,6.7,7.3,7.8,6,6.7,6.3,5.9,7.3,8.5,9,7.8,8.3,8.4,9.1,8.4,7.4,8.5,8.5,5.6,8.1,7.7,7.7,6.7,7.6,6.9,8.2,7.2],[7.1,7.8,7.3,8.4,5.1,8,8.6,4.7,8.4,7.7,7.1,7,7.2,6.3,7.8,7.1,6.4,7.1,7.5,5.8,6.8,6.3,5.2,7.2,8.4,8.8,7.8,8.3,8,8.9,7.7,7.4,8.1,8.4,5.3,7.9,7.6,7.5,6.7,7.5,6.5,8,6.9],[7,7.9,7.4,8.5,5.3,8,8.4,4.9,8.5,7.8,7.2,7.1,7.2,6.6,7.8,7.2,6.5,7.3,7.6,5.8,6.8,6.3,5.8,7.3,8.4,8.9,7.7,8.3,8.1,9,7.9,7.4,8.3,8.4,5.5,8,7.7,7.6,6.7,7.7,6.6,8.1,7],[8.3,8.5,7.9,8.8,5.5,8.6,9.1,6.8,8.8,8.5,8.4,6.9,8.1,6.2,8.4,8,6.9,8.1,8,7.2,7.5,7.4,4.7,7.8,8.7,9,8.3,8.8,8.4,8.9,8.4,8.1,8.7,8.8,6.3,8,8.1,8.5,8,8.1,7.6,8.3,7.8],[7.8,8.7,7.8,8.7,4.8,8.6,9,5,8.8,7.9,7.7,7.2,7.7,6.5,8,7.6,6.7,7.4,8,6,7.3,6.6,5.2,7.6,8.7,9,8.2,8.7,8.1,9.2,7.5,7.9,8.3,8.8,5.3,8.2,8,7.7,7,7.9,6.6,8.1,7.1]],"container":"<table class=\"display\">\n  <thead>\n    <tr>\n      <th> <\/th>\n      <th>CONT<\/th>\n      <th>INTG<\/th>\n      <th>DMNR<\/th>\n      <th>DILG<\/th>\n      <th>CFMG<\/th>\n      <th>DECI<\/th>\n      <th>PREP<\/th>\n      <th>FAMI<\/th>\n      <th>ORAL<\/th>\n      <th>WRIT<\/th>\n      <th>PHYS<\/th>\n      <th>RTEN<\/th>\n    <\/tr>\n  <\/thead>\n<\/table>","options":{"scrollX":true,"dom":"lfrtipB","buttons":["copy","csv","excel","pdf","print"],"pageLength":5,"lengthMenu":[5,10,20,45],"columnDefs":[{"className":"dt-right","targets":[1,2,3,4,5,6,7,8,9,10,11,12]},{"orderable":false,"targets":0}],"order":[],"autoWidth":false,"orderClasses":false}},"evals":[],"jsHooks":[]}</script><!--/html_preserve-->
<br/><br/>

I added buttons to download the table to different formats, changed the page length to 5, and changed the values in the *Show entries* drop down. Play around with the table. There is a lot more to do with this package and we will come back to it often.

> **Recommendation** Use `DT::datatable` for large tables where extensive styling is desired.

That’s all for this assignment. 

## Assignment 3: Code

If you are interested in making your science more transparent and reproducible, you need to provide at least two things---the raw data you generated and the code you used to analyze it. Hopefully it is obvious by now that you need to provide access to ***both*** components; neither is particularly useful without the other. We will cover data availability in a future lesson. For this assignment, you will practice several different methods for making your code accessible. The method or methods you choose for your own work will depend on the type of analyses *and* the type of code. 

> Your assignment is to implement these methods in your document and play around with the different options. 

### Purl

Knitr comes with a built-in function called `purl`, which allows you to extract all the R code from an R Markdown document and convert it to an R script. In order to run `purl`, you must either load the knitr library first (i.e., `library(knitr)`) and then run `purl` or call the function directly by running `knitr::purl()`. We will start by discussing some simple *options* for running `purl` and then talk about *how* you run the command. The basic structure of the command is:

> `knitr::purl(input="filename.Rmd", documentation = L)`

By default, `purl` uses the base name of the input file as the base name of the output file. If you want to control this behavior, add the option `output="filename.R"` where `filename` is whatever you choose. 

The option `documentation` is an integer that specifies the level (`L`) of documentation to add to the script. You have three choices

* **0** means output pure code to the script, discard all Markdown text and code chunk details. 
* **1** (the default) means discard all Markdown text but add the chunk headers to the script as commented lines. 
* **2** means to add all Markdown text and code chunks to the script as commented lines.

As far as I know, you **cannot** run `purl` from inside an actual code chunk. I have no idea why nor was I able to find an answer. If have an answer or know a solution, please let us know. There *easiest* way to generate an R script from an R Markdown document with `purl` to  is to run the command in the Console like so:

`knitr::purl(input="filename.Rmd", documentation = 1)`

> Run the `purl` command using the three options described above for `documentation` option and look at the output files. 

Inline R expressions are ignored by default. For example, if you had an inline R expression like this `` `r
sqrt(2)` `` 
the expression would not be included in the R script generated by `purl`. If you want to include inline expressions in the R script, you need to set the global R option `knitr.purl.inline = TRUE` before calling `knitr::purl()`. 

Remember way back when you generated your initial R Markdown document a default code chunk was added just below the YAML header?


````
```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
````

If you add `knitr.purl.inline = TRUE` to that code chunk, all inline expressions will be added to the R script. 

````
```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE, knitr.purl.inline = TRUE)
```
````

The last thing I want to mention is that you can *prevent* certain code chunks from appearing in the R Script by adding the option `purl = FALSE` to the chunk. For example, if you add this option to the `setup` chunk we just discussed that chunk will not appear in the final document.  

````
```{r setup, include=FALSE, purl = FALSE}
knitr::opts_chunk$set(echo = TRUE, knitr.purl.inline = TRUE)
```
````

Test the behavior of the different options for `purl` on your document. You can also use this funtion on *any* R Markdown document to quickly retrieve the code. For example, if you download the Rmd file for this page from GitHub you can run `purl` to quickly extract the R code.  

> **Recommendation** Use `purl` to generate a simple R script version of your R Markdown document *after* the document is finished and saved. You can then link to the file somewhere in your document. 

### Download Rmd

I hope by now you have seen that any document I present in this course has a link to a GitHub repo where you can download or copy the `.Rmd` file. That's great and all, but wouldn't it be nice if you could do it right from the HTML page? Well, you can by adding one simple line of code as a property of `html_document` in your YAML header ---`code_download: true`. 

```
output:
  html_document:
    theme: journal
    toc: true
    toc_float: true
    toc_depth: 3
    highlight: tango
    code_download: true
```

You could of course set the property to `false` except this is the default value and nothing will change. Look back at the top of this page and you should now see a `Code` button in the upper right corner. Click on the drop down and select `Download Rmd` and this entire page should be saved to your Downloads directory. 

> Go ahead and add this option to your YAML header.

### Code Folding

I have mentioned a time or two that the benefits of using R Markdown is the ability to ***execute*** and ***display*** code in your final document. If you go back to the default `setup` chunk at the top of your `.Rmd` you should see this:

```
knitr::opts_chunk$set(echo = TRUE)
```

I discussed this chunk previously in #5 of the [Chunk structure & options](https://stri-con.github.io/data-curation/2020/04/09/lesson-2/#chunk-structure-options-1) section in Lesson 2. Briefly, this is a *global command* that ensures all R code chunks are visible in the final document, unless you escape this behavior by using `echo = FALSE` in a particular chunk. Of course, you could also set the global option to `FALSE` as is `knitr::opts_chunk$set(echo = FALSE)` and then none of the R code would be visible at all. This is a perfectly fine option in some situations but not in others. 

Let's face it---code takes up a lot of space in a document and large code chunks are not particularly pleasing to look at. You may encounter situations where you both want the code available on a page *but* you also want to hide the code. For this we use a technique called ***code folding***. Near the bottom of [Lesson 0](https://stri-con.github.io/data-curation/2020/03/28/lesson-0/), I used some simple HTML to make a section that folds the R code for the Clifford Attractor. There is a little `Show/hide` button that allows you to look at the code if you want to; otherwise it is hidden by default. But this approach is a little clunky because you must **a**) know some HTML and **b**) include this for every chunk. 

R Markdown has a similar functionality for showing and hiding code but it only takes a single line of code added to the YAML header. Again, return to your YAML header and add the argument  `code_folding:` as a nested property of `html_document:`. Your two options for `code_folding:` are `show` and `hide`. 

```
output:
  html_document:
    theme: journal
    toc: true
    toc_float: true
    toc_depth: 3
    highlight: tango
    code_download: true
    code_folding: hide
```

Once you add this to the YAML header, the drop down `Code` button in the upper right corner of the page should now include `Show All Code` and `Hide All Code`. This allows the user to specify how they want to view the code in the document. Either property you set for `code_folding` will be the default state for the entire document. 

You should also notice that a new `Code` button appears next to every code chunk in your document. Again, if you want to exclude the code from individual chunks, just set `echo = FALSE` for that chunk and the code will not be included at all. 

> Add `code_folding:` argument to your YAML header and set a property value. 

<br/>

As far as I know there is no way of folding the *results* of a code chunk or folding indivudual chunks unless you use HTML. 

That's all for this assignment. 

## Session Info


```r
sessionInfo()
```

```
## R version 3.6.1 (2019-07-05)
## Platform: x86_64-apple-darwin15.6.0 (64-bit)
## Running under: macOS Catalina 10.15.3
## 
## Matrix products: default
## BLAS:   /Library/Frameworks/R.framework/Versions/3.6/Resources/lib/libRblas.0.dylib
## LAPACK: /Library/Frameworks/R.framework/Versions/3.6/Resources/lib/libRlapack.dylib
## 
## locale:
## [1] en_US.UTF-8/en_US.UTF-8/en_US.UTF-8/C/en_US.UTF-8/en_US.UTF-8
## 
## attached base packages:
## [1] stats     graphics  grDevices utils     datasets  methods   base     
## 
## other attached packages:
## [1] DT_0.12          rmarkdown_2.1    kableExtra_1.1.0 epuRate_0.1     
## [5] knitr_1.28      
## 
## loaded via a namespace (and not attached):
##  [1] Rcpp_1.0.4        later_1.0.0       highr_0.8         compiler_3.6.1   
##  [5] pillar_1.4.3      base64enc_0.1-3   tools_3.6.1       digest_0.6.25    
##  [9] jsonlite_1.6.1    evaluate_0.14     lifecycle_0.2.0   tibble_3.0.0     
## [13] viridisLite_0.3.0 pkgconfig_2.0.3   rlang_0.4.5       shiny_1.4.0      
## [17] cli_2.0.2         rstudioapi_0.11   crosstalk_1.0.0   yaml_2.2.1       
## [21] xfun_0.13         fastmap_1.0.1     stringr_1.4.0     httr_1.4.1       
## [25] xml2_1.2.2        htmlwidgets_1.5.1 vctrs_0.2.4       hms_0.5.3        
## [29] webshot_0.5.2     glue_1.4.0        R6_2.4.1          fansi_0.4.1      
## [33] readr_1.3.1       magrittr_1.5      promises_1.1.0    scales_1.1.0     
## [37] ellipsis_0.3.0    htmltools_0.4.0   assertthat_0.2.1  rvest_0.3.5      
## [41] xtable_1.8-4      mime_0.9          colorspace_1.4-1  httpuv_1.5.2     
## [45] stringi_1.4.6     munsell_0.5.0     crayon_1.3.4
```
