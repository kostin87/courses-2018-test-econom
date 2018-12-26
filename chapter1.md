---
title: 'Test 1'
description: 'Тестирование по эконометрии'
attachments: null
---

## Вычисление обычной доходности

```yaml
type: NormalExercise
key: 98360b49d2
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть цены актива spy и msft.
- Вычислите обычную доходность для этого актива и запишите ее в переменную Rspy и Rmsft.
- Вычислите доходность портфеля с весами 0.5 и 0.5 и запишите ее в переменную Rportf.

`@hint`
Доходность это темп прироста цены

`@pre_exercise_code`
```{r}
load(url('https://assets.datacamp.com/production/repositories/4264/datasets/2a1cb49c1085af50c535acf5f11f7211c08209bf/MSFT.RData'))
load(url('https://assets.datacamp.com/production/repositories/4264/datasets/1aaea273f16388fed19feec2e06d2ba5984044d2/SPY.RData'))
spy=SPY$SPY.Close
msft=MSFT$MSFT.Close
```

`@sample_code`
```{r}
Rspy =
Rmsft=
Rportf=
```

`@solution`
```{r}
Rspy =diff(spy)/spy[-NROW(spy)]
Rmsft=diff(msft)/spy[-NROW(msft)]
Rportf=0.5*Rspy+0.5*Rmsft
```

`@sct`
```{r}
ex() %>% check_object("Rspy") %>% check_equal()
ex() %>% check_object("Rmsft") %>% check_equal()
ex() %>% check_object("Rportf") %>% check_equal()
success_msg("Well done!")
```

---

## Вычисление логарифмической доходности

```yaml
type: NormalExercise
key: 61f0a215c8
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть цены актива spy.
- Вычислите логарифмическую доходность для этого актива и запишите ее в переменную r.

`@hint`
Доходность это темп прироста цены

`@pre_exercise_code`
```{r}
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
```

`@sample_code`
```{r}
r<-

```

`@solution`
```{r}
r<-diff(log(spy))
```

`@sct`
```{r}
ex() %>% check_object("r") %>% check_equal()
success_msg("Well done!")
```

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
- У вас есть логарифмическая доходность r.
- Постройте её гистограмму с разбиением на 50 столбцов.

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
r

```

`@solution`
```{r}
hist(r,breaks = 50)
```

`@sct`
```{r}
test_function_result("hist")
```

---

## Insert exercise title here

```yaml
type: NormalExercise
key: 0e0cefe504
xp: 100
```



`@instructions`


`@hint`


`@pre_exercise_code`
```{r}

```

`@sample_code`
```{r}

```

`@solution`
```{r}

```

`@sct`
```{r}

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
- У вас есть логарифмическая доходность r.
- нарисуйте её график, используя линию.

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
r

```

`@solution`
```{r}
plot(r,type = "l")
```

`@sct`
```{r}
test_function_result("plot")
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
spy3=spy[201:(length(spy))]
```

`@sct`
```{r}
test_object("spy1")
test_object("spy2")
test_object("spy3")
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
- Для вектора доходностей r рассчитайте среднеквадратическое отклонение и запишите в переменную s соответственно.

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
test_object("s")
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
- Для вектора доходностей r рассчитайте среднее и запишите в переменную m соответственно.

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
test_object("m")
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
- Для вектора доходностей r рассчитайте дисперсию и запишите в переменные v соответственно.

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
test_object("v")
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
- У вас есть вектор доходностей r. Создайте вектор rNew, который состоял бы только из неотрицательных значений вектора r.

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
test_object("rNew")
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
test_object("c3")
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
- Постройте линейну регрессию spy от линейного тренда и запишите ее в переменную fit.

`@hint`


`@pre_exercise_code`
```{r}
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
```

`@sample_code`
```{r}
fit=

```

`@solution`
```{r}
t=1:length(spy)
fit=lm(spy~t)
```

`@sct`
```{r}
test_object("fit")
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
x=c(3,6,5,7,8,5,4,8,9,6,4,3,6,7,9,7,6,10,11,10)
t=1:length(x)
t2=t^2
fit=lm(x~t+t2)
```

`@sct`
```{r}
test_mc(correct = 1)
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

У вас есть результаты линейной регрессии fit. Является ли переменная t значимой?

`@possible_answers`
- Да
- Нет

`@hint`


`@pre_exercise_code`
```{r}
x=c(3,6,5,7,8,5,4,8,9,6,4,3,6,7,9,7,6,10,11,10)
t=1:length(x)
t2=t^2
fit=lm(x~t+t2)
```

`@sct`
```{r}
test_mc(correct = 2)
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

У вас есть результаты линейной регрессии fit. Является ли переменная t2 значимой?

`@possible_answers`
- Да
- Нет

`@hint`


`@pre_exercise_code`
```{r}
x=c(3,6,5,7,8,5,4,8,9,6,4,3,6,7,9,7,6,10,11,10)
t=1:length(x)
t2=t^2
fit=lm(x~t+t2)
```

`@sct`
```{r}
test_mc(correct = 2)
```

---

## ARIMA2

```yaml
type: NormalExercise
key: 54aa250dfd
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть вектор spy, постройте по нему Arima(1,1,1) регрессию и запишите её в переменную fit.

`@hint`
Функция arima.

`@pre_exercise_code`
```{r}
require('forecast')
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
```

`@sample_code`
```{r}
fit=
```

`@solution`
```{r}
fit=arima(spy,c(1,1,1))
```

`@sct`
```{r}
test_object("fit")
```

---

## VaR1

```yaml
type: NormalExercise
key: 558478a59e
lang: r
xp: 100
skills: 5
```



`@instructions`
- У вас есть timeSeries вектор доходностей r. Рассчитайте модифицированный VaR по этому вектору и запишите в переменную VaR.

`@hint`


`@pre_exercise_code`
```{r}
library('timeSeries')
library("PerformanceAnalytics")
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
r<-diff(log(spy))
r=timeSeries(r,charvec=(1:NROW(r))*24*60*60)
```

`@sample_code`
```{r}
VaR=
```

`@solution`
```{r}
VaR=VaR(r)
```

`@sct`
```{r}
test_object("VaR")
```

---

## Sharp Ratio

```yaml
type: NormalExercise
key: 285bccf614
lang: r
xp: 100
skills: 1
```



`@instructions`
- У вас есть timeSeries вектор доходностей r. Рассчитайте Sharp Ratio по этому вектору и запишите в переменную sharp_ratio.

`@hint`


`@pre_exercise_code`
```{r}
library('timeSeries')
library("PerformanceAnalytics")
n=round(runif(1, min = 1, max = 30))
load(url("http://s3.amazonaws.com/assets.datacamp.com/production/course_2233/datasets/SPY.RData"))
spy=SPY[[1]][((n-1)*390+1):(n*390),2]
r<-diff(log(spy))
r=timeSeries(r,charvec=(1:NROW(r))*24*60*60)
```

`@sample_code`
```{r}
sharp_ratio=
```

`@solution`
```{r}
sharp_ratio=SharpeRatio(r)
```

`@sct`
```{r}
test_object("sharp_ratio")
```

---

## Загрузка данных с yahoo

```yaml
type: NormalExercise
key: 09f5eaf7a1
lang: r
xp: 100
skills: 1
```



`@instructions`
-Загрузите данные SPY

`@hint`


`@pre_exercise_code`
```{r}
require("quantmod")
```

`@sample_code`
```{r}

```

`@solution`
```{r}
getSymbols('SPY')
```

`@sct`
```{r}
test_object("SPY")
```
