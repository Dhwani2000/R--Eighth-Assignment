# R--Eighth-Assignment

> library(readxl)
> Students_Grades <- read_excel("Assignment 6 dataset.xlsx")
> Students_Grades
   Name        Age Sex    Grade
   <chr>     <dbl> <chr>  <dbl>
 1 Raul         25 Male      80
 2 Booker       18 Male      83
 3 Lauri        21 Female    90
 4 Leonie       21 Female    91
 5 Sherlyn      22 Female    85
 6 Mikaela      20 Female    69
 7 Raphael      23 Male      91
 8 Aiko         24 Female    97
 9 Tiffaney     21 Female    78
10 Cornia       23 Female    81
11 Petronila    23 Female    98
12 Alecia       20 Female    87
13 Shemika      23 Female    97
14 Fallon       22 Female    90
15 Deloris      21 Female    67
16 Randee       23 Female    91
17 Eboni        20 Female    84
18 Delfina      19 Female    93
19 Ernestina    19 Female    93
20 Milo         19 Male      67
  
  
> library(plyr)
> Students_Average <- ddply(Students_Grades, "Sex", transform.data.frame, Grade.Average=mean(Grade))
> Students_Average
        Name Age    Sex Grade Grade.Average
1      Lauri  21 Female    90       86.9375
2     Leonie  21 Female    91       86.9375
3    Sherlyn  22 Female    85       86.9375
4    Mikaela  20 Female    69       86.9375
5       Aiko  24 Female    97       86.9375
6   Tiffaney  21 Female    78       86.9375
7     Cornia  23 Female    81       86.9375
8  Petronila  23 Female    98       86.9375
9     Alecia  20 Female    87       86.9375
10   Shemika  23 Female    97       86.9375
11    Fallon  22 Female    90       86.9375
12   Deloris  21 Female    67       86.9375
13    Randee  23 Female    91       86.9375
14     Eboni  20 Female    84       86.9375
15   Delfina  19 Female    93       86.9375
16 Ernestina  19 Female    93       86.9375
17      Raul  25   Male    80       80.2500
18    Booker  18   Male    83       80.2500
19   Raphael  23   Male    91       80.2500
20      Milo  19   Male    67       80.2500
  
  
> write.table(Students_Average, "Average_of_Students")
  "Name" "Age" "Sex" "Grade" "Grade.Average"
"1" "Lauri" 21 "Female" 90 86.9375
"2" "Leonie" 21 "Female" 91 86.9375
"3" "Sherlyn" 22 "Female" 85 86.9375
"4" "Mikaela" 20 "Female" 69 86.9375
"5" "Aiko" 24 "Female" 97 86.9375
"6" "Tiffaney" 21 "Female" 78 86.9375
"7" "Cornia" 23 "Female" 81 86.9375
"8" "Petronila" 23 "Female" 98 86.9375
"9" "Alecia" 20 "Female" 87 86.9375
"10" "Shemika" 23 "Female" 97 86.9375
"11" "Fallon" 22 "Female" 90 86.9375
"12" "Deloris" 21 "Female" 67 86.9375
"13" "Randee" 23 "Female" 91 86.9375
"14" "Eboni" 20 "Female" 84 86.9375
"15" "Delfina" 19 "Female" 93 86.9375
"16" "Ernestina" 19 "Female" 93 86.9375
"17" "Raul" 25 "Male" 80 80.25
"18" "Booker" 18 "Male" 83 80.25
"19" "Raphael" 23 "Male" 91 80.25
"20" "Milo" 19 "Male" 67 80.25
  
> write.table(Students_Average, "AOS", sep = ",")
  "Name","Age","Sex","Grade","Grade.Average"
"1","Lauri",21,"Female",90,86.9375
"2","Leonie",21,"Female",91,86.9375
"3","Sherlyn",22,"Female",85,86.9375
"4","Mikaela",20,"Female",69,86.9375
"5","Aiko",24,"Female",97,86.9375
"6","Tiffaney",21,"Female",78,86.9375
"7","Cornia",23,"Female",81,86.9375
"8","Petronila",23,"Female",98,86.9375
"9","Alecia",20,"Female",87,86.9375
"10","Shemika",23,"Female",97,86.9375
"11","Fallon",22,"Female",90,86.9375
"12","Deloris",21,"Female",67,86.9375
"13","Randee",23,"Female",91,86.9375
"14","Eboni",20,"Female",84,86.9375
"15","Delfina",19,"Female",93,86.9375
"16","Ernestina",19,"Female",93,86.9375
"17","Raul",25,"Male",80,80.25
"18","Booker",18,"Male",83,80.25
"19","Raphael",23,"Male",91,80.25
"20","Milo",19,"Male",67,80.25
  

> Students_i <- subset(Students_Grades, grepl("i", Name))
> Students_i
   Name        Age Sex    Grade
   <chr>     <dbl> <chr>  <dbl>
 1 Lauri        21 Female    90
 2 Leonie       21 Female    91
 3 Mikaela      20 Female    69
 4 Aiko         24 Female    97
 5 Tiffaney     21 Female    78
 6 Cornia       23 Female    81
 7 Petronila    23 Female    98
 8 Alecia       20 Female    87
 9 Shemika      23 Female    97
10 Deloris      21 Female    67
11 Eboni        20 Female    84
12 Delfina      19 Female    93
13 Ernestina    19 Female    93
14 Milo         19 Male      67
     
> write.table(Students_i, "Student_I", sep = ",")
"Name","Age","Sex","Grade"
"1","Lauri",21,"Female",90
"2","Leonie",21,"Female",91
"3","Mikaela",20,"Female",69
"4","Aiko",24,"Female",97
"5","Tiffaney",21,"Female",78
"6","Cornia",23,"Female",81
"7","Petronila",23,"Female",98
"8","Alecia",20,"Female",87
"9","Shemika",23,"Female",97
"10","Deloris",21,"Female",67
"11","Eboni",20,"Female",84
"12","Delfina",19,"Female",93
"13","Ernestina",19,"Female",93
"14","Milo",19,"Male",67     
