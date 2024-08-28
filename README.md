# 3D-Dev-Guide

Эта статья описывает правила и порядок 3D разработки

<a name="top"></a>
## Структура пайплайна

> 1. [Reference Board](#reference)
> 1. [Druft / Blocking](#druft)
> 1. [High Poly](#hp)
> 1. [LODs](#lods)
> 2. [Unwrap & Pack](#unwrap)
> 1. [Bake](#bake)
> 2. [Texturing](#texturing)
> 3. [Engine Setup](#enginesetup)

<a name="reference"></a>
## 1. Reference Board

Для сбора и композиции референсов используется программа [PureRef](https://www.pureref.com/).

### Виды референсов

* **Концепт** — рисунок, который показывает, как в будущем должна выглядеть модель. Это ее общий вид, который утвердил арт директор и геймдизайнер. На каждой картинке видны силуэт будущей модели и крупные формы.
* **Фотографии** — нужны, чтобы лучше понять силуэт и составляющие модели. Работа художника — это подражание реальному миру, поэтому сначала стоит искать референсы в реальности или на фотографиях, потому что любой рисунок — не объективный референс.
* **Работы других художников** — скорее всего ты не первый, кто моделит эту вещь. Полезно посмотреть какую работу проделали другие моделлеры и понять, какой путь они прошли. Опыт десятков других художников заслуживает отдельной категории референсов.
* **Детали** — помогают понять, как функционирует объект и как детали крепятся друг к другу.
* **Материалы, текстуры** — важно найти хорошие фотографии и арты с выразительными текстурами и фактурами. Из головы хороший материал не сделать, поэтому важно запастись рефами.
* **Повреждения и потертости** — у разных объектов они сильно отличаются. Из всех возможных «50 оттенков ржавчины» для проекта нужно выбрать 2-3, которые ты будешь использовать. Очень часто, даже опытные художники считают, что они могут выдумать повреждения из головы, но это почти нереально. Повреждения — это сложные формы, за которыми видно устройство объекта. Без референсов хорошие повреждения не сделаешь.

Зачастую референсы разбивают по группам на рефборде:
> 1. Общий вид объекта
> 2. Контекст и окружение объекта
> 3. Вид спереди
> 4. Вид сбоку
> 5. Вид сзади
> 6. Вид сверху/снизу
> 7. Эскизы и концепты, сделанные вручную
> 8. Модели других художников
> 9. Для важных деталей составляются дополнительные группы референсов

[Подробнее про референсы от XYZ](https://www.school-xyz.com/blog/aaa_pajplajn_statya_2_7_vsyo_pro_drafty#:~:text=%D0%A8%D0%B0%D0%B3%201%3A%20%D0%A0%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%20%D1%81%20%D1%80%D0%B5%D1%84%D0%B5%D1%80%D0%B5%D0%BD%D1%81%D0%B0%D0%BC%D0%B8)

<a name="druft"></a>
## 2. Druft & Blocking

**Драфт** — это упрощенная форма модели, которую мы делаем из простых блоков.

Если драфт выглядит невыразительно — сразу переделывай, чтобы после не было серьезных проблем.

Этапы:

> 2.1 [Общие формы - база](#druft-base)  
> 2.2 [Масштаб, пропорции, силуэт](#druft-size)  
> 2.3 [Детализация](#druft-details)  
> 2.4 [Материалы и текстурные сеты](#druft-texture)  

<a name="druft-base"></a>
### 2.1 Общие формы - база

Сначала моделируются крупные формы, которые образуют силуэт. Важны пропорции, масштаб и механика объекта. Он должен быть узнаваем, даже без детализации.

На блокинг средней модели у тебя должно уходить **не более 40 минут**.Если ты тратишь больше 40 минут, то, скорее всего, ты потратил кучу времени на вещи, не влияющие на силуэт — то-есть не справился с этим этапом.

<a name="druft-size"></a>
### 2.2 Масштаб, пропорции, силуэт

#### 2.2.1 Силуэт

На этом этапе из простых форм делаем объект читаемым. Визуальное восприятие любого объекта начинается с силуэта. Нет смысла моделить детали, если силуэт не читается.

Создай несколько примитивов, которые образуют формы объекта. Следи за тем, чтобы силуэт легко читался и не был скучным. Если не вышло — переделывай, потому что потом даже красивые текстуры не спасут модель.

#### 2.2.2 Масштаб и пропорции

Чтобы понять масштаб объекта, его нужно с чем-то сравнить.
Для наших глаз все относительно. Чтобы масштаб легко было читать, добавь к модели дополнительные детали или объекты.

**Не забывай о пропорциях.**
На этапе блокинга важно следить, чтобы пропорции были правильными. Для этого найди объект по которому будет сверяться размер других моделей. Пока на этапе блокинга нет большой детализации — ошибки исправлять легко.

[Подробнее по масштабы от XYZ](https://www.school-xyz.com/blog/aaa_pajplajn_statya_2_7_vsyo_pro_drafty#:~:text=%D0%A8%D0%B0%D0%B3%203%3A%20%D0%94%D0%B5%D0%BB%D0%B0%D0%B5%D0%BC%20%D0%B1%D0%BB%D0%BE%D0%BA%D0%B8%D0%BD%D0%B3)

<a name="druft-details"></a>
### 2.3 Детализация

Добавляем детализацию к драфту и улучшаем его. По факту идет подготовка под сабдив/скульпт/hp.

[Подробнее по детализацию от XYZ](https://www.school-xyz.com/blog/aaa_pajplajn_statya_2_7_vsyo_pro_drafty#:~:text=%D0%A8%D0%B0%D0%B3%204%3A%20%D0%94%D0%B5%D1%82%D0%B0%D0%BB%D1%8C%D0%BD%D1%8B%D0%B9%20%D0%B4%D1%80%D0%B0%D1%84%D1%82)

<a name="druft-details"></a>
### 2.3 Материалы и текстурные сеты

Уже с этого этапа важно понимать сколько будет материалов, на каких частях модели они будут находиться, и готовить почву для соблюдения правила: **Один материал - находится в одном текстурном сете**. Это предотвращяет двойную работу по редактированию одинакового материала в нескольких текстурных сетах. 

<a name="hp"></a>
## 3. High Poly

High poly — это детализированная модель без ограничений по полигонам. Такие модели делают концепторы, а в видеоиграх они нужны для запечки нормала.

На high poly можно всё, потому что нет ограничений по полигонам. Главное ограничение — чтобы файл открылся на компе. На high poly работают с квадратами вместо треугольников, а от угловатостей избавляются при помощи сглаживания.

**Софт:**
* Большая часть High Poly делается в **Blender** при помощи сабдивов и фасок.
* Для создания геометрически сложных объектов можно использовать **Plasticity**. Однако стоит помнить, что после этого софта сетку нужно будет ретопить в Blender или Zbrush.
* Мелкая детализация (сколы, царапины, повреждения), сварные швы, частные случаи фасок - **ZBrush**.

ZBrush воспринимает только триангулированную сетку. Перед экспортом в ZBrush обязательно триангулировать сетку (н.п. накинуть модификатор Triangulate).

**Перед экспортом в любую программу нужно триангулировать ВСЕГДА (вручную, Ctrl + T, модификаторы).**

<a name="lods"></a>
## 4. LODs



<a name="unwrap"></a>
## 5. Unwrap & Pack

<a name="bake"></a>
## 6. Bake

<a name="texturing"></a>
## 7. Texturing

Требования к разрешению и формату экспортируемых текстур

<a name="enginesetup"></a>
## 8. Engine Setup

