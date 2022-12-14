# Supervised learning, project #1

## Описание задачи

Из «Бета-Банка» стали уходить клиенты. Каждый месяц. Немного, но заметно. Банковские маркетологи посчитали: сохранять текущих клиентов дешевле, чем привлекать новых.

Нужно спрогнозировать, уйдёт клиент из банка в ближайшее время или нет. Вам предоставлены исторические данные о поведении клиентов и расторжении договоров с банком.

Постройте модель с предельно большим значением F1-меры. Чтобы сдать проект успешно, нужно довести метрику до 0.59. Проверьте F1-меру на тестовой выборке самостоятельно.

Дополнительно измеряйте AUC-ROC, сравнивайте её значение с F1-мерой.

Источник данных: https://www.kaggle.com/barelydedicated/bank-customer-churn-modeling

## Используемые модели, техники

Логистическая регрессия, дерево решений, случайный лес.

Борьба с дисбалансом классов посредством `class_weight='balanced'`, downsampling, upsampling.

GridSearchCV.

## Результат

Наилучшим образом себя показала модель на основе случайного леса с использованием техники upsampling.  
Гиперпараметры:
```
'max_depth': 10,
'min_samples_leaf': 1,
'min_samples_split': 4,
'n_estimators': 100
```

Значение F1-меры данной модели на тестовой выборке составило 0,6150. Это выше необходимого порога в 0,59. Значение метрики AUC-ROC данной модели на тестовой выборке составило 0,8557. Модель довольно хорошо справляется с правильной классификацией целевого признака.