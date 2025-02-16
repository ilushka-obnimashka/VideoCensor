## Установка

> [!Note]
> **Внимание:** 
> Для установки proof-of-check.py необходимо использовать менеджер пакетов Poetry. Убедитесь, что он установлен на вашем устройстве перед началом работы с проектом.[Установка и работа с Poetry](#установка-и-работа-с-poetry)

1. Клонируйте репозиторий:
```bash
    git clone https://github.com/ilushka-obnimashka/VideoCensor.git
    cd VideoCensor
```
2. Переключитесь на ветку proof-of-concept:
```bash
   git checkout proof-of-concept
```
3. Создайте виртуальное окружение и установите зависимости, указанные в файле pyproject.toml:
```bash
   poetry install
```
4. Активируйте виртаульное окружение:
```bash
   potry shell
```
5. Выберите интепретатор в среде разработки:

▎Visual Studio Code:
   1. Откройте командную палитру (Ctrl + Shift + P).
   2. Введите Python: Select Interpreter и выберите интерпретатор, который соответствует вашей виртуальной среде Poetry (обычно он будет находиться в папке .venv вашего проекта).
   3. После этого VS Code будет использовать выбранный интерпретатор для выполнения вашего кода.

▎PyCharm:
   1. Откройте настройки проекта (File -> Settings или Ctrl + Alt + S).
   2. Перейдите в раздел Project: <your_project_name> -> Python Interpreter. 
   3. Выберите Add Interpretator -> Add Local Interpretator -> Select existing
   4. Выберите Type: Poetry. 
   5. Нажмите OK, чтобы применить изменения.
      (Подробнее https://www.jetbrains.com/help/pycharm/configuring-python-interpreter.html#add_local_interpreters)

6. Запустите код

## Установка и работа с Poetry
### Установка

1. Установите `Poetry` c официального источника:
   * 1.1 Установка на Linux, macOS, Windows (WSL):
   ```bash
    curl -sSL https://install.python-poetry.org | python3 -
    ```
   * 1.2 Установка на Windows (PowerShell):
   ```bash
    (Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -
    ```

2. Проверьте работу `Poetry`:
```bash
    poetry --version
```
Если вы видите что-то вроде ``Poetry (version 2.0.0)``, ваша установка готова к использованию!

Если такой ответ не последовал, то перейдите к пункту 3.

3. Добавьте `Poetry` в ваш `PATH`:
* 3.1 Добавление на Linux, macOS, Windows (WSL):
   ```bash
  export PATH="$HOME/.local/bin:$PATH"
  source ~/.bashrc
   ```
* 1.2 Добавление на Windows (PowerShell):
  * Скопируйте путь установки:
    * После завершения установки запомните или скопируйте путь, который будет указан в конце установки. Обычно это `%APPDATA%\Python\Scripts`.

  * Добавьте путь в переменные окружения:

    * Нажмите правой кнопкой мыши на кнопку "Пуск" и выберите "Система".

    * В открывшемся окне выберите "Дополнительные параметры системы" на левой панели.

    * В окне "Свойства системы" нажмите кнопку "Переменные среды...".

    * В разделе "Переменные среды" найдите переменную Path под "Переменные пользователя для [ВашеИмя]" и выберите её.

    * Нажмите кнопку "Изменить...".

    * В окне редактирования переменной нажмите "Создать" и вставьте скопированный путь `%APPDATA%\Python\Scripts`.

    * Нажмите "ОК" для сохранения изменений во всех открытых окнах.

4. Настройте `Poetry` для создания виртуального окружения в проекте:
```bash
  poetry config virtualenvs.in-project true
```
5.  Установите плагин для запуска оболочки с активированным виртуальным окружением:
```bash
  poetry self add poetry-plugin-shell
```