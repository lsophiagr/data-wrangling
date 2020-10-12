Laboratorio 1
================
Sophia Gamarro
8/9/2020

## PROBLEMA 1

``` r
library(readxl)
library(readr)
library(tidyverse) 
```

    ## ── Attaching packages ───────────────────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ ggplot2 3.3.2     ✓ dplyr   0.8.5
    ## ✓ tibble  3.0.3     ✓ stringr 1.4.0
    ## ✓ tidyr   1.1.1     ✓ forcats 0.5.0
    ## ✓ purrr   0.3.3

    ## ── Conflicts ──────────────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(tidytext)
library(dplyr)
setwd("/Users/sophiagamarro/Documents/Semestre II 2020/Data Wrangling/Lab1")
excel1<-read_excel('01-2018.xlsx')
excel2<-read_excel('02-2018.xlsx')
excel3<-read_excel('03-2018.xlsx')
excel4<-read_excel('04-2018.xlsx')
excel5<-read_excel('05-2018.xlsx')
excel6<-read_excel('06-2018.xlsx')
excel7<-read_excel('07-2018.xlsx')
excel8<-read_excel('08-2018.xlsx')
```

    ## New names:
    ## * `` -> ...10

``` r
excel9<-read_excel('09-2018.xlsx')
excel10<-read_excel('10-2018.xlsx')
excel11<-read_excel('11-2018.xlsx')
excel1$Fecha <- "01-2018"
excel2$Fecha <- "01-2018"
excel3$Fecha <- "01-2018"
excel4$Fecha <- "01-2018"
excel5$Fecha <- "01-2018"
excel6$Fecha <- "01-2018"
excel7$Fecha <- "01-2018"
excel8$Fecha <- "01-2018"
excel9$Fecha <- "01-2018"
excel10$Fecha <- "01-2018"
excel11$Fecha <- "01-2018"

dataset<-dplyr::bind_rows(excel1,excel2, excel3, excel4, excel5, excel6, excel7, excel8, excel9, excel10, excel11)

write.csv(dataset,'dataset.csv')
head(dataset)
```

    ## # A tibble: 6 x 11
    ##   COD_VIAJE CLIENTE UBICACION CANTIDAD PILOTO     Q CREDITO UNIDAD Fecha  TIPO
    ##       <dbl> <chr>       <dbl>    <dbl> <chr>  <dbl>   <dbl> <chr>  <chr> <dbl>
    ## 1  10000001 EL PIN…     76002     1200 Ferna… 300        30 Camio… 01-2…    NA
    ## 2  10000002 TAQUER…     76002     1433 Hecto… 358.       90 Camio… 01-2…    NA
    ## 3  10000003 TIENDA…     76002     1857 Pedro… 464.       60 Camio… 01-2…    NA
    ## 4  10000004 TAQUER…     76002      339 Angel…  84.8      30 Panel  01-2…    NA
    ## 5  10000005 CHICHA…     76001     1644 Juan … 411        30 Camio… 01-2…    NA
    ## 6  10000006 UBIQUO…     76001     1827 Luis … 457.       30 Camio… 01-2…    NA
    ## # … with 1 more variable: ...10 <dbl>

## PROBLEMA 2

``` r
moda <- function(v) {
  uniqv <- unique(v)
  uniqv[which.max(tabulate(match(v, uniqv)))]
}

vector_1 <- c(4,1,3,9,7)
vector_2<- c(1,9,4,2,2)
vector_3 <- c(9,1,4,5,1)

lista <- list(vector_1,vector_2,vector_3)

lapply(lista, moda)
```

    ## [[1]]
    ## [1] 4
    ## 
    ## [[2]]
    ## [1] 2
    ## 
    ## [[3]]
    ## [1] 1

## PROBLEMA 3

``` r
parque_vehicular<-read.delim("Parque.txt", header=T, sep="|")
```

    ## Warning in scan(file = file, what = what, sep = sep, quote = quote, dec = dec, :
    ## EOF within quoted string

``` r
head(parque_vehicular)
```

    ##   ANIO_ALZA MES NOMBRE_DEPARTAMENTO NOMBRE_MUNICIPIO MODELO_VEHICULO
    ## 1      2007   5       HUEHUETENANGO    HUEHUETENANGO            2007
    ## 2      2007   5         EL PROGRESO        EL JICARO            2007
    ## 3      2007   5          SAN MARCOS             OCOS            2007
    ## 4      2007   5           ESCUINTLA      SAN JOS\xc9            2006
    ## 5      2007   5             JUTIAPA           MOYUTA            2007
    ## 6      2007   5           GUATEMALA        FRAIJANES            1997
    ##            LINEA_VEHICULO TIPO_VEHICULO USO_VEHICULO MARCA_VEHICULO CANTIDAD  X
    ## 1                SPORT125          MOTO  MOTOCICLETA      ASIA HERO        1 NA
    ## 2 BT-50 DBL CAB 4X2 TURBO       PICK UP   PARTICULAR          MAZDA        1 NA
    ## 3                   JL125          MOTO  MOTOCICLETA         KINLON        1 NA
    ## 4               JL125T-15          MOTO  MOTOCICLETA        JIALING        1 NA
    ## 5                 JH100-2          MOTO  MOTOCICLETA        JIALING        1 NA
    ## 6  TACOMA XTRA CAB 4X4 V6       PICK UP   PARTICULAR         TOYOTA        1 NA
