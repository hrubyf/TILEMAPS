# HEXAGON TILEMAPS
[Download RStudio](https://rstudio.com/products/rstudio/download/#download)
## Testfrage A
Welche Abbildung gibt Ihrer Meinung nach die geographische Gestalt der Steiermark am besten wieder? Weisen Sie bitte jeder Abbildung (A bis H) einen Rang von 1 (finde ich am geeignetsten) bis 8 (finde ich am ungeeignetsten) zu, bis alle Rangplätze zwischen 1 und 8 vergeben sind.
![alt text](https://lh6.googleusercontent.com/1IFOvqctairloaPbaL1BnakcE6Hl-nSgpWwKunS51KGoPe11AQCBKD8AaLPTiyDbuJS1XE8gTsTI6MRBJYhHSJcFy31BpUhAKvaFEaxOaxpArmAlJC-fCuwyIxUMeg=w1823)

## Download der gesammelten empirischen Daten
https://drive.google.com/file/d/1IVb6NvgHeaLNpawO-VdfO230Rebc7kwz/view?usp=sharing

## Datenanalyse unter Annahme nicht-normalverteilter Daten (nicht-parametrische Tests)
Da wir es mit ordinal-skalierten (d.h. nach den Rängen 1 bis 8 geordneten) Daten zu tun haben und daher von keiner Normalverteilung ausgehen können, müssen wir einen nicht-parametrischen Test verwenden. Hierfür bietet sich in unserem Fall der Kruskal–Wallis Test an:
 
*"Use the Kruskal–Wallis test when you have one nominal variable and one ranked variable. It tests whether the mean ranks are the same in all the groups." (McDonald, J. H. (2009): Handbook of biological statistics).*
## R-SNIPPETS 
## Aufbereitung und Durchsicht der Daten
a) Zum Einlesen von Exceldateien das Paket "readxl" installieren und laden: 
```
install.packages("readxl")
library(readxl)
```
b) Daten in RStudio laden:
```
HEX <- read_excel("HEX.xlsx")
```
c) Um sich einen ersten Überblick über die Daten zu verschaffen:
```
install.packages("psych")
library(psych)

describeBy(HEX$Rank, HEX$Design)

boxplot(HEX$Rank~HEX$Design)
```
## Test auf Unterschiede hinsichtlich der Präferenzen verschiedener Tilemaps. 
H0: Alle Tilemaps werden ähnlich bewertet. Kein Design wird als besonders gut oder schlecht evaluiert.
HA: Die Bewertung einzelner Tilemaps unterscheiden sich signifikant.
```
kruskal.test(HEX$Rank~HEX$Design)
```
## Post-hoc-Test 
Zwischen welchen Tilemaps gibt es in Bezug auf die Bewertung signifikante Unterschiede?
```
pairwise.wilcox.test(HEX$Rank, HEX$Design, paired = FALSE, p.adjust = "bonferroni")
```
## Testfrage B
Welche Abbildung gibt Ihrer Meinung nach die geographische Gestalt der Steiermark bester wieder?
![alt text](https://lh4.googleusercontent.com/uMi2zloyyGRcsZSEsRvLDt2DjTIQMyDPNRPkErA2XrNFpCtfDiYgcFGke7g-UJsjNDHO7TebB4JDkmozcZzvWNdyaS0Ahy5F7RoVsG6PNY5bsUt1n-h8QVZqFaUjiQ=w1117)

## Download der gesammelten empirischen Daten
https://drive.google.com/file/d/1msdEsIRhzEFXvxpVZE3LdYFv1Xi61kTp/view?usp=sharing

## Einstichproben-Wilcoxon-Test
```
wilcox.test(HEXvsSQU$Rank, mu=1.5)
```
## Testfrage C
Welches Hexagon gibt Ihrer Meinung nach die geographische Lage des Bezirks "XY" am besten wieder?
![alt text](https://lh3.googleusercontent.com/Gu8up1JPQ8_B4FUaIBZ2y6MnHTqkPoisMNMSs6cM5Jh_ZwoHEe0HyVp10OXRWS1GYav-wRAbhcKkJvh7VWhFfSd5J3iAShWwj1RljyvEUWsvAD4uQYKyiu6mzdry2w=w1500)
