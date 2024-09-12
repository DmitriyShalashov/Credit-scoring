# Кредитный скоринг

Данный проект содержит реализацию модели машинного обучения для определения кредитоспособности населения по нескольким заранее заданным признакам. Для взаимодействия с моделью реализован User Interface. Ниже представление описание проекта.

## Содержание

- [Установка](#установка)
- [Использование](#использование)
- [Примеры](#примеры)
- [Данные](#данные)
- [Техническое описание](#техническое_описание)

## Установка

Подробная инструкция по установке и настройке проекта. Например:

1. Клонируйте репозиторий:
    ```bash
    git clone https://github.com/username/project_name.git
    ```
2. Перейдите в директорию проекта:
    ```bash
    cd project_name
    ```
3. Установите необходимые зависимости:
    ```bash
    pip install streamlit
    ```
4. Запустите User Interface:
   ```bash
   streamlit run UI.py
    ```
5. Убедитесь, что текущая версия sklearn 1.3.2. Перейдите в браузер и начните использование.
   
## Использование
Проект может быть использован для определения кредитоспособности населения.

## Примеры
Ниже представлена демонстрация работы User Interface.
### [демонстрация_проекта.mp4](демонстрация_проекта.mp4)

## Данные
Для обучения модели и тестирования использован датасет "german_credit_data.csv", содержащий информацию о 1000 пользователях. Для определения кредитоспособности было использовано 8 признаков: возраст, пол, количество работ, тип владеемой недвижимости, совокупный размер сберегательных счетов, размер текущего счёта, длительность кредита и его цель.

## Техническое описание
### [UI.py](UI.py)
Через API streamlit код создает веб-страницу, куда пользователь вводит данные и получает прогноз по нажатию на кнопку, который выполняет функция predict. 
### [input_processing.py](input_processing.py)
Функция в файле делает предобработку отправленных пользователем данных перед функцией predict.
### [one_hot_encoder.joblib](one_hot_encoder.joblib)
Обученное one-hot кодирование для категориальных признаков.
### [ordinal_encoder.joblib](ordinal_encoder.joblib)
Порядковое кодирование для признака Saving accounts.
### [scaler.joblib](scaler.joblib)
Обученная стандартизация признаков.
### Описание решения
К категориальным признакам ('Sex', 'Housing', 'Checking account', 'Purpose') применено one-hot кодирование.  
К Saving accounts применено порядковое кодирование. 
При выборе модели сравнивались Random Forest Classifier и Gradient Boosting Classifier, для обеих был сделан подбор гиперпараметров через GridSearch. Лучше справилась модель градиентного бустинга (roc_auc: 0.764 на тесте). 
Анализ данных, обучение и тестирование моделей представлены в файле [Credit_scoring_final.ipynb](Credit_scoring_final.ipynb).




#   C r e d i t - s c o r i n g  
 