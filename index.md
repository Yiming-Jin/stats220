# My meme - "Homework Rules"
Welcome to my website! The first part of the first assignment in course STATS220 is to create a meme by ourselves. Therefore, I created this page. Not only for the assignment, but also that I want to record my first `R` project.

## What does my meme look like?
Below is the meme called "[Homework Rules](https://github.com/Yiming-Jin/stats220/blob/main/my_meme.png?raw=true)". I made it by using the `R` package [{magick}](https://cran.r-project.org/web/packages/magick/vignettes/intro.html).
![homeworkrules](https://github.com/Yiming-Jin/stats220/blob/main/my_meme.png?raw=true)

## The `R` code I used to create the meme
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
1. **What was the motivation?**  
In my first year of university, I got into a lot of trouble because of the Academic Integrity things. That is the reason of why I made this meme called "Homework Rules".  

2. **How is my meme new?**
* *What does the original picture I used look like?*  
  * [The picture with "WARNING":](https://pm1.narvii.com/6012/eaf9d53782254d50cfdd2be2342e61ea3b153bc2_hq.jpg)  
  ![](https://pm1.narvii.com/6012/eaf9d53782254d50cfdd2be2342e61ea3b153bc2_hq.jpg)  
  * [The picture with "NO":](https://www.incimages.com/uploaded_files/image/1920x1080/getty_525041723_970647970450098_70024.jpg)
  ![](https://www.incimages.com/uploaded_files/image/1920x1080/getty_525041723_970647970450098_70024.jpg)
  * [The picture with "YES":](https://www.tlnt.com/wp-content/uploads/sites/4/2017/01/Yes-sign.jpg)
  ![](https://www.tlnt.com/wp-content/uploads/sites/4/2017/01/Yes-sign.jpg)
  
<!--- 图片本来是什么样子的（网站链接和直接的图片) --->
* *What did I do to these pictures and why did I do that?*  
I changed the size of the pictures to make my meme look much cleaner and comfortable after combining them together. Then, I started to combine these pictures and the sentences in my brain together. Firstly, I separated my meme into three parts:  
  * *The first row*   
For the first row, I started with a sign which has a big "WARNING" to show that searching the answers on Chegg is not recommended. The red bold sentence is uesd to warning the people who see this meme: do not do this!  
  * *The second row*  
For the second row, I used a red big bold "NO". I want to show that if you have troubles when you doing your homework, copying others's work is absolutely not okay! As same as the first row of the meme, the red bold sentence is uesd to warning the people who see this meme: do not do this!  
  * *The third row*  
The third row is about the things that we could do when we meet troubles during doing our homework. That is, asking our teacher! Therefore, I used green bold sentence to show that this action is safe.  
  
  However, the most important thing is, listening carefully in class! Therefore, I put a thirty-five-degree pink band over my meme with the red sentence "Listening   carefully in class is the most correct way!". The reason of why I choose 35 degree is because that this minimizes the coverage of my meme.  
  
  In the end, I also added 20px on left/right and 40px on top/bottom, so that I could write a title, which is "when you have trouble with your homework:", on my       meme. 
