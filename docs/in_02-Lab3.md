

# Lab 3 {#Lab_2 .unnumbered}

## LAB AIM {.unnumbered}

Welcome to Lab 3. This is worth 8% (80 points) and you can drop your lowest lab out of six.

This is a ONE WEEK LAB. You only have one lab session (today) working on this during class, then until next Friday to finish up and write up. The maximum time it should take is about 4-5 hrs of your time.

<br>

------------------------------------------------------------------------

## LAB SET-UP (Important!) {.unnumbered}

### STEP 1: IMPORTANT - Create a Lab 3 project.. {.unnumbered}

You need a separate project for every lab!

-   **[1A]** Go here to read more about projects and to make a project for Lab 2: [Projects](#T1_Projects)

-   **[1B]** If you haven't already, open your project in R-Studio. It should look like this, but say Lab 2 for everything.

<div class="figure">
<img src="./index_images/im_T1_Projectcheck.png" alt="How to check you are in a project" width="100%" />
<p class="caption">(\#fig:L3-Projectcheck)How to check you are in a project</p>
</div>

<br>

------------------------------------------------------------------------

### STEP 2: Download code-Packages from the app store.. {.unnumbered}

Today we need a few new libraries/apps. Just like last week, select and install the ones you need from the "app store"

-   **[2A]** Follow the instructions here ([Installing Packages](#T2_Libraries_install)) to go to the 'install/app store' and install these package(s):

    -   `olsrr`

We will load and use them later in the lab.

------------------------------------------------------------------------

### STEP 3: Create your lab report structure {.unnumbered}

-   **[3A]** Using the tutorial instructions, make a new RMarkdown Report ([Markdown Tutorial](#T31_Basics))

-   **[3B]** Open your RmD report file (click on its name in the files tab, as long as you are running your project). Click visual mode and see if you can identify the code chunks, space for text and yaml files.

-   **[3C]** Using the [YAML tutorial](#Tut4E_YAML), edit the YAML code to include, A title, your author name, automatically created today's date, a floating table of contents, numbered sections (this won't appear until you start typing section headings) and the lumen theme. (See the screenshot below)

-   **[3D]** Now you are going to delete all "the friendly welcome text" (leaving the code at the top), so you have space to write your answers. (see the screenshot below)

<img src="./index_images/im_L2_SetupReport.png" alt="" width="100%" style="display: block; margin: auto;" />

-   **[3E]** Now, lets set up your report structure.

    -   Write the. following three level-1 chapter headings (bold), with the sub-headings as Level-2. Remember that to do this in `source` mode, you need to use a single \# for level 1 and a double \## for level 2. If you are in `visual` mode, type the headings, then click on that line, and click the little arrow next to Normal. \*see screenshot below)

        -   **Code checks**

        -   **Plant Sales**

            -   Data Description
            -   Data summary
            -   Quality control
            -   Exploratory Analysis
            -   Initial Regression

-   **[4F]** Click knit. This should work, ask you to save (then click knit again) and create a html file in your lab 2 folder AND show you it on your screen. IF YOU HAVE PROBLEMS ASK FOR HELP

-   **[4G]** Close down the html file so that you are back in your lab report again.

<br>

------------------------------------------------------------------------

### STEP 4: Get the input data {.unnumbered}

-   **[4A]** Go to Canvas Lab or click this link to download "[advertising.csv](https://psu.instructure.com/courses/2450096/files/189331361/download?download_frd=1)". Put it in your Lab 3 folder.

------------------------------------------------------------------------

## 2. SELLING HOUSEPLANTS {.unnumbered}

Houseplants are the new big thing and you're going to make the world want to buy them! You are a top advertising executive at Leaves&Co and you have been collecting data on how well your marketing campaigns have been running.

You have run 200 marketing campaigns over the last few year. For each one, you recorded:

-   How much you spent (in units of thousands of dollars) on
    -   TV adverts
    -   radio adverts
    -   and newspaper adverts
-   How many houseplants were sold (in thousands of plants).
-   You also know the "X-Factor" of how popular that plant was at the time (percentage popularity),
-   And you know the general height of type plant in inches.

Your job now is to explore the data work out which type of advertising campaign is the most effective.

### Your Answer format {.unnumbered}

**Imagine this is a real report in an advertising company. You will be graded on the professionalism of your final report.**

In all of your answers below, I expect good formatting, appropriate units and full sentences to explain your answers. For example, please make sure that you use headings and sub-headings to make your lab easier to follow and grade.

You are welcome to use any/all of the markdown features we have learned so far, for example equations, text formatting, pictures, code-chunk options or anything else that makes your report look more professional.

All the methods to answer these questions are either things you have done in previous labs or they are in the Tutorials.



### Step 2.1: Read in data {.unnumbered}

-   Read the data into R and assign it to a variable called "adverts"

<br>

### Step 2.2: Exploratory analysis/study design {.unnumbered}

-   Summarize the the dataset using R and suggest any quality control issues (e.g. unusual values, missing data etc) - Tutorial 7,

-   Write up your study design e.g. object of analysis, sampling frame, the potential population your CEO has in mind, variables (and units.), sample size.

<br>

### Step 2.3: Quality control {.unnumbered}

You should have noticed a few issues with your dataset.

-   Use [Tutorial 8.4.2](https://psu-spatial.github.io/Stat462-2026/T8_Wrangle.html#tidyversedplyr-filter-command) on filtering to remove the row containing the illogical data point

-   Use the "na.omit" command on "adverts" to remove any rows containing missing values.

-   (<https://www.r-bloggers.com/2024/12/how-to-use-na-omit-in-r-a-comprehensive-guide-to-handling-missing-values/>)

-   In the text below your code, record what you did, eg how many rows were removed? Why? Why do you think -999 wasn't a "real" value.

<br>

### Step 2.4: Exploratory analysis {.unnumbered}

-   Now that you have tidied your data, repeat your summaries of the dataset as a whole

-   Create a professional histogram of each variable and underneath each one, write a few sentences describing the each variable and anything you see. (for histograms, see [Tutorial 6.3](https://psu-spatial.github.io/Stat462-2026/T6_plots.html#ggplot2-histograms)).

<br>

### Step 2.5: Initial scatterplots {.unnumbered}

You are trying to predict sales.

FOR EACH PREDICTOR (TV, Radio, Newspaper, Plant height)

-   Use the `lm()` command to create a simple linear regression model to predict sales ([see this 2025 tutorial](https://psu-spatial.github.io/Stat462-2025/in_T14_Regression.html#1_Regression))

-   Create a professional scatterplot for each of the others against your response including the line of best fit (for scatterplots, see [Tutorial 6.2](https://psu-spatial.github.io/Stat462-2026/T6_plots.html#ggplot2-scatterplots))

-   Underneath comment on the relationship that each variable appears to have with sales, and describe the form/strength/direction/features of the scatterplot.

-   Write out the equation of each model, explaining what all coefficients mean in the context of the problem),

-   Discuss whether you think each model meets the LINE assumptions from what you see, showing me you understand what each assumption is.

Hint, think about what I have asked you to do in past labs to answer this.

<br>

### Step 2.6: Favourite model {.unnumbered}

-   Out of the three models, where do you see the greatest increase in sales if you increase the advertising budget?

-   Provide evidence to justify your answer (thinking about uncertainties on your estimate).

-   Which model explains the most variability in the sales data? Provide evidence to justify your answer.

-   Are there any issues with your answers (e.g. are all the models valid? - there might be no issues! I genuinely can't remember how I set the data)

### Step 2.7: Peace lilies {.unnumbered}

-   You have a new client who needs to sell 8000 peace lilies but hates newspapers. Conduct an hypothesis test to assess whether you typically sell less than 8000 plants in a situation where you spend zero-money on newspaper advertising. You are happy to be wrong one time in 25. Can you advise your client it is OK to not advertise in newspapers?

### Step 2.8: TV fears {.unnumbered}

-   Another client is skeptical of TV. Use the ANOVA table output to conduct a hypothesis test to examine if there is evidence to suggest a relationship between TV advertising and plant sales at a significance of 1%.

### Step 2.9: Summary {.unnumbered}

-   Imagine you have to summarise what you have done for your boss. What are the messages they should take from this dataset in terms of their advertising campaigns?

Congrats! Finished

------------------------------------------------------------------------

<br>

## 4. WHAT TO SUBMIT {.unnumbered}

### If you are using your own laptop {.unnumbered}

Press knit one final time. You will have created two files; a `.Rmd` file containing your code and a `.html` file for viewing your finished document.

Find the html and RmD files in your Lab 1 folder on your computer. Double click the html file to open it in your browser and check it's the one you want to submit.

**You need to submit BOTH of these files on the relevant Canvas assignment page.**

You can also add comments to your submission as needed on the canvas page, or you can message Dr G.

<div class="figure">
<img src="./index_images/im_T1_WhattoSubmit.png" alt="Find them in your STAT462 folder on your computer" width="100%" />
<p class="caption">(\#fig:L1-Submit)Find them in your STAT462 folder on your computer</p>
</div>

### If you are using Posit Cloud online {.unnumbered}

1.  Press knit one final time. You will have created two files; a `.Rmd` file containing your code and a `.html` file for viewing your finished document.

2.  Go to the files tab an click on the little check-box by the RmD file. Then click the blue "more button" and press export. Save onto your computer.

<div class="figure">
<img src="./index_images/im_T1_CloudSubmit.png" alt="How do download the files from PositCloud" width="100%" />
<p class="caption">(\#fig:L1-CloudDownload)How do download the files from PositCloud</p>
</div>

2.  Uncheck the .RmD box and click the box by the html file. Then click the blue "more button" and press export. Save onto your computer.

**You need to submit BOTH of these files on the relevant Canvas assignment page.**

You can also add comments to your submission as needed on the canvas page, or you can message Dr G.

<br>

## CHECK YOUR GRADE! {#CheckGradeL3 .unnumbered}

### RUBRIC {.unnumbered}

This is how you will be graded (percent)

-   **HTML FILE SUBMISSION - 10 marks**

-   **RMD CODE SUBMISSION - 10 marks**

-   **MARKDOWN/CODE STYLE - 20 MARKS** <br> How to get full marks for this:

    -   Your YAML code is working e.g. when you press knit, you see your author name, a table of contents etc etc (see step 4)

    -   Your code and document is neat and easy to read. LOOK AT YOUR HTML FILE IN YOUR WEB-BROWSER BEFORE YOU SUBMIT. For example:

        -   There is a spell check next to the save button.

        -   You have written in full sentences and it is clear what question your answers are referring to.

        -   You have included units!

        -   You have included formatting like headings/subheadings and bullets. Many people make typos with the headings. The easiest way to do it is to use visual mode, then highlight the text and click Header 1, Header 2 etc.

-   

[80 marks total]

Overall, here is what your lab should correspond to:

<table class=" lightable-classic-2 table table-striped table-hover table-responsive" style='font-family: "Arial Narrow", "Source Sans Pro", sans-serif; margin-left: auto; margin-right: auto; margin-left: auto; margin-right: auto;'>
 <thead>
  <tr>
   <th style="text-align:left;"> POINTS </th>
   <th style="text-align:left;"> Approx grade </th>
   <th style="text-align:left;"> What it means </th>
  </tr>
 </thead>
<tbody>
  <tr>
   <td style="text-align:left;"> 98-100 </td>
   <td style="text-align:left;"> A* </td>
   <td style="text-align:left;"> Exceptional.  Above and beyond.   THIS IS HARD TO GET. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 93-98 </td>
   <td style="text-align:left;"> A </td>
   <td style="text-align:left;"> Everything asked for with high quality.   Class example </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 85-93 </td>
   <td style="text-align:left;"> B+/A- </td>
   <td style="text-align:left;"> Solid work but the odd  mistake or missing answer in either the code or interpretation </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 70-85 </td>
   <td style="text-align:left;"> B-/B </td>
   <td style="text-align:left;"> Starting to miss entire/questions sections, or multiple larger mistakes. Still a solid attempt.  </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 60-70 </td>
   <td style="text-align:left;"> C/C+ </td>
   <td style="text-align:left;"> It’s clear you tried and learned something.  Just attending labs will get you this much as we can help you get to this stage </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 40-60 </td>
   <td style="text-align:left;"> D </td>
   <td style="text-align:left;"> You submit a single word AND have reached out to Dr G or Aish for help before the deadline (make sure to comment you did this so we can check) </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 30-40 </td>
   <td style="text-align:left;"> F </td>
   <td style="text-align:left;"> You submit a single word…....  ANYTHING..                Think, that's 30-40 marks towards your total…. </td>
  </tr>
  <tr>
   <td style="text-align:left;"> 0+ </td>
   <td style="text-align:left;"> F </td>
   <td style="text-align:left;"> Didn’t submit, or incredibly limited attempt.  </td>
  </tr>
</tbody>
</table>
