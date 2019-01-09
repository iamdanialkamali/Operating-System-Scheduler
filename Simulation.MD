CHAPTER 17


۱.۱ حدسم این بود که  آدرس شروع اولین خانه خالی رو برمیگردونه ولی alloc آدرس شروع خانه گرفته شده و free برای موفقیت صفر را برمیگرداند
۱.۲ خانه های آزاد و تقسیم شده ی حافظه رو نشان میدهد و ترتیب قرار گیری آنها
۱.۳لیست با گذشت زمان به چند قسمت  کوچک تقسیم میشود


۲.تعداد قسمت  های کوچک تولید شده بیشتر میشود (باید coalesce کنیم) 


۳. سرعتش افزایش پیدا میکند//////////جستجو در لیست کم میشود
First :6.7
Best : 7.2
۴. طبیعتا مقدار زمانیش برای worst و best  تغییری نمیکنه چون در هرصورت کل لیست رو میچرخه
اما در first fit  اگر sizesort-  داشته باشیم همیشه اولین خونه جوابه مگه اینکه کلا جا نشه        و برای size sort+ تاثیز منفی داره روی نتیجه اش




















































۵.برای n = 100000  نتیجه زمانی بدون coaleason
16407.0591927
18359.7350121
18071.9511509
15777.0409584 
14515.9208775
برای n = 100000  نتیجه زمانی با coaleason
2488.46197128
2489.76612091
2522.61090279
2490.71884155
2501.51085854


در  orderبالا  در یک سری دستور ها ارور میدهد


ptr[70018] = Alloc(9)  returned -1 (searched 63 elements)
Free List [ Size 63 ]:  [ addr:1000 sz:1 ] [ addr:1001 sz:1 ] [ addr:1002 sz:1 ] [ addr:1003 sz:1 ] [ addr:1004 sz:1 ] [ addr:1005 sz:2 ] [ addr:1007 sz:1 ] [ addr:1008 sz:2 ] [ addr:1010 sz:1 ] [ addr:1011 sz:2 ] [ addr:1013 sz:1 ] [ addr:1014 sz:1 ] [ addr:1015 sz:1 ] [ addr:1016 sz:2 ] [ addr:1018 sz:1 ] [ addr:1019 sz:1 ] [ addr:1020 sz:1 ] [ addr:1021 sz:1 ] [ addr:1022 sz:2 ] [ addr:1024 sz:1 ] [ addr:1025 sz:2 ] [ addr:1027 sz:1 ] [ addr:1028 sz:1 ] [ addr:1029 sz:2 ] [ addr:1031 sz:1 ] [ addr:1032 sz:2 ] [ addr:1037 sz:1 ] [ addr:1038 sz:1 ] [ addr:1039 sz:1 ] [ addr:1040 sz:1 ] [ addr:1041 sz:1 ] [ addr:1042 sz:2 ] [ addr:1044 sz:3 ] [ addr:1047 sz:1 ] [ addr:1048 sz:1 ] [ addr:1049 sz:3 ] [ addr:1052 sz:1 ] [ addr:1053 sz:3 ] [ addr:1056 sz:1 ] [ addr:1057 sz:1 ] [ addr:1058 sz:1 ] [ addr:1059 sz:2 ] [ addr:1061 sz:1 ] [ addr:1062 sz:3 ] [ addr:1065 sz:1 ] [ addr:1066 sz:3 ] [ addr:1069 sz:1 ] [ addr:1070 sz:1 ] [ addr:1071 sz:1 ] [ addr:1072 sz:4 ] [ addr:1076 sz:1 ] [ addr:1077 sz:1 ] [ addr:1078 sz:1 ] [ addr:1079 sz:4 ] [ addr:1083 sz:1 ] [ addr:1084 sz:2 ] [ addr:1086 sz:1 ] [ addr:1087 sz:1 ] [ addr:1088 sz:4 ] [ addr:1092 sz:1 ] [ addr:1093 sz:1 ] [ addr:1094 sz:2 ] [ addr:1096 sz:4 ] 


در حالت عادی مموری به کلی قسمت های ریز تقسیم میشه که کنار هم  قرار میگیرن
با استفاده از -C سرعت به طرز چشمگیری افزایش می یابد 


۶. به ازای ۵۰ هر alloc بعدا free میشود به ازای کمتر از ۵۰ هم همین روال است چون باید فضایی برای free کردن alloc شده باشه
به ازای ۱۰۰ و نزدیک ۱۰۰ هم همه فقظ alloc اند


۷.
به ازای n = 100
FIRST
SIZESORT-                                        39
Alignment  = 1
FIRST
SIZESORT+                                        20
Alignment  = 1


FIRST
SORTADD                                        18
Alignment  = 1






CHAPTER 18
۱.با افزایش address space  اندازه ی page size افزایش میاید  چون پیجای بیشتری نیاز داریم
افزایش  page size اعث کاهش تعداد پیچ های مورد نیاز میشه پس اندازه page table کاهش پیدا میکنه


استفاده از پیج خیلی بزرگ باعث هدر رفت زیاد حافظه میشه


۲.با افزایش درصدش  پیج های بیشتری valid میشن
پس hit ها بیشتر میشن


۳. اولی اگخ منظور نسبت به واقعی باشه  چون سایزش خیلی page size کمه
سومی چون کل حافظه به دو تا page تقسیم میشه


۴.
هر کدوم منفی باشه
page size> address-space (منطقی نیست ولی ارور نمیده)
Address-space > Physical memory
اگه قابل تقسیم به هم  نباشند






 
CHAPTER 19
۱.نانو ثانیه
۲.
۳. 
5000 عدد مناسب است


  

۴ لینک بالا


۵ -o0 برای جلوگیری از optimization
۶.                  
هر core یک tlb داره طبیعتا باید بایکی بودنش hit  ها بیشتر باشه


۷.باید قبل از trials ارایه رو init کنیم




CHAPTER 20


همون یک رجیستر کافیه تا به جدول اول اشاره کنه
برای هر بار 3 تا جستجو(lookup) لازمه
Seed = 0 


Virtual Address 611c:
 --> pde index:0x18 [decimal 24] pde contents:0xa1 (valid 1, pfn 0x21 [decimal 33])
   --> pte index:0x8 [decimal 8] pte contents:0xb5 (valid 1, pfn 0x35 [decimal 53])
     --> Translates to Physical Address 0x6bc --> Value: 08
Virtual Address 3da8:
 --> pde index:0xf [decimal 15] pde contents:0xd6 (valid 1, pfn 0x56 [decimal 86])
   --> pte index:0xd [decimal 13] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 17f5:
 --> pde index:0x5 [decimal 5] pde contents:0xd4 (valid 1, pfn 0x54 [decimal 84])
   --> pte index:0x1f [decimal 31] pte contents:0xce (valid 1, pfn 0x4e [decimal 78])
     --> Translates to Physical Address 0x9d5 --> Value: 1c
Virtual Address 7f6c:
 --> pde index:0x1f [decimal 31] pde contents:0xff (valid 1, pfn 0x7f [decimal 127])
   --> pte index:0x1b [decimal 27] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 0bad:
 --> pde index:0x2 [decimal 2] pde contents:0xe0 (valid 1, pfn 0x60 [decimal 96])
   --> pte index:0x1d [decimal 29] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 6d60:
 --> pde index:0x1b [decimal 27] pde contents:0xc2 (valid 1, pfn 0x42 [decimal 66])
   --> pte index:0xb [decimal 11] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 2a5b:
 --> pde index:0xa [decimal 10] pde contents:0xd5 (valid 1, pfn 0x55 [decimal 85])
   --> pte index:0x12 [decimal 18] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 4c5e:
 --> pde index:0x13 [decimal 19] pde contents:0xf8 (valid 1, pfn 0x78 [decimal 120])
   --> pte index:0x2 [decimal 2] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 2592:
 --> pde index:0x9 [decimal 9] pde contents:0x9e (valid 1, pfn 0x1e [decimal 30])
   --> pte index:0xc [decimal 12] pte contents:0xbd (valid 1, pfn 0x3d [decimal 61])
     --> Translates to Physical Address 0x7b2 --> Value: 1b
Virtual Address 3e99:
 --> pde index:0xf [decimal 15] pde contents:0xd6 (valid 1, pfn 0x56 [decimal 86])
   --> pte index:0x14 [decimal 20] pte contents:0xca (valid 1, pfn 0x4a [decimal 74])
     --> Translates to Physical Address 0x959 --> Value: 1e



Seed = 1


Virtual Address 6c74:
 --> pde index:0x1b [decimal 27] pde contents:0xa0 (valid 1, pfn 0x20 [decimal 32])
   --> pte index:0x3 [decimal 3] pte contents:0xe1 (valid 1, pfn 0x61 [decimal 97])
     --> Translates to Physical Address 0xc34 --> Value: 06
Virtual Address 6b22:
 --> pde index:0x1a [decimal 26] pde contents:0xd2 (valid 1, pfn 0x52 [decimal 82])
   --> pte index:0x19 [decimal 25] pte contents:0xc7 (valid 1, pfn 0x47 [decimal 71])
     --> Translates to Physical Address 0x8e2 --> Value: 1a
Virtual Address 03df:
 --> pde index:0x0 [decimal 0] pde contents:0xda (valid 1, pfn 0x5a [decimal 90])
   --> pte index:0x1e [decimal 30] pte contents:0x85 (valid 1, pfn 0x05 [decimal 5])
     --> Translates to Physical Address 0x0bf --> Value: 0f
Virtual Address 69dc:
 --> pde index:0x1a [decimal 26] pde contents:0xd2 (valid 1, pfn 0x52 [decimal 82])
   --> pte index:0xe [decimal 14] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 317a:
 --> pde index:0xc [decimal 12] pde contents:0x98 (valid 1, pfn 0x18 [decimal 24])
   --> pte index:0xb [decimal 11] pte contents:0xb5 (valid 1, pfn 0x35 [decimal 53])
     --> Translates to Physical Address 0x6ba --> Value: 1e
Virtual Address 4546:
 --> pde index:0x11 [decimal 17] pde contents:0xa1 (valid 1, pfn 0x21 [decimal 33])
   --> pte index:0xa [decimal 10] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 2c03:
 --> pde index:0xb [decimal 11] pde contents:0xc4 (valid 1, pfn 0x44 [decimal 68])
   --> pte index:0x0 [decimal 0] pte contents:0xd7 (valid 1, pfn 0x57 [decimal 87])
     --> Translates to Physical Address 0xae3 --> Value: 16
Virtual Address 7fd7:
 --> pde index:0x1f [decimal 31] pde contents:0x92 (valid 1, pfn 0x12 [decimal 18])
   --> pte index:0x1e [decimal 30] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)
Virtual Address 390e:
 --> pde index:0xe [decimal 14] pde contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page directory entry not valid)
Virtual Address 748b:
 --> pde index:0x1d [decimal 29] pde contents:0x80 (valid 1, pfn 0x00 [decimal 0])
   --> pte index:0x4 [decimal 4] pte contents:0x7f (valid 0, pfn 0x7f [decimal 127])
     --> Fault (page table entry not valid)

3. در cahce به دلیل  spatial locality  خیلی از اوقات hit میخوره
