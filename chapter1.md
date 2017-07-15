---
title       : What is the vector?
description : This chapter making a vector using R. 
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:MultipleChoiceExercise lang:r xp:50 skills:1 key:25d2e141cf
## R Notebook - Vector

오늘은 벡터에 대해서 배워보도록 할게요.
오른쪽 그림을 보고, 벡터가 몇차원인지 클릭해봅시다.

*** =instructions
- 1차원
- 2차원
- 3차원

*** =hint
Have a look at the plot. Which color does the point with the lowest rating have?

*** =pre_exercise_code
```{r}
# image loadings
#png("vector/img/2png.png")
#img <- read("vector/img/2png.png")
#plot(img)

library(imager)
file <- system.file('vector/img/2png.png', package = 'imager')  
im <- load.image(file)
plot(im)


```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "다시 생각해보세요."
msg_success <- "벡터는 1차원 입니다. "
test_mc(correct = 1, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:e25e666443
## R -- Vector

R에서는 벡터가 가장 작은 단위입니다. 
R은 통계를 위해 만들어졌기 때문에, 벡터를 이용해서 진행합니다. 

이번 장에서는 벡터를 이용하여, 
John Doe, Jane Doe, Steve Graves의 벡터를 만들고,
변수들의 status를 확인해보도록 합니다. 

*** =instructions
- "John Doe", "Jane Doe", "Steve Graves"인 벡터들을  `subject_name`에 넣어봅시다. 
- (98.1, 98.6, 101.4), 3가지 값을 `temperature`에 넣어봅시다.  
- Use `plot()` to  plot `good_movies$Run` on the x-axis, `good_movies$Rating` on the y-axis and set `col` to `good_movies$Genre`.

*** =hint
- Use `str()` for the first instruction.
- For the second instruction, you should use `...[movie_selection$Rating >= 5, ]`.
- For the plot, use `plot(x = ..., y = ..., col = ...)`.

*** =pre_exercise_code
```{r}
# You can also prepare your dataset in a specific way in the pre exercise code
load(url("https://s3.amazonaws.com/assets.datacamp.com/course/teach/movies.RData"))
movie_selection <- Movies[Movies$Genre %in% c("action", "animated", "comedy"), c("Genre", "Rating", "Run")]

# Clean up the environment
rm(Movies)
```

*** =sample_code
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection


# Select movies that have a rating of 5 or higher: good_movies


# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre

```

*** =solution
```{r}
# movie_selection is available in your workspace

# Check out the structure of movie_selection
str(movie_selection)

# Select movies that have a rating of 5 or higher: good_movies
good_movies <- movie_selection[movie_selection$Rating >= 5, ]

# Plot Run (i.e. run time) on the x axis, Rating on the y axis, and set the color using Genre
plot(good_movies$Run, good_movies$Rating, col = good_movies$Genre)
```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_function("str", args = "object",
              not_called_msg = "You didn't call `str()`!",
              incorrect_msg = "You didn't call `str(object = ...)` with the correct argument, `object`.")

test_object("good_movies")

test_function("plot", args = "x")
test_function("plot", args = "y")
test_function("plot", args = "col")

test_error()

success_msg("Good work!")
```
