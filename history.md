*Aleks Mayer, [19.07.16 13:41]*
Коллеги, а как называлась тулза, которая позволяла постоянно опрашивать файл и выводить его содержимое на экран? Не tail

*Aleks Mayer, [19.07.16 13:41]*
Мне надо /proc/mdstat опрашивать каждые 3 секунды

*Phil Kulin, [19.07.16 13:41]*
однострочник на шелле?

*Алексей Широких, [19.07.16 13:44]*
watch

*Алексей Широких, [19.07.16 13:45]*
watch -n3 cat /proc/mdstat

*Aleks Mayer, [19.07.16 13:46]*
Да, watch. Только на диске убунты его нет. :(

*Алексей Широких, [19.07.16 13:48]*
страдай стардашку

*Daniel Podolsky, [19.07.16 13:49]*
while sleep 3; do cat /proc/mdstat; done

*Алексей Широких, [19.07.16 13:49]*
*[In reply to Daniel Podolsky]*
никарсиво

*Aleks Mayer, [19.07.16 13:53]*
*[In reply to Daniel Podolsky]*
спасибо

*Aleks Mayer, [19.07.16 13:54]*
*[In reply to Алексей Широких]*
Да пофигу, главное что работает.

*Alexey Mochkin, [19.07.16 14:17]*
*[In reply to Daniel Podolsky]*
тут задумался и наваял на bash'е простенькую реализацию watch'а
http://pastebin.com/5Yz8xzzi

*Alexey Mochkin, [19.07.16 14:18]*
работает и даже экран не засирает

*Alexey Mochkin, [19.07.16 14:19]*
^_^

*Алексей Широких, [19.07.16 14:28]*
ух

*Алексей Широких, [19.07.16 14:28]*
а можешь еще ключ -d сделать :) ?

*Alexey Mochkin, [19.07.16 14:28]*
будешь моей реализацией полльзоваться?)

*Алексей Широких, [19.07.16 14:28]*
:)

*Алексей Широких, [19.07.16 14:28]*
нет

*Алексей Широких, [19.07.16 14:29]*
ну раз пошла такая пьянка :)

*Alexey Mochkin, [19.07.16 14:30]*
*[In reply to Алексей Широких]*
мне на работе иногда и работать надо, а не только переписывать системные тулзы на bash'е 😉

*Алексей Широких, [19.07.16 14:30]*
да понятно :)

*Алексей Широких, [19.07.16 14:30]*
ну раз взялся то :)

*Алексей Широких, [19.07.16 14:30]*
там смысл всего watch как бы именно в -d

*Alexey Mochkin, [19.07.16 14:31]*
у? я такой ключ-то первый раз вижу

*Alexey Mochkin, [19.07.16 14:31]*
а для тебя он смысл...

*Alexey Mochkin, [19.07.16 14:32]*
ну лан не первый, но всё же я не часто его использую

*Алексей Широких, [19.07.16 14:32]*
я переодически пользуюсь да

*Алексей Широких, [19.07.16 14:33]*
с watch -n 60 тогад поглядываешь на вывод и понятно где изменилось

*Alexey Mochkin, [19.07.16 19:00]*
*[In reply to Алексей Широких]*
http://pastebin.com/LLky7AEk

Тут уже и красота наведена. Нна сколько смог проверить скрипт всеядный, норм ест и команд со встроенными опциями и pipeline'ы внутри команд.
asis как обычно 😉

*Алексей Широких, [19.07.16 19:02]*
*[In reply to Alexey Mochkin]*
гимн этому городу.

*Алексей Широких, [19.07.16 19:02]*
спасибо.

*Karter, [19.07.16 19:02]*
*[In reply to Alexey Mochkin]*
А начиналось с 10 строк.

*Karter, [19.07.16 19:02]*
14.

*Alexey Mochkin, [19.07.16 19:02]*
гыгы)

*Alexey Mochkin, [19.07.16 19:03]*
ну парсинг и проверка опций место занимают, ну и посимвольное сравнение для diff'а тоже не однострочное

*Karter, [19.07.16 19:03]*
*[In reply to Alexey Mochkin]*
Выкладывай на гитхаб, будем коммитать. )