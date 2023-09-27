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
S1 — Блокирующая (Blocker)  | Приложение не запускается ни на одном устройстве или выдаёт ошибку при загрузке.   *Пример: приложение не открывается, поэтому невозможно сделать покупку*.  
S2 — Критическая (Critical) | Часть функционала не работает, но это не блокирует процесс. *Пример: Скидка по купону не работает, но товар всё равно можно купить без скидки*.  
