# Microservices-Diagram

API - Общий протокол общений для выставленного ТЗ в ДЗ
Оркестратор - сервис управления рабочими процессами. Обладает внутренним сервисом для дополнительной логики
    Имеет кеш для быстрого доступа к нужным данным. Кеш объединен с сервисом Game Process
Game Process - игровая лгогика (Сервис абстрактный, сервисов может быть болльше)
auth/reg - авторизация/утентификация/регистрация. Имеет свою бд
Game data - Данные игры. Сохраняется в БД и дублируется в кеше.

Самый частый компонент, к которому будут меняться требования:
Game Process не определен с точным количеством логики и возможностью вынесению в отдельные микросервисы, дополнительные модули(кеш, бд, брокер) могут доопределиться. 
Game data - требования к бд будут меняться постоянно с появлением новых процессов. 

Узкие места и потенциальные проблемы масштабирования приложения и способы их решения:
Узкие местаа в онлайн игре это взаимодействие между сервисами. Микросервисы общаются по сети по сравнению с монолитом, где все итдет в коде.
Может быть потребует разделение на новые микросервисы с разными бд и/или общим кешем
Может потребется распределенные бд с отдельным оркестратором для связывания.






