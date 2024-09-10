# 1. Возможности графического интерфейса в OpenCV

## 1.1 Начало работы с изображениями

Научитесь загружать изображение, отображать его и сохранять обратно.

Цель:\
В этом уроке вы узнаете, как:

Прочитать изображение из файла       (используя **cv::imread** )\
Отобразить изображение в окне OpenCV (используя **cv::imshow** )\
Записать изображение в файл          (используя **cv::imwrite** )

``` python
import cv2 as cv
import sys
 
img = cv.imread(cv.samples.findFile("starry_night.jpg"))
 
if img is None:
    sys.exit("Could not read the image.")
 
cv.imshow("Display window", img)
k = cv.waitKey(0)
 
if k == ord("s"):
    cv.imwrite("starry_night.png", img)
```

## 1.2 Начало работы с видео

Научитесь воспроизводить видео, снимать видео с камеры и писать видео

## 1.3 Функции рисования в OpenCV

Научитесь рисовать линии, прямоугольники, эллипсы, круги и т. д. с помощью OpenCV

## 1.4 Мышь как кисть

Рисуйте мышкой

## 1.5 Трекбар как цветовая палитра

Создать трекбар для управления определенными параметрами
