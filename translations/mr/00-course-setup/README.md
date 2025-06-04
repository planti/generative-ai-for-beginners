<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9f4785899ee92500f524b4acb26e3bb3",
  "translation_date": "2025-05-19T12:21:13+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "mr"
}
-->
# या कोर्ससह सुरुवात करणे

तुम्ही हा कोर्स सुरू करण्यासाठी आणि जनरेटिव्ह AI सह काय निर्माण करण्याची प्रेरणा मिळते ते पाहण्यासाठी आम्ही खूप उत्सुक आहोत!

तुमच्या यशाची खात्री करण्यासाठी, ही पृष्ठे सेटअप पद्धती, तांत्रिक आवश्यकता, आणि जर आवश्यक असेल तर मदत कुठे मिळेल याची माहिती देते.

## सेटअप पद्धती

हा कोर्स सुरू करण्यासाठी, तुम्हाला खालील पद्धती पूर्ण कराव्या लागतील.

### 1. या रेपोला फोर्क करा

तुमच्या स्वतःच्या GitHub खात्यावर [या संपूर्ण रेपोला फोर्क करा](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) जेणेकरून तुम्ही कोणताही कोड बदलू शकाल आणि आव्हाने पूर्ण करू शकाल. तुम्ही [या रेपोला स्टार (🌟) देखील देऊ शकता](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst) जेणेकरून तुम्हाला ते आणि संबंधित रेपो सहज सापडतील.

### 2. कोडस्पेस तयार करा

कोड चालवताना कोणत्याही अवलंबित्वाच्या समस्या टाळण्यासाठी, आम्ही हा कोर्स [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) मध्ये चालवण्याची शिफारस करतो.

हे तुमच्या फोर्क केलेल्या रेपोवर `Code` पर्याय निवडून आणि **Codespaces** पर्याय निवडून तयार केले जाऊ शकते.

![कोडस्पेस तयार करण्यासाठी बटणांचे संवाद दर्शवित आहे](../../../00-course-setup/images/who-will-pay.webp)

### 3. तुमचे API कीज साठवणे

कोणत्याही प्रकारचे अनुप्रयोग तयार करताना तुमचे API कीज सुरक्षित ठेवणे महत्त्वाचे आहे. आम्ही शिफारस करतो की तुमच्या कोडमध्ये कोणतेही API कीज थेट साठवू नका. त्या तपशीलांना सार्वजनिक रेपोमध्ये कमिट केल्याने सुरक्षा समस्या निर्माण होऊ शकतात आणि खराब व्यक्तीद्वारे वापरल्यास अनावश्यक खर्च देखील होऊ शकतो. Python साठी `.env` फाईल कशी तयार करावी आणि `GITHUB_TOKEN` कसे जोडावे याबद्दल येथे एक स्टेप-बाय-स्टेप मार्गदर्शक आहे:

1. **तुमच्या प्रोजेक्ट डायरेक्टरीवर जा**: तुमचा टर्मिनल किंवा कमांड प्रॉम्प्ट उघडा आणि ज्या ठिकाणी तुम्हाला `.env` फाईल तयार करायची आहे त्या प्रोजेक्टच्या मूळ डायरेक्टरीवर जा.

   ```bash
   cd path/to/your/project
   ```

2. **`.env` फाईल तयार करा**: तुमच्या पसंतीच्या टेक्स्ट एडिटरचा वापर करून `.env` नावाची नवीन फाईल तयार करा. तुम्ही कमांड लाइन वापरत असल्यास, तुम्ही `touch` (on Unix-based systems) or `echo` (Windows वर) वापरू शकता:

   युनिक्स-आधारित प्रणाली:
   ```bash
   touch .env
   ```

   Windows:
   ```cmd
   echo . > .env
   ```

3. **`.env` फाईल संपादित करा**: `.env` फाईल टेक्स्ट एडिटरमध्ये (उदा., VS Code, Notepad++, किंवा इतर कोणत्याही एडिटरमध्ये) उघडा. खालील ओळ फाईलमध्ये जोडा, `your_github_token_here` तुमच्या वास्तविक GitHub टोकनने बदला:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **फाईल सेव्ह करा**: बदल सेव्ह करा आणि टेक्स्ट एडिटर बंद करा.

5. **`python-dotenv`**: If you haven't already, you'll need to install the `python-dotenv` पॅकेज स्थापित करा जेणेकरून `.env` फाईलमधून पर्यावरणीय चल लोड करता येतील. तुम्ही ते `pip` वापरून स्थापित करू शकता:

   ```bash
   pip install python-dotenv
   ```

6. **तुमच्या Python स्क्रिप्टमध्ये पर्यावरणीय चल लोड करा**: तुमच्या Python स्क्रिप्टमध्ये, `.env` फाईलमधून पर्यावरणीय चल लोड करण्यासाठी `python-dotenv` पॅकेज वापरा:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

हे झाले! तुम्ही यशस्वीरित्या `.env` फाईल तयार केली आहे, तुमचे GitHub टोकन जोडले आहे, आणि ते तुमच्या Python अनुप्रयोगात लोड केले आहे.

## तुमच्या संगणकावर स्थानिकपणे कसे चालवायचे

तुमच्या संगणकावर स्थानिकपणे कोड चालवण्यासाठी, तुम्हाला काही आवृत्ती [Python ची स्थापना](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst) आवश्यक आहे.

त्यानंतर रेपो वापरण्यासाठी, तुम्हाला ते क्लोन करणे आवश्यक आहे:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

एकदा तुम्ही सर्व काही तपासले की, तुम्ही सुरुवात करू शकता!

## ऐच्छिक पद्धती

### Miniconda स्थापित करणे

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) हा [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, तसेच काही पॅकेजेस स्थापित करण्यासाठी एक हलका इंस्टॉलर आहे. Conda स्वतः एक पॅकेज व्यवस्थापक आहे, जो वेगवेगळ्या Python [**आभासी वातावरणे**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) आणि पॅकेजेस सेटअप आणि स्विच करणे सोपे बनवतो. `pip`.

You can follow the [MiniConda installation guide](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) to set it up.

With Miniconda installed, you need to clone the [repository](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (if you haven't already)

Next, you need to create a virtual environment. To do this with Conda, go ahead and create a new environment file (_environment.yml_). If you are following along using Codespaces, create this within the `.devcontainer` directory, thus `.devcontainer/environment.yml` द्वारे उपलब्ध नसलेल्या पॅकेजेस स्थापित करण्यासाठी हे उपयुक्त आहे.

खालील स्निपेटसह तुमच्या वातावरण फाईलला भरा:

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

जर तुम्हाला conda वापरताना त्रुटी आल्यास, तुम्ही खालील आदेश टर्मिनलमध्ये वापरून Microsoft AI लायब्ररीस मॅन्युअली स्थापित करू शकता.

```
conda install -c microsoft azure-ai-ml
```

वातावरण फाईल आमच्यासाठी आवश्यक अवलंबित्व दर्शवते. `<environment-name>` refers to the name you would like to use for your Conda environment, and `<python-version>` is the version of Python you would like to use, for example, `3` ही Python ची नवीनतम प्रमुख आवृत्ती आहे.

हे झाल्यावर, तुम्ही खालील आदेश चालवून तुमचे Conda वातावरण तयार करू शकता

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

जर तुम्हाला कोणत्याही समस्यांचा सामना करावा लागला तर [Conda वातावरण मार्गदर्शक](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) पहा.

### Python समर्थन विस्तारासह Visual Studio Code वापरणे

आम्ही या कोर्ससाठी [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) एडिटर आणि [Python समर्थन विस्तार](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) स्थापित करण्याची शिफारस करतो. हे, तथापि, अधिक शिफारस आहे आणि निश्चित आवश्यकता नाही

> **टीप**: VS Code मध्ये कोर्स रेपो उघडल्याने, तुम्हाला प्रकल्प एका कंटेनरमध्ये सेट करण्याचा पर्याय आहे. हे कोर्स रेपोमध्ये असलेल्या [विशेष `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) निर्देशिकेमुळे आहे. याबद्दल अधिक नंतर.

> **टीप**: एकदा तुम्ही रेपो क्लोन करून ते VS Code मध्ये उघडल्यावर, ते तुम्हाला Python समर्थन विस्तार स्थापित करण्याचे सुचवेल.

> **टीप**: जर VS Code तुम्हाला रेपो कंटेनरमध्ये पुन्हा उघडण्याची सूचना दिली, तर स्थानिकपणे स्थापित केलेल्या Python आवृत्तीचा वापर करण्यासाठी हे विनंती नाकारावे.

### ब्राउझरमध्ये Jupyter वापरणे

तुम्ही तुमच्या ब्राउझरमध्ये [Jupyter वातावरण](https://jupyter.org?WT.mc_id=academic-105485-koreyst) वापरून प्रकल्पावर काम देखील करू शकता. क्लासिक Jupyter आणि [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) दोन्ही ऑटो-कम्प्लीशन, कोड हायलाइटिंग इत्यादी वैशिष्ट्यांसह एक आनंददायक विकास वातावरण प्रदान करतात.

स्थानिकपणे Jupyter सुरू करण्यासाठी, टर्मिनल/कमांड लाइनवर जा, कोर्स निर्देशिकेवर जा, आणि कार्यान्वित करा:

```bash
jupyter notebook
```

किंवा

```bash
jupyterhub
```

हे Jupyter उदाहरण सुरू करेल आणि त्याचा प्रवेश करण्यासाठी URL कमांड लाइन विंडोमध्ये दाखवला जाईल.

एकदा तुम्ही URL वर प्रवेश केल्यावर, तुम्हाला कोर्सची रूपरेषा दिसेल आणि कोणत्याही `*.ipynb` file. For example, `08-building-search-applications/python/oai-solution.ipynb`.

### Running in a container

An alternative to setting everything up on your computer or Codespace is to use a [container](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). The special `.devcontainer` folder within the course repository makes it possible for VS Code to set up the project within a container. Outside of Codespaces, this will require the installation of Docker, and quite frankly, it involves a bit of work, so we recommend this only to those with experience working with containers.

One of the best ways to keep your API keys secure when using GitHub Codespaces is by using Codespace Secrets. Please follow the [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) guide to learn more about this.

## Lessons and Technical Requirements

The course has 6 concept lessons and 6 coding lessons.

For the coding lessons, we are using the Azure OpenAI Service. You will need access to the Azure OpenAI service and an API key to run this code. You can apply to get access by [completing this application](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

While you wait for your application to be processed, each coding lesson also includes a `README.md` फाईलवर जाऊन कोड आणि आउटपुट पाहता येतील.

## प्रथमच Azure OpenAI सेवा वापरणे

जर तुम्ही प्रथमच Azure OpenAI सेवा वापरत असाल, तर कृपया [Azure OpenAI सेवा संसाधन कसे तयार करावे आणि तैनात करावे](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst) याबद्दलच्या मार्गदर्शकाचे अनुसरण करा.

## प्रथमच OpenAI API वापरणे

जर तुम्ही प्रथमच OpenAI API वापरत असाल, तर कृपया [इंटरफेस तयार करण्याची आणि वापरण्याची मार्गदर्शिका](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst) अनुसरण करा.

## इतर शिकणाऱ्यांना भेटा

इतर शिकणाऱ्यांना भेटण्यासाठी आम्ही आमच्या अधिकृत [AI Community Discord सर्व्हर](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) मध्ये चॅनेल तयार केले आहेत. हे जनरेटिव्ह AI मध्ये स्तर उंचावण्याचा विचार करणाऱ्या समान विचारांच्या उद्योजक, निर्माते, विद्यार्थी आणि कोणालाही नेटवर्क करण्याचा एक उत्तम मार्ग आहे.

[![डिस्कॉर्ड चॅनेलमध्ये सामील व्हा](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

प्रकल्प टीम देखील कोणत्याही शिकणाऱ्यांना मदत करण्यासाठी या Discord सर्व्हरवर असेल.

## योगदान करा

हा कोर्स एक ओपन-सोर्स उपक्रम आहे. जर तुम्हाला सुधारणा किंवा समस्या दिसल्या तर कृपया [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) तयार करा किंवा [GitHub समस्या](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) लॉग करा.

प्रकल्प टीम सर्व योगदानांचे निरीक्षण करेल. ओपन सोर्समध्ये योगदान करणे हे जनरेटिव्ह AI मध्ये तुमचे करिअर निर्माण करण्याचा एक अद्भुत मार्ग आहे.

ज्याद्वारे तुम्ही तुमच्या योगदानाचे अधिकार आम्हाला देण्याचा अधिकार आहे हे घोषित करणारा Contributor License Agreement (CLA) सह बहुतेक योगदानांची आवश्यकता आहे. तपशीलांसाठी, [CLA, Contributor License Agreement वेबसाइट](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) भेट द्या.

महत्त्वाचे: या रेपोमध्ये मजकूर अनुवाद करताना, कृपया मशीन अनुवादाचा वापर करू नका याची खात्री करा. आम्ही समुदायाद्वारे अनुवाद सत्यापित करू, त्यामुळे कृपया फक्त त्या भाषांमध्ये अनुवादांसाठी स्वयंसेवा करा ज्या भाषांमध्ये तुम्ही प्रवीण आहात.

जेव्हा तुम्ही एक पुल विनंती सबमिट करता, तेव्हा एक CLA-बॉट स्वयंचलितपणे ठरवेल की तुम्हाला CLA प्रदान करणे आवश्यक आहे का आणि PR योग्यरित्या सजवेल (उदा., लेबल, टिप्पणी). बॉटद्वारे प्रदान केलेल्या सूचनांचे अनुसरण करा. आमच्या CLA चा वापर करून सर्व रेपोसिटरीजमध्ये तुम्हाला हे एकदाच करावे लागेल.

या प्रकल्पाने [Microsoft ओपन सोर्स आचारसंहिता](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) स्वीकारली आहे. अधिक माहितीसाठी आचारसंहिता FAQ वाचा किंवा [Email opencode](opencode@microsoft.com) वर कोणत्याही अतिरिक्त प्रश्नांसह संपर्क साधा.

## चला सुरूवात करूया

आता तुम्ही हा कोर्स पूर्ण करण्यासाठी आवश्यक पद्धती पूर्ण केल्या आहेत, चला [जनरेटिव्ह AI आणि LLMs परिचय](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) घेऊन सुरू करूया.

**अस्वीकृति**:
हे दस्तऐवज AI भाषांतर सेवा [Co-op Translator](https://github.com/Azure/co-op-translator) वापरून भाषांतरित केले गेले आहे. आम्ही अचूकतेसाठी प्रयत्न करतो, कृपया लक्षात ठेवा की स्वयंचलित भाषांतरे त्रुटी किंवा अचूकतेच्या अभावासह असू शकतात. मूळ भाषेतील दस्तऐवज अधिकृत स्रोत म्हणून विचारात घेतला पाहिजे. गंभीर माहिती साठी, व्यावसायिक मानवी भाषांतराची शिफारस केली जाते. या भाषांतराच्या वापरामुळे उद्भवलेल्या कोणत्याही गैरसमजुती किंवा चुकीच्या अर्थासाठी आम्ही जबाबदार नाही.