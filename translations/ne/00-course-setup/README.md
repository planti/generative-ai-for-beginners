<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9f4785899ee92500f524b4acb26e3bb3",
  "translation_date": "2025-05-19T12:21:55+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "ne"
}
-->
# यो पाठ्यक्रम सुरु गर्ने

हामी तपाईलाई यो पाठ्यक्रम सुरु गर्न र Generative AI सँग के निर्माण गर्न प्रेरित हुनुहुन्छ भनेर हेर्न पाउँदा धेरै उत्साहित छौं!

तपाईंको सफलताको सुनिश्चित गर्न, यो पृष्ठले सेटअप चरणहरू, प्राविधिक आवश्यकताहरू, र आवश्यक परेमा मद्दत प्राप्त गर्न कहाँ जान्ने outlines गर्दछ।

## सेटअप चरणहरू

यो पाठ्यक्रम लिन सुरु गर्न, तपाईंले निम्न चरणहरू पूरा गर्न आवश्यक छ।

### 1. यस Repo लाई Fork गर्नुहोस्

तपाईंको GitHub खातामा [यस सम्पूर्ण repo लाई fork गर्नुहोस्](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) ताकि तपाईं कुनै पनि कोड परिवर्तन गर्न र चुनौतीहरू पूरा गर्न सक्नुहुन्छ। तपाईं [यस repo लाई स्टार (🌟) दिन पनि सक्नुहुन्छ](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) ताकि यसलाई र सम्बन्धित repos लाई सजिलै भेट्न सकिन्छ।

### 2. एक codespace बनाउनुहोस्

कोड चलाउँदा कुनै निर्भरता समस्या आउनबाट बच्नको लागि, हामी यस पाठ्यक्रमलाई [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) मा चलाउन सिफारिस गर्छौं।

यसलाई तपाईंको fork गरिएको repo को संस्करणमा `Code` विकल्प चयन गरेर र **Codespaces** विकल्प चयन गरेर बनाइन्छ।

![Dialog showing buttons to create a codespace](../../../00-course-setup/images/who-will-pay.webp)

### 3. तपाईंको API कुञ्जीहरू भण्डारण गर्नुहोस्

कुनै पनि प्रकारको एप्लिकेसन निर्माण गर्दा तपाईंको API कुञ्जीहरू सुरक्षित राख्नु महत्त्वपूर्ण हुन्छ। हामी सिफारिस गर्छौं कि कुनै पनि API कुञ्जीहरू सिधै तपाईंको कोडमा भण्डारण नगर्नुहोस्। ती विवरणहरूलाई सार्वजनिक रिपोजिटरीमा कमिट गर्दा सुरक्षा समस्याहरू र खराब अभिनेता द्वारा प्रयोग गर्दा अनावश्यक लागतहरू हुन सक्छ।
Python को लागि `.env` फाइल कसरी बनाउने र `GITHUB_TOKEN` थप्ने चरण-दर-चरण मार्गदर्शन यहाँ छ:

1. **तपाईंको प्रोजेक्ट डाइरेक्टरीमा जानुहोस्**: तपाईंको टर्मिनल वा कमाण्ड प्रम्प्ट खोल्नुहोस् र जहाँ तपाईं `.env` फाइल बनाउनु पर्छ त्यहाँको तपाईंको प्रोजेक्टको मूल डाइरेक्टरीमा जानुहोस्।

   ```bash
   cd path/to/your/project
   ```

2. **`.env` फाइल बनाउनुहोस्**: तपाईंको मनपर्ने टेक्स्ट एडिटर प्रयोग गरेर `.env` नामक नयाँ फाइल बनाउनुहोस्। यदि तपाईं कमाण्ड लाइन प्रयोग गर्दै हुनुहुन्छ भने, तपाईं `touch` (on Unix-based systems) or `echo` प्रयोग गर्न सक्नुहुन्छ (विन्डोजमा):

   Unix-आधारित प्रणालीहरू:
   ```bash
   touch .env
   ```

   विन्डोज:
   ```cmd
   echo . > .env
   ```

3. **`.env` फाइल सम्पादन गर्नुहोस्**: `.env` फाइललाई टेक्स्ट एडिटरमा खोल्नुहोस् (जस्तै, VS Code, Notepad++, वा कुनै अन्य एडिटर)। फाइलमा निम्न लाइन थप्नुहोस्, `your_github_token_here` लाई तपाईंको वास्तविक GitHub टोकनसँग प्रतिस्थापन गर्नुहोस्:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **फाइल सुरक्षित गर्नुहोस्**: परिवर्तनहरू सुरक्षित गर्नुहोस् र टेक्स्ट एडिटर बन्द गर्नुहोस्।

5. **`python-dotenv`**: If you haven't already, you'll need to install the `python-dotenv` प्याकेजलाई तपाईंको Python एप्लिकेसनमा `.env` फाइलबाट वातावरण चरहरू लोड गर्न स्थापना गर्नुहोस्। तपाईं `pip` प्रयोग गरेर यसलाई स्थापना गर्न सक्नुहुन्छ:

   ```bash
   pip install python-dotenv
   ```

6. **तपाईंको Python स्क्रिप्टमा वातावरण चरहरू लोड गर्नुहोस्**: तपाईंको Python स्क्रिप्टमा `.env` फाइलबाट वातावरण चरहरू लोड गर्न `python-dotenv` प्याकेज प्रयोग गर्नुहोस्:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

त्यसै हो! तपाईंले सफलतापूर्वक `.env` फाइल बनाउनु भएको छ, तपाईंको GitHub टोकन थप्नु भएको छ, र तपाईंको Python एप्लिकेसनमा लोड गर्नु भएको छ।

## तपाईंको कम्प्युटरमा स्थानीय रूपमा कसरी चलाउने

तपाईंको कम्प्युटरमा स्थानीय रूपमा कोड चलाउनको लागि, तपाईंलाई [Python को कुनै संस्करण स्थापना गर्नु पर्नेछ](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)।

त्यसपछि रिपोजिटरी प्रयोग गर्नको लागि, तपाईंले यसलाई क्लोन गर्नु पर्छ:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

जब तपाईंले सबै चेक आउट गर्नु भएको छ, तपाईं सुरु गर्न सक्नुहुन्छ!

## वैकल्पिक चरणहरू 

### Miniconda स्थापना गर्दै 

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, साथै केही प्याकेजहरू स्थापना गर्नको लागि एक हल्का स्थापना उपकरण हो।
Conda आफैं एक प्याकेज प्रबन्धक हो, जसले विभिन्न Python [**भर्चुअल वातावरणहरू**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) र प्याकेजहरू सेटअप र स्विच गर्न सजिलो बनाउँछ। यो `pip`.

You can follow the [MiniConda installation guide](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) to set it up.

With Miniconda installed, you need to clone the [repository](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (if you haven't already)

Next, you need to create a virtual environment. To do this with Conda, go ahead and create a new environment file (_environment.yml_). If you are following along using Codespaces, create this within the `.devcontainer` directory, thus `.devcontainer/environment.yml` मार्फत उपलब्ध नभएका प्याकेजहरू स्थापना गर्नको लागि पनि उपयोगी हुन्छ।

तलको स्निपेटको साथमा तपाईंको वातावरण फाइललाई पूर्ण गर्नुहोस्:

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

यदि तपाईंले conda प्रयोग गर्दा त्रुटिहरू पाउनुहुन्छ भने तपाईं Microsoft AI Libraries लाई निम्न कमाण्ड प्रयोग गरेर टर्मिनलमा म्यानुअली स्थापना गर्न सक्नुहुन्छ। 

```
conda install -c microsoft azure-ai-ml
```

वातावरण फाइलले हामीलाई आवश्यक निर्भरता निर्दिष्ट गर्दछ। `<environment-name>` refers to the name you would like to use for your Conda environment, and `<python-version>` is the version of Python you would like to use, for example, `3` Python को नवीनतम प्रमुख संस्करण हो।

त्यस पछि, तपाईं आफ्नो Conda वातावरणलाई कमाण्ड लाइन/टर्मिनलमा तलका कमाण्डहरू चलाएर बनाउन सक्नुहुन्छ

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

यदि तपाईं समस्यामा पर्नुहुन्छ भने [Conda वातावरण गाइड](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) हेर्नुहोस्।

### Python समर्थन विस्तारको साथ Visual Studio Code प्रयोग गर्दै

हामी यो पाठ्यक्रमको लागि [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) एडिटर प्रयोग गर्न सिफारिस गर्छौं जसमा [Python समर्थन विस्तार](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) स्थापना गरिएको छ। यो, तथापि, सिफारिस मात्र हो र निश्चित आवश्यकता होइन

> **Note**: VS Code मा पाठ्यक्रम रिपोजिटरी खोल्दा, तपाईंलाई परियोजना एक कन्टेनरमा सेट अप गर्ने विकल्प हुन्छ। यो पाठ्यक्रम रिपोजिटरी भित्र पाइने [विशेष `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) निर्देशिकाको कारण हो। यस बारेमा पछि थप जान्नेछ।

> **Note**: एक पटक तपाईंले रिपोजिटरीलाई क्लोन गरेर VS Code मा खोल्नुभयो भने, यो तपाईंलाई Python समर्थन विस्तार स्थापना गर्न स्वतः सुझाव दिनेछ।

> **Note**: यदि VS Code ले रिपोजिटरीलाई कन्टेनरमा पुनः खोल्न सुझाव दिन्छ भने, स्थानीय रूपमा स्थापना गरिएको Python संस्करण प्रयोग गर्नको लागि यो अनुरोध अस्वीकार गर्नुहोस्।

### ब्राउजरमा Jupyter प्रयोग गर्दै

तपाईं ब्राउजरमा नै [Jupyter वातावरण](https://jupyter.org?WT.mc_id=academic-105485-koreyst) प्रयोग गरेर पनि परियोजनामा काम गर्न सक्नुहुन्छ। दुवै क्लासिक Jupyter र [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) स्वतः पूर्ति, कोड हाइलाइटिङ्ग आदि जस्ता सुविधाहरूको साथमा एक रमाइलो विकास वातावरण प्रदान गर्दछ।

स्थानीय रूपमा Jupyter सुरु गर्न, टर्मिनल/कमाण्ड लाइनमा जानुहोस्, पाठ्यक्रम निर्देशिकामा जानुहोस्, र कार्यान्वयन गर्नुहोस्:

```bash
jupyter notebook
```

वा

```bash
jupyterhub
```

यसले एक Jupyter इन्स्टेन्स सुरु गर्नेछ र यसलाई पहुँच गर्न URL कमाण्ड लाइन विन्डोमा देखाइनेछ।

एक पटक तपाईंले URL पहुँच गर्नुभयो भने, तपाईंले पाठ्यक्रमको रूपरेखा देख्नु पर्नेछ र कुनै पनि `*.ipynb` file. For example, `08-building-search-applications/python/oai-solution.ipynb`.

### Running in a container

An alternative to setting everything up on your computer or Codespace is to use a [container](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). The special `.devcontainer` folder within the course repository makes it possible for VS Code to set up the project within a container. Outside of Codespaces, this will require the installation of Docker, and quite frankly, it involves a bit of work, so we recommend this only to those with experience working with containers.

One of the best ways to keep your API keys secure when using GitHub Codespaces is by using Codespace Secrets. Please follow the [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) guide to learn more about this.

## Lessons and Technical Requirements

The course has 6 concept lessons and 6 coding lessons.

For the coding lessons, we are using the Azure OpenAI Service. You will need access to the Azure OpenAI service and an API key to run this code. You can apply to get access by [completing this application](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

While you wait for your application to be processed, each coding lesson also includes a `README.md` फाइलमा जान सक्नुहुन्छ जहाँ तपाईं कोड र आउटपुटहरू हेर्न सक्नुहुन्छ।

## Azure OpenAI सेवा पहिलो पटक प्रयोग गर्दै

यदि यो Azure OpenAI सेवासँग काम गर्ने तपाईंको पहिलो पटक हो भने, कृपया [Azure OpenAI सेवा स्रोत सिर्जना र परिनियोजन गर्ने](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst) कसरी गर्ने बारेमा यो मार्गदर्शन अनुसरण गर्नुहोस्।

## OpenAI API पहिलो पटक प्रयोग गर्दै

यदि यो OpenAI API सँग काम गर्ने तपाईंको पहिलो पटक हो भने, कृपया [इन्टरफेस सिर्जना र प्रयोग गर्ने](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst) कसरी गर्ने बारेमा मार्गदर्शन अनुसरण गर्नुहोस्।

## अन्य शिक्षार्थीहरूलाई भेट्नुहोस्

हामीले हाम्रो आधिकारिक [AI Community Discord सर्भर](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) मा अन्य शिक्षार्थीहरूलाई भेट्नको लागि च्यानलहरू सिर्जना गरेका छौं। यो Generative AI मा स्तरवृद्धि गर्न खोज्ने अन्य समान विचारधारा भएका उद्यमीहरू, निर्माताहरू, विद्यार्थीहरू, र जो कोहीसँग नेटवर्किङ्ग गर्ने एक महान तरिका हो।

[![Join discord channel](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

परियोजना टोली पनि यस Discord सर्भरमा कुनै पनि शिक्षार्थीहरूलाई मद्दत गर्न उपस्थित हुनेछ।

## योगदान गर्नुहोस्

यो पाठ्यक्रम एक खुला-स्रोत पहल हो। यदि तपाईंले सुधारका क्षेत्रहरू वा समस्याहरू देख्नुहुन्छ भने, कृपया [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) सिर्जना गर्नुहोस् वा [GitHub समस्या](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) लग गर्नुहोस्।

परियोजना टोलीले सबै योगदानहरू ट्र्याक गर्नेछ। खुला स्रोतमा योगदान गर्नु भनेको Generative AI मा तपाईंको करियर निर्माण गर्ने एक अद्भुत तरिका हो।

धेरैजसो योगदानहरूले तपाईंलाई Contributor License Agreement (CLA) मा सहमत हुन आवश्यक पर्दछ जसले तपाईंलाई अधिकार छ र वास्तवमा हामीलाई तपाईंको योगदान प्रयोग गर्ने अधिकार दिन्छ। विवरणको लागि, [CLA, Contributor License Agreement वेबसाइट](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) हेर्नुहोस्।

महत्त्वपूर्ण: यस repo मा पाठ्यक्रम अनुवाद गर्दा, कृपया सुनिश्चित गर्नुहोस् कि तपाईंले मेसिन अनुवाद प्रयोग गर्नुहुन्न। हामी समुदाय मार्फत अनुवादहरूको पुष्टि गर्नेछौं, त्यसैले कृपया केवल ती भाषाहरूमा अनुवादको लागि स्वयंसेवा गर्नुहोस् जहाँ तपाईंलाई दक्षता छ।

जब तपाईंले pull request सबमिट गर्नुहुन्छ, CLA-bot ले स्वचालित रूपमा निर्धारण गर्नेछ कि तपाईंले CLA प्रदान गर्नु आवश्यक छ कि छैन र PR लाई उपयुक्त रूपमा सजाउनुहोस् (जस्तै, लेबल, टिप्पणी)। तपाईंलाई हाम्रो CLA प्रयोग गर्ने सबै रिपोजिटरीहरूमा मात्र एक पटक यो गर्न आवश्यक हुनेछ।

यस परियोजनाले [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) अपनाएको छ। थप जानकारीको लागि Code of Conduct FAQ पढ्नुहोस् वा [Email opencode](opencode@microsoft.com) मा कुनै पनि थप प्रश्न वा टिप्पणीहरूको साथ सम्पर्क गर्नुहोस्।

## सुरु गरौं

अब तपाईंले यो पाठ्यक्रम पूरा गर्न आवश्यक चरणहरू पूरा गर्नुभएको छ, [Generative AI र LLMs को परिचय](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) प्राप्त गरेर सुरु गरौं।

**अस्वीकरण**:  
यो कागजात AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) प्रयोग गरेर अनुवाद गरिएको हो। हामी शुद्धताको लागि प्रयास गर्छौं, तर कृपया जानकार रहनुहोस् कि स्वचालित अनुवादमा त्रुटिहरू वा असमानताहरू हुन सक्छन्। यसको मूल भाषामा रहेको कागजातलाई आधिकारिक स्रोतको रूपमा मान्नुपर्छ। महत्वपूर्ण जानकारीको लागि, व्यावसायिक मानव अनुवाद सिफारिस गरिन्छ। यस अनुवादको प्रयोगबाट उत्पन्न कुनै पनि गलतफहमी वा गलत व्याख्याको लागि हामी जिम्मेवार हुने छैनौं।