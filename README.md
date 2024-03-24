# TMDB API

## Основные скрипты

### hello_api_tmdb
#### Описание
Используется для тестирования доступа к базе данных TMDB.

#### Запуск скрипта
```python
python3 hello_api_TMBD.py
```
После запуска скрипт предложит ввести ключ API.
*Внимание!* При вводе ключа API символы не отображаются!

Успешный запуск:
```python
>>> python3 hello_api_TMDB.py                                                 
Enter your api key v3:                                                                                                           
4000000
```

#### Получение ключа API
Ключ API можно получить [здесь](https://www.themoviedb.org/settings/api).

### make_own_db
#### Описание
Выгружает из удалённой базы данных [TMDB](https://www.themoviedb.org/) ограниченное число фильмов (1000) и сохраняет их в локальный файл.

#### Запуск скрипта
```python
>>> python3 make_own_db.py
```

После запуска скрипт предложит ввести ключ API.
*Внимание!* При вводе ключа API символы не отображаются!

Успешный запуск:
```python
>>> python3 make_own_db.py
Enter your api key v3:
please, wait, this operation may take smth like 15-20 minutes
0.0 percent complete
10.0 percent complete
<...>
90.0 percent complete
```

#### Получение ключа API
Ключ API можно получить [здесь](https://www.themoviedb.org/settings/api). 

### search_in_db
#### Описание
Выдает отсортированный по алфавиту список названий найденных фильмов.

Просит пользователя ввести путь к базе данных, затем ключевое слово (фразу) из названия фильма, который хочет найти пользователь. Ищет без учёта регистра. 

#### Запуск скрипта
```python
>>> python3 search_in_db.py
```
#### Успешный запуск
```python
>>> python3 search_in_db.py
Enter path to DataBase:MyFilmDB.json
Enter film to search for:ari
Ariel
Pirates of the Caribbean: Dead Man's Chest
Pirates of the Caribbean: The Curse of the Black Pearl
```

### find_similar
#### Описание
Находит в базе данных и возвращает отсортированный по названию список фильмов, похожих на заданный пользователем фильм, по параметрам: принадлежность к коллекции, оригинальный язык фильма, бюджет, жанр. Просит пользователя ввести путь к базе данных, затем ключевое слово (фразу), которая является точным названием фильма.

Параметрам дан разный "вес": принадлежность к коллекции - 1000, оригинальный язык фильма - 300, бюджет - 100, жанр - 500. При совпадении параметра похожего фильма с параметром фильма, заданного пользоавателем, вес "похожести" увеличивается на "вес" этого параметра. Суммарный вес совпавших параметров - это рейтинг похожести фильма.

Из списка наиболее похожих фильмов удаляется сам фильм, заданный пользователем (совпадающий сам с собой), затем по весу выбираются наиболее похожие фильмы, и их отсортированный список возвращается пользователю. Список фильмов ограничен восемью фильмами.

#### Запуск скрипта
```python
>>> python3 find_similar.py
```

#### Успешный запуск
```python
>>> python3 find_similar.py
Enter path to DataBase:MyFilmDB.json
Enter film to search for:Ariel
Four Rooms
Hable con ella
Judgment Night
Kunstgriff
Las Hurdes
Megacities
Sonntag im August
The Dark
Varjoja paratiisissa
```
