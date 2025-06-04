<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "9f4785899ee92500f524b4acb26e3bb3",
  "translation_date": "2025-05-19T12:20:29+00:00",
  "source_file": "00-course-setup/README.md",
  "language_code": "bn"
}
-->
# এই কোর্সের সাথে শুরু করা

আপনি এই কোর্সটি শুরু করতে যাচ্ছেন এবং Generative AI দিয়ে কী তৈরি করতে অনুপ্রাণিত হন তা দেখার জন্য আমরা খুবই উত্তেজিত!

আপনার সাফল্য নিশ্চিত করার জন্য, এই পৃষ্ঠায় সেটআপ ধাপ, প্রযুক্তিগত প্রয়োজনীয়তা এবং প্রয়োজন হলে কোথায় সাহায্য পাবেন তা উল্লেখ করা হয়েছে।

## সেটআপ ধাপসমূহ

এই কোর্সটি শুরু করতে, আপনাকে নিম্নলিখিত ধাপগুলি সম্পূর্ণ করতে হবে।

### ১. এই রিপোটি ফর্ক করুন

এই সম্পূর্ণ রিপোটি [ফর্ক করুন](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) আপনার নিজস্ব GitHub অ্যাকাউন্টে যাতে আপনি যেকোন কোড পরিবর্তন করতে এবং চ্যালেঞ্জ সম্পন্ন করতে পারেন। আপনি এই রিপোটি এবং সম্পর্কিত রিপোগুলি সহজে খুঁজে পেতে [স্টার (🌟) দিতে পারেন](https://docs.github.com/en/get-started/exploring-projects-on-github/saving-repositories-with-stars?WT.mc_id=academic-105485-koreyst)।

### ২. একটি কোডস্পেস তৈরি করুন

কোড চালানোর সময় যেকোন নির্ভরতা সমস্যা এড়াতে, আমরা এই কোর্সটি একটি [GitHub Codespaces](https://github.com/features/codespaces?WT.mc_id=academic-105485-koreyst) এ চালানোর পরামর্শ দিই।

এটি তৈরি করা যায় আপনার ফর্ক করা রিপোতে `Code` বিকল্পটি নির্বাচন করে এবং **Codespaces** বিকল্পটি নির্বাচন করে।

![কোডস্পেস তৈরি করার বোতামগুলি দেখানো ডায়ালগ](../../../00-course-setup/images/who-will-pay.webp)

### ৩. আপনার API কীগুলি সংরক্ষণ করা

যেকোন ধরনের অ্যাপ্লিকেশন তৈরি করার সময় আপনার API কীগুলি নিরাপদ এবং সুরক্ষিত রাখা গুরুত্বপূর্ণ। আমরা সুপারিশ করি আপনার কোডে সরাসরি কোন API কী সংরক্ষণ না করতে। এই বিবরণগুলি একটি পাবলিক রিপোজিটরিতে কমিট করলে নিরাপত্তা সমস্যা এবং এমনকি অবাঞ্ছিত খরচ হতে পারে যদি কোন খারাপ ব্যক্তি এটি ব্যবহার করে। এখানে একটি `.env` ফাইল তৈরি করার জন্য এবং `GITHUB_TOKEN` যোগ করার জন্য ধাপে ধাপে গাইড দেওয়া হলো:

1. **আপনার প্রকল্পের ডিরেক্টরিতে যান**: আপনার টার্মিনাল বা কমান্ড প্রম্পট খুলুন এবং `.env` ফাইল তৈরি করতে চান এমন আপনার প্রকল্পের মূল ডিরেক্টরিতে যান।

   ```bash
   cd path/to/your/project
   ```

2. **`.env` ফাইল তৈরি করুন**: আপনার পছন্দের টেক্সট এডিটর ব্যবহার করে `.env` নামে একটি নতুন ফাইল তৈরি করুন। আপনি যদি কমান্ড লাইন ব্যবহার করছেন, তাহলে `touch` (on Unix-based systems) or `echo` (Windows এ):

   ইউনিক্স-ভিত্তিক সিস্টেম:
   ```bash
   touch .env
   ```

   Windows:
   ```cmd
   echo . > .env
   ```

3. **`.env` ফাইল সম্পাদনা করুন**: `.env` ফাইলটি একটি টেক্সট এডিটরে (যেমন VS Code, Notepad++, বা অন্য যেকোন এডিটর) খুলুন। ফাইলে নিম্নলিখিত লাইনটি যোগ করুন, `your_github_token_here` আপনার প্রকৃত GitHub টোকেন দিয়ে প্রতিস্থাপন করুন:

   ```env
   GITHUB_TOKEN=your_github_token_here
   ```

4. **ফাইলটি সংরক্ষণ করুন**: পরিবর্তনগুলি সংরক্ষণ করুন এবং টেক্সট এডিটরটি বন্ধ করুন।

5. **`python-dotenv`**: If you haven't already, you'll need to install the `python-dotenv` প্যাকেজ ইনস্টল করুন যা `.env` ফাইল থেকে আপনার Python অ্যাপ্লিকেশনে পরিবেশ ভেরিয়েবল লোড করবে। আপনি এটি `pip` ব্যবহার করে ইনস্টল করতে পারেন:

   ```bash
   pip install python-dotenv
   ```

6. **আপনার Python স্ক্রিপ্টে পরিবেশ ভেরিয়েবল লোড করুন**: আপনার Python স্ক্রিপ্টে, `.env` ফাইল থেকে পরিবেশ ভেরিয়েবল লোড করতে `python-dotenv` প্যাকেজটি ব্যবহার করুন:

   ```python
   from dotenv import load_dotenv
   import os

   # Load environment variables from .env file
   load_dotenv()

   # Access the GITHUB_TOKEN variable
   github_token = os.getenv("GITHUB_TOKEN")

   print(github_token)
   ```

এটাই! আপনি সফলভাবে একটি `.env` ফাইল তৈরি করেছেন, আপনার GitHub টোকেন যোগ করেছেন এবং এটি আপনার Python অ্যাপ্লিকেশনে লোড করেছেন।

## কিভাবে আপনার কম্পিউটারে লোকালি চালাবেন

আপনার কম্পিউটারে কোড লোকালি চালানোর জন্য, আপনার কাছে কিছু সংস্করণের [Python ইনস্টল করা](https://www.python.org/downloads/?WT.mc_id=academic-105485-koreyst) থাকতে হবে।

তারপর রিপোজিটরিটি ব্যবহার করতে, আপনাকে এটি ক্লোন করতে হবে:

```shell
git clone https://github.com/microsoft/generative-ai-for-beginners
cd generative-ai-for-beginners
```

আপনি যখন সবকিছু চেক আউট করবেন, তখন আপনি শুরু করতে পারেন!

## ঐচ্ছিক ধাপসমূহ

### Miniconda ইনস্টল করা

[Miniconda](https://conda.io/en/latest/miniconda.html?WT.mc_id=academic-105485-koreyst) হল [Conda](https://docs.conda.io/en/latest?WT.mc_id=academic-105485-koreyst), Python, এবং কয়েকটি প্যাকেজ ইনস্টল করার জন্য একটি হালকা ওজনের ইনস্টলার।
Conda নিজেই একটি প্যাকেজ ম্যানেজার, যা বিভিন্ন Python [**ভার্চুয়াল পরিবেশ**](https://docs.python.org/3/tutorial/venv.html?WT.mc_id=academic-105485-koreyst) এবং প্যাকেজ সেটআপ এবং স্যুইচ করা সহজ করে তোলে। এটি `pip`.

You can follow the [MiniConda installation guide](https://docs.anaconda.com/free/miniconda/#quick-command-line-install?WT.mc_id=academic-105485-koreyst) to set it up.

With Miniconda installed, you need to clone the [repository](https://github.com/microsoft/generative-ai-for-beginners/fork?WT.mc_id=academic-105485-koreyst) (if you haven't already)

Next, you need to create a virtual environment. To do this with Conda, go ahead and create a new environment file (_environment.yml_). If you are following along using Codespaces, create this within the `.devcontainer` directory, thus `.devcontainer/environment.yml` এর মাধ্যমে উপলব্ধ নয় এমন প্যাকেজ ইনস্টল করার জন্যও সহায়ক।

নিচের স্নিপেটটি দিয়ে আপনার পরিবেশ ফাইল পূরণ করুন:

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

যদি আপনি কন্ডা ব্যবহার করার সময় ত্রুটি পান তবে আপনি নিম্নলিখিত কমান্ডটি একটি টার্মিনালে ব্যবহার করে মাইক্রোসফট AI লাইব্রেরিগুলি ম্যানুয়ালি ইনস্টল করতে পারেন।

```
conda install -c microsoft azure-ai-ml
```

পরিবেশ ফাইলটি আমাদের প্রয়োজনীয় নির্ভরতাগুলি উল্লেখ করে। `<environment-name>` refers to the name you would like to use for your Conda environment, and `<python-version>` is the version of Python you would like to use, for example, `3` হল Python এর সর্বশেষ প্রধান সংস্করণ।

এটি সম্পন্ন হলে, আপনি আপনার কমান্ড লাইন/টার্মিনালে নিচের কমান্ডগুলি চালিয়ে আপনার কন্ডা পরিবেশ তৈরি করতে পারেন

```bash
conda env create --name ai4beg --file .devcontainer/environment.yml # .devcontainer sub path applies to only Codespace setups
conda activate ai4beg
```

যদি আপনি কোন সমস্যায় পড়েন তবে [কন্ডা পরিবেশের গাইড](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html?WT.mc_id=academic-105485-koreyst) দেখুন।

### Python সাপোর্ট এক্সটেনশনের সাথে Visual Studio Code ব্যবহার করা

আমরা এই কোর্সের জন্য [Visual Studio Code (VS Code)](https://code.visualstudio.com/?WT.mc_id=academic-105485-koreyst) এডিটর এবং [Python সাপোর্ট এক্সটেনশন](https://marketplace.visualstudio.com/items?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) ইনস্টল করার পরামর্শ দিচ্ছি। তবে এটি একটি সুপারিশ মাত্র, আবশ্যিক প্রয়োজনীয়তা নয়।

> **নোট**: কোর্স রিপোজিটরি VS Code এ খুলে, আপনি একটি কন্টেইনারের মধ্যে প্রকল্পটি সেট আপ করার বিকল্প পাবেন। এটি [বিশেষ `.devcontainer`](https://code.visualstudio.com/docs/devcontainers/containers?itemName=ms-python.python&WT.mc_id=academic-105485-koreyst) ডিরেক্টরির কারণে যা কোর্স রিপোজিটরির মধ্যে পাওয়া যায়। পরে এ সম্পর্কে আরও।

> **নোট**: আপনি যখন রিপোজিটরিটি ক্লোন করে VS Code এ খুলবেন, এটি আপনাকে স্বয়ংক্রিয়ভাবে একটি Python সাপোর্ট এক্সটেনশন ইনস্টল করার পরামর্শ দেবে।

> **নোট**: যদি VS Code আপনাকে একটি কন্টেইনারে রিপোজিটরিটি পুনরায় খুলতে বলে, স্থানীয়ভাবে ইনস্টল করা Python সংস্করণ ব্যবহার করার জন্য এই অনুরোধটি প্রত্যাখ্যান করুন।

### ব্রাউজারে Jupyter ব্যবহার করা

আপনি ব্রাউজারের মধ্যেই [Jupyter পরিবেশ](https://jupyter.org?WT.mc_id=academic-105485-koreyst) ব্যবহার করে প্রকল্পে কাজ করতে পারেন। উভয় ক্লাসিক Jupyter এবং [Jupyter Hub](https://jupyter.org/hub?WT.mc_id=academic-105485-koreyst) অটো-কমপ্লিশন, কোড হাইলাইটিং ইত্যাদি বৈশিষ্ট্য সহ একটি সুন্দর ডেভেলপমেন্ট পরিবেশ প্রদান করে।

লোকালিতে Jupyter শুরু করতে, টার্মিনাল/কমান্ড লাইনে যান, কোর্স ডিরেক্টরিতে যান এবং চালান:

```bash
jupyter notebook
```

অথবা

```bash
jupyterhub
```

এটি একটি Jupyter ইনস্ট্যান্স শুরু করবে এবং এটি অ্যাক্সেস করার URL কমান্ড লাইন উইন্ডোর মধ্যে দেখানো হবে।

আপনি একবার URL অ্যাক্সেস করলে, আপনি কোর্সের রূপরেখা দেখতে পাবেন এবং যেকোন `*.ipynb` file. For example, `08-building-search-applications/python/oai-solution.ipynb`.

### Running in a container

An alternative to setting everything up on your computer or Codespace is to use a [container](https://en.wikipedia.org/wiki/Containerization_(computing)?WT.mc_id=academic-105485-koreyst). The special `.devcontainer` folder within the course repository makes it possible for VS Code to set up the project within a container. Outside of Codespaces, this will require the installation of Docker, and quite frankly, it involves a bit of work, so we recommend this only to those with experience working with containers.

One of the best ways to keep your API keys secure when using GitHub Codespaces is by using Codespace Secrets. Please follow the [Codespaces secrets management](https://docs.github.com/en/codespaces/managing-your-codespaces/managing-secrets-for-your-codespaces?WT.mc_id=academic-105485-koreyst) guide to learn more about this.

## Lessons and Technical Requirements

The course has 6 concept lessons and 6 coding lessons.

For the coding lessons, we are using the Azure OpenAI Service. You will need access to the Azure OpenAI service and an API key to run this code. You can apply to get access by [completing this application](https://azure.microsoft.com/products/ai-services/openai-service?WT.mc_id=academic-105485-koreyst).

While you wait for your application to be processed, each coding lesson also includes a `README.md` ফাইলের কোড এবং আউটপুট দেখতে পারবেন।

## প্রথমবারের মতো Azure OpenAI পরিষেবা ব্যবহার করা

যদি এটি আপনার প্রথমবার Azure OpenAI পরিষেবার সাথে কাজ হয়, তবে কিভাবে [একটি Azure OpenAI পরিষেবা রিসোর্স তৈরি এবং স্থাপন করবেন](https://learn.microsoft.com/azure/ai-services/openai/how-to/create-resource?pivots=web-portal&WT.mc_id=academic-105485-koreyst) এই গাইডটি অনুসরণ করুন।

## প্রথমবারের মতো OpenAI API ব্যবহার করা

যদি এটি আপনার প্রথমবার OpenAI API এর সাথে কাজ হয়, তবে কিভাবে [ইন্টারফেস তৈরি এবং ব্যবহার করবেন](https://platform.openai.com/docs/quickstart?context=pythont&WT.mc_id=academic-105485-koreyst) এই গাইডটি অনুসরণ করুন।

## অন্যান্য শিক্ষার্থীদের সাথে পরিচিত হন

আমরা আমাদের অফিসিয়াল [AI কমিউনিটি Discord সার্ভার](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst) এ অন্যান্য শিক্ষার্থীদের সাথে পরিচিত হওয়ার জন্য চ্যানেল তৈরি করেছি। এটি অন্য মতামতপ্রাপ্ত উদ্যোক্তা, নির্মাতা, শিক্ষার্থী এবং Generative AI-এ উন্নতি করতে ইচ্ছুক যে কারো সাথে নেটওয়ার্ক করার একটি দুর্দান্ত উপায়।

[![ডিসকর্ড চ্যানেল যোগদান করুন](https://dcbadge.limes.pink/api/server/ByRwuEEgH4)](https://aka.ms/genai-discord?WT.mc_id=academic-105485-koreyst)

প্রকল্প দলটি এই Discord সার্ভারেও থাকবে শিক্ষার্থীদের সাহায্য করার জন্য।

## অবদান রাখুন

এই কোর্সটি একটি ওপেন সোর্স উদ্যোগ। আপনি যদি উন্নতির ক্ষেত্র বা সমস্যাগুলি দেখতে পান, তাহলে একটি [Pull Request](https://github.com/microsoft/generative-ai-for-beginners/pulls?WT.mc_id=academic-105485-koreyst) তৈরি করুন বা একটি [GitHub ইস্যু](https://github.com/microsoft/generative-ai-for-beginners/issues?WT.mc_id=academic-105485-koreyst) লগ করুন।

প্রকল্প দলটি সমস্ত অবদান ট্র্যাক করবে। ওপেন সোর্সে অবদান রাখা আপনার Generative AI ক্যারিয়ার গড়ার একটি চমৎকার উপায়।

অধিকাংশ অবদান আপনাকে একটি Contributor License Agreement (CLA) সম্মতিতে সম্মত হতে প্রয়োজন, যা ঘোষণা করে যে আপনার কাছে অধিকার রয়েছে এবং আসলে আমাদের আপনার অবদান ব্যবহার করার অধিকার প্রদান করে। বিস্তারিত জানার জন্য, [CLA, Contributor License Agreement ওয়েবসাইট](https://cla.microsoft.com?WT.mc_id=academic-105485-koreyst) দেখুন।

গুরুত্বপূর্ণ: এই রিপোতে টেক্সট অনুবাদ করার সময়, অনুগ্রহ করে নিশ্চিত করুন যে আপনি মেশিন অনুবাদ ব্যবহার করবেন না। আমরা কমিউনিটির মাধ্যমে অনুবাদগুলি যাচাই করব, তাই অনুগ্রহ করে এমন ভাষায় অনুবাদের জন্য স্বেচ্ছাসেবক হোন যেখানে আপনি দক্ষ।

আপনি যখন একটি pull request জমা দেবেন, একটি CLA-bot স্বয়ংক্রিয়ভাবে নির্ধারণ করবে যে আপনাকে একটি CLA প্রদান করতে হবে কিনা এবং PR টি যথাযথভাবে সাজাবে (যেমন, লেবেল, মন্তব্য)। বট দ্বারা প্রদত্ত নির্দেশাবলী অনুসরণ করুন। আমাদের CLA ব্যবহার করে সমস্ত রিপোজিটরির জুড়ে আপনাকে এটি একবারই করতে হবে।

এই প্রকল্পটি [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/?WT.mc_id=academic-105485-koreyst) গ্রহণ করেছে। আরও তথ্যের জন্য Code of Conduct FAQ পড়ুন বা [Email opencode](opencode@microsoft.com) এর সাথে যেকোন অতিরিক্ত প্রশ্ন বা মন্তব্য নিয়ে যোগাযোগ করুন।

## শুরু করা যাক

এখন যে আপনি এই কোর্সটি সম্পূর্ণ করার জন্য প্রয়োজনীয় পদক্ষেপগুলি সম্পন্ন করেছেন, আসুন [Generative AI এবং LLMs এর পরিচিতি](../01-introduction-to-genai/README.md?WT.mc_id=academic-105485-koreyst) দিয়ে শুরু করি।

**অস্বীকৃতি**:  
এই নথিটি AI অনুবাদ পরিষেবা [Co-op Translator](https://github.com/Azure/co-op-translator) ব্যবহার করে অনুবাদ করা হয়েছে। আমরা যথাসম্ভব সঠিকতার জন্য চেষ্টা করি, তবে অনুগ্রহ করে সচেতন থাকুন যে স্বয়ংক্রিয় অনুবাদে ত্রুটি বা অসঙ্গতি থাকতে পারে। এর নিজস্ব ভাষায় মূল নথিটি কর্তৃত্বপূর্ণ উৎস হিসেবে বিবেচিত হওয়া উচিত। গুরুত্বপূর্ণ তথ্যের জন্য, পেশাদার মানব অনুবাদ সুপারিশ করা হয়। এই অনুবাদ ব্যবহারের ফলে উদ্ভূত কোনো ভুল বোঝাবুঝি বা ভুল ব্যাখ্যার জন্য আমরা দায়ী নই।