---
title: 'Test 1'
description: 'Тестирование по эконометрии'
attachments: null
---

## Отрисовка гистограмм

```yaml
type: NormalExercise
key: 15e90a572d
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть переменная r.
- Постройте её гистограмму с разбиением на 50 столбцов.

`@hint`


`@pre_exercise_code`
```{r}
r=rnorm(10000,10,10)
```

`@sample_code`
```{r}
r

```

`@solution`
```{r}
hist(r,breaks = 50)
```

`@sct`
```{r}
ex() %>% check_function("hist") %>% {
  check_arg(., "x") %>% check_equal()
  check_arg(., "breaks") %>% check_equal()
}
success_msg("Отлично!")
```

---

## Определение распределения

```yaml
type: MultipleChoiceExercise
key: c360e6347f
xp: 50
```

У нас есть случайная величина x. Как вы думаете к какому распределению она относится?

`@possible_answers`
- 'Нормальное'
- 'Хи-квадрат'
- 'Стьюдента'

`@hint`
Нарисуйте гистограмму

`@pre_exercise_code`
```{r}
x=rchisq(10000, 40)
```

`@sct`
```{r}
msg2 <- "Nice one!"
msg3 <- "Not quite, give it another shot."
ex() %>% check_mc(2, feedback_msgs = c(msg2, msg3))
```

---

## Отрисовка обычного графика

```yaml
type: NormalExercise
key: 650c69a43c
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть переменная r.
- нарисуйте её график, используя линию.

`@hint`


`@pre_exercise_code`
```{r}
r=rnorm(10000,10,10)+(1:10000)*0.2
```

`@sample_code`
```{r}
r

```

`@solution`
```{r}
plot(r,type = "l")
```

`@sct`
```{r}
ex() %>% check_function("plot") %>% {
  check_arg(., "x") %>% check_equal()
  check_arg(., "type") %>% check_equal()
}
success_msg("Отлично!")
```

---

## Разбиение векторов

```yaml
type: NormalExercise
key: 44d031f162
lang: r
xp: 100
skills: 5
```



`@instructions`
- Разбейте вектор spy на три вектора spy1, spy2, spy3.
- spy1 - первые 100 наблюдений, spy2 - вторые 100 наблюдений, spy3 - оставшиеся

`@hint`


`@pre_exercise_code`
```{r}
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
```

`@sample_code`
```{r}
spy1=
spy2=
spy3=

```

`@solution`
```{r}
spy1=spy[1:100]
spy2=spy[101:200]
spy3=spy[201:(NROW(spy))]
```

`@sct`
```{r}
ex() %>% check_object("spy1") %>% check_equal()
ex() %>% check_object("spy2") %>% check_equal()
ex() %>% check_object("spy3") %>% check_equal()
success_msg("Отлично!")
```

---

## Среднеквадратическое отклонение

```yaml
type: NormalExercise
key: ddb7608ad9
lang: r
xp: 100
skills: 5
```



`@instructions`
- Для вектора r рассчитайте среднеквадратическое отклонение и запишите в переменную s соответственно.

`@hint`


`@pre_exercise_code`
```{r}
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
r<-diff(log(spy))
```

`@sample_code`
```{r}
s=
```

`@solution`
```{r}
s=sd(r)
```

`@sct`
```{r}
ex() %>% check_object("s") %>% check_equal()
success_msg("Отлично!")
```

---

## Среднее

```yaml
type: NormalExercise
key: 8ed83c7cd0
lang: r
xp: 100
skills: 1
```



`@instructions`
- Для вектора r рассчитайте среднее и запишите в переменную m соответственно.

`@hint`


`@pre_exercise_code`
```{r}
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
r<-diff(log(spy))
```

`@sample_code`
```{r}
m=

```

`@solution`
```{r}
m=mean(r)

```

`@sct`
```{r}
ex() %>% check_object("m") %>% check_equal()
success_msg("Отлично!")
```

---

## дисперсия

```yaml
type: NormalExercise
key: c5c9f67f18
lang: r
xp: 100
skills: 1
```



`@instructions`
- Для вектора r рассчитайте дисперсию и запишите в переменные v соответственно.

`@hint`


`@pre_exercise_code`
```{r}
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
r<-diff(log(spy))
```

`@sample_code`
```{r}
v=
```

`@solution`
```{r}
v=var(r)
```

`@sct`
```{r}
ex() %>% check_object("v") %>% check_equal()
success_msg("Отлично!")
```

---

## Ограничение векторов

```yaml
type: NormalExercise
key: 606c591624
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть вектор r. Создайте вектор rNew, который состоял бы только из неотрицательных значений вектора r.

`@hint`


`@pre_exercise_code`
```{r}
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
r<-diff(log(spy))
```

`@sample_code`
```{r}
rNew=

```

`@solution`
```{r}
rNew=r[r>=0]
```

`@sct`
```{r}
ex() %>% check_object("rNew") %>% check_equal()
success_msg("Отлично!")
```

---

## Объединение векторов

```yaml
type: NormalExercise
key: cfdb284084
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть два вектора c1 и c2, объедините их в матрицу с двумя столбцами c3.

`@hint`


`@pre_exercise_code`
```{r}
c1=rnorm(1000)
c2=rnorm(1000)

```

`@sample_code`
```{r}
c3=

```

`@solution`
```{r}
c3=cbind(c1,c2)
```

`@sct`
```{r}
ex() %>% check_object("c3") %>% check_equal()
success_msg("Отлично!")
```

---

## Линейная регрессия

```yaml
type: NormalExercise
key: 6ca86c7e87
lang: r
xp: 100
skills: 5
```



`@instructions`
- Постройте линейную регрессию x от y и фиктивной переменной z и запишите ее в переменную fit.

`@hint`


`@pre_exercise_code`
```{r}
x=rnorm(10000)
y=x+rnorm(10000,1,1.5)
z=x>2
```

`@sample_code`
```{r}
fit=

```

`@solution`
```{r}
fit=lm(x~y+z)
```

`@sct`
```{r}
ex() %>% check_object("fit") %>% check_equal()
success_msg("Отлично!")
```

---

## Результаты регрессии1

```yaml
type: MultipleChoiceExercise
key: dd5093e3d3
lang: r
xp: 50
skills: 1
```

У вас есть результаты линейной регрессии fit. Является ли регрессия значимой?

`@possible_answers`
- Да
- Нет

`@hint`


`@pre_exercise_code`
```{r}
x=rnorm(10000)
y=x+rnorm(10000,1,100)
z=x+rnorm(10000,0,5)>3
fit=lm(x~y+z)

```

`@sct`
```{r}
msg2 <- "Nice one!"
msg3 <- "Not quite, give it another shot."
a=summary(fit)
if(a$fstatistic[1]>qf(0.95,a$fstatistic[2],a$fstatistic[3])){
  r=1
}else{r=2}
ex() %>% check_mc(r, feedback_msgs = c(msg2, msg3))
```

---

## Результаты регрессии2

```yaml
type: MultipleChoiceExercise
key: ba1aef6938
lang: r
xp: 50
skills: 1
```

У вас есть результаты линейной регрессии fit. Является ли переменная y значимой?

`@possible_answers`
- Да
- Нет

`@hint`


`@pre_exercise_code`
```{r}
x=rnorm(10000)
y=x+rnorm(10000,1,100)
z=x+rnorm(10000,0,5)>3
fit=lm(x~y+z)
```

`@sct`
```{r}
msg2 <- "Nice one!"
msg3 <- "Not quite, give it another shot."
a=summary(fit)
if(a$coefficients[2,4]>0.05){
  r=2
}else{r=1}
ex() %>% check_mc(r, feedback_msgs = c(msg2, msg3))
```

---

## Результаты регрессии3

```yaml
type: MultipleChoiceExercise
key: d2043621d1
lang: r
xp: 50
skills: 1
```

У вас есть результаты линейной регрессии fit. Является ли переменная zTRUE значимой?

`@possible_answers`
- Да
- Нет

`@hint`


`@pre_exercise_code`
```{r}
x=rnorm(10000)
y=x+rnorm(10000,1,100)
z=x+rnorm(10000,0,5)>3
fit=lm(x~y+z)
```

`@sct`
```{r}
msg2 <- "Nice one!"
msg3 <- "Not quite, give it another shot."
a=summary(fit)
if(a$coefficients[3,4]>0.05){
  r=2
}else{r=1}
ex() %>% check_mc(r, feedback_msgs = c(msg2, msg3))
```

---

## Результаты регрессии4

```yaml
type: MultipleChoiceExercise
key: f067ffdee0
xp: 50
```

У вас есть результаты линейной регрессии fit. Что обозначает переменная zTRUE?

`@possible_answers`
- На сколько в среднем x в случае z TRUE больше, чем x в случае z FALSE
- В среднем x больше у на величину коэффициента zTRUE
- x является положительной величиной, потому что zTRUE>0

`@hint`


`@pre_exercise_code`
```{r}
x=rnorm(10000)
y=x+rnorm(10000,1,100)
z=x+rnorm(10000,0,5)>3
fit=lm(x~y+z)
```

`@sct`
```{r}
msg2 <- "Nice one!"
msg3 <- "Not quite, give it another shot."
ex() %>% check_mc(1, feedback_msgs = c(msg2, msg3))
```
