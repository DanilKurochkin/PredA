# Запуск проекта


## 1. Создание conda-окружения

Рекомендуется запускать проект в отдельном окружении.

```bash
conda create -n analytics-lab python=3.11 -y
conda activate analytics-lab
```

---

## 2. Установка зависимостей

После активации окружения установите зависимости из `requirements.txt`:

```bash
pip install -r requirements.txt
```

---

## 3. Подключение окружения к Jupyter

Чтобы окружение появилось в списке доступных kernel в Jupyter Notebook, выполните:

```bash
pip install ipykernel
python -m ipykernel install --user --name analytics-lab --display-name "Python (analytics-lab)"
```

---

## 4. Запуск Jupyter Notebook

```bash
jupyter notebook
```

После запуска notebook выберите kernel:

```text
Python (analytics-lab)
```

## 5. Обновление зависимостей

Если в процессе работы были установлены новые библиотеки, обновите `requirements.txt`:

```bash
pip freeze > requirements.txt
```

Или из Jupyter Notebook:

```python
!pip freeze > requirements.txt
```

---

## 6. Дополнительно: сохранение conda-окружения

Для conda-проектов можно дополнительно сохранить полное описание окружения:

```bash
conda env export > environment.yml
```

Восстановить окружение из `environment.yml` можно так:

```bash
conda env create -f environment.yml
conda activate weather-lab
```

---

## 7. Проверка окружения

Для проверки, что notebook использует правильное окружение:

```python
import sys

print(sys.executable)
```

Путь должен указывать на созданное окружение `weather-lab`.
