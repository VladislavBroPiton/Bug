# Bug
Багом (от англ. bug) или дефектом часто называют ошибку в программном коде. Это не совсем ошибка, а скорее несоответствие фактического результата ожидаемому. То, как должна работать программа, описывают в требованиях к разработке. В идеальном мире она будет работать именно так, как её задумали заказчики. Но в реальности можно увидеть не то, что ожидалось.   
###  Виды багов  
**Визуальный**, относится к интерфейсу приложения. Кнопка «Купить» уехала за пределы экрана.   
**Функциональный**. Не сохраняются данные: пользователь нажимает кнопку «Купить», но ничего не происходит, или может применить одноразовый купон на скидку два раза.  
**Дефект UX**, влияет на удобство. Чтобы подтвердить мобильный телефон, пользователю приходится несколько раз покидать и возвращаться в мобильное приложение.   
**Баг нагрузки**. Интернет-магазин должен выдерживать большой наплыв посетителей, например в Чёрную пятницу, поэтому там часто проводят нагрузочное тестирование. Например, искусственно создают ситуацию, когда в один раздел одновременно зашло несколько тысяч пользователей. Если приложение не загружается или зависает — это баг нагрузки.    
**Баг производительности**. Приложение занимает в памяти смартфона слишком много места, работает медленно и быстро тратит заряд батареи.    
**Баг требований, или логический баг**. До начала разработки приложения или отдельной «фичи» в требованиях что-то не учли. Например, забыли добавить всплывающее оповещение, что при включённом VPN приложение может работать с ошибками. Программист запрограммировал так, как было в требованиях (или как он их понял). В итоге, приложение работает, как описано в требованиях, но не так, как нужно бизнесу.  
### Чем отличается приоритет от серьёзности и как их используют   
**Серьёзность** показывает, насколько баг влияет на возможность работать в программе. Обычно выделяют 5 уровней серьёзности бага. Самый опасный — блокирующий баг. Например, мобильное приложение перестало загружаться, и пользователь видит пустой экран. Самый безвредный — тривиальный баг. Он не влияет на работу приложения, а многие пользователи его даже не заметят. Это может быть, например, опечатка в разделе меню, куда редко заходят.   

Серьёзность бага | Как влияет на систему
:--------|---------:
S1 — Блокирующая (**Blocker**)  | Приложение не запускается ни на одном устройстве или выдаёт ошибку при загрузке.   *Пример: приложение не открывается, поэтому невозможно сделать покупку*.  
S2 — Критическая (**Critical**) | Часть функционала не работает, но это не блокирует процесс. *Пример: Скидка по купону не работает, но товар всё равно можно купить без скидки*.  
S3 — Значительная (**Major**)   | Часть логики работает некорректно, но пользователь может решить проблему другим способом. *Пример: поиск в приложении не выдаёт нужный товар, но его можно найти, если искать по брендам*.
S4 — Незначительная (**Minor**) | Не нарушает логику приложения. *Пример: кнопка «Купить» уехала за экран и видна только наполовину*.
S5 — Тривиальная (**Trivial**)  | Не относится к логике приложения и не влияет на общее качество продукта. *Пример: малозаметная опечатка в меню*.

**Приоритет** — это критерий, который показывает, насколько быстро нужно исправить дефект. С точки зрения функционала баг может быть несерьёзный и некритичный, но при этом важный для бизнеса. Обычно выделяют три приоритета:  
- высокий — исправить в первую очередь  
- средний — исправить, когда разобрались с первой категорией багов   
- низкий — исправить, когда разобрались с багами других приоритетов   

**Если баг имеет большое системное влияние, то мы пишем Siverity**  
**Если баг имеет большое бизнес влияние, то мы пишем Priority**  

У бага есть нулевая стадия, когда он, как кот Шрёдингера, может быть багом, а может — просто непониманием со стороны пользователя. Тестировщик сталкивается с чем-то непонятным в работе системы и начинает разбираться, что произошло. Это называется локализацией. Её цель — убедиться, что обнаружили именно дефект. Для этого тестировщик смотрит проектную документацию, ставит эксперименты и узнаёт, в каких ситуациях воспроизводится дефект и можно ли его как-то обойти.    
В результате локализации может быть два вывода:   
- Это не баг, или проблема не на стороне разработчиков. Например, внутренний пользователь чего-то не знает по системе и его нужно обучить. Или у пользователя приложения застряли деньги, а проблема на стороне банка.    
- Это баг программы, и его нужно завести в баг-трекинговой системе.   

В тестировании **баг-репорт** — это отчёт об ошибке, который заводится в баг-трекинговой системе.    

Шаблон баг‑репорта   

Поле | Что содержит
:-----|--------:
Заголовок | Суть проблемы. Должен быть ёмким и понятным.
Описание | Обычно дублирует заголовок, поэтому не всегда обязательно.
Шаги воспроизведения | Описание действий, которые нужно совершить, чтобы дойти до бага.
Фактический результат | Что видим после того, как воспроизвели баг.
Ожидаемый результат | Что на самом деле хотели увидеть, как это должно работать по ТЗ.
Окружение | Где нашли баг. Например, ОС, браузер или тестовая среда.
Вложения | Логи, скриншоты. 
Дополнительная информация | Например, пояснения от тестировщика: какие способы он ещё пробовал, чтобы воспроизвести баг, и что получилось.

**Заголовок**
 Информативный заголовок помогает понять суть проблемы, не читая весь баг-репорт. При этом он не должен быть слишком коротким или длинным.   

**Локализация** 
Найти баг для джуна — радость. Но важно убедиться, что это именно дефект, и понять, в чём он заключается. Иначе разработчикам придётся разбираться с проблемой, которая может быть не на их стороне.  

**Вложения** 
Если баг визуальный или UX (поехала вёрстка, не работает кнопка), то без скриншота или скринкаста не разобраться — важно показать, что видит пользователь. 

**Шаги воспроизведения** 
Бывает, что джун начинает издалека: «Включить компьютер». Или пишет слишком абстрактно: «Заходишь на страницу, товар не отображается». Важно искать золотую середину: описывать те шаги, которые относятся к багу, и так, чтобы другим коллегам было понятно. Например: нажать кнопку «Начать», сканировать любой товар из задачи.  

**Взгляд на проблему**  
Тестировщику важно хотя бы пытаться смотреть на проблему с точки зрения бизнеса. Например, текст не помещается в поле, а как этот баг влияет на бизнес? Ответ на вопрос поможет в будущем определять серьёзность и приоритет бага.  

**Фактический и ожидаемый результат**
То, как тестировщик заполнит эти поля, влияет на его коммуникацию по задаче с разработчиком. Если проблема описана непонятно, разработчик не сможет сразу за неё взяться, а будет уточнять детали у тестировщика. Например, придёт с вопросами, если увидит в документе, что фактический результат — кнопка не работает, а ожидаемый результат — кнопка работает.   

Самый полезный для тестировщика вопрос — «Что если?». На нём завязана вся локализация. Выдвигайте больше гипотез и проверяйте их с разных сторон.  У начинающих тестировщиков обычно фокус на деталях. Но чтобы прогрессировать, важно идти от частного к целому и видеть картину шире. При составлении баг-репорта подумайте, как дефект влияет на процессы, функциональность и удобство пользователя.  
### Пример
**Заголовок**: [Инвентаризация] В начатой задаче сканирование товара не записывается в задачу, в логах ошибка <Error…>.  
**Предусловия**: Приложение Инвентаризация запущено и активно, открыта невыполненная задача для инвентаризации.  
Шаги:  
1.  Нажать кнопку «Начать».  
2.  Сканировать любой товар из задачи.  
Фактический результат: при попытке сканирования товара сканер пищит (как и должен), но в задачу сканирование не записывается. В системных логах приложения ошибка <Error…> (приложен кусок лога с ошибкой). В серверных логах ошибка <Error…> (приложен кусок лога с ошибкой).  
