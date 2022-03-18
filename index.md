# Assignment 1:

## Part A Meme:

![meme](https://github.com/antariksh2001/stats220/blob/main/my_meme1.png)

The R code used to create this meme is as follows:

```r

library(magick)

old_homer <- image_read("https://static.wikia.nocookie.net/clarence/images/b/b8/Screenshot_%285360%29.png/revision/latest/scale-to-width-down/1920?cb=20161117010123")%>%
  image_scale(500)

mid_homer <- image_read("https://media.wired.com/photos/593252a226780e6c04d2af1a/master/pass/the-homer-ft.jpg")%>%
  image_scale(500)

mid_homer_cropped <- image_crop(mid_homer, "250x0") %>%
  image_scale("x400")


chad_homer <- image_read("https://ih1.redbubble.net/image.2154415465.9777/mp,504x498,matte,f8f8f8,t-pad,600x600,f8f8f8.jpg")%>%
  image_scale(500)%>%
  image_charcoal()


background1 <- image_blank(width = 600, 
                           height = 300, 
                           color = "#000000")%>%
  image_annotate(text = "People who edit memes in MS Paint", 
                 color = "#FFFFFF", 
                 font = "Comic Sans",
                 gravity = "center",
                 size = 30)

background2 <- image_blank(width = 600, 
                           height = 300, 
                           color = "#000000")%>%
  image_annotate(text = "People who make original memes\n in Photoshop/GIMP", 
                 color = "#FFFFFF", 
                 font = "Comic Sans",
                 gravity = "center",
                 size = 30)

background3 <- image_blank(width = 600, 
                           height = 500, 
                           color = "#000000")%>%
  image_annotate(text = "People who write 50 lines of code\n to make *aesthetic* memes in R", 
                 color = "#FFFFFF", 
                 font = "Comic Sans",
                 gravity = "center",
                 size = 30)

top_vector <- c(old_homer, background1)
top_row <- image_append(top_vector)

mid_row_vector <- c(mid_homer, background2)
mid_row <- image_append(mid_row_vector)

bottom_row_vector <- c(chad_homer, background3)
bottom_row <- image_append(bottom_row_vector)

meme <- c(top_row, mid_row, bottom_row)%>%
  image_append(stack = TRUE) %>%
  image_scale(800)

image_border(meme, "hotpink")

image_write(meme, "my_meme1.png")


```

## Inspiration: 

This meme was inspired from the **Drake Hotline Bling** meme and has been adapted so that it:
* Uses a couple of ✨*fabulous felines*✨ 
* Is topical to the [University of Auckland](https://www.auckland.ac.nz/en.html). 

### An Example of the Original:
![Hotline Bling meme](https://images.ctfassets.net/pwv49hug9jad/5K39I2JrCfevWx2vrXJwkr/def7943e979c90cb421121d2fa6665d4/atl-blog-memes-10a.jpg?fm=webp)

## Process: 

I followed the following process when creating this meme in R: 

1. Found images of the aforementioned ✨*fabulous felines*✨ using the `image_read` function before scaling them to 300 pixels 
2. Generated backgrounds using the `image_blank` function 
3. Generated the two sets of text using the `image_annotate` function 
4. Created vectors for each row using `c`
5. Generated the final result by combining the two vectors using the `image_append` function 



