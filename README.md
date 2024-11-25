# DSMEDxMFTIBIO
## ЗАДАЧА
Определить эмоциональное состояние собеседника, проводя анализ текстовой расшифровки его голосового сообщения.

## КОМАНДА ПРОЕКТА
Бадретдинова Рушана - Тим Лид
Евдокимов Денис - Участник команды
Белова Виктория - Участник команды
Комаревцева Анна - Участник команды
Артюшев Рафаэль - Участник команды

## ДАННЫЕ
Текстовые расшифровки голосовых сообщений, размеченные по категориям эмоций в фомате .csv (https://github.com/rushbad/DSMEDxMFTIBIO/blob/main/%D0%A4%D1%80%D0%B0%D0%B7%D1%8B-%D1%8D%D0%BC%D0%BE%D1%86%D0%B8%D0%B8.csv)

## ПРЕДОБРАБОТКА ДАННЫХ 
Было проведено: 
 - Удаление дубликатов и пропусков:
Необходимо избавиться от дублирующихся записей и заполнить пропуски, чтобы улучшить качество выходных данных.
 - Исключение класса "Недовольство":
Класс "Недовольство" будет удалён из выборки, поскольку он представлен недостаточно.
 - Анализ текстов и обрезка длинных записей:
Необходимо выявить наиболее длинные тексты и обрезать их, так как избыточная длина может негативно сказаться на эффективности модели.
 - Нормализация:
    -  Приведение текста к нижнему регистру, а также удаление пунктуации и чисел.
    -  Удаление стоп-слов будет выполняться с помощью библиотеки NLTK.
    -  Применение стемминга с использованием SnowballStemmer.
    -  Токенизация с помощью методов CountVectorizer и Word2Vec.

## EXPLORATION DATA ANALYSIS
Распределение текстов по эмоциям

![image](https://github.com/user-attachments/assets/6cb8cc65-6f2b-4799-b429-9364a920c4a3)

Распределение длины текстов по символам

![image](https://github.com/user-attachments/assets/b3564f68-45c6-4218-a05c-ee514484a941)

Распределение длины текстов по тональности

![image](https://github.com/user-attachments/assets/068af01e-432f-484f-94a4-5b65741d357e)

Корреляция между длинной текста и эмоциями 
![image](https://github.com/user-attachments/assets/1a4ff72d-0bc7-4428-a92b-f9f27d34eea1)
**Корреляция Пирсона:** 0.08
Значение 0.08 указывает на очень слабую положительную линейную связь между длиной текста и эмоциями. Это означает, что практически нет линейной зависимости между этими двумя параметрами в ваших данных.

## КЛАССИЧЕСКИЕ МОДЕЛИ МАШИННОГО ОБУЧЕНИЯ 
Предобработка CountVectorizer 
![image](https://github.com/user-attachments/assets/71264a0b-cccd-4155-a4ca-af6533a21864)

Предобработка Word2Vec
![image](https://github.com/user-attachments/assets/0f597dfd-1840-4587-9fe2-ad1d4c39b3db)

CountVectorizer продемонстрировал более высокие результаты по сравнению с Word2Vec.

## Bidirectional Long Short-Term Memory
![image](https://github.com/user-attachments/assets/5e8c2acd-d574-40fb-820d-778633577091)

Пока не удалось достичь аналогичных результатов с использованием Bi-LSTM.



