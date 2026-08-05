---

> ## Challenge Advisor: Update & Finalize Your Project Overview
>
> > 💡 **These grey text instructions are just for you, the team's Challenge Advisor; please delete them once you have completed the steps below.**
>
> We've pre-populated this Challenge Project Overview page — which is what will be shared with your Break Through Tech student team in August — using the details from your submission form. You should have received an email inviting you to join this repo as a Collaborator, enabling you to add files and make edits.
> 
> In order for your project to be finalized and assigned to a team, please:
> 1. **Review all sections below** and update or expand any content as needed, making sure to address the SME Feedback in the section immediately below. Look for square brackets to find the places below that require additional inputs from you (e.g., "About [Company / Org Name]").
> 2. **Add your dataset** to the [data folder](data) in this repo.
> 3. **Close the Issue assigned to you in this repo** to let us know that you have made your edits and the overview page is ready for final review. You can do this by going to the _Issues_ tab in the top left section of the menu above, add a comment that says "CA review complete", and click the button to Close the Issue. 
>
> If you're unfamiliar with how to edit a page like this in GitHub, check out [this tutorial](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/handson/edit-readme.html) for a quick overview (start with step 2 and only edit this page), and [this guide](https://ubc-lib-geo.github.io/gis-workshop-waml-template/content/markdown.html) on how to use Markdown to compose text.
>
>
> ❌ Remember that this is a public repo. Do NOT include: Proprietary data, PII, API keys, credentials, or anything confidential.

---
## 📋 BTT Internal Evaluation Notes
*(This section is for BTT staff and CAs only — remove before sharing with students)*

### Technical Vetting
| Check | Status | Notes |
| :--- | :--- | :--- |
| Python Compatibility | 🟢 | Project utilizes standard NLP libraries and Python-based evaluation metrics; compatible with Google Colab. |
| Data Readiness | 🟢 | Corpus is pre-processed and indexed in a vector database; gold-standard pairs are in structured CSV/JSON formats. |
| Resource Check | 🟡 | Relies on external API keys for LLM inference, creating a dependency risk if quotas are exhausted or models change. |

### Internal Scores
- **Student Fit Score:** 7/10
- **Technical Depth Score:** 8/10
- **Overall Recommendation:** REVISE

### Advisor Feedback Draft
This project offers a high-impact opportunity to engage with critical legal AI safety. By narrowing the target area to a single, well-defined failure mode and employing a highly structured attack framework instead of open-ended hacking, the Fellows can maintain focus and engagement. Additionally, replacing generic LLM calls with a fixed, smaller-scale model or simulated environment will ensure deterministic benchmarking and provide small wins that foster a sense of productivity.
---

# Legal AI Accuracy Evaluation, Red-Teaming & Improvement Recommendations

**Company / Org:** ProseAI  
**Challenge Advisor:** Benjamin Booker, benjaminbooker@gmail.com  
**AI Studio Coach:** Nagalakshmi Pulivarthi,nagalakshmi.pulivarthi@breakthroughtech.org  
**Program:** Break Through Tech AI Studio - Fall 2026  

---

## 🏢 About ProseAI
ProseAI is a legal technology organization dedicated to increasing access to justice for self-represented litigants in family court. Their primary mission involves developing reliable, AI-driven legal tools that provide accurate information while mitigating the risks of hallucinations and improper citations that can cause significant harm in legal proceedings.

---

## 🎯 The Challenge
### Project Summary
This project focuses on building a robust evaluation and red-teaming framework to audit the accuracy of ProseAI’s legal information retrieval and generation systems. Teams will utilize Alaska-specific family law datasets to design an evaluation harness, document failure modes, and provide actionable recommendations to improve system reliability and citation accuracy.

### Success Criteria
Success is measured across three components: Part A - Accuracy Evaluation (working evaluation system computing retrieval metrics like Hit@K, MRR, NDCG); Part B - Red-Teaming (breadth and quality of discovered failures, specifically 40-50 reproducible cases with several rated critical); Part C - Improvement Recommendations (specificity, actionability, and ranking by severity). Overarching criterion: reusability for ProseAI.

### Project Milestones
Use these milestones to guide your work. Your team will create a GitHub Projects board to track tasks within each milestone.
| Month | Milestone | Key Activities |
|-------|-----------|----------------|
| **September** | Data Exploration & Preprocessing | Audit the existing vector database index, clean raw court opinion text, and structure the gold-standard query/answer pairs for automated testing. |
| **October** | Feature Engineering & Baseline Modeling | Implement retrieval evaluation metrics (Hit@K, MRR, NDCG) and establish a baseline performance score using the provided legal corpus. |
| **November** | Model Optimization & Evaluation | Develop the citation verification module, conduct systematic red-teaming to uncover failure modes, and quantify hallucination risks. |
| **December** | Insights, Deliverables & Presentation | Synthesize failure mode taxonomies into prioritized improvement recommendations and package the final evaluation library and documentation. |

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset
**Name and Source:** Alaska Family-Law Corpus (CourtListener/ProseAI)  
**Format:** Vector DB Index, CSV, JSON  
**Size:** 1gb to 5gb  
**Location:** Provided via secure shared repository access  

### Key Details
- A corpus of Alaska family-law legal sources: published court opinions from CourtListener, Alaska statutes and procedural rules covering domestic relations (custody, child support, protective orders), and a ProseAI-created gold-standard set of roughly 100-150 query/answer pairs. The corpus is pre-processed and pre-indexed in a vector database; gold-standard pairs are in CSV/JSON format.
- Teams must manage constraints regarding legal citation formats and ensure the evaluation system accounts for semantic similarity versus strict string matching when verifying AI responses.

---

## 🛠️ Suggested Approach
**ML Problem Type:** NLP & RAG  
**Recommended Libraries:**
- Natural Language Processing (NLP)
- Deep Learning / Neural Networks
- Large Language Models (LLMs)/ Generative AI
- Transfer Learning / Pre-trained Models
**Evaluation Metrics:** Hit@K, Mean Reciprocal Rank (MRR), Normalized Discounted Cumulative Gain (NDCG), and custom citation-accuracy scores.

---

## 📚 Resources to Get Started
The following resources will help your team understand the problem space and potential technical approaches for this project:
**Background Reading:**
- Provided white papers on legal AI safety and the challenges of RAG-based hallucination in the domestic relations legal sector.
**Technical Tutorials:**
- Documentation for LangChain/LlamaIndex evaluation modules and vector search optimization guides.
**Code Examples:**
- Starter repositories for RAG-based QA evaluation and custom red-teaming scripts provided by the advisor.

---

## 🤝 How We'll Work Together
**Check-ins:** During our biweekly 60-min AI Studio Lab Section meeting block (2nd and 4th week of every month)  
**Communication:** Slack and project-specific GitHub issues for technical blockers.  
**Response time:** 48 hours for non-urgent technical questions.  
**Recommended Tools:**
- **Coding:** Google Colab Free Tier  
- **Collaboration:** GitHub, Notion  
- **Virtual Meetings:** Zoom, Google Meet  

---

## 🚀 Getting Started
1. **Review this overview document** and note any questions for our first meeting.
2. **Begin reviewing the dataset** using the link provided in the Dataset section.
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects).

I'm excited to work with you!

---

## ❓ Questions?
Please bring any questions to our first meeting during the week of August 24th (Break Through Tech's Bridge to Studio - Session B).
