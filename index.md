# Assignment 1:

## Part A Meme:

![meme](https://github.com/antariksh2001/stats220/blob/main/my_meme1.png)

The R code used to create this meme is as follows:

```r

library(magick)
confused_cat_url <- "https://yt3.ggpht.com/ytc/AKedOLRj_FI_gQkJiXJ88JuPj2f30i77BQYX9l-KkkV1=s900-c-k-c0x00ffffff-no-rj"
excited_cat_url <- "https://static.boredpanda.com/blog/wp-content/uploads/2015/07/smiling-cat-2__605.jpg"

# confused cat img
confused_cat <- image_read(confused_cat_url)%>%
  image_scale(300)

# excited_cat_img 
excited_cat <- image_read(excited_cat_url)%>%
  image_scale(300)

# other courses text
other_courses <- image_blank(height = 300, width = 300, color = "#000000")%>%
  image_annotate(text = "Me in other courses", color = "#FFFFFF", size = "30", font = "Comic Sans", 
                 gravity = "center")

# Stats 220 text
stats_220 <- image_blank(height = 300, width = 300, color = "#000000")%>%
  image_annotate(text = "Me in Stats 220", color = "#FFFFFF", size = "30", font = "Comic Sans", 
                 gravity = "center")

# top row
top_row <- c(confused_cat, other_courses)%>%
  image_append()

# bottom row
bottom_row <- c(excited_cat, stats_220)%>%
  image_append()

meme <- c(top_row, bottom_row)%>%
  image_append(stack = TRUE)

image_write(meme, "my_meme.png")

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



