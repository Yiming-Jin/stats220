# My meme - "Homework Rules"
The first part of the first assignment in course STATS220 is to create a meme by ourselves. Therefore, I created this page. Not only for the assignment, but also that I want to record my first R project.

## What does my meme look like?
[Homework Rules:](https://github.com/Yiming-Jin/stats220/blob/main/my_meme.png?raw=true)
![homeworkrules](https://github.com/Yiming-Jin/stats220/blob/main/my_meme.png?raw=true)

## The R code I used to create the meme
```r
library(magick)
warning <- image_read("https://pm1.narvii.com/6012/eaf9d53782254d50cfdd2be2342e61ea3b153bc2_hq.jpg") %>%
  image_scale(530)

no <- image_read("https://www.incimages.com/uploaded_files/image/1920x1080/getty_525041723_970647970450098_70024.jpg") %>%
  image_scale(530)

yes <- image_read("https://www.tlnt.com/wp-content/uploads/sites/4/2017/01/Yes-sign.jpg") %>%
  image_scale(530)

chegg_text <- image_blank(width = 530, 
                          height = 380, 
                          color = "#000000") %>%
  image_annotate(text = "Asking\nChegg?",
                 color = "#ff0000",
                 size = 85,
                 font = "sans",
                 gravity = "center")

copy_text <- image_blank(width = 530, 
                         height = 298, 
                         color = "#000000") %>%
  image_annotate(text = "Copying\nOthers?",
                 color = "#ff0000",
                 size = 85,
                 font = "sans",
                 gravity = "center")

teacher_text <- image_blank(width = 530, 
                            height = 354, 
                            color = "#000000") %>%
  image_annotate(text = "Asking\nTeacher?",
                 color = "#00ff00",
                 size = 85,
                 font = "sans",
                 gravity = "center")

first_row <- c(warning, chegg_text) %>%
  image_append()

second_row <- c(copy_text, no) %>%
  image_append()

third_row <- c(yes, teacher_text) %>%
  image_append()

image <- c(first_row, second_row, third_row) %>%
  image_append(stack = TRUE)

image_border(image, "#ffffff", "20x40") %>%
  image_annotate("When you have trouble with your homework:",
                 color = "black",
                 size = 30,
                 font = "Times") %>%
  image_annotate("Listening carefully in class is the most correct way!",
                 color = "red",
                 size = 60,
                 boxcolor = "pink",
                 font = "Times",
                 degrees = 35,
                 location = "+50+100") 

meme <- image_read("http://localhost:29998/session/preview.jpeg?viewer_pane=1&capabilities=1&host=http%3A%2F%2F127.0.0.1%3A15138")
image_write(meme, "my_meme.png")
```
## Some information about the meme I created 
**1. What was the motivation?**  
In my first year of university, I got into a lot of trouble because of the Academic Integrity things. That is the reason of why I made this meme called "Homework Rules". The meme could be separated into three parts:  
* *The first row*   
For the first row, I started with a sign which has a big "WARNING" on it to show that searching the answers on Chegg is not recommended. The red bold 
* *The second row*  
For the second row, I used a red big bold "NO". I want to show that if you have troubles when you doing your homework, copying others's work is absolutely not okay!
* *The third row*
用chegg可能你理解了再写还是可行的 但是完全抄袭他人是完全不被认可的 所以一个是警告 一个是红色大写的no
**2. How is my meme new?**
* *图片本来是什么样子的（网站链接和直接的图片*
* *经过我的改变之后是什么样子的*
