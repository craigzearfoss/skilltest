# WHCC Developer Demo
Please create a private fork from this repo. 
Please add your WHCC contact to the repo as a collaborator when you're done.

# Description
Complete this web-based news reader that leverages the Hacker News API.
Some work has already been done in the index.html file.
Please do not use a framework, just vanilla javascript or typescript.
You may use webpack, babel, or any other compiler you're comfortable with.
You may also use ES6, do not worry about supporting ES5.
Try to timebox your work to approximately 1-2 hours.

# Requirements
1. The app should initially display a list of the 15 most recent Hacker News stories in descending order.
1. Each story list item should show the title, the author's name, and the time it was posted.
1. The users are very impatient so please display each story as soon as it is fetched.
1. The app should support infinite scrolling. When a user reaches the bottom of the page it should load more stories.
1. The app should be appealing to users on both desktop and mobile, please style it to the best of your ability.

# Core Values of Design
1. Polished simplicity in the user experience and aesthetic.
1. Focus on empathy for the user’s experience.

# Resources
1. Hacker News API: https://github.com/HackerNews/Api
1. Hacker News: https://news.ycombinator.com/news

# Discussion Notes
1. What decisions did you make before you began development?

A long time ago I used an infinity scroller so I googled one for reference. I think the only thing I really used from it was the javascript to bind the scroll event to determine when to load more messages. That's not something I've done in a long while so it's always good to be able to find the right quickly info when you need it. It also gave me the idea of loading a page of stories at a time, because, to be honest, if I hadn't seen that I might have loaded stories one at a time.

2. How did you decide what to work on in order to meet the time constraint?

I first wrote the functions to make the initial api request and load the first 15 stories and display them. 

Once I had that I moved them to a self-invoking function.  

Then I bound the scrolling event to load more stories. I made a function to load a full page worth of stories at once, but I fetched the stories individually in a separate function. I add a counter to keep track of the stories as they loaded so that a new page wouldn't be loaded until the current one was finished. 

I experimented with loading the stories one at a time, but eventually decided to just load a full pages because it was faster and looked smoother.

I realized that if a page was so big that there wasn't a scroll bar it wouldn't load more stories so on the intial page load I kept loading stories until the page was full so that there would be a scroll bar.  I then bound a resize event so that enough stories to fill the page would be loaded when the window was resized.

3. What was your decision making process for your code organization?

What was your decision making process for your code organization?
I decided to use a self-invoking function to make it highly modularized so it could easily be plugged in anywhere and ported to other projects.

4. If you had more time, what would you have implemented?

I would pretty up the html and styles. I'd probably use a JavaScript templater.  I'd also adjust the scrolling code so that it can be insterted into a div or other html element, instead of just the body. I'd pass in the id of the element to the self-invoking function.

