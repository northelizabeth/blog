---
title: "Correspondance Analysis of Luxury to Mid-Range Car Brand Perception"
date: 2020-11-27
---


Code to reproduce analysis (R):   
1 install . packages ( " FactoMineR " )  
2 install . packages ( " factoextra " )  
3 install . packages ( " gplots " )  
4 install . packages ( " graphics " )  
5 library ( FactoMineR )  
6 library ( factoextra )  
7 library ( gplots )  
8 library ( graphics )  
9  
10 cardata <- data ( datacar )  
11 head ( datacar )  
12 View ( datacar )  
13 dt <- as . table ( as . matrix ( datacar ) )  
14  
15 fviz _ screeplot ( res . ca ) +  
16 geom _ hline ( yintercept =33.33 , linetype =2 , color = " red " )  
17  
18 mosaicplot ( dt , shade = TRUE , las =2 ,  
19 main = " Car Perceptions Among Students " )  
20  
21  
22 res . ca <- CA ( datacar , graph = FALSE )  
23 print ( res . ca )  
24 summary ( res . ca )  
25  
26  
27 get _ eigenvalue ( res . ca )  
28 fviz _ ca _ biplot ( res . ca , repel = TRUE )  
29  
30 fviz _ ca _ biplot ( res . ca , map = " colgreen " , arrow = c ( TRUE , FALSE ) ,  
31 repel = TRUE )  
32  
33 # # Extra Analysis out of interest  
34 balloonplot ( t ( dt ) , main = " Car Perception " , xlab = " " , ylab = " " ,  
35 label = FALSE , show . margins = FALSE )  
36  
37 eig . val <- get _ eigenvalue ( res . ca )  
38 eig . val  
39  
40 fviz _ screeplot ( res . ca , addlabels = TRUE , ylim = c (0 ,50) )  
41  
42 fviz _ screeplot ( res . ca ) +  
43 geom _ hline ( yintercept =33.33 , linetype =2 , color = " red " )  
44  
45 row <- get _ ca _ row ( res . ca )  
46 row  
47 head ( row $ inertia )  
48 head ( row $ contrib )  
49 # Cos2 : quality on the factore map  
50 head ( row $ cos2 )  
51 # Contributions to the principal components  
52 head ( row $ contrib )  
53  
54 fviz _ contrib ( res . ca , choice = " row " , axes = 1 , top = 10)  
55 # Contributions of rows to dimension 2  
56 fviz _ contrib ( res . ca , choice = " row " , axes = 2 , top = 10)  
57  
58 fviz _ contrib ( res . ca , choice = " col " , axes = 1:2)  

