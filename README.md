<div dir="rtl">

راهنمای نوشتن برنامه‌ها به زبان R
=================================

#### همکاری در این کار:

- برای شروع به همکاری لطفا این مخزن را [فورک کنید](https://github.com/Cirice/My-R-Style-Guide); سپس یک انشعاب (Branch) درست کنید و شروع به کار کنید; سرانجام کارتان را به مخزن اعمال کنید و تغییراتتان را به گیت‌هاب push کنید، و [ یک درخواست Pull را ارسال کنید](https://help.github.com/articles/creating-a-pull-request).

- درخواست‌تان را از طریق [Project Issue Tracker](https://github.com/Cirice/My-R-Style-Guide/issues) بیان کنید.


## معرفی:

R یک زبان برنامه نویسی سطح بالای تابعی است که در کار‌های مربوط به تحلیل آماری و ترسیم نمودار‌های داده ای بسیار پر طرفدار است. هدف این راهنما ساده کردن فرایند نوشتن، خواندن، توزیع کردن و بررسی کردن کد نوشته به این زبان است. این نوشته حاوی تعداد زیادی نکته و مطلب است که به نظر من می‌توانند به دستیابی به هدف ذکر شده کمک کنند.

## قواعد ناگذاری

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

#### حالت نامطلب

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
average.value # this is prefered
AverageValue # also accepted
kMedianValue # constant variable
```

```R
# Function naming examples
CalculateMedian
ImportData
```

<div dir="rtl">

#### حالت نامطلب

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

#### حالت نامطلب

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

# Line break indentation
mean <- CalculateMean(data = c(1, 2, 3, 4, 5, 6, 7,
                               8, 9, 10))
```

<div dir="rtl">

#### حالت نامطلب

<div dir="ltr">

```R
# Mixing Tab with Space
mean <- CalculateMean(data = c(1, 2, 3, 4, 5, 6, 7,
								8, 9, 10))

# Using Tab for indentation                       
if (a == b) {
	x <- 1
}
```


<div dir="rtl">

## استفاده از فاصله(Spacing)

1. سمت چپ و راست همگی عملگر دودویی(binary operators) یک حرف فاصله(Space character) بگذارید(عملگر‌های دودویی مثل +، -، /, =، -> و غیره).
2. قبل از علامت , (comma) فاصله نگذارید.
3. همیشه بعد از علامت , (comma) یک حرف فاصله بگذارید.
4.  همیشه قبل از ) (پرانتز باز) یک حرف فاصله بگذارید.
5. بعد از ) (پرانتز باز) و قبل از ( (پرانتز بسته) حرف فاصله نگذارید.
6.   بعد از ](beacket باز) و قبل از [ (bracket بسته) حرف فاصله نگذارید.

### تبصره:
1. در زمان مقدار دهی به آرگومان‌های یک تابع می‌توانید سمت چپ و راست عملگر = فاصله‌ای نگدارید.
2. قبل از ) (پرانتز باز) در زمان فراخوانی یک تابع حرف فاصله نگدارید.
3. به طور کلی برای بالاتر بردن خوانایی کدتان می‌توانید بیشتر از یک حرف فاصله استفاده کنید.