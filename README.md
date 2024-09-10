# 1. Возможности графического интерфейса в OpenCV

## 1.1 Начало работы с изображениями

Научитесь загружать изображение, отображать его и сохранять обратно.

Цель:\
В этом уроке вы узнаете, как:

Прочитать изображение из файла       (используя **cv.imread** )\
Отобразить изображение в окне OpenCV (используя **cv.imshow** )\
Записать изображение в файл          (используя **cv.imwrite** )

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
**Объяснение:**

В качестве первого шага импортируется библиотека OpenCV python. Правильный способ сделать это — дополнительно присвоить ей имя cv , которое используется в дальнейшем для ссылки на библиотеку.

```python
import cv2 as cv
import sys
```
Теперь давайте проанализируем основной код. В качестве первого шага мы считываем изображение "starry_night.jpg" из образцов OpenCV. Для этого вызов функции cv::imread загружает изображение, используя путь к файлу, указанный первым аргументом. Второй аргумент необязателен и указывает формат, в котором мы хотим получить изображение. Это может быть:

IMREAD_COLOR загружает изображение в формате BGR 8-bit. Это значение по умолчанию , которое здесь используется.\
IMREAD_UNCHANGED загружает изображение как есть (включая альфа-канал, если он есть)\
IMREAD_GRAYSCALE загружает изображение как интенсивное\
После считывания данные изображения будут сохранены в объекте cv::Mat .

img = cv.imread ( cv.samples.findFile ( "starry_night.jpg" ))
Примечание
OpenCV предлагает поддержку форматов изображений Windows bitmap (bmp), переносимых форматов изображений (pbm, pgm, ppm) и Sun raster (sr, ras). С помощью плагинов (вам необходимо указать их использование, если вы создаете библиотеку самостоятельно, тем не менее, в пакетах, которые мы поставляем, они присутствуют по умолчанию) вы также можете загружать такие форматы изображений, как JPEG (jpeg, jpg, jpe), JPEG 2000 (jp2 - кодовое название в CMake как Jasper), файлы TIFF (tiff, tif) и переносимую сетевую графику (png). Кроме того, OpenEXR также возможен.
После этого выполняется проверка, корректно ли загружено изображение.

если img равен  None :
    sys.exit( "Не удалось прочитать изображение." )
Затем изображение отображается с помощью вызова функции cv::imshow . Первый аргумент — заголовок окна, а второй аргумент — объект cv::Mat , который будет показан.

Поскольку мы хотим, чтобы наше окно отображалось до тех пор, пока пользователь не нажмет клавишу (иначе программа завершится слишком быстро), мы используем функцию cv::waitKey , единственным параметром которой является то, как долго она должна ждать ввода пользователя (измеряется в миллисекундах). Ноль означает вечное ожидание. Возвращаемое значение — это нажатая клавиша.

cv.imshow ( "Окно отображения" , img)
k = cv.waitKey (0)
В конце концов, изображение записывается в файл, если нажата клавиша "s". Для этого вызывается функция cv::imwrite , которая имеет путь к файлу и объект cv::Mat в качестве аргумента.

если k == ord( "s" ):
    cv.imwrite ( "starry_night.png" , img)

## 1.2 Начало работы с видео

Научитесь воспроизводить видео, снимать видео с камеры и писать видео

## 1.3 Функции рисования в OpenCV

Научитесь рисовать линии, прямоугольники, эллипсы, круги и т. д. с помощью OpenCV

## 1.4 Мышь как кисть

Рисуйте мышкой

## 1.5 Трекбар как цветовая палитра

Создать трекбар для управления определенными параметрами
