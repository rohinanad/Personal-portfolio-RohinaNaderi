# Homework 2: Tab <!-- omit in toc -->

- [Overview](#overview)
- [Background](#background)
- [Requirements](#requirements)
  - [Background Image](#background-image)
  - [Current Time](#current-time)
  - [Greeting](#greeting)
  - [Menu \& Extra Functionality](#menu--extra-functionality)
  - [Design](#design)
- [Submission](#submission)

## Overview
<hr>

One of the most common ways users interact with HTML, CSS, and JavaScript while browsing is not only through webpages, but also extenstions--small packaged software that can modify the behavior or experience of a user's browser.

In this assignment, we will be creating an extenstion for Chrome, which modifies the new tab page. By default, Chrome's new tab contains a simple page with a search bar and some frequently visited websites, however, in this assignment we will be overriding the default new tab with a custom page designed by you!

We will also be utilizing several APIs--**application programming interfaces**--to make our new tab more flavorful! Application programming interfaces are a way for different applications to interact with each other.

<div style="break-after:page"></div>

## Background

<hr>

Firstly, if you are not using Chrome, please do so for this assignment. Though the extenstion should run on any chromium-based browser, we will only be testing/grading your extenstion on **Chrome**. Also, if you are currently using any extenstions that alter Chrome's default new tab, you must disable them to ensure your extenstion works correctly.

Though they may seem complex at first, extenstions are relatively simple to begin working on and deploying. Start by [cloning the GitHub repository](https://www.github.com/krizh-p/CS395-HW2-Tab) that contains starter code for you.

You can do this by either downloading the .Zip file from GitHub and extracting it normally or using the command below in a terminal:

    git clone https://github.com/krizh-p/CS395-HW2-Tab

Opening the folder you downloaded from GitHub will display multiple files and folders.

<hr>

Let's go through the files you see.

Begin by opening `manifest.json`. The `manifest.json` file is the only file that every extenstion must contain; this file contains metadata the extenstion gives Chrome to help explain/list the permissions the extenstion requires as well as other functionalities such as background scripts and content scripts (which we will not be using here).

Opening this file you will see a JSON-formatted file containing useful information regarding the extenstion.

- Inside the file, you should edit the following keys:
  - `author` - with your name
  - `name` - give your extenstion a unique name
  - `description` and `version` - this are optional to edit, but feel free to utilize them.
  
Finally, take a look at the following key:

    "chrome_url_overrides": {
        "newtab": "newtab.html"
        }

Here we are informing Chrome that we will be overriding Chrome's default new tab (`"newtab"`) with the path to our own page, `"newtab.html"` (which is located in the same directory as this manifest.json). Now, whenever you open a new tab, Chrome will load `newtab.html`--this will be the file containing your HTML.

Note the other folders located in the GitHub repo: `assets`, `css`, and `js`. You must place all assets such as `.png` or `.jpeg` files in the `/assets/` subdirectory, and all .css and .js files in their respective folders.

<hr>

Lastly, let's go over how you can add this extenstion to Chrome, so that when you begin work, you can actually test the extenstion in real time. First open up Chrome, and head to settings:

![Open settings](image.png)

![Extenstion Settings](image-1.png)

![Load unpacked](image-2.png)

After clicking "Load unpacked," in the File Explorer popup, select the folder that contains your extenstion files.

![Selct folder](image-3.png)

You should now see your extenstion loaded into Chrome

![Extenstion loaded](image-5.png)

`This page is very important because if your extenstion has errors, they will be displayed here, next to the "Details" button!`

<div style="break-after:page"></div>

## Requirements

<hr>

The extenstion should contain the following features:

### Background Image

- When a new tab is opened, the page's background should be set to a randomized image. You can use public APIs like the Unsplash API or Picsum.
  - For your convienence, here are some URLs that return a random image: `https://source.unsplash.com/random/1920x1080/?modern` and if that doesn't work try `https://picsum.photos/1920/1080`.
    - In the Unsplash API link, you can replace the GET parameter value `modern` with another keyword to the type of image you want returned (ie. landscapes, clouds, city).

### Current Time

- On top of the background image, the center of the new tab page should display the current time (HOUR:MINUTE) in a large, easily visible font.

- While the user hovers their mouse over the current time, the time should expand to also display seconds (HOUR:MINUTE:SECONDS).

### Greeting
  
- Below the current time, in slightly smaller text, show a greeting, such as "Hello, (name)". You may keep a placeholder name for the first time the extenstion is opened.

- Users should be able to modify their name by double clicking on their name--the "(name)" part should become editable and the user should be able to add input.
  - This text should be saved and persist when the user opens a new tab. _([Hint: Chrome storage documentation](https://developer.chrome.com/docs/extensions/reference/storage/)_.)

### Menu & Extra Functionality

- Somewhere on your screen, add a menu button which implements **two** of the following three choices; feel free to be more creative with these extra functions and play around/experiment with different CSS/HTML/JS.
  - #### Random Quote
    - The bottom of the screen should contain a centered, randomized quote.
    - You can utilize the Quotable API at this URL to obtain a random quote: `https://api.quotable.io/random`.
  - #### Pomodoro Timer
    - Implement a Pomodoro timer feature that allows users to set focused work intervals and short breaks
    - Display the countdown timer prominently on the screen.
    - Include buttons for starting, pausing, and resetting the timer.
  - #### Sticky Notes
    - Provide the option for users to create and manage sticky notes.
    - Allow users to add, edit, and delete sticky notes with personalized content.
    - Sticky notes should be movable and resizable on the screen.

### Design

The design of the new tab should prioritize accessibility, usability, and aesthetic appeal. Ensure that the font and color choices are visually pleasing and easy to read. Your new tab should have intuitive interactions the extension should work seamlessly on Google Chrome's new tab page after installation. You should maintain a cohesive design across all your elements.

Please feel free to add creative choices that reflect you!

<div style="break-after:page"></div>

## Submission

<hr>

Submit a Zip file in the following format to Blackboard by September 12th before class:

``LASTNAME-CS395-HW2-Tab.zip``

The zip file should contain a folder with the same name as the zip file, and the folder inside should contain all code. For example: `LASTNAME-CS395-HW2-Tab.zip --> LASTNAME-CS395-HW2-Tab --> (files or folders pertaining code, such as newtab.html, /js/ )`.

Please email us if you have any questions or need an extenstion. Late Submissions won't be accepted without prior approval.