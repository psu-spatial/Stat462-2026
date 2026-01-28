

# Lab 1 {#Lab_1 .unnumbered}

## Aim

Welcome to Lab 1. This is worth 8% (80 points) and you can drop your lowest lab out of six.

This is a ONE WEEK LAB. You only have one lab session (today) working on this during class, then until next Friday to finish up and write up. The maximum time it should take is about 4-5 hrs of your time.

The aim of this lab is to get comfortable creating your lab reports, and how to edit both text and code. Finally you will get to apply some knowledge from the course so far.

<br>

------------------------------------------------------------------------

<br>

## LAB SET-UP (Important!) {.unnumbered}

This might take a while during week 1, but I promise that after a few labs, this will be very easy.

### STEP 1:  Install/update R and R-Studio {.unnumbered}

If you are using R on your computer, you should be running R version "4.5.2 [Not] Part in a Rumble" (look at the top of the console), and R-Studio version 2026.01.0. (apple blossom).

If you've already completed Homework 1 & installed/updated R, then, move to STEP 2. If you're using PositCloud, move to STEP 2.

-   **[1A]** First click here to learn more about R, R-Studio and R-Markdown: [What are R and R-Studio](#WhatIsR)

-   **[1B a]** If you're not planning to use your own computer, go here to make an account and log into Posit Cloud, which will let you use R online. [Tutorial on Posit Cloud](#Setup_Online)

-   **[1B b]** If you are planning to use your own laptop but don't yet have R and R studio, go here to learn how to install them. [Tutorial on Installing R](#Setup_Desktop)

-   **[1B c]** if you already have R on your laptop, you probably need to update it! You should be running R version "4.5.2 [Not] Part in a Rumble" (look at the top of the console), and R-Studio version 2026.01.0. (apple blossom). If not, click here to learn more - [Tutorial on Updating R](#Setup_UpdateDesktop)

And finally,

-   **[1C]** Especially if you are new to R, use the tutorials to take a look around! Or take this opportunity to complete the Data Camp section of Homework 1. [NEED TUTORIAL LINK]

<br>

### STEP 2: Creating a project..

It's likely that past R users did not have to use projects, but they are WONDERFUL.

-   **[2A]** Go here to read more about projects and to make a project for Lab 1: [Projects](#T1_Projects)

-   **[2B]** If you haven't already, open your project in R-Studio. It should look like this.

<div class="figure">
<img src="./index_images/im_T1_Projectcheck.png" alt="How to check you are in a project" width="1049" />
<p class="caption">(\#fig:L1-Projectcheck)How to check you are in a project</p>
</div>

<br>

------------------------------------------------------------------------

### STEP 3: Download code-Packages from the app store.. {.unnumbered}

Just like there are millions of apps for your phone, there are about 20,000 'packages' or 'libraries' that you can download and use in R. Just like phone apps can do wildly different things, some of the Packages will contain data, others might help you make beautiful graphics, others might do complex statistics, or speed up performance.. The options are endless.

BUT! Just like phone apps, you don't want to have every package in existence downloaded from the app-store onto your computer. Instead, we select and install the ones we need from the R "app store".

-   **[3A]** Read [About Packages](#T2_Libraries_about), and [Installing Packages](#T2_Libraries_install)

-   **[3B]** Follow the instructions to go to the 'install/app store' and install these three packages:

    -   `rmdformats`

    -   `tidyverse`

    -   `ggstatsplot`

We will load and use them later in the lab.

------------------------------------------------------------------------

### STEP 4: Create your lab report

-   **[4A]** Watch the quick video overview of R Markdown. [Markdown Tutorial](#T31_Basics)

-   **[4B]** Using the tutorial instructions, make a new RMarkdown Report ( [Markdown Tutorial](#T31_Basics))

-   **[4C]** Open your RmD report file (click on its name in the files tab, as long as you are running your project). Click visual mode and see if you can identify the code chunks, space for text and yaml files. 

-   **[4D]** Using the [YAML tutorial](#Tut4E_YAML), edit the YAML code to include, A title, your author name, automatically created today's date, a floating table of contents, numbered sections (this won't appear until you start typing section headings) and the lumen theme. 

-   **[4E]** Click knit. This should work and create a html file in your lab 1 folder AND show you it on your screen. IF YOU HAVE PROBLEMS ASK FOR HELP (as long as you have first installed `rmdformats`)

------------------------------------------------------------------------

<br>

## QUESTIONS

### STEP 5:  R-Markdown {.unnumbered}

-   **[5A]** Close down the html file so that you are back in your lab report again.

-   **[5B]** Now you are going to delete all "the friendly welcome text" (leaving the code at the top), so you have space to write your answers.

<img src="./index_images/T3_DeleteText.png" alt="" width="100%" style="display: block; margin: auto;" />

-   **[5B]**  Create a level 1 heading called "Questions" 


<img src="./index_images/L3B_Questions1.png" alt="" width="100%" style="display: block; margin: auto;" />


The result should look like this


<img src="./index_images/L3B_Questions2.png" alt="" width="100%" style="display: block; margin: auto;" />

-   **[5C]**  Below this, using bullet points and clearly marking what your answer refers to, answer these questions:

     +   [**QUESTION 1:**]{.underline} Using a bullet point list (hint visual mode, then click the bullet button), in your own words, state the difference between viewing your lab script using the Source Button vs the Visual Button (try it!) [Tutorial](#T32A_visualmode)
    

      +  [**QUESTION 2:**]{.underline} In your own words and based on what you learned from Monday's lecture notes (lecture 3D), describe the central limit theorem. 
   


Press knit and check it still works.

------------------------------------------------------------------------

<br>

### STEP 6: R-Coding {.unnumbered}

The following questions link to your homework and datacamp. For those who have programmed in R, they are trivial, but use it to get used to the markdown format.

In the space for Question 6, make a new code chunk. (either a single one or mulitple is fine). Answer the following questions using R.

You get the first one for free :)

1.  Calculate the sum of 1+1 and assign it to the variable 'a' (e.g. a \<- 1+1)


``` r
a <- 1+1
```

2.  Calculate the sum of 1+3 and assign it to the variable 'b'

3.  Calculate your age to the power 4 and assign it to a variable called yourname (e.g. mine would be `helen <-` )

4.  Calculate the sum of a/b and assign it to the variable ans

5.  Calculate the number of characters in the word "Llanfairpwllgwyngyllgogerychwyrndrobwllllantysiliogogogoch" using the nchar commannd (hint <https://www.educative.io/answers/how-to-calculate-the-size-of-a-string-using-nchar-in-r>, and USE QUOTES)

------------------------------------------------------------------------

<br>

### STEP 7: MPG Data {.unnumbered}

Should update Jan27

------------------------------------------------------------------------

<br>

## What do I submit? {#Lab_1_01}

Press knit one final time.

You will have created two files; a `.Rmd` file containing your code and a `.html` file for viewing your finished document. You need to submit BOTH of these files on the relevant Canvas assignment page. You can also add comments to your submission as needed on the canvas page, or you can message Dr G.

To download them on posit cloud, click on the check box by the RmD and html, then click on the little blue cog on the far right of the Files tab (you might need to maximise the window), then press export.
