<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9f4785899ee92500f524b4acb26e3bb3",
  "translation_date": "2025-05-19T12:37:21+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "bg"
}
-->
# Започване с този курс

Много сме развълнувани, че започвате този курс и ще видим какво ще ви вдъхнови да създадете с Генеративния AI!

За да гарантираме вашия успех, тази страница очертава стъпките за настройка, техническите изисквания и къде да получите помощ, ако е необходимо.

## Стъпки за настройка

За да започнете този курс, ще трябва да изпълните следните стъпки.

### 1. Форкнете това хранилище

[Форкнете цялото това хранилище](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) във вашия собствен GitHub акаунт, за да можете да променяте кода и да завършвате предизвикателствата. Можете също така да [звездате (🌟) това хранилище](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst), за да го намерите и свързаните с него хранилища по-лесно.

### 2. Създайте кодово пространство

За да избегнете проблеми със зависимостите при изпълнение на кода, препоръчваме да изпълнявате този курс в [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst).

Това може да бъде създадено, като изберете опцията `Code` на вашата форкната версия на това хранилище и изберете опцията **Codespaces**.

![Диалогов прозорец, показващ бутони за създаване на кодово пространство](../../../00-course-setup/images/who-will-pay.webp)

### 3. Съхранение на вашите API ключове

Поддържането на вашите API ключове безопасни и сигурни е важно, когато изграждате всякакъв вид приложение. Препоръчваме да не съхранявате никакви API ключове директно в кода си. Публикуването на тези данни в обществено хранилище може да доведе до проблеми със сигурността и дори нежелани разходи, ако бъдат използвани от злонамерен актьор.
Ето ръководство стъпка по стъпка как да създадете `.env` файл за Python и да добавите `GITHUB_TOKEN`:

1. **Навигирайте до вашата проектна директория**: Отворете вашия терминал или команден ред и навигирайте до кореновата директория на вашия проект, където искате да създадете файла `.env`.

   ```bash
   cd path/to/your/project
   ```

2. **Създайте файла `.env`**: Използвайте предпочитания от вас текстов редактор, за да създадете нов файл с име `.env`. Ако използвате командния ред, можете да използвате `touch` (on Unix-based systems) or `echo` (в Windows):

   Unix-базирани системи:
   ```bash
   touch .env
   ```

   Windows:
   ```cmd
   echo . > .env
   ```

3. **Редактирайте файла `.env`**: Отворете файла `.env` в текстов редактор (например, VS Code, Notepad++ или друг редактор). Добавете следния ред във файла, заменяйки `your_github_token_here` с вашия действителен GitHub токен:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **Запазете файла**: Запазете промените и затворете текстовия редактор.

5. **Инсталирайте пакета `python-dotenv`**: If you haven't already, you'll need to install the `python-dotenv`, за да заредите променливите на околната среда от файла `.env` във вашето Python приложение. Можете да го инсталирате с `pip`:

   ```bash
   pip install python-dotenv
   ```

6. **Заредете променливите на околната среда във вашия Python скрипт**: Във вашия Python скрипт използвайте пакета `python-dotenv`, за да заредите променливите на околната среда от файла `.env`:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

Това е всичко! Успешно създадохте `.env` файл, добавихте вашия GitHub токен и го заредихте във вашето Python приложение.

## Как да изпълните локално на вашия компютър

За да изпълните кода локално на вашия компютър, ще трябва да имате някаква версия на [Python инсталирана](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst).

След това, за да използвате хранилището, трябва да го клонирате:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

След като всичко е проверено, можете да започнете!

## Допълнителни стъпки

### Инсталиране на Miniconda

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) е лек инсталатор за инсталиране на [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, както и няколко пакета.
Conda сама по себе си е мениджър на пакети, който улеснява настройването и превключването между различни Python [**виртуални среди**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) и пакети. Тя също така е полезна за инсталиране на пакети, които не са налични чрез `pip`.

You can follow the [MiniConda installation guide](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) to set it up.

With Miniconda installed, you need to clone the [repository](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (if you haven't already)

Next, you need to create a virtual environment. To do this with Conda, go ahead and create a new environment file (_environment.yml_). If you are following along using Codespaces, create this within the `.devcontainer` directory, thus `.devcontainer/environment.yml`.

Продължете и попълнете файла на околната среда с фрагмента по-долу:

```yml
name: <environment-name>
channels:
 - defaults
 - microsoft
dependencies:
- python=<python-version>
- openai
- python-dotenv
- pip
- pip:
    - azure-ai-ml

```

Ако установите, че получавате грешки, използвайки conda, можете ръчно да инсталирате Microsoft AI Libraries, използвайки следната команда в терминал.

```
conda install -c microsoft azure-ai-ml
```

Файлът на околната среда уточнява зависимостите, които ни трябват. `<environment-name>` refers to the name you would like to use for your Conda environment, and `<python-version>` is the version of Python you would like to use, for example, `3` е последната основна версия на Python.

С това, можете да продължите и да създадете вашата Conda среда, като изпълните командите по-долу във вашия команден ред/терминал

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

Обърнете се към [ръководството за среди на Conda](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst), ако срещнете някакви проблеми.

### Използване на Visual Studio Code с разширението за поддръжка на Python

Препоръчваме използването на редактора [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) с инсталирано разширение за поддръжка на Python за този курс. Това обаче е повече препоръка, отколкото задължително изискване.

> **Забележка**: Като отворите хранилището на курса във VS Code, имате възможност да настроите проекта в контейнер. Това е заради [специалната `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) директория, намираща се в хранилището на курса. Повече за това по-късно.

> **Забележка**: След като клонирате и отворите директорията във VS Code, тя автоматично ще ви предложи да инсталирате разширение за поддръжка на Python.

> **Забележка**: Ако VS Code ви предложи да отворите хранилището в контейнер, откажете това искане, за да използвате локално инсталираната версия на Python.

### Използване на Jupyter в браузъра

Можете също така да работите по проекта, използвайки [Jupyter средата](https://jupyter.org?WT.mc_id=academic-105485-koreyst) директно във вашия браузър. Както класическият Jupyter, така и [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) предоставят доста приятна среда за разработка с функции като автоматично допълване, подчертаване на код и др.

За да стартирате Jupyter локално, отидете до терминала/командния ред, навигирайте до директорията на курса и изпълнете:

```bash
jupyter notebook
```

или

```bash
jupyterhub
```

Това ще стартира Jupyter инстанция и URL за достъп до нея ще бъде показан в прозореца на командния ред.

След като получите достъп до URL, трябва да видите съдържанието на курса и да можете да навигирате до всеки `*.ipynb` file. For example, `08-building-search-applications/python/oai-solution.ipynb`.

### Running in a container

An alternative to setting everything up on your computer or Codespace is to use a [container](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). The special `.devcontainer` folder within the course repository makes it possible for VS Code to set up the project within a container. Outside of Codespaces, this will require the installation of Docker, and quite frankly, it involves a bit of work, so we recommend this only to those with experience working with containers.

One of the best ways to keep your API keys secure when using GitHub Codespaces is by using Codespace Secrets. Please follow the [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) guide to learn more about this.

## Lessons and Technical Requirements

The course has 6 concept lessons and 6 coding lessons.

For the coding lessons, we are using the Azure OpenAI Service. You will need access to the Azure OpenAI service and an API key to run this code. You can apply to get access by [completing this application](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

While you wait for your application to be processed, each coding lesson also includes a `README.md` файл, където можете да видите кода и изходите.

## Използване на Azure OpenAI услугата за първи път

Ако това е първият ви път, когато работите с Azure OpenAI услугата, моля, следвайте това ръководство как да [създадете и разположите ресурс за Azure OpenAI услуга.](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## Използване на OpenAI API за първи път

Ако това е първият ви път, когато работите с OpenAI API, моля, следвайте ръководството как да [създадете и използвате интерфейса.](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## Срещнете други обучаващи се

Създадохме канали в нашия официален [AI Community Discord сървър](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) за срещи с други обучаващи се. Това е страхотен начин да се свържете с други предприемачи, строители, студенти и всеки, който иска да се развива в Генеративния AI.

[![Присъединете се към канала в Discord](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

Екипът на проекта също ще бъде на този Discord сървър, за да помага на всички обучаващи се.

## Допринасяне

Този курс е инициатива с отворен код. Ако видите области за подобрение или проблеми, моля, създайте [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) или регистрирайте [GitHub проблем](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst).

Екипът на проекта ще следи всички приноси. Допринасянето към отворен код е невероятен начин да изградите кариерата си в Генеративния AI.

Повечето приноси изискват от вас да се съгласите с Лицензионно споразумение за приносител (CLA), което декларира, че имате правото и наистина предоставяте ни правата да използваме вашия принос. За подробности, посетете [CLA, уебсайта на Лицензионното споразумение за приносител](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst).

Важно: когато превеждате текст в това хранилище, моля, уверете се, че не използвате машинен превод. Ще проверим преводите чрез общността, така че моля, доброволствайте само за преводи на езици, на които сте компетентни.

Когато изпратите pull request, CLA-ботът автоматично ще определи дали трябва да предоставите CLA и ще украси PR съответно (например, етикет, коментар). Просто следвайте инструкциите, предоставени от бота. Ще трябва да направите това само веднъж за всички хранилища, използващи нашия CLA.

Този проект е приел [Кодекса за поведение на Microsoft Open Source](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst). За повече информация прочетете FAQ на Кодекса за поведение или се свържете с [Email opencode](opencode@microsoft.com) с всякакви допълнителни въпроси или коментари.

## Да започнем

Сега, когато завършихте необходимите стъпки за завършване на този курс, нека започнем с [въведение в Генеративния AI и LLMs](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst).

**Отказ от отговорност**:  
Този документ е преведен с помощта на AI услуга за превод [Co-op Translator](https://github.com/Azure/co-op-translator). Въпреки че се стремим към точност, моля, имайте предвид, че автоматичните преводи може да съдържат грешки или неточности. Оригиналният документ на неговия роден език трябва да се счита за авторитетен източник. За критична информация се препоръчва професионален човешки превод. Не носим отговорност за недоразумения или погрешни интерпретации, произтичащи от използването на този превод.