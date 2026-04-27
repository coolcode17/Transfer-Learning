# Transfer-Learning
Классификация рукописных цифр с применением трансферного обучения VGG16 и аугментации данных на базе TensorFlow/Keras.
# Handwritten Digits Classification using Transfer-Learning, VGG16, VGG19, MobileNetV2, ResNet50

![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-D00000?style=for-the-badge&logo=Keras&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

## Описание проекта
[cite_start]Данный проект посвящен глубокому изучению **трансферного обучения (Transfer Learning)** и **аугментации данных (Data Augmentation)** для задачи классификации изображений. [cite_start]В рамках работы проведено исследование нескольких предобученных архитектур сверточных нейронных сетей, оценка их эффективности и сравнение подходов к заморозке/разморозке слоев.

## Структура исследования и обученные модели

В ходе выполнения проекта были реализованы и обучены следующие модели:

### 1. Базовая модель VGG16 (Замороженные слои)
- [cite_start]Использована архитектура **VGG16** с весами ImageNet.
- [cite_start]Все сверточные слои заморожены, заменен только финальный классификатор.
- [cite_start]Применена сильная аугментация данных (6 различных вариантов преобразований, таких как повороты, сдвиги, масштабирование).
- [cite_start]Проведено тестирование на тестовой выборке и пользовательских изображениях.

### 2. Сравнение с VGG19
- [cite_start]Базовая архитектура заменена на **VGG19**.
- [cite_start]Проведен сравнительный анализ точности и скорости обучения по отношению к VGG16.

### 3. Влияние степени аугментации
- [cite_start]Повторное обучение модели VGG16, но с уменьшенным количеством аугментаций (только 2 варианта преобразований).
- [cite_start]Проведено сравнение траекторий обучения (графиков Loss и Accuracy) моделей с сильной и слабой аугментацией.

### 4. Тонкая настройка (Fine-Tuning) VGG16
- [cite_start]Использована архитектура VGG16 с применением сильной аугментации (6 вариантов).
- [cite_start]**Разморожены последние 4 слоя** базовой модели для их совместного обучения с новым классификатором.
- [cite_start]Обучение проводилось с пониженной скоростью обучения (Adam, lr=1e-5) для аккуратной настройки весов.
- [cite_start]Результаты сравнены с полностью замороженной версией VGG16.

### 5. Альтернативные архитектуры
- [cite_start]Проведено трансферное обучение для двух дополнительных архитектур из пакета `tensorflow.keras.applications`.
- [cite_start]Выполнен итоговый сравнительный анализ всех протестированных моделей.

## Результаты и визуализация

[cite_start]Для каждой обученной модели велся лог-файл и строились графики процесса обучения.

> **<img src="https://github.com/coolcode17/Transfer-Learning/blob/main/Aug6.PNG">** `Пример аугментации данных перед подачей в нейросеть`.*
## Результаты обучения

> **<img src="https://github.com/coolcode17/Transfer-Learning/blob/main/VGG16.PNG">* 
VGG16.*
> **<img src="https://github.com/coolcode17/Transfer-Learning/blob/main/VGG19.PNG">*
VGG19.*

> **<img src="https://github.com/coolcode17/Transfer-Learning/blob/main/VGG16Aug2.PNG">*
> 2 варианта аугментации.*

### Размороженные последние 4 слоя
> **<img src="https://github.com/coolcode17/Transfer-Learning/blob/main/VGG16Unfrozen.PNG">*
>  *Разморозка последних 4 слоев сети VGG16.*

## Тестирование на пользовательских данных
[cite_start]Все модели были проверены не только на отложенной тестовой выборке, но и на сторонних изображениях, подготовленных пользователем.
> **<img src="https://github.com/coolcode17/Transfer-Learning/blob/main/sevenUnfrozenVGG16.PNG">*
> **<img src="https://github.com/coolcode17/Transfer-Learning/blob/main/ConfusionMatrix">*

## Технические требования и запуск
- [cite_start]Операционная система: Windows или Linux.
- [cite_start]Рекомендуется запуск с использованием GPU (например, в Google Colab).
## Как запустить проект
1. Склонируйте репозиторий: `git clone https://github.com/ВАШ_НИК/VGG16-Digits-Classification.git`
2. Откройте `4LABA.ipynb` в Jupyter Notebook или Google Colab.
3. Убедитесь, что установлены все необходимые библиотеки: `tensorflow`, `opencv-python`, `pandas`, `matplotlib`, `scikit-learn`.
4. Запустите ячейки по порядку. Датасет скачается автоматически через `kagglehub`.
