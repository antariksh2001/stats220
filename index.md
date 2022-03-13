# Assignment 1:

## Part A Meme:

![meme](https://github.com/antariksh2001/stats220/blob/main/my_meme.png?raw=true)

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
