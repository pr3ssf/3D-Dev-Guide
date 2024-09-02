<a name="top"></a>
# 3D-Dev-Guide

Эта статья описывает правила и порядок 3D разработки, который нужно соблюдать.

<a name="top"></a>
## Структура пайплайна

> 1. [Reference Board](#reference)
> 2. [Druft / Blocking](#druft)
> 3. [High Poly](#hp)
> 4. [LODs](#lods)
> 5. [Unwrap & Pack](#unwrap)
> 6. [Bake](#bake)
> 7. [Texturing](#texturing)
> 8. [Engine Setup](#enginesetup)

## Техническая информация

> 9. [Требования к моделям](#models)
> 10. [Используемый софт](#software)
> 11. [Правила оформления сцен](#scene-rules)
> 12. [Структура текстурных карт](#texturemaps)
> 13. [Организация рабочей директории](#hierarchy)

## Терминология и обозначения

**_hp_** - High Poly - высокодетализированная модель.  
**_lp_** - Low Poly - оптимизированная модель, подготовленная для загрузки в движок.  


<a name="reference"></a>
## 1. Reference Board

Для сбора и композиции референсов используется программа [PureRef](#software).

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

**[⬆ _К содержанию_](#top)**

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

На блокинг средней модели у тебя должно уходить **не более 40 минут**. Если ты тратишь больше 40 минут, то, скорее всего, ты потратил кучу времени на вещи, не влияющие на силуэт — то-есть не справился с этим этапом.

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

<a name="druft-texture"></a>
### 2.4 Материалы и текстурные сеты

Уже с этого этапа важно понимать сколько будет материалов, на каких частях модели они будут находиться, и готовить почву для соблюдения правила: **Один материал - находится в одном текстурном сете**. Это предотвращяет двойную работу по редактированию одинакового материала в нескольких текстурных сетах. 

**[⬆ _К содержанию_](#top)**

<a name="hp"></a>
## 3. High Poly

High poly — это детализированная модель без ограничений по полигонам. Такие модели делают концепторы, а в видеоиграх они нужны для запечки нормала.

На high poly можно всё, потому что нет ограничений по полигонам. Главное ограничение — чтобы файл открылся на компе. На high poly работают с квадратами вместо треугольников, а от угловатостей избавляются при помощи сглаживания.

**Софт:**
* Большая часть High Poly делается в [Blender](#software) при помощи сабдивов и фасок.
* Для создания геометрически сложных объектов можно использовать [Plasticity](#software). Однако стоит помнить, что после этого софта сетку нужно будет ретопить в Blender или Zbrush.
* Мелкая детализация (сколы, царапины, повреждения), сварные швы, частные случаи фасок - [ZBrush](#software).

ZBrush воспринимает только триангулированную сетку. Перед экспортом в ZBrush обязательно триангулировать сетку (н.п. накинуть модификатор `Triangulate`).

Плавные переходы и изгибы геометрии нуждаются в отдельном внимании. В частных случаях нужно накинуть сабдив или поддерживающие ребра. Артефакты High Poly переносятся на Low Poly при запекании.

**Перед экспортом в любую программу нужно триангулировать ВСЕГДА (вручную, Ctrl + T, модификаторы).**

**[⬆ _К содержанию_](#top)**

<a name="lods"></a>
## 4. LODs

**LOD** – Level Of Details. Уровень детализации модели. Принцип построения нескольких вариантов одного объекта с разной степенью проработки, для уменьшения нагрузки на видеокарту.

В большинстве случаев используются 3-4 уровня детализации:
> LOD1 - 100% tris  
> LOD2 - LOD1*_0.3~0.5_ tris  
> LOD3 - LOD2*_0.3~0.5_ tris  
> Culling  

Для обычных моделей окружения лоды создаются правилу: Все LOD'ы должны работать с одним начальным текстурным сетомю.
В частных случаях для всех или некторых LOD'ов отдельно делается индивидуальный Unwrap и Pack и соответственно индивидуальный текстурный сет/сеты.

**Пункты, о которых стоит помнить:**

> * На ребрах больших / главных мидполи моделях или моделях без LOD системы, которые не будут использоваться на сцене в большом количестве для лучшего вида можно применять **двойные фаски** (чтобы углы модели были не более 45 градусов)
> * Если планируется плотное взаимодействе модели и физики, то следует сделать коллайдер и примитивов - в боьлшистве случаев подойдет очень примерное повторение форм объекта.
> * Если у объекта есть движущиеся части, то их Pivot Point должен быть выставлен в их центр, и нужно привязать их к родительскому объекту.

Если после создания LOD'ов модели они должны пройти стадиб проверки, то на проверку уходит модель **без триангуляции** и эта же модель, но уже **триангулированая**.

Модели триангулируются **ВРУЧНУЮ**.

[Нагляднее про LOD](https://dzen.ru/a/YSSl6QGHHAZ8YaAs)  
[Статья про LOD](https://cgitems.ru/articles/chto-takoe-lody-i-lodirovanie-v-igrakh-kak-nastroit-lody-lods/)

**[⬆ _К содержанию_](#top)**

<a name="unwrap"></a>
## 5. Unwrap & Pack

> 5.1 [Правила развертки](#unwrap-unwrap)  
> 5.2 [Правила упаковки](#unwrap-pack)  

Легче всего проставить начаальные швы и проверить грубый анврап в Blender или рабочем софте. Кроме этапа первичной расстановки швов остальная работа выполняется в программе [RizomUV VS](#).

<a name="unwrap-unwrap"></a>
### 5.1 Правила развертки

> 1. Трингуляция перед экспортом в [RizomUV VS](#software).
> 2. Соблюдать правило: **Hard Edge = Cut, Cut = Hard Edge**.
> 3. Непропорционально длинные или вытянутые полигоны требуют либо поддерживающих ребер, либо ручного редактирования
> 4. Тангент UV-шеллов находится в серой зоне.
> 5. Все UV-шеллы одного масштаба (нет непропорционально огромных участков). Если не получается соблюсти этот пункт - добавить новые швы или эджи в редакторе.

<a name="unwrap-pack"></a>
### 5.2 Правила упаковки

> 1. UV-шеллы деталей и частей объекта по возможности пакуются в одну область UV-пространства. _Пример: при упаковке модели молотка UV-шеллы железной и деревянной части будут сгруппированны поотдельности в разных частях UV-пространства для удобства редактирования и поиска отдельных UV-шеллов._ 
> 2. UV-шеллы одного объекта располагать параллельно друг другу вертикально или горизонтально для возможности использования **НЕ** tri-planar проецирования или наложения тайловой текстуры. Направление выбирать от типа текстуры, которая будет расположена на этой геометрии.
> 3. При использовании оверлапов все UV-шеллы, кроме оригинального, переносятся на 1 udim вправо. По итогу все оверлапнутые UV-шеллы должны переместиться на правое UV-поле **КРОМЕ НИЖНЕГО**, а на основном UV-поле должна остаться вся развертка без оверлапов. При надобности после запекания развертку можно вернуть в исходное состояние.

[Официальный канал RizomUV](https://www.youtube.com/@RizomUV)  
[Статья про развертку от XYZ](https://www.school-xyz.com/blog/uv-razvyortka-aaa-pajplajn-47-samyj-polnyj-gajd)

**[⬆ _К содержанию_](#top)**

<a name="bake"></a>
## 6. Bake

> 6.1 [Подготовка модели к запеканию](#bake-prepare)  
> 6.2 [Правила запекания](#bake-process)  
> 6.3 [Настройки итогового запекания для URP](#bake-settings)  

Текстурные карты Normal и Ambient Occlusion запекаются в [Marmoset Toolbag](#software). Остальные карты можно также запечь в Marmoset Toolbag или перед текстурированием в [Adobe Substance Painter](#software).
Для перехода на этап запекания важно удостовериться, что этап развертки выполнен полностью и без ошибок.

<a name="bake-prepare"></a>
### 6.1 Подготовка модели к запеканию

> 1. _High Poly_ лучше делать чуть больше _Low Poly_.
> 2. Все _hp_ и _lp_ должны быть расположены в одном месте относительно друг друга.
> 3. У всех мешей Pivot Point должен располагаться в центре координат: `A (select all)` -> `Ctrl + A` -> `Apply All Transforms`.
> 4. При запекании нескольких текстурных сетов на **каждый** LP объект должен быть назначен один **униальный материал**.
> 5. Для запекания `Material ID` на все хп меши должны быть назначены уникальные материалы.
> 6. **Преимущественно для цилиндрических объектов** - для корректного запекания Normal Map лучше добавлять поддерживающие ребра в местах запекания Normal _(эта геометрия убирается после запекания)_. Если этого не сделать - нужно будет рисовать `Skews` или карты поплывут.
> 7. Нейминг High Poly мешей - `_high`, Low Poly мешей - `_low`, Флоатеров - `_high_fl(N)`, где `N` - порядковый номер флоатера.
> 8. Для соблюдения правильности нейминга и легкого переноса lp и hp мешей с флоатерами рекомендуется использовать мост [BTBridge](https://www.youtube.com/watch?v=sSfoNy6bNdA).
> 9. **Опционально:** сделать explode модели - разместить части Low Poly модели на расстоянии друг от друга, для облегчения их редактирования в Marmoset. После explode модели рекомендуется скопировать Low Poly моделить через `instance` и собрать модель в единое целое, это поможет избежать двойной работы по сборке explode модели при изменении ее геометрии во время ее возможного редактирования.
> 10. Триангуляция вручную или модификатором `Triangulate`.
> 11. _**Если не используется BTBridge (устарело):**_ Из софта экспортятся два файла - основная лп+хп модель и флоатеры.

<a name="bake-process"></a>
### 6.2 Правила запекания

> 1. Настроить `Cage Offset` на лп мешах.
> 2. Настроить `Skews`. _Tip: можно включить отображение только хп, лкм на лп в иерархии и настраивать Skews только по хп._
> 3. Для использования скрытых объектов в запекании `Geometry` - `Use Hidden Meshes`
> 4. `Geometry` - `Tangent Orientation`: `Right-Handed` - OpenGL, `Left-Handed` - DirectX
> 5. _**(Устаревшее, см. след)**_ Импорт основных моделей через `Quick Loader`- `Auto-Reload` (при использовании функционала `Quick Loader` все группы High и Low сбрасываются до исходных), флоатеры импортятся отдельным файлом и добавляются в папку **_High_** меша, к которому относятся. Лучше после импорта _флоатеров_ переносить их меши в папку Hight, а сам объект оставлять в общей иерархии, чтобы можно было его Reload-нуть из его настроек.
> 6. С испрользованием **BTBridge**: При изменении объектов в **Blender** и экспорте в **Marmoset** через **BTBridge** `Quick Loader` подгрузит изменения только изначально добавленных мешей, новые созданные меши или меши с измененным именем добавлены не будут. Если в **Blender** было изменено кол-во объектов или их нейминг, то легче создать новую сцену **Marmoset** через меню аддона.
> 7. После запекания `P` для подтягивания текстурных карт в слоты.
> 8. При запекании нескольких текстурных сетов: `Texture Sets` - `Multiple Texture Sets`.
> 9. При работе с моделями, которые будут располагаться только в одном вертикальном положении (архитектура, стационарные объекты): `Maps` - `AO` - `Floor Occlusion` - добавляет затенение AO в нижней части меша.
> 10. Чтобы при запекании AO все объекты двали затенение друг на друга `Maps` - `AO` - `Ignore Groups`.
> 11. `Maps` - `AO` - `Two-Sided`: пустые места на Ambient будут закрашиваться черным цветом, т.е. места, где хп отсутствует, AO будет черная.

<a name="bake-settings"></a>
### 6.3 Настройки итогового запекания для URP

> 1. `Tangent Orientation`: Right-Handed
> 2. `Samples`: x64
> 3. `Format`: 8bit/Channel
> 4. `Texture Sets` - `Master`: 8192 x 8192
> 5. `AO` - `Ray Count`: 4096

**[⬆ _К содержанию_](#top)**

<a name="texturing"></a>
## 7. Texturing

Нетайловое текстурирование происходит в программе [Adobe Substance Painter](#software) в пайплайне MetallicRoughness.

**Параметры экспорта:**

> 1. **Output Template:** SpecularGlossiness
> 2. **File Type:** PNG 8bit
> 3. **Size:** 4096
> 4. **Padding:** Dilation Infinite

**Текстурные карты:**

> 1. `Normal` - `_N`
> 2. `Ambient Occlusion` - `_AO`
> 3. `Height` - `_H`
> 4. `SpecularGlossiness` - `_SG`
> 5. `AlbedoTransparency` - `_D`
> 6. `EmissionGrayscale` - `_E`

![image](https://github.com/user-attachments/assets/33c370cf-f1ee-4f44-bf2c-e57e6b942e96)

**[⬆ _К содержанию_](#top)**

<a name="enginesetup"></a>
## 8. Engine Setup

> 1. В проекте для объекта создается папка.
> 2. В папку импортируется fbx файл, который содержит в себе LOD0..LOD(N) и коллайдер (при наличии).
> 3. В этой же папке создаются папки _Materials_ и _TS_(Имя Объекта)_.
> 4. В папке _Materials_ создаются материалы для модели - по материалу на каждый текстурный сет.
> 5. В параметре `Surface Options` - `Workflow Mode` выставляется значение `Specular`.
> 6. В слоты текстурных карт материалов переносятся раннее импортированные текстурные карты объектов.
> 7. В настройках `Inspector` - `Materials` выставить параметр `Material Creation Mode` - `Standart (Legacy)`.
> 8. В слоты материалов, расположенные ниже, переносятся настроенные ранее материалы.
> 9. Если модель будет использоваться как Static и в ее UV-сетах не развернута Lightmap, то нужно активировать параметр `Inspector` - `Model` - `Generate Lightmap UVs`.
> 10. Перенести модель на сцену `Assets` для настройки.
> 11. В иерархии выделить объекть `ПКМ` - `Prefab` - `Unpack`.
> 12. Из объекта удаляется Collider (при наличии).
> 13. На LOD0 объекта добавляется компонент `Mesh Collider` и в него перетаскивается Collider (с синим значком сетки) из иерархии проекта из импортированного в начале fbx файла (его можно развернуть).
> 14. На главном объекте настраивается компонент `LOD Group`.
> 15. После окончания настройки выделить главный объект и перетащить его в файлы проекта, чтобы префаб запаковался.

**[⬆ _К содержанию_](#top)**

<a name="models"></a>
## 9. Требования к моделям

### UAV / FPV Drone

> 1. На модель создается два LOD'а и два текстурных сета - по одному на каждый LOD.
> 2. LOD0 - Высокодетализированная модель для показа в гараже до 40k tris с одним текстурным сетом в разрешении 4k без использования оверлапов на видных местах.
> 3. LOD1 - Высокооптимизированная модель для использования в активном игровом процессе до 10k tris с одним текстурным сетом в разрешении 1k с использованием оверлапов.
> 4. Коллайдер создается и назначется только для LOD0.

### Архитектура

> 1. Texture Sets: 1-2 - Trim Sheet - Atlas
> 2. Textures Export Resolution: 4k.
> 3. Texel Density: 1.5-5 px/cm.
> 4. Tris Count: <10k.
> 5. LOD: LOD0, LOD1, LOD2.

### Пропсы

> 1. Texture Sets: Trim Sheet - Atlas.
> 2. Textures Export Resolution: 4k.
> 3. Texel Density: 1.5-3 px/cm.
> 4. Tris Count: <500.
> 5. LOD: LOD0, LOD1 - Sprite

**[⬆ _К содержанию_](#top)**

<a name="software"></a>
## 10. Используемый софт

> * [_**Blender 4.2**_](https://www.blender.org/) - Моделинг, развертка, тайловое текстурирование, рендер.
> * [_**Marmoset Toolbag 4**_](https://marmoset.co/) - Запекание текстурных карт, рендер.
> * [_**RizomUV VS RS 2024.0**_](https://www.rizom-lab.com/) - Развертка и упаковка Single и TrimSheet UV.
> * [_**ZBrush 2023.2.2**_](https://www.maxon.net/en/zbrush) - Скульпт, детализация, ретопология.
> * [_**Plasticity 2024**_](https://www.plasticity.xyz/) - Hard Surface моделирование.
> * [**_Unity 6_**](https://unity.com/releases/unity-6) - Движок проекта.
> * [_**Weeek**_](https://weeek.net/ru) - Таск менеджер.
> * [**_PureRef 2_**](https://www.pureref.com/download.php) - Создание рефборда.
> * [_**Adobe Substance Painter 10.0.0**_](https://www.adobe.com/products/substance3d/apps/painter.html) - Тестурирование, композитинг текстурных карт.
> * [_**Adobe Substance Designer 13.1.2**_](https://www.adobe.com/ru/products/substance3d-designer.html) - Создание тайловых текстур.
> * [_**Adobe Photoshop 2024**_](https://www.adobe.com/products/photoshop.html) - Создание, редактирование и композитинг текстурных карт.
> * [_**Adobe Illustrator 2024**_](https://www.adobe.com/products/illustrator.html) - Векторная графика, зарисовки, создание атласов и Trim Sheet темплейтов. 
> * [_**Adobe Premiere Pro 2024**_](https://www.adobe.com/products/premiere.html) - Видео композитинг.
> * [_**Adobe After Effects 2024**_](https://www.adobe.com/products/aftereffects.html) - Анимация.

**[⬆ _К содержанию_](#top)**

<a name="scene-rules"></a>
## 11. Правила оформления сцен

Объект - любой компонент в используемом софте, у которого возможно изменить имя.

### Общие правила:

> 1. В именах объектов используются только буквы _**латинского алфавита**_.
> 2. В именовании объектов не используется транслит: **НЕПРАВИЛЬНО** - `Derevo`, **ПРАВИЛЬНО** - `Tree`.
> 3. Для разделения частей имени объекта используется нижнее подчеркивание `_`: `Tree_Oak_Small`.
> 4. Важно держать иерархию проекта в порядке: используйте папки, разделение по цветам, инстансирование.
> 5. Важно следить за оптимизацией проектов.

### Blender:

> 1. Объект в сцене расположен в центре координат.
> 2. Pivot Point (Origin) объекта совпадает с центром координат.
> 3. Направление объекта совпадает с видами (front, left, right, back, bottom)
> 4. Обекты в иерархии должны быть логически распределены по папкам и иметь понятный нейминг.
> 5. На сцене не должно быть мусорных объектов.

### Substance Painter:

> 1. Распределять слои по логическим папкам
> 2. Использовать цвета папок для разграничения пространства иерархии слоев.
> 3. Где возможно использовать `Instanced` слои.

**[⬆ _К содержанию_](#top)**

<a name="texturemaps"></a>
## 12. Структура текстурных карт

> * **MetallicSmoothness:** RGB - Metallic, Alpha - Gloss
> * **SpecularGlossiness:** RGB - Specular (generated), Alpha - Gloss
> * **MaskMap (TerrainLayers):** Red - Metallic, Green - AmbientOcclusion, Blue - Height, Alpha - Gloss
> * **MaskMap (HDRP):** Red - Roughness, Green - Metallic, Blue - AmbientOcclusion, Alpha - Height

**[⬆ _К содержанию_](#top)**

<a name="hierarchy"></a>
## 13. Организация рабочей директории

Для каждой модели или подпроекта создается своя папка с ресурсными файлами.

Обозначения папок с ресурсными файлами:
> 1. _**ae**_ - After Effects projects and source files.
> 2. **_ai_** - Illustrator projects and source files.
> 3. **_fbx_** - Mesh Files.
> 4. **_pr_** - Premiere Pro projects and source files.
> 5. **_ps_** - Photoshop files.
> 6. **_ref_** - PureRef board and other references.
> 7. **_scene_** - Blender scenes.
> 8. **_sd_** - Substance Designer scenes and source files.
> 9. **_sp_** - Substance Painter scenes and source files.
> 10. **_tb_** - Marmoset Toolbag scenes and source files.
> 11. **_temp_** - Temporary files.
> 12. **_tex_** - Textures.
> 13. **_zbr_** - ZBrush scenes and source files.

**[⬆ _К содержанию_](#top)**
