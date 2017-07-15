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
행렬은 2차원입니다. 배열은 다차원 입니다. 

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

msg_bad <- "다시 생각해보세요."
msg_success <- "정답이예요. 벡터는 1차원 입니다."
test_mc(correct = 1, feedback_msgs = c(msg_success, msg_bad, msg_bad))
```

--- type:NormalExercise lang:r xp:100 skills:1 key:e25e666443
## R -- Vector

R에서는 벡터가 가장 작은 단위입니다. 
R은 통계를 위해 만들어졌기 때문에, 벡터를 이용해서 진행합니다. 

이번 장에서는 벡터를 이용하여, 
John Doe, Jane Doe, Steve Graves의 벡터를 만들고,
변수들의 status를 확인해보도록 합니다. 

*** =instructions
- John Doe, Jane Doe, Steve Graves, 3가지 값을 변수명 `subject_name`에 넣어봅시다. 

- 98.1, 98.6, 101.4, 3가지 값을 변수명 `temperature`에 넣어봅시다. 
 숫자에는 "따옴표"를 붙이지 않습니다.

- FALSE, FALSE, TRUE, 3가지 값을 변수명 `flu_status`에 넣어봅시다. 
단,TRUE, FALSE는 바이너리 값입니다. 따옴표를 붙이지 않습니다.  

- is(변수명)을 통해서 원소값을 확인합니다. 

*** =hint
- 변수명 <- c(3가지 값)
- 변수명에는 변수명만 넣으세요. 따옴표 붙이지 않습니다. 

*** =sample_code
```{r}
# 변수명 `subject_name`

# 변수명 `temperature`

# 변수명 `flu_status`

# 변수명 `subject_name` 벡터 원소값 확인

# 변수명 `temperature` 벡터 원소값 확인

# 변수명 `flu_status` 벡터 원소값 확인

```

*** =solution
```{r}
# 변수명 `subject_name`
subject_name <- c("John Doe", "Jane Doe", "Steve Graves")
# 변수명 `temperature`
temperature <- c(98.1, 98.6, 101.4)
# 변수명 `flu_status`
flu_status <- c(FALSE, FALSE, TRUE)
# 변수명 `subject_name` 벡터 원소값 확인
is(subject_name)
# 변수명 `temperature` 벡터 원소값 확인
is(temperature)
# 변수명 `flu_status` 벡터 원소값 확인
is(flu_status)

```

*** =sct
```{r}
# SCT written with testwhat: https://github.com/datacamp/testwhat/wiki

test_error()

success_msg("Good work!")
```
