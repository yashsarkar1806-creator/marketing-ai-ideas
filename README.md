# Marketing × AI Project Ideas for DTC Brands and Tech/SaaS Companies

A curated list of **small and medium marketing projects** for direct-to-consumer (DTC) brands and tech/SaaS
companies, covering growth, CX, content, analytics and brand. Each idea has a short description, a difficulty
level, and links to **real, open models, datasets, Hugging Face Spaces and open-source repos** that could power it.

I keep this list as a backlog for my own portfolio. Ideas marked ✅ are already built.

**Difficulty**
* 🟢 **Small:** a weekend; one script, notebook or static page.
* 🟡 **Medium:** one to two weeks; data cleaning, a model or two, charts and a written recommendation.

> All links were checked when this list was written (Oct 2026). Hugging Face Spaces can go to sleep or be paused by their owners.
> Always read each model or dataset card for its license and intended use before using it commercially.

---

## Contents

1. [Growth & performance marketing](#1-growth--performance-marketing)
2. [Customer experience & voice of customer](#2-customer-experience--voice-of-customer)
3. [Content & creative](#3-content--creative)
4. [Analytics & measurement](#4-analytics--measurement)
5. [Brand & market research](#5-brand--market-research)
6. [Toolbox: models, datasets, Spaces and libraries](#6-toolbox)
7. [Daily builds](#daily-builds)

---

## 1. Growth & performance marketing

### ✅ UTM link builder + naming convention · 🟢 Small · DTC + SaaS
A static web page that builds clean UTM links and enforces a campaign naming convention so GA4 reports stay tidy.
**Built:** [utm-builder](https://github.com/yashsarkar1806-creator/utm-builder)

### ✅ CAC / LTV / ROAS / payback calculator · 🟢 Small · DTC + SaaS
Unit-economics calculator with DTC and SaaS LTV formulas, break-even ROAS and a metrics cheat sheet.
**Built:** [marketing-metrics-calculator](https://github.com/yashsarkar1806-creator/marketing-metrics-calculator)

### Ad-copy variant generator with a brand-voice checklist · 🟢 Small · DTC
Generate 10 headline/primary-text variants for Meta or Google ads from a product brief using a small open LLM, then
score each against a brand-voice checklist (length limits, banned words, benefit-led, CTA present).
* Models: [Qwen/Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct) (Apache-2.0), [HuggingFaceTB/SmolLM2-1.7B-Instruct](https://huggingface.co/HuggingFaceTB/SmolLM2-1.7B-Instruct) (Apache-2.0)
* Example data: [smangrul/ad-copy-generation](https://huggingface.co/datasets/smangrul/ad-copy-generation), [llm-wizard/Product-Descriptions-and-Ads](https://huggingface.co/datasets/llm-wizard/Product-Descriptions-and-Ads)
* Inspiration Space: [Agents-MCP-Hackathon/AI-Marketing-Content-Creator](https://huggingface.co/spaces/Agents-MCP-Hackathon/AI-Marketing-Content-Creator)

### SaaS trial-to-paid churn model · 🟡 Medium · SaaS
Predict which customers are likely to churn and turn the top drivers into lifecycle email triggers
(e.g. "no login in 7 days", "on a monthly contract").
* Data: [scikit-learn/churn-prediction](https://huggingface.co/datasets/scikit-learn/churn-prediction) (telco churn, CC-BY-4.0), a good stand-in for subscription churn
* Libraries: [scikit-learn](https://github.com/scikit-learn/scikit-learn), [streamlit/streamlit](https://github.com/streamlit/streamlit) for a simple app

### Bank-marketing response model (who to target) · 🟡 Medium · Tech / fintech
Classic direct-marketing dataset: predict who will say yes to a campaign and compare the lift against targeting everyone.
* Data: [UCI Bank Marketing](https://archive.ics.uci.edu/dataset/222/bank+marketing) (CC BY 4.0)

---

## 2. Customer experience & voice of customer

### ✅ Product-review sentiment & theme analysis · 🟡 Medium · DTC
VADER sentiment plus keyword theme tagging on product reviews, with charts and CX recommendations.
**Built:** [dtc-review-sentiment-analysis](https://github.com/yashsarkar1806-creator/dtc-review-sentiment-analysis)

### Upgrade it: transformer sentiment + zero-shot themes · 🟡 Medium · DTC
Re-run the review analysis with a transformer model, compare it with VADER, and tag themes with zero-shot
classification instead of keyword lists.
* Models: [cardiffnlp/twitter-roberta-base-sentiment-latest](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment-latest) (CC-BY-4.0), [nlptown/bert-base-multilingual-uncased-sentiment](https://huggingface.co/nlptown/bert-base-multilingual-uncased-sentiment) (predicts 1-5 stars, multilingual), [facebook/bart-large-mnli](https://huggingface.co/facebook/bart-large-mnli) and [MoritzLaurer/deberta-v3-large-zeroshot-v2.0](https://huggingface.co/MoritzLaurer/deberta-v3-large-zeroshot-v2.0) (zero-shot themes)
* Real review data: [saattrupdan/womens-clothing-ecommerce-reviews](https://huggingface.co/datasets/saattrupdan/womens-clothing-ecommerce-reviews), [McAuley-Lab/Amazon-Reviews-2023](https://huggingface.co/datasets/McAuley-Lab/Amazon-Reviews-2023) (beauty, fashion and more; check the card for terms), [fancyzhx/amazon_polarity](https://huggingface.co/datasets/fancyzhx/amazon_polarity) (Apache-2.0)
* Try it: [Gradio-Blocks/Multilingual-Aspect-Based-Sentiment-Analysis](https://huggingface.co/spaces/Gradio-Blocks/Multilingual-Aspect-Based-Sentiment-Analysis)

### Review emotion map · 🟢 Small · DTC
Go beyond positive/negative: classify reviews into joy, anger, surprise, sadness and so on, then find which products trigger which emotions.
* Model: [j-hartmann/emotion-english-distilroberta-base](https://huggingface.co/j-hartmann/emotion-english-distilroberta-base)

### Support-ticket intent classifier · 🟡 Medium · DTC + SaaS
Classify incoming support messages (refund, shipping, cancel subscription, bug) and estimate how many could be
answered by help-centre articles.
* Data: [bitext/Bitext-retail-ecommerce-llm-chatbot-training-dataset](https://huggingface.co/datasets/bitext/Bitext-retail-ecommerce-llm-chatbot-training-dataset), [bitext/Bitext-customer-support-llm-chatbot-training-dataset](https://huggingface.co/datasets/bitext/Bitext-customer-support-llm-chatbot-training-dataset) (CDLA-Sharing-1.0), [PolyAI/banking77](https://huggingface.co/datasets/PolyAI/banking77) (CC-BY-4.0, fintech intents)
* Library: [huggingface/setfit](https://github.com/huggingface/setfit), few-shot text classification that trains in minutes

### Review topic discovery · 🟡 Medium · DTC + SaaS
Find themes you didn't know to look for (e.g. "sizing runs small", "app crashes on login") using topic modelling.
* Library: [MaartenGr/BERTopic](https://github.com/MaartenGr/BERTopic) (MIT) with [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) embeddings
* Try it: [Hellisotherpeople/HF-BERTopic](https://huggingface.co/spaces/Hellisotherpeople/HF-BERTopic)

---

## 3. Content & creative

### Product-description rewriter for SEO · 🟢 Small · DTC
Take bland product descriptions and rewrite them for a target keyword and brand tone, then check length, keyword use and readability.
* Model: [Qwen/Qwen2.5-1.5B-Instruct](https://huggingface.co/Qwen/Qwen2.5-1.5B-Instruct)
* Data: [bprateek/amazon_product_description](https://huggingface.co/datasets/bprateek/amazon_product_description)

### Product-image alt-text and caption generator · 🟢 Small · DTC
Auto-generate alt text for product images, which helps accessibility and image SEO.
* Model: [Salesforce/blip-image-captioning-base](https://huggingface.co/Salesforce/blip-image-captioning-base)
* Data: [ashraq/fashion-product-images-small](https://huggingface.co/datasets/ashraq/fashion-product-images-small)
* Try it: [tonyassi/blip-image-captioning-large](https://huggingface.co/spaces/tonyassi/blip-image-captioning-large)

### Visual merchandising tagger · 🟡 Medium · DTC
Tag a product catalogue by colour, style and occasion with zero-shot image classification, then find which tags sell best.
* Model: [openai/clip-vit-base-patch32](https://huggingface.co/openai/clip-vit-base-patch32)
* Data: [ashraq/fashion-product-images-small](https://huggingface.co/datasets/ashraq/fashion-product-images-small)

### Clean product shots for ads · 🟢 Small · DTC
Batch-remove backgrounds from product photos for marketplace listings and ad creative.
* Try it: [not-lain/background-removal](https://huggingface.co/spaces/not-lain/background-removal)

### Webinar / podcast → blog post and social snippets · 🟡 Medium · SaaS
Transcribe a product webinar, summarise it, and turn it into a blog outline and five LinkedIn posts.
* Models: [openai/whisper-small](https://huggingface.co/openai/whisper-small) (speech-to-text), [facebook/bart-large-cnn](https://huggingface.co/facebook/bart-large-cnn) (summarisation)
* Try it: [openai/whisper](https://huggingface.co/spaces/openai/whisper), [Xenova/whisper-web](https://huggingface.co/spaces/Xenova/whisper-web) (runs in the browser)

### Audio ads and voice-over drafts · 🟢 Small · DTC + SaaS
Draft 15-second audio ad scripts and listen to them before paying for a studio. Pair with a jingle bed.
* Try it: [k2-fsa/text-to-speech](https://huggingface.co/spaces/k2-fsa/text-to-speech)
* Model: [facebook/musicgen-small](https://huggingface.co/facebook/musicgen-small) (short background music; check its non-commercial license)

---

## 4. Analytics & measurement

### ✅ DTC & SaaS campaign performance dashboard · 🟡 Medium · DTC + SaaS
Channel ROAS/CPA, share of spend vs share of results, funnel drop-off and seasonality.
**Built:** [dtc-saas-campaign-dashboard](https://github.com/yashsarkar1806-creator/dtc-saas-campaign-dashboard)

### RFM segmentation + customer lifetime value · 🟡 Medium · DTC
Segment customers by recency, frequency and monetary value (Champions, At-risk, Lost), then predict CLV and
suggest a lifecycle email for each segment.
* Data: [UCI Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii) and [UCI Online Retail](https://archive.ics.uci.edu/dataset/352/online+retail) (real UK e-commerce transactions, CC BY 4.0)
* Libraries: [pymc-labs/pymc-marketing](https://github.com/pymc-labs/pymc-marketing) (CLV models). [CamDavidsonPilon/lifetimes](https://github.com/CamDavidsonPilon/lifetimes) is the classic, now archived.

### GA4 e-commerce funnel analysis · 🟡 Medium · DTC
Use Google's public GA4 sample of the Google Merchandise Store to build a purchase funnel, find drop-off by device
and channel, and visualise it in Tableau or Power BI.
* Data: [GA4 obfuscated sample e-commerce dataset (BigQuery)](https://developers.google.com/analytics/bigquery/web-ecommerce-demo-dataset)

### Marketing mix model starter · 🟡 Medium · DTC + SaaS
Estimate each channel's incremental contribution and diminishing returns instead of trusting last-click.
* Libraries: [google/meridian](https://github.com/google/meridian) (Apache-2.0), [facebookexperimental/Robyn](https://github.com/facebookexperimental/Robyn) (MIT), [pymc-labs/pymc-marketing](https://github.com/pymc-labs/pymc-marketing)

### Demand / sales forecast for a launch calendar · 🟢 Small · DTC
Forecast weekly orders with holiday effects (Black Friday, Diwali, EOFY, Ramadan) to plan stock and spend.
* Library: [facebook/prophet](https://github.com/facebook/prophet)
* Data: [UCI Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii)

### Olist marketplace deep-dive · 🟡 Medium · DTC / marketplace
Real Brazilian e-commerce data with orders, delivery times and review scores. Test whether late delivery drives bad reviews.
* Data: [Olist Brazilian E-Commerce on Kaggle](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) (check the license on Kaggle)

---

## 5. Brand & market research

### Competitor review gap analysis · 🟡 Medium · DTC + SaaS
Compare review themes for your brand vs two competitors (from public review exports) to find positioning gaps,
e.g. "competitor A wins on shipping, loses on sizing".
* Models: [facebook/bart-large-mnli](https://huggingface.co/facebook/bart-large-mnli), [BAAI/bge-small-en-v1.5](https://huggingface.co/BAAI/bge-small-en-v1.5) (embeddings for clustering)

### Keyword clustering for an SEO content plan · 🟢 Small · DTC + SaaS
Group a keyword export into topic clusters with embeddings, then map each cluster to a pillar page.
* Model: [sentence-transformers/all-MiniLM-L6-v2](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2)
* Libraries: [MaartenGr/KeyBERT](https://github.com/MaartenGr/KeyBERT) (keyword extraction), [eliasdabbas/advertools](https://github.com/eliasdabbas/advertools) (SEO and SEM utilities)

### Brand mention & influencer scan · 🟢 Small · DTC
Pull brand and competitor names out of social posts or comments with named-entity recognition, then score sentiment per brand.
* Models: [dslim/bert-base-NER](https://huggingface.co/dslim/bert-base-NER), [cardiffnlp/twitter-roberta-base-sentiment-latest](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment-latest)

### Multilingual market check (India, UAE, Europe, Australia) · 🟡 Medium · DTC + SaaS
Run the same review or social analysis across languages to compare how a brand is perceived in each market.
* Models: [tabularisai/multilingual-sentiment-analysis](https://huggingface.co/tabularisai/multilingual-sentiment-analysis), [nlptown/bert-base-multilingual-uncased-sentiment](https://huggingface.co/nlptown/bert-base-multilingual-uncased-sentiment)
* Data: [AmazonScience/massive](https://huggingface.co/datasets/AmazonScience/massive) (multilingual intents, 50+ languages)

---

## 6. Toolbox

| Type | Link | Use it for |
|---|---|---|
| Library | [huggingface/transformers](https://github.com/huggingface/transformers) | Running any of the models above in Python |
| Library | [gradio-app/gradio](https://github.com/gradio-app/gradio) | Turning a project into a shareable demo (and hosting on HF Spaces) |
| Library | [streamlit/streamlit](https://github.com/streamlit/streamlit) | Simple dashboards |
| Library | [cjhutto/vaderSentiment](https://github.com/cjhutto/vaderSentiment) | Fast rule-based sentiment, no GPU |
| Model | [distilbert/distilbert-base-uncased-finetuned-sst-2-english](https://huggingface.co/distilbert/distilbert-base-uncased-finetuned-sst-2-english) | Lightweight English sentiment baseline |
| Dataset | [Yelp/yelp_review_full](https://huggingface.co/datasets/Yelp/yelp_review_full) | 1-5 star review text (see card for Yelp's terms) |
| Dataset | [fancyzhx/amazon_polarity](https://huggingface.co/datasets/fancyzhx/amazon_polarity) | Positive/negative product reviews (Apache-2.0) |

---

## Daily builds

New projects built from the ideas above, newest first.

- **2026-10-27** · [pakka-rto-shield](https://github.com/yashsarkar1806-creator/pakka-rto-shield): startup concept for Indian D2C brands that scores cash-on-delivery orders for return-to-origin risk, with a full GTM, pricing and metrics brief, a landing page with a live scoring demo, ROI calculator and UTM/dataLayer tracking ([live demo](https://yashsarkar1806-creator.github.io/pakka-rto-shield/), synthetic data)
- **2026-10-26** · [dabara-coffee-landing](https://github.com/yashsarkar1806-creator/dabara-coffee-landing): landing page for a fictional DTC filter-coffee brand with an A/B headline test, UTM capture, blend quiz, INR/AUD subscription builder, GA4-style dataLayer events and a brand/GTM brief ([live demo](https://yashsarkar1806-creator.github.io/dabara-coffee-landing/))
- **2026-10-26** · [dtc-growth-command-center](https://github.com/yashsarkar1806-creator/dtc-growth-command-center): Streamlit app for a fictional DTC brand with RFM and cohort retention, a channel budget optimiser, Hugging Face review sentiment, AI campaign briefs and an exportable insights report (synthetic data)

---

## Contributing

Suggestions are welcome. Open an issue with the idea, who it helps (DTC, SaaS or both), the difficulty, and a link to a real dataset or model.

## License

MIT for this list, see [LICENSE](LICENSE). Linked models, datasets and Spaces keep their own licenses.

Curated by Yash Sarkar · Master of Marketing (UWA) · GA4 and Google Ads certified
