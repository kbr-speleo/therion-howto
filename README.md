# Therion HOWTO

## Конфигурация шрифтов для PDF (Debian 8)

    sudo apt-get install ttf-dejavu-extra lcdf-typetools
    echo pdf-fonts /usr/share/fonts/truetype/ttf-dejavu/DejaVuSerifCondensed.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSerifCondensed-Italic.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSerifCondensed-Bold.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSansCondensed.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSansCondensed-Oblique.ttf >> ~/.therion/therion.ini 

В других дистрибуциях Линукса шрифты могут быть в других папках. Напримерь в Debian 9:

    sudo apt-get install fonts-dejavu-extra lcdf-typetools
    echo pdf-fonts /usr/share/fonts/truetype/dejavu/DejaVuSerifCondensed.ttf /usr/share/fonts/truetype/dejavu/DejaVuSerifCondensed-Italic.ttf /usr/share/fonts/truetype/dejavu/DejaVuSerifCondensed-Bold.ttf /usr/share/fonts/truetype/dejavu/DejaVuSansCondensed.ttf /usr/share/fonts/truetype/dejavu/DejaVuSansCondensed-Oblique.ttf >> ~/.therion/therion.ini

## Ошибки

Программа Therion довольно сложная и часто вылетает с не очень ясными кодами ошибок.

    therion: error -- scrap HMb@main defined at plan.th2 [1622] is too large to process in metapost in this scale -- maximal scale for this scrap is 1 : 870663

Может имет две причины. Во первых проверьте, имеет ли **каждый** из "обрывков" карты (*scrap*) не менее чем **тве** точки-пикеты (*station*). Therion испльзует
их для определения масштаба каждого с обрывков и если их нету, он вылетает с такой ошибкой.

Вторая возможная причина это именно то что написано - карта которую Therion пытается составить автоматически слишком большая. В таком случае нужно воспользоваться
опцией `scale`:

```
layout normal
    scale 1 500
endlayout
````

Непонятные ошибки в роде:

    Segmentation fault
    therion: error -- unknown exception

У меня это случается на стадии генерирования модели Loch (.lox) в случае ошибок в обрисовке корридоров на карте.

```
line wall
endwall

area water
endarea
```

## Links

* [https://therion.speleo.sk/wiki/tips]
* [https://therion.speleo.sk/wiki/tbe:wiki2]
* [http://wscc.darkgem.com/footleg/therion/Therion%20Tutorial%2015thMar2016.pdf]
* [http://marcocorvi.altervista.org/caving/tbe/fulltoc.htm]
* [http://marcocorvi.altervista.org/caving/tbe/m_02/m_02a.htm]
* [http://marcocorvi.altervista.org/caving/tbe/m_02/m_027.htm]
* [https://therion.speleo.sk/wiki/outputs]
