# Studuing-rob
###### <a href="https://moscityhack2022.innoagency.ru/">MoscowCityHack-22</a>
10-06-22 --> 13-06-22

ЗАДАЧА. ОПИСАНИЕ ЗАДАЧИ
-----
Студентам часто сложно сохранять мотивацию во время обучения. 
Одна из причин — они не успевают отрефлексировать пройденный материал, тем самым теряют из фокуса цель обучения, и, как следствие, бросают курс.

Разработайте помощника в обучении — чат-бота, который бы помогал студентам рефлексировать пройденный материал, 
держать в фокусе их цель обучения и ее достижение.


НАЗНАЧЕНИЕ РАЗРАБОТКИ
----
 <li>
  I.Рефлексия:
  <ul>I.1 Что студент прошёл</ul>
  <ul>I.2 Каков текущий прогресс</ul>
  <ul>I.3 Сменилась цель?</ul>
 </li>

  <li>
  II. Целеполагание:
  <ul>II.1 напоминает о цели</ul>
  <ul>II.2 спрашивает о перемене цели: не сменилась ли она?</ul>

 <li>
  III. Анкетирует студента:
  <ul>III.1 Помогает ли бот в обучении?</ul>
  <ul>III.2 Собирает данные об эффективности образования на Платформе</ul>
 </li>


 ЦЕННЫЙ ПРОДУКТ
 -----
 PRIMARY DATA: получатель ЦП: Платформа

 ПОЛЬЗОВАТЕЛЬ БОТА
 -----
 Клиент Платформы, проходящий обучение на ней.
 
 
 СУЩНОСТИ СИСТЕМЫ
 ----
 Бот (id)
 Студент (клиент) "Нетологии", проходящий обучающую программу. (id_tg)
 Обучающая программа
 
 
 ФУНКЦИОНАЛ СИСТЕМЫ
 -----
 ##### функц-е
 
 <table>
  <tr>
   <td>направление</td>
   <td>user case</td> 
  </tr>
  <tr>
  <td>I. Рефлексия</td>
   <td>
    I.1 Что студент прошёл? (реквест на саммари по изученному) //определить периоды отслеживания<br>
    I.2 Предоставляет данные о том, каков текущий прогресс (дашборд в чат) // инструмент для дашборда/ атрибуты - вельюсы
   </td>
   <tr>
    <td>
     II. Целеполагание: трекает прогресс по достижению цели обучения/ трекает статус цели
     <td>
     II.1 напоминает о цели (уведомление с отчетом о прогрессе (визуализация данных + детальная статистика))<br>
     II.2 спрашивает о перемене цели: не сменилась ли она? (серверное событие. по расписанию и/или триггеру (нет активности в курсе или активность снизилась). Бот отправляет в чат вопрос о статусе цели. data --> bd)
     </td>
   </tr>
  <tr>
   <td>
     III. Опрашивает студента
   </td> 
   <td>
     III.1 Помогает ли бот в обучении? (серверное событие: по расписанию и/или триггеру. Бот отправляет в чат вопрос об эффек-ти бота. data --> bd)<br>
     III.2 Собирает данные об эффективности образования на Платформе. (серверное событие: по расписанию и/или триггеру. Бот отправляет в чат вопрос об эффек-ти обрават-й программы. data --> bd)
  </td> 
 </tr>
 </table>
 

 
   
  

  
  

  
  
 
 
 ##### нефункц-е

 
  ##### предполагаемый поток событий. основные точки касания. 
 <a href = "https://www.figma.com/file/2SGijjRWQudLG0JT8ASlrd/%D1%81%D1%85%D0%B5%D0%BC%D0%BA%D0%B8.-%D0%B1%D0%BE%D1%82%D0%B0-%D1%82%D1%80%D0%B5%D0%BA%D0%B5%D1%80%D0%B0-%D0%BE%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D1%8F.-%D1%85%D0%B0%D0%BA.?node-id=0%3A1">user flow</a>
  
  
  
ДОП. ТРЕБОВАНИЯ/ ЗАМЕЧАНИЯ ОРГАНИЗАТОРОВ
-----
<li>
 Интеграции
 <ul>Нетология-бот: 👎</ul>
</li>
<li>
 Логика
 <ul>Залить на сервер: 👎</ul>
</li>
<li>
 Датасеты
 <ul>организаторы предоставят предобработанные данные</ul>
</li>

СТЕК
-----
- Бот:Telebot/ IOgram/ other
- АД: Python/ R
- СУБД: SQLite
- Слайды: Figma
- Брокер сообщений: RabbitMQ/ Reddit/ other

OUR TEAM
----

<table>
 <tr>
  <td>NAME</td>
  <td>ROLE</td>
 </tr>
 <tr>
  <td>SABINA</td>
  <td>CONTENT STRATEGIST| UX ANALYST</td>
 </tr> 
 <tr>
  <td>VALERIA</td>
  <td>DESIGNER</td>
 </tr>  
 <tr>
  <td>JULIAN</td>
  <td>PYTHON BACKEND DEV</td>
 </tr>
 <tr>
  <td>JAVA BACKEND DEV</td>
  <td>ALEXANDER</td>
 </tr>
 <tr>
  <td>KARINA</td>
  <td>TEAM LEAD & BI SA DA</td>
 </tr>
<table>


CORE-CONCEPT OUR CREW
-----
 
 

ВОПРОСЫ
-----
1. каково поведение бота, если обуч.программа постановлена на паузу или завершена студентом?
2. каково поведение бота, если студент одновременно проходит >1 программы? (предусмотреть переключение в меню бота между программами
3. в разрезе какого периода(-ов) запрашивать отчет об усвоенных навыках?
4. каковы критерии, характеризующие прогресс обучения? 
  4.1 можем ли мы сами их определить или уже есть перечень критериев?
5. данные о прогрессе в обучении на Платформе можно ли звпросить сводку о завершенных студентом программах?
 
 
 возможные статусы цели обучения = {current, change --> реквест на new status + add record in db}
