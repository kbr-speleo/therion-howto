# Therion HOWTO

## Конфигурация шрифтов для PDF (Ubuntu)

    sudo apt-get install ttf-dejavu-extra
    echo pdf-fonts /usr/share/fonts/truetype/ttf-dejavu/DejaVuSerifCondensed.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSerifCondensed-Italic.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSerifCondensed-Bold.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSansCondensed.ttf /usr/share/fonts/truetype/ttf-dejavu/DejaVuSansCondensed-Oblique.ttf >> ~/.therion/therion.ini 

В других дистрибуциях Линукса шрифты могут быть в других папках.

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


