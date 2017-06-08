<div dir="rtl">

راهنمای نوشتن برنامه‌ها به زبان R
=================================

#### همکاری در این کار:

- برای شروع به همکاری لطفا این مخزن را [فورک کنید](https://github.com/Cirice/My-R-Style-Guide); سپس یک انشعاب (Branch) درست کنید و شروع به کار کنید; سرانجام کارتان را به مخزن اعمال کنید و تغییراتتان را به گیت‌هاب push کنید، و [ یک درخواست Pull را ارسال کنید](https://help.github.com/articles/creating-a-pull-request).

- درخواست‌تان را از طریق [Project Issue Tracker](https://github.com/Cirice/My-R-Style-Guide/issues) بیان کنید.

## معرفی:

R یک زبان برنامه نویسی سطح بالای تابعی است که در کار‌های مربوط به تحلیل آماری و ترسیم نمودار‌های داده ای بسیار پر طرفدار است. هدف این راهنما ساده کردن فرایند نوشتن، خواندن، توزیع کردن و بررسی کردن کد نوشته به این زبان است. این نوشته حاوی تعداد زیادی نکته و مطلب است که به نظر من می‌توانند به دستیابی به هدف ذکر شده کمک کنند.

## خلاصه قواعد مهم:

1. از attach استفاده نکنید.
2. از ; استفاده نکنید.
3. بجای = از -> استفاهده کنید.
4. همه‌ی comment ها را با # و یک حرف فاصله بعد آن شروع کنید.
5. از Tab برای identation استفاده نکنید بجای Tab از Space(حرف فاصله) استفاده کنید.
6. ترجیحا طول هر خط نباید بیشتر از 80 حرف باشد و این مقدار نباید به هیچ دلیلی بیشتر از 100 شود.
7. در صورت استفاده از object system های مختلف R مثل S3 و S4 متود‌ها و توانایی‌های دو یا چند سیستم مختلف(مثلا Inheritance) را با هم مخلوط نکنید.
8. در صورت وجود چند روش درست برای انجام یک کار یا نوشتن کد در استفاده از روشی که برگزیده اید consistent باشید(همه جا از یک روش استفاده کنید).

### لطفا بقیه قواعد  را به دقت مطالعه کنید.

## قواعد نامگذاری

### نامگذاری فایل‌ها:

1. نام فایل‌های R همیشه باید با .R ختم شوند.
2. نام فایل باید معنی دار باشد.
3. ترجیحا برای نوشتن نام فایل از حروف کوچک انگلیسی(a-z)،  اعداد(9-0) و برای جدا کردن عبارت‌های چند بخشی از _(underline) استفاده کنید.
4. ترجیحا نام فایل را با عدد یا _ شروع نکنید.

#### حالت مطلوب

<div dir="ltr">

calculate_revenue.R

find_max_in_list1.R

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

eeawaQe.R

1sSomeFuns.R

<div dir="rtl">

### نامگذاری متغیر‌ها و تابع‌ها:

1. در نامگذاری متغیر‌ها و تابع‌ها از -(hyphen) و _(underscore) استفاده نکنید.
2. ترجیحا برای نامگذاری متغیر‌ها از حروف کوچک انگلیسی (a-z) استفاده کنید.
3. در نام متغیر‌ها برای جدا کردن بخش‌های نام‌های چند بخشی از . (نقطه) استفاده کنید(مثلا average.value).
4. برای نامگذاری تابع‌ها ازشکل [CamelCase](https://en.wikipedia.org/wiki/Camel_case) استفاده کنید(مثلا CalculateAverage).
5. می‌توان برای نامگذاری متغیر‌ها شبیه قاعده نامگذاری تابع‌ها عمل کرد ولی در این حالت حرف اول متغیر را کوچک بنویسید(مثلا averageValue).
7. نام متغیر‌هایی که مقدارشان درطول اجرا تغییر نمی‌کند(منظور متغیرهای Constant هستند) را مثل نام تابع‌ها بنویسید ولی با این تفاوت که نام مورد بحث با حرف k(حرف کوچک k) شروع می‌شود(مثلا kConstantValue).

#### حالت مطلوب

<div dir="ltr">

```R
# Variable naming examples
average.value # this is preferred
AverageValue # also accepted
kMedianValue # constant variable
```

```R
# Function naming examples
CalculateMedian
ImportData
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
# Variable naming examples
average_Value
Average-Value
kmedianValue
```

```R
# Function naming examples
calculate.median
Import_data
```
<div dir="rtl">

## قواعد نوشتاری

### طول خطوط در برنامه

1. ترجیحا طول هر خط باید حداکثر 80 حرف باشد.
2. طول خط نباید(با در نظر گرفتن comment) از 100 حرف بیشتر باشد.

#### حالت مطلوب

<div dir="ltr">

```R
mean <- CalculateMean(data = c(1, 2, 3)) # this line is 97 characters long(with comments included)

```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
clusters<-factor(c("New", "Passed", "VIP", "Churn"), levels = c("New", "Passed", "VIP", "Churn")) # I'm 123 characters long
```

<div dir="rtl">

## استفاده از تورفتگی(Indentation)

1. از دو حرف فاصله(Space character) برای ایجاد یک تورفتگی استفاده کنید.
2. از حرف Tab برای ایجاد تورفتگی استفاده نکنید.
3. از ترکیب Tab و Space برای ایجاد تورفتگی استفاده نکنید.

### تبصره:
1. اگر درون(همان) پرانتز line break(ادامه عبارت به خط بعد انتقال پیدا کرد) اتفاق افتاد ادامه عبارت انتقال پیدا کرده به خط بعد را همتراز با اولین حرف (غیر Space) درون پرانتز شروع کنید.


#### حالت مطلوب

<div dir="ltr">

```R
# Indent the statement inside if expression                          
if (a == b) {
  x <- 1
}
```

```R
# Line break indentation
mean <- CalculateMean(data = c(1, 2, 3, 4, 5, 6, 7,
                               8, 9, 10))
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
# Mixing Tab with Space
mean <- CalculateMean(data = c(1, 2, 3, 4, 5, 6, 7,
								8, 9, 10))

```

```R
# Using Tab for indentation                       
if (a == b) {
	x <- 1
}
```


<div dir="rtl">

## فاصله گذاری در متن(Spacing)

1. سمت چپ و راست همگی عملگر دودویی(binary operators) یک حرف فاصله(Space character) بگذارید(عملگر‌های دودویی مثل +، -، /, =، -> و غیره).
2. قبل از علامت , (comma) فاصله نگذارید.
3. همیشه بعد از علامت , (comma) یک حرف فاصله بگذارید.
4.  همیشه قبل از ) (پرانتز باز) یک حرف فاصله بگذارید.
5. بعد از ) (پرانتز باز) و قبل از ( (پرانتز بسته) حرف فاصله نگذارید.
6.   بعد از ](bracket باز) و قبل از [ (bracket بسته) حرف فاصله نگذارید.

### تبصره:
1. در زمان مقدار دهی به آرگومان‌های یک تابع می‌توانید سمت چپ و راست عملگر = فاصله‌ای نگدارید.
2. قبل از ) (پرانتز باز) در زمان فراخوانی یک تابع حرف فاصله نگدارید.
3. به طور کلی برای بالاتر بردن خوانایی کدتان می‌توانید بیشتر از یک حرف فاصله استفاده کنید.
4. همیشه و در همه حال بعد از , (comma) یک حرف فاصله بگذارید.

#### حالت مطلوب

<div dir="ltr">

```R
# Correct use of spaces
tab.prior <- table(df[df$days.from.opt < 0, "team.id"])
total <- sum(x[, 1])
total <- sum(x[1, ])
```

```R
# No space after '(' and before ')' and also one space right before '(' 
if (debug)
```

```R
# Use of additional spaces for clarity
plot(x    = x.coord,
     y    = data.mat[, MakeColName(metric, ptiles[1], "roiOpt")],
     ylim = ylim,
     xlab = "dates",
     ylab = metric,
     main = (paste(metric, " for 4 samples ", sep = "")))
```

```R
# Always put one space after ','
x[1, ]
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
# Incorrect spacing
tab.prior <- table(df[df$days.from.opt<0, "team.id"])  # needs spaces around '<'
tab.prior <- table(df[df$days.from.opt < 0,"team.id"])  # needs a space after the comma
tab.prior<- table(df[df$days.from.opt < 0, "team.id"])  # needs a space before <-
tab.prior<-table(df[df$days.from.opt < 0, "team.id"])  # needs spaces around <-
total <- sum(x[,1])  # needs a space after the comma
total <- sum(x[ ,1])  # needs a space after the comma, not before

```

```R
if ( debug )  # no spaces around debug
```

```R
x[1,]  # needs a space after the comma
```
```R
# No space before '('
if(debug)

```

<div dir="rtl">

## استفاده از کروشه(Curly Braces)

1. عبارتی که می‌تواند درون کروشه قرار بگیرد را روی همان خطی که statement قبلی آن روی آن است نگذارید.
2. در یک خط یک کروشه را نبندید; منظور اینکه نیاید هم } و { روی یک خط قرار داشته باشند.
3. شما می‌توانید برای block های تک خظی از کروشه استفاده نکنید لذا در صورت انجام این کار در بقیه کد خود نیز بدین صورت عمل کنید(consistency داشته باشید).
4. همیشه statement بعد else را درون کروشه بگذارید.

#### حالت مطلوب

<div dir="ltr">

```R
# Do either of these two but not both in your code

# case 1
if (is.null(ylim)) {
  ylim <- c(0, 0.06)
}

# case 2
if (is.null(ylim)) ylim <- c(0, 0.06)

```

```R
if (condition) {
  one or more lines
} else {
  one or more lines
}
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
if (is.null(ylim)) ylim <- c(0, 0.06)
```

```R
if (is.null(ylim)) {ylim <- c(0, 0.06)}
```
```R
if (condition) {
  one or more lines
}
else {
  one or more lines
}
```

```R
if (condition)
  one line
else
  one line


```

<div dir="rtl">

## مقدار دهی به متغیر‌ها(Variable Assignments)

1. همیشه از -> بجای = برای مقدار دهی استفاده کنید.

#### حالت مطلوب

<div dir="ltr">


```R
a <- 2
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
a = 3
```

<div dir="rtl">

## استفاده از ;(Semicolon)

1. هیچ وقت از علامت semicolon برای جدا کردن expression ها و یا statement های روی یک خط استفاده نکنید.
2. از semicolon برای پایان دادن به خط استفاده نکنید.

#### حالت مطلوب

<div dir="ltr">


```R
x <- 5
x <- x/2
```

```R
require(lda)
require(ggplot)
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
x <- 5; x <- x/2
```

```R
require(lda); require(ggplot);
```

<div dir="rtl">
## قواعد Comment گذاری

1. به طور کلی comment را خط بالای کد خودتان و یا در ادامه کدتان روی همان خط می‌توانید اضافه کنید.
2. comment را با # و یک حرف فاصله بلافاصله بعد آن(بعد حرف #) شروع کنید.
3. comment های کوتاه را می‌توانید در ادامه کدتان روی همان خط بنویسید.
4. هیچ وقت به کدی که کاری بدیهی انجام می‌دهد comment اضافه نکنید.
2. comment ها را با تغییر کدتان در صورت لزوم به روز رسانی کنید.

#### حالت مطلوب

<div dir="ltr">

```R
# Create histogram of frequency of campaigns by pct budget spent.
hist(df$pct.spent,
     breaks = "scott",  # method for choosing number of buckets
     main   = "Histogram: fraction budget spent by campaignid",
     xlab   = "Fraction of budget spent",
     ylab   = "Frequency (count of campaignids)")
```

```R
require(lda)
require(ggplot)
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
# Setting x = 5
x <- 5
```

```R
#Calculating the residues
residue <-CalculateAverageResidue(data) # I's a very very long and cumbersome comment; you better avoid writing very very long comments this way altogether! 
```

<div dir="rtl">

## تعریف و فراخوانی تابع

1. در زمان تعریف یک تابع argument هایی را که مقدار پیشفرض ندارند پیش از متغیر‌هایی که مقدار پیشفرض دارند بنویسید.
2. هم در زمان تعریف و هم زمان فراخوانی یک تابع شما می‌توانید از line break استفاده کنید  لذا توجه داشته باشید که در این حالتline break بین assignment ها مجاز است.

#### حالت مطلوب

<div dir="ltr">

```R
PredictOutcome <- function(query, values, num.days,
                           show.plot = TRUE)
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
PredictOutcome <- function(query, values, num.days, show.plot =
                           TRUE)
```

<div dir="rtl">

## اضافه کردن مستند تابع(Function Documentation)

1. هر تابعی که می‌نویسید باید بلافاصله پس از قسمت تعریف نام وآرگومان‌های تابع دارای یک بخش مستند تابع باشد.
2. بخش مستند تابع به فرم comment نوشته می‌شود و به ترتیب حاوی  ۱) یک جمله توضیحی که تابع شما چه کاری انجام می‌دهد ۲) یک قیمت به نام Args که توضیحاتی درباره متغیر ورودی و نوع آن می‌دهد ۳) یک بخش Returns گه درباره‌ی return value های تابع شما توضیح می‌دهد.
3. در صورتی که تابع شما یک routine یا procedure است در قسمت Returns درباره‌ی side-effect های اجرای تابعتان توضیح دهید.
4. هدف نوشتن و اضافه کردن function doc این است که دیگران و خودتان(بعد از کذشت زمان) بتوانید بدون خواند source code تابع بفهمید که یک تابع نوشته شده به چه صورت عمل می‌کند و برای اجرای درست آن به چه آرگومان‌هایی نیاز است و همین طور خروجی و یا side-effect ای اجرای تابع چه هستند.

#### حالت مطلوب

<div dir="ltr">

```R
CalculateSampleCovariance <- function(x, y, verbose = TRUE) {
  # Computes the sample covariance between two vectors.
  #
  # Args:
  #   x: One of two vectors whose sample covariance is to be calculated.
  #   y: The other vector. x and y must have the same length, greater than one,
  #      with no missing values.
  #   verbose: If TRUE, prints sample covariance; if not, not. Default is TRUE.
  #
  # Returns:
  #   The sample covariance between x and y.
  
  n <- length(x)
  # Error handling
  if (n <= 1 || n != length(y)) {
    stop("Arguments x and y have different lengths: ",
         length(x), " and ", length(y), ".")
  }
  if (TRUE %in% is.na(x) || TRUE %in% is.na(y)) {
    stop(" Arguments x and y must not have missing values.")
  }
  covariance <- var(x, y)
  if (verbose)
    cat("Covariance = ", round(covariance, 4), ".\n", sep = "")
  return(covariance)
}
```

<div dir="rtl">

#### حالت نامطلوب

<div dir="ltr">

```R
CalculateSampleCovariance <- function(x, y, verbose = TRUE) {  
  n <- length(x)
  # Error handling
  if (n <= 1 || n != length(y)) {
    stop("Arguments x and y have different lengths: ",
         length(x), " and ", length(y), ".")
  }
  if (TRUE %in% is.na(x) || TRUE %in% is.na(y)) {
    stop(" Arguments x and y must not have missing values.")
  }
  covariance <- var(x, y)
  if (verbose)
    cat("Covariance = ", round(covariance, 4), ".\n", sep = "")
  return(covariance)
}
```

<div dir="rtl">

## مراجع

<div dir="ltr">

1. [Google's R Style Guide](https://google.github.io/styleguide/Rguide.xml)