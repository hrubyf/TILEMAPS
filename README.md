# TILEMAPS
[Download RStudio](https://rstudio.com/products/rstudio/download/#download)
## Testfrage
Welche Abbildung gibt Ihrer Meinung nach die geographische Gestalt der Steiermark am besten wieder? Weisen Sie bitte jeder Abbildung (A bis H) einen Rang von 1 (finde ich am geeignetsten) bis 8 (finde ich am ungeeignetsten) zu, bis alle Rangplätze zwischen 1 und 8 vergeben sind.
![alt text](https://lh6.googleusercontent.com/1IFOvqctairloaPbaL1BnakcE6Hl-nSgpWwKunS51KGoPe11AQCBKD8AaLPTiyDbuJS1XE8gTsTI6MRBJYhHSJcFy31BpUhAKvaFEaxOaxpArmAlJC-fCuwyIxUMeg=w1823)

## Download der gesammelten empirischen Daten
https://drive.google.com/file/d/1IVb6NvgHeaLNpawO-VdfO230Rebc7kwz/view?usp=sharing

## Datenanalyse unter Annahme nicht-normalverteilter Daten (nicht-parametrische Tests)
Da wir es mit ordinal-skalierten (d.h. nach den Rängen 1 bis 8 geordneten) Daten zu tun haben und daher von keiner Normalverteilung ausgehen können, müssen wir einen nicht-parametrischen Test verwenden. Hierfür bietet sich in unserem Fall der Kruskal–Wallis Test an:
 
*"Use the Kruskal–Wallis test when you have one nominal variable and one ranked variable. It tests whether the mean ranks are the same in all the groups." (McDonald, J. H. (2009): Handbook of biological statistics).*
## R-snippets | Aufbereitung und Prüfung der Daten
a) Zum Einlesen von Exceldateien das Paket "readxl" installieren und laden: 
```
install.packages("readxl")
library(readxl)
```
b) Daten in RStudio laden:
```
HEX <- read_excel("HEX.xlsx")
```
