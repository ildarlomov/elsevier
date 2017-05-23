# ElsevierAPI 
Программа для взаимодействия с API  Elsevier

Всего доступно 3 функции у класса ElsevierAPI

1)search_by_words(['algorithm', 'boolean'], 'keywords')
Производит поиск по полнотекстовым документа с заданным запросом (словами, которые указаны первым аргументом)
Опции:
keywords - поиск по ключевым словам автора
abstract - поиск в аннотации
all - по всему документу
Результаты, для которых доступен текст, скачиваются в таблицу text_articles
(для них есть вся необходимая инфа, включая scopus-ссылку)
Остальные, в базу meta_articles. Здесь будет очень ограниченное количество информации, но достаточное чтобы найти и купить статью

2)download_subject(subj)
Функция запускает загрузку сожержимого по subj в базу из Science Direct

3)a.get_references(EID='1-s2.0-S0304397513001527', option='print')
Функция, которая скачивает references по EID ресурса. Данный идентификатор есть у всех материалов на Elsevier. Он также, досупен
в поиске и для не openaccess статей. Есть две опции 'print' и 'save'. Первая распечатывает результаты на экране в удобном виде. Вторая складывает результаты в MongoDB в виде EID:references. 
