# How to design a CSS-file clearly

Normally CSS files have the following structure:

    .example {
        height: 100%;
        color: blue;
    }
    .example2, .example3 { …

In the course of the design, this becomes quite a long list and you can't stop scrolling. Very cumbersome handling.

The next step is to display each class, tag or ID in one line:

    .example {height: 100%; color: blue}
    .example2, .example3 { …

Then we loosen it up a bit with Enter and Tabs:

    .example         {height: 100%; color: blue}
    .example2, 
    .example3        { …

As some classes consist of many instructions, the line breaks at some point and because they also contain different instructions, it becomes confusing again.

And now comes the real hack: We group the various instructions according to their content. This may mean that we have to write down some classes several times, but it remains very clear, compact and scrollwheel-friendly:

    /* COLOR */
    .example         {color: blue; background-color: purple}
    .example2        {color: red}
    
    /* DIMENSIONS */
    .example         {height: 100%; width: 50%}
    .example3        {height: 50%; width: 100%}
    
    /* WHAT EVER */
    .example2, 
    .example3        { …

The basic grid in the 'style.css' has proven itself (it starts with what could be important first, etc.). But a different order is also possible; the terms after that serve as examples). The 'empty-style.css' is your template, which you can fill immediately.

The good thing about this is that the order of processing does not get mixed up during grouping!

I always insert MEDIA QUERIES indented after the main instruction. This makes it easier to find your way around and also speeds up troubleshooting:

    .example         {color: blue; background-color: purple}
    .example2        {color: red}
                         @media only screen and (min-width: 500px) 
                         {.example2 {color: green}
