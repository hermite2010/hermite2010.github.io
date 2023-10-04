---
layout: default
title: "Datawrapping Your Way to Victory"
author: Joseph Bradley
description: Basic tutorial on how to use Datawrapper
image: ![Datawrapper logo](/assests/images/Datawrapper Logo.png)
---
# Get Your Data Visualization Game to the Next Level with Datawrapper
In the realm of data science, presenting insights in a visually appealing and digestible manner is crucial. It's not just about numbers; it's about telling a compelling story that resonates with your audience. This is where Datawrapper steps in, empowering data scientists to create stunning, informative graphics effortlessly.


## Getting Started and Step One: Uploading Data
#### Signing Up

![signing up for Datawrapper](/assets/images/Screenshot 2023-10-04 112606.png)

This is straight forward, sign up or sign in by whatever method suits you. After signing in we can begin to use the magic of Datawrapper.

#### Choosing/Uploading Your Data

Once you are signed in, we choose to create a NEW graph, and it will take us to a screen that looks like this:

![step one](/assets/images/Screenshot 2023-10-04 112831.png)

Here we can choose a variety of different ways to upload our data. For this tutorial we will use the Income vs. Life expectancy data set that they provide. 

![select the data](/assets/images/Screenshot 2023-10-04 112913.png)

### Step Two: Check and Describe
#### Check the data
Now that we have the data loaded we should double check to make sure the data looks right and includes the information we want. There is a lot that we can do on this page like restricting variables to a range, checking variable distributions, and more. But if you know your data is good to go, this is more of a formality. 

![step two](/assets/images/Screenshot 2023-10-04 113043.png)

We can also choose to exclude parts of the data to make graphic creation more streamlined. In our case, we will exclude the population column. 

![exlude population](/assets/images/Screenshot 2023-10-04 113239.png)

### Step Three: Visualize
#### Choosing the Chart Type
Datawrapper offers a wide array of chart types. From classic bar charts to intricate Sankey diagrams, depending on what you want to convey, there is sure to be an option for your needs. Continuing with our example, we will use a scatter plot. 

![step three](/assets/images/Screenshot 2023-10-04 113310.png)

Also, be sure to name your graph!

#### Refine

Now we decide what variable we want on the axis. The options will be all the columns that you decided to include in your data set from step two. Lets set GDP as the horizontal axis and Fertility Rate as the vertical axis. 

![step refine](/assets/images/Screenshot 2023-10-04 113601.png)

### Additional Variables

Even with two axis, we can convey information about multiple variables at the same time. Lets do this with color. Find the "Customize Color" switch that looks like this:

![customize color](/assets/images/Screenshot 2023-10-04 113805.png)

Now we can choose another variable to convey on our graph. We will pick colors for the different continents that the countries are in. 

![Continent Colors](/assets/images/Screenshot 2023-10-04 113811.png)

We can also choose size as a way to convey another variable. Lets choose child mortality rate for this variable. (Be sure to label the caption correctly, unlike me!)

![Size](/assets/images/Screenshot 2023-10-04 113956.png)

Shape is also an option to convey yet another variable. For this tutorial we will change the shape but not attribute it to a variable. 

![shape](/assets/images/Screenshot 2023-10-04 114209.png)

Lastly, we can choose to show a trend line that best fits the data. The calculations are done automatically with the columns you chose as the x and y axis, all we have to do is choose what line would work best. In this tutorial I selected the power trend line.

![trend line](/assets/images/Screenshot 2023-10-04 114250.png)

### Ensuring Accessibility and Clarity
A great thing about Datawrapper is the ability to create inclusive visuals. People with visual disabilites can find many visuals hard to understand. For example, below your graph-in-progress there is a selection that allows you to see how your graph would look for various people with visual diabilites. 

![visual disabilites](/assets/images/Screenshot 2023-10-04 114307.png)

### Annotate
In the refine section here we can add alternate description to our graph so that blind people can also have a web reader tell them about the graph we made. It is also here that we edit the general description, title, source, claim authorship, and provide access to the data we made the graph with. 

![Annotate](/assets/images/Screenshot 2023-10-04 114533.png)

### Layout
In layout, we can choose a theme for our graph. In our example I chose the high contrast theme.

![theme](/assets/images/Screenshot 2023-10-04 114645.png)

It is also here that we can choose to allow links to the data to show up on the graph. We can also have social media sharing links for quick sharing of the graph. 

![links](/assets/images/Screenshot 2023-10-04 114710.png)

### Step Four: Publish and Embed
Now we have nearly reached the end of our graphic creation journey. One of the last things we need to do it publish our graph. Since we have an account, it will be placed on our account's dashboard after publication. If we do not publish we cannot share our graph in all of it's glory. 

![Publish](/assets/images/Screenshot 2023-10-04 114738.png)

After we publish, we are now able to more effectively share our graph. We are provided a link and code for embedding into websites or markdown files. 

![Link and embed](/assets/images/Screenshot 2023-10-04 114752.png)

And that is it! We made our graph!

# Look at the graph we made!
It is embedded into this blog post and completley interactable!
(I made a few changes to some errors, but it should generally look the same)

<iframe title="GDP and Fertility Rate (children per woman)" aria-label="Scatter Plot" id="datawrapper-chart-Cr4lj" src="https://datawrapper.dwcdn.net/Cr4lj/3/" scrolling="no" frameborder="0" style="width: 0; min-width: 100% !important; border: none;" height="400" data-external="1"></iframe><script type="text/javascript">!function(){"use strict";window.addEventListener("message",(function(a){if(void 0!==a.data["datawrapper-height"]){var e=document.querySelectorAll("iframe");for(var t in a.data["datawrapper-height"])for(var r=0;r<e.length;r++)if(e[r].contentWindow===a.source){var i=a.data["datawrapper-height"][t]+"px";e[r].style.height=i}}}))}();
</script>

# Conclusion
As data scientists, we love our data. We spend hours cleaning, manipulating, and working our data. We have amazing tools to help us do that. Unfotunately, those tools are not optimized for visualizing our data. Datawrapper is just one tool that is better suited for visualizing your data than R or Python. It is simple, straigh forward, and can elevate your visualization game. Impress your coworkers, boss, and loved ones with the interactable graphics that you can now create. 

So why wait? Head over to Datawrapper, sign up, and start turning your data into engaging narratives today!

Happy visualizing!
