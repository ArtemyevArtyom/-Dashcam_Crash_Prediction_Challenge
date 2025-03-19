Цель работы:
Разработка модели компьютерного зрения для предсказания столкновений транспортных средств с видеорегистратора в рамках Kaggle-соревнования.

Ключевые достижения:

Архитектура модели:

Создана гибридная нейросетевая архитектура на основе EfficientNetB0 (для извлечения пространственных признаков) и бидирекционных LSTM (для анализа временных зависимостей).

Реализована обработка видео с применением TimeDistributed слоёв для последовательного анализа кадров.

Аналитика данных:

Проведена предобработка видео (нормализация, ресайз до 224x224, ограничение длины последовательности 20 кадрами).

Выявлен дисбаланс классов в данных (примеры без столкновений преобладают).

Результаты:

Достигнута AUC ~0.49 и accuracy ~0.5 на валидации, что указывает на необходимость доработки модели (возможно, из-за недостатка данных или сложности задачи).

Проанализировано распределение предсказаний: модель демонстрирует склонность к консервативным прогнозам (концентрация вероятностей вокруг 0.5).

Инструменты и методы:

Использованы TensorFlow/Keras, OpenCV для обработки видео, sklearn для метрик.

Реализованы генераторы данных для эффективной работы с большими видеофайлами.

Настроены коллбэки: EarlyStopping, ModelCheckpoint, ReduceLROnPlateau.

Выводы для оптимизации:

Требуется увеличение датасета, применение аугментаций.

Возможна замена LSTM на 3D-свёртки или трансформеры для лучшего анализа временных паттернов.

Необходима балансировка классов и тонкая настройка гиперпараметров.
