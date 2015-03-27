# Final Project Assignment 2: Explore One More! (FP2) 


# OPL-Project
## Exploration of the SlideShow Library
######by Alex Nevers

For the second library exploration, I chose SlideShow. This slideshow proved to be not all that difficult to work with. Each slide is its own procedure simply named "slide", with specifications for slide width, title, alignment, and timeout following as arguments. The other important argument is easily the element list, or "item", which actually prints bullet points. It's possible item is also used for something other than bullet points, though I would have to explore the library further to find out, which i intend to.

The first section of my output is generalizing slides, which is shown b using number variables to print slide numbers in each successive slide, whic is easily done. Im interested in finding out how this could be useful past integers. THe next section of code output is using successive steps or bullet points. In the previous section, hitting space brought you to the next slide with text already visible. Using the successive steps method means that each next item or bullet point displays after hitting space, as most slideshows do. This also comes with the option to display an item, remove it, and the display a different item in its place, as is shown in the output (Third step displays, is removed, New Third step and the fourth step shown)

I used the last section to try out more fun things like text formatting, which will be useful when creating more graphic slides. Bold, Bold+Italic, and serif text were all displayed, along with an example or a paragraph in bplace of bullet points. I intend to study this library further, maybe finding a way to incorporate the icon or image librar into it as well, to create more graphic and visually interesting output.


####Output

Capture of output from the below program [here.](http://imgur.com/a/9iu7s)


####Test Code
    #lang slideshow

    (define (slide-n n)
    (slide
    #:title "How to Generalize Slides (1 - 3)"
    (item "This is slide number" (number->string n))))
       (slide-n 1)
       (slide-n 2)
       (slide-n 3)

    (slide
     #:title "Example of Successive Steps"
     (item "First step")
     'next
     (item "Second step")
     'next
     'alts
     (list (list (item "Tentative third step")
                 'next
                 (item "This isn't working... back up"))
           (list (item "Third step that works")))
     'next
     (item "Fourth step"))


    (slide #:title "Let's test out font stuff here" #:layout 'center
           #:timeout #f 
           (item (bt "HEY THIS IS BOLD"))
           (item (bit "This is super emphasized"))
           (item (rt "Heres some serif text"))
           (para "Heres an awful nice long run on sentence to give you an idea of what a paragraph looks like in a slideshow.
           We can make this even bigger by adding another sentence to it! 
           Wow, lookit it go. What a nice paragraph. Wowza."))
