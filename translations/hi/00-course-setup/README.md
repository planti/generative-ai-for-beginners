<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9f4785899ee92500f524b4acb26e3bb3",
  "translation_date": "2025-05-19T09:00:09+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "hi"
}
-->
# इस कोर्स की शुरुआत

हम इस कोर्स को शुरू करने के लिए आपके उत्साह को लेकर बहुत उत्साहित हैं और देखना चाहते हैं कि आप जेनरेटिव एआई के साथ क्या बना सकते हैं!

आपकी सफलता सुनिश्चित करने के लिए, इस पेज में सेटअप स्टेप्स, तकनीकी आवश्यकताएँ, और यदि आवश्यक हो तो मदद कैसे प्राप्त करें, यह सब वर्णित है।

## सेटअप स्टेप्स

इस कोर्स को शुरू करने के लिए, आपको निम्नलिखित चरणों को पूरा करना होगा।

### 1. इस रिपो को फोर्क करें

[इस पूरे रिपो को फोर्क करें](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) अपने खुद के GitHub अकाउंट पर ताकि आप किसी भी कोड को बदल सकें और चुनौतियों को पूरा कर सकें। आप इसे [स्टार (🌟) भी कर सकते हैं](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) ताकि इसे और संबंधित रिपो को आसानी से खोज सकें।

### 2. एक कोडस्पेस बनाएं

कोड चलाते समय किसी भी निर्भरता समस्या से बचने के लिए, हम इस कोर्स को [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) में चलाने की सलाह देते हैं।

यह आपके फोर्क किए गए संस्करण में `Code` विकल्प चुनकर और **Codespaces** विकल्प चुनकर बनाया जा सकता है।

![कोडस्पेस बनाने के लिए बटन दिखाने वाला डायलॉग](../../../00-course-setup/images/who-will-pay.webp)

### 3. अपने API कुंजियों को सुरक्षित रखना

किसी भी प्रकार के एप्लिकेशन को बनाते समय अपने API कुंजियों को सुरक्षित और सुरक्षित रखना महत्वपूर्ण है। हम सलाह देते हैं कि किसी भी API कुंजी को सीधे आपके कोड में न रखें। उन विवरणों को सार्वजनिक रिपॉजिटरी में प्रतिबद्ध करना सुरक्षा समस्याओं और यहां तक कि अवांछित लागतों का परिणाम हो सकता है यदि किसी बुरे अभिनेता द्वारा उपयोग किया जाता है।
यहां Python के लिए `.env` फ़ाइल बनाने और `GITHUB_TOKEN` जोड़ने का चरण-दर-चरण मार्गदर्शिका है:

1. **अपने प्रोजेक्ट डायरेक्टरी में नेविगेट करें**: अपना टर्मिनल या कमांड प्रॉम्प्ट खोलें और अपने प्रोजेक्ट की रूट डायरेक्टरी पर नेविगेट करें जहां आप `.env` फ़ाइल बनाना चाहते हैं।

   ```bash
   cd path/to/your/project
   ```

2. **`.env` फ़ाइल बनाएं**: अपने पसंदीदा टेक्स्ट एडिटर का उपयोग करके `.env` नामक एक नई फ़ाइल बनाएं। यदि आप कमांड लाइन का उपयोग कर रहे हैं, तो आप Windows पर `touch` (on Unix-based systems) or `echo` का उपयोग कर सकते हैं:

   Unix-आधारित सिस्टम:
   ```bash
   touch .env
   ```

   Windows:
   ```cmd
   echo . > .env
   ```

3. **`.env` फ़ाइल संपादित करें**: `.env` फ़ाइल को टेक्स्ट एडिटर (जैसे, VS Code, Notepad++, या कोई अन्य एडिटर) में खोलें। फ़ाइल में निम्नलिखित पंक्ति जोड़ें, `your_github_token_here` को आपके वास्तविक GitHub टोकन से बदलें:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **फ़ाइल सहेजें**: परिवर्तन सहेजें और टेक्स्ट एडिटर बंद करें।

5. **`python-dotenv`**: If you haven't already, you'll need to install the `python-dotenv` पैकेज इंस्टॉल करें ताकि पर्यावरण चर को `.env` फ़ाइल से आपके Python एप्लिकेशन में लोड किया जा सके। आप इसे `pip` का उपयोग करके इंस्टॉल कर सकते हैं:

   ```bash
   pip install python-dotenv
   ```

6. **अपने Python स्क्रिप्ट में पर्यावरण चर लोड करें**: अपने Python स्क्रिप्ट में, `.env` फ़ाइल से पर्यावरण चर लोड करने के लिए `python-dotenv` पैकेज का उपयोग करें:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

बस इतना ही! आपने सफलतापूर्वक `.env` फ़ाइल बनाई, अपने GitHub टोकन जोड़ा, और इसे अपने Python एप्लिकेशन में लोड किया।

## अपने कंप्यूटर पर स्थानीय रूप से कैसे चलाएं

अपने कंप्यूटर पर कोड को स्थानीय रूप से चलाने के लिए, आपके पास कुछ संस्करण [Python इंस्टॉल होना चाहिए](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst)।

फिर रिपॉजिटरी का उपयोग करने के लिए, आपको इसे क्लोन करना होगा:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

एक बार जब आपके पास सब कुछ चेक आउट हो जाए, तो आप शुरू कर सकते हैं!

## वैकल्पिक चरण

### Miniconda इंस्टॉल करना

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, और कुछ पैकेज इंस्टॉल करने के लिए एक हल्का इंस्टॉलर है।
Conda खुद एक पैकेज मैनेजर है, जो विभिन्न Python [**वर्चुअल एनवायरनमेंट्स**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) और पैकेज के बीच सेटअप और स्विच करना आसान बनाता है। यह `pip`.

You can follow the [MiniConda installation guide](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) to set it up.

With Miniconda installed, you need to clone the [repository](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (if you haven't already)

Next, you need to create a virtual environment. To do this with Conda, go ahead and create a new environment file (_environment.yml_). If you are following along using Codespaces, create this within the `.devcontainer` directory, thus `.devcontainer/environment.yml` के माध्यम से उपलब्ध नहीं होने वाले पैकेज इंस्टॉल करने में भी काम आता है।

नीचे दिए गए स्निपेट के साथ अपनी एनवायरनमेंट फ़ाइल को भरें:

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

यदि आपको conda का उपयोग करते समय त्रुटियाँ मिलती हैं, तो आप निम्नलिखित कमांड का उपयोग करके Microsoft AI लाइब्रेरीज़ को मैन्युअल रूप से इंस्टॉल कर सकते हैं।

```
conda install -c microsoft azure-ai-ml
```

एनवायरनमेंट फ़ाइल में आवश्यकताएँ निर्दिष्ट की गई हैं। `<environment-name>` refers to the name you would like to use for your Conda environment, and `<python-version>` is the version of Python you would like to use, for example, `3` Python का नवीनतम प्रमुख संस्करण है।

इसके साथ, आप अपने कमांड लाइन/टर्मिनल में नीचे दिए गए कमांड्स को चलाकर अपने Conda एनवायरनमेंट को बना सकते हैं

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

यदि आप किसी समस्या में पड़ते हैं, तो [Conda एनवायरनमेंट्स गाइड](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) देखें।

### Python समर्थन एक्सटेंशन के साथ Visual Studio Code का उपयोग करना

हम इस कोर्स के लिए [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) एडिटर का उपयोग करने की सलाह देते हैं जिसमें [Python समर्थन एक्सटेंशन](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) इंस्टॉल किया गया है। हालांकि, यह एक सिफारिश है और कोई निश्चित आवश्यकता नहीं है।

> **ध्यान दें**: VS Code में कोर्स रिपॉजिटरी को खोलकर, आपके पास प्रोजेक्ट को एक कंटेनर के भीतर सेट करने का विकल्प होता है। ऐसा [विशेष `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) डायरेक्टरी के कारण होता है जो कोर्स रिपॉजिटरी में पाई जाती है। इसके बारे में बाद में अधिक।

> **ध्यान दें**: जब आप डायरेक्टरी को क्लोन और VS Code में खोलते हैं, तो यह स्वचालित रूप से आपको Python समर्थन एक्सटेंशन इंस्टॉल करने का सुझाव देगा।

> **ध्यान दें**: यदि VS Code आपको रिपॉजिटरी को एक कंटेनर में पुनः खोलने का सुझाव देता है, तो इस अनुरोध को अस्वीकार करें ताकि Python के स्थानीय रूप से इंस्टॉल किए गए संस्करण का उपयोग कर सकें।

### ब्राउज़र में Jupyter का उपयोग करना

आप ब्राउज़र में [Jupyter एनवायरनमेंट](https://jupyter.org?WT.mc_id=academic-105485-koreyst) का उपयोग करके प्रोजेक्ट पर काम कर सकते हैं। क्लासिक Jupyter और [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) ऑटो-कम्प्लीशन, कोड हाइलाइटिंग जैसी सुविधाओं के साथ एक सुखद विकास वातावरण प्रदान करते हैं।

स्थानीय रूप से Jupyter शुरू करने के लिए, टर्मिनल/कमांड लाइन पर जाएं, कोर्स डायरेक्टरी पर नेविगेट करें, और निम्नलिखित को निष्पादित करें:

```bash
jupyter notebook
```

या

```bash
jupyterhub
```

यह एक Jupyter इंस्टेंस शुरू करेगा और इसे एक्सेस करने के लिए URL कमांड लाइन विंडो में दिखाया जाएगा।

एक बार जब आप URL तक पहुँच जाते हैं, तो आपको कोर्स की रूपरेखा दिखाई देनी चाहिए और किसी भी `*.ipynb` file. For example, `08-building-search-applications/python/oai-solution.ipynb`.

### Running in a container

An alternative to setting everything up on your computer or Codespace is to use a [container](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). The special `.devcontainer` folder within the course repository makes it possible for VS Code to set up the project within a container. Outside of Codespaces, this will require the installation of Docker, and quite frankly, it involves a bit of work, so we recommend this only to those with experience working with containers.

One of the best ways to keep your API keys secure when using GitHub Codespaces is by using Codespace Secrets. Please follow the [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) guide to learn more about this.

## Lessons and Technical Requirements

The course has 6 concept lessons and 6 coding lessons.

For the coding lessons, we are using the Azure OpenAI Service. You will need access to the Azure OpenAI service and an API key to run this code. You can apply to get access by [completing this application](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

While you wait for your application to be processed, each coding lesson also includes a `README.md` फ़ाइल पर नेविगेट करने में सक्षम होना चाहिए जहां आप कोड और आउटपुट देख सकते हैं।

## Azure OpenAI सेवा का पहली बार उपयोग करना

यदि यह आपका Azure OpenAI सेवा के साथ काम करने का पहला अवसर है, तो कृपया [Azure OpenAI सेवा संसाधन को बनाने और तैनात करने के तरीके पर इस गाइड का पालन करें।](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst)

## OpenAI API का पहली बार उपयोग करना

यदि यह आपका OpenAI API के साथ काम करने का पहला अवसर है, तो कृपया [इंटरफ़ेस को बनाने और उपयोग करने के तरीके पर इस गाइड का पालन करें।](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst)

## अन्य शिक्षार्थियों से मिलें

हमने अन्य शिक्षार्थियों से मिलने के लिए हमारे आधिकारिक [AI कम्युनिटी Discord सर्वर](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) में चैनल बनाए हैं। यह जेनरेटिव एआई में स्तर बढ़ाने के लिए अन्य समान विचारधारा वाले उद्यमियों, निर्माताओं, छात्रों, और किसी के साथ नेटवर्किंग का एक शानदार तरीका है।

[![Discord चैनल में शामिल हों](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

प्रोजेक्ट टीम भी इस Discord सर्वर पर किसी भी शिक्षार्थियों की मदद करने के लिए होगी।

## योगदान करें

यह कोर्स एक ओपन-सोर्स पहल है। यदि आप सुधार या मुद्दों के क्षेत्र देखते हैं, तो कृपया एक [पुल रिक्वेस्ट](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) बनाएं या एक [GitHub मुद्दा](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) लॉग करें।

प्रोजेक्ट टीम सभी योगदानों को ट्रैक करेगी। ओपन सोर्स में योगदान करना जेनरेटिव एआई में अपना करियर बनाने का एक अद्भुत तरीका है।

अधिकांश योगदानों के लिए आपको एक Contributor License Agreement (CLA) पर सहमत होना आवश्यक होता है, जिसमें यह घोषणा होती है कि आपके पास योगदान करने का अधिकार है और वास्तव में आप हमें अपने योगदान का उपयोग करने का अधिकार देते हैं। विवरण के लिए, [CLA, Contributor License Agreement वेबसाइट](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) पर जाएं।

महत्वपूर्ण: इस रिपो में टेक्स्ट का अनुवाद करते समय, कृपया सुनिश्चित करें कि आप मशीन अनुवाद का उपयोग नहीं करते हैं। हम अनुवादों को समुदाय के माध्यम से सत्यापित करेंगे, इसलिए कृपया केवल उन भाषाओं में अनुवाद के लिए स्वयंसेवा करें जिनमें आप कुशल हैं।

जब आप एक पुल रिक्वेस्ट सबमिट करते हैं, तो एक CLA-बॉट स्वचालित रूप से निर्धारित करेगा कि आपको CLA प्रदान करने की आवश्यकता है और PR को उपयुक्त रूप से सजाएगा (जैसे, लेबल, टिप्पणी)। बस बॉट द्वारा प्रदान किए गए निर्देशों का पालन करें। आपको हमारे CLA का उपयोग करने वाले सभी रिपॉजिटरी में केवल एक बार ऐसा करना होगा।

इस प्रोजेक्ट ने [Microsoft ओपन सोर्स आचार संहिता](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) को अपनाया है। अधिक जानकारी के लिए आचार संहिता FAQ पढ़ें या [Email opencode](opencode@microsoft.com) से किसी भी अतिरिक्त प्रश्न या टिप्पणियों के साथ संपर्क करें।

## चलिए शुरू करें

अब जब आपने इस कोर्स को पूरा करने के लिए आवश्यक चरणों को पूरा कर लिया है, तो चलिए जेनरेटिव एआई और LLMs का [परिचय प्राप्त करके](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) शुरू करते हैं।

**अस्वीकरण**:  
यह दस्तावेज़ AI अनुवाद सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) का उपयोग करके अनुवादित किया गया है। जबकि हम सटीकता के लिए प्रयासरत हैं, कृपया ध्यान दें कि स्वचालित अनुवाद में त्रुटियां या अशुद्धियाँ हो सकती हैं। मूल भाषा में मूल दस्तावेज़ को आधिकारिक स्रोत माना जाना चाहिए। महत्वपूर्ण जानकारी के लिए, पेशेवर मानव अनुवाद की सिफारिश की जाती है। इस अनुवाद के उपयोग से उत्पन्न किसी भी गलतफहमी या गलत व्याख्या के लिए हम उत्तरदायी नहीं हैं।