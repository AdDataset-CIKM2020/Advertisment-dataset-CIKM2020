# Advertisment-dataset-CIKM2020
Link to download dataset: https://mega.nz/folder/X8AVUADL#MicodbojCW4lsMsfmD7jnQ

# English readme
Data structure:

```
Number of field	Name of field		Number of nonzero records (test)	Type
0   	        original_id       	277493 (76707)  			int64 
1   	        id1               	277493 (76707)  			int64 
2   	        processed_banner  	277493 (76707)  			str
3   	        processed_site    	277493 (76707)  			str
4   	        title             	275284 (75591)  			str
5   	        url               	277493 (76707)  			str
```

1. original_id - is not unique, it combines examples related to one site (in this case processed_site under one original_id can be repeated, and processed_banner differ significantly).
2. id1 - unique record index
3. processed_banner - processed advertising text
4. processed_site - processed text of the product web page
5. title - raw text of the product web page title
6. url - link to the site from which processed_site and title were obtained

The following text processing was applied:

1. The headers and footers of the html were removed [processed_site]

2. The menu item, site management item [processed_site] were removed

3. Items that the user cannot see were removed: those with the hidden tag, and those that are overlapped by other items [processed_site]

4. All numbers have been replaced by the NUM tag

5. Symbols "\n\t" have been replaced with spaces

6. The symbols "?!" have been replaced by " . "

7. All other non-alphabetic characters have been removed

8. All characters of non-Russian alphabet were deleted (to remove html tags, hidden characters)

9. The texts are in lower case

10. Repeating tokens in a row have been replaced by one with the help of regular expression: 

    ```python
    r"(\b[\w+\s]{1,}?\b[\s\.]+)(\1+)"
    ```

# Russian readme
Структура данных:

```
Номер поля	Название поля		Число не нулл записей (test)	Тип
0   		original_id       	277493 (76707)  				int64 
1   		id1               	277493 (76707)  				int64 
2   		processed_banner  	277493 (76707)  				str
3   		processed_site    	277493 (76707)  				str
4   		title             	275284 (75591)  				str
5   		url               	277493 (76707)  				str
```

1. original_id - не уникален, объединяет примеры, относящиеся к одному сайту (при этом processed_site под одним original_id могут повторяться, а processed_banner отличаются значительно)
2. id1 - уникальный индекс записи
3. processed_banner - обработанный рекламный текст
4. processed_site - обработанный текст веб-страницы товара
5. title - необработанный текст заголовка веб-страницы товара
6. url - ссылка на сайт, с которого получен processed_site и title

Применялась следующая обработка текста:

1. Были удалены headers и footers html-разметки [processed_site]

2. Были удалены элемент меню, управления сайта [processed_site]

3. Были удалены элементы, которые пользователь не может увидеть: с тегом hidden, а также те, которые перекрываются другими элементами [processed_site]

4. Все числа заменены на тег NUM

5. Символы "\n\t" были заменены на пробелы

6. Символы "?!." были заменены на " . "

7. Все остальные неалфавитные символы были удалены

8. Все символы не русского алфавита были удалены (для удаления html-разметки, скрытых символов)

9. Тексты приведены к нижнему регистру

10. Повторяющиеся подряд токены были заменены на один с помощью: 

    ```python
    r"(\b[\w+\s]{1,}?\b[\s\.]+)(\1+)"
    ```

