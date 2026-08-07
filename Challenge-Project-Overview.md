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
In this project, you will use Alaska family-law court opinions, statutes, and a gold-standard set of query/answer pairs and information-retrieval evaluation, citation verification using string and semantic similarity, and systematic red-teaming to build a system that measures the retrieval and generation accuracy of a legal AI's output, discover the conditions under which it fails, and recommend how to improve it. This will help our company address the risk that AI-generated legal documents contain hallucinated or inaccurate citations, which can cause real harm to self-represented litigants in family court.

### Success Criteria

How Success Is Measured

The guiding principle: this project succeeds by producing a rigorous, honest measurement of the system, not by the system achieving a good score. A strong evaluation that reveals serious weaknesses is a successful project, because surfacing the truth is precisely its purpose. The fellows are graded on the quality of their measurement and analysis, never on how well ProseAI's system happens to perform.

Success is measured across three components and one overarching criterion.

Part A — Accuracy Evaluation. Success is a working evaluation system that computes retrieval metrics (Hit@1, Hit@5, Hit@10, MRR, NDCG) across the full gold set, broken down by motion type and reported separately for statute/rule retrieval and case-law retrieval, alongside per-document generation-accuracy and hallucination-risk scores. The measure is correctness and reproducibility, not the metric values themselves: the harness should produce a complete, trustworthy accuracy report on demand, including for a system version it has not seen before.

Part B — Red-Teaming. Success is measured by the breadth and quality of discovered failures: a set of distinct, reproducible failure cases spanning all four attack categories (edge cases, adversarial phrasing, jurisdiction traps, hallucination triggers), each categorized by type and severity, and assembled into a regression suite that runs reliably. A reasonable target is on the order of 40–50 reproducible cases with several rated critical. The deeper measure of quality is discovery; whether the red-team surfaces failure modes not already known to ProseAI, rather than rediscovering known issues.

Part C — Improvement Recommendations. Success is measured by actionability. Each recommendation should be specific, ranked by its severity to user outcomes, and tied directly to evidence from Parts A and B. The bar: a reader can tell from each recommendation exactly what to change and why it matters. "Increase retrieval depth for protective-order queries, where Hit@5 is 0.4 versus 0.8 elsewhere" passes; "improve retrieval quality" does not.

Overarching criterion: reusability. The ultimate measure of success is whether ProseAI can re-run the complete evaluation against an updated version of the system after the project ends and obtain a trustworthy before-and-after comparison without the fellows present. The strategic purpose of this project is a permanent quality gate and standing regression suite, not a one-time report. If that re-run is possible in January, the project has delivered its lasting value regardless of how any individual metric came out.

### Project Milestones
Use these milestones to guide your work. Your team will create a GitHub Projects board to track tasks within each milestone.

| Month | Milestone | Key Activities |
|---|---|---|
| September | Foundation & Retrieval Evaluation | • Explore the corpus and the gold set: motion-type distribution, citation patterns, document structure.<br>• Connect to the vector index and build the retrieval evaluation harness.<br>• Compute the baseline retrieval metrics (Hit@K, MRR, NDCG), broken down by motion type and by statute vs case law.<br>• Identify the weakest-retrieving query categories as early red-team targets.<br>• **Deliverable:** Retrieval evaluation harness + baseline retrieval metrics with breakdowns. |
| October | Generation Accuracy & Citation Verification | • Generate sample documents with fictional names across the common motion types.<br>• Build the citation extractor and verifier.<br>• Produce per-document hallucination-risk scores and analyze where generation accuracy is weakest.<br>• Begin red-teaming the weak spots found in September.<br>• **Deliverable:** Citation verification module + generation-accuracy / hallucination-risk scoring + first batch of documented failures. |
| November | Red-Teaming & Failure Analysis | • Run the full red-team campaign across edge cases, adversarial phrasing, jurisdiction traps, and hallucination triggers.<br>• Document each failure as a reproducible, categorized test case; assemble the regression suite.<br>• Analyze failure patterns: which conditions most reliably break the system and how badly.<br>• **Deliverable:** Failure-mode taxonomy + reproducible red-team regression suite categorized by severity. |
| December | Recommendations, Final Report & Presentation | • Synthesize evaluation and red-team findings into prioritized improvement recommendations.<br>• Package the full evaluation system and regression suite for ProseAI to reuse on every future change.<br>• Present findings and recommendations to ProseAI stakeholders.<br>• **Deliverable:** Final report (PDF) + open-source evaluation & red-team library (GitHub) + prioritized recommendations + presentation slides. |

> **Note for the team:** Please create a GitHub Projects board in this repository to break these milestones into weekly tasks. Go to the **Projects** tab → **New project** → Choose **Board** → Add columns for each month.

---

## 📊 Dataset
**Name and Source:** 

Dataset description. The project uses a corpus of Alaska family-law legal sources: published court opinions from CourtListener (the Free Law Project's public database), Alaska statutes and procedural rules covering domestic relations (custody, child support, protective orders), and a ProseAI-created gold-standard set of roughly 100–150 query/answer pairs — each a realistic self-represented-litigant situation paired with the legal sources a well-researched answer would cite. The court opinions and statutes are public record and contain no personally identifiable information; all sample documents used in evaluation are generated with fictional party names.

How it will be shared. ProseAI will provide the corpus pre-processed and pre-indexed in a vector database, so the team can evaluate the existing system from day one without re-embedding anything. The gold-standard pairs will be shared as a structured file (CSV/JSON). Access to the vector index and to the LLM and embedding services is provided through ProseAI-issued API keys (read access on the index), distributed to the team at the start of the project.

---

## 🛠️ Suggested Approach

**ML Problem Type:** Natural Language Processing (NLP), Deep Learning / Neural Networks, Large Language Models (LLMs)/ Generative AI, Transfer Learning / Pre-trained Models

**Recommended Libraries:**
- [e.g., pandas, scikit-learn, TensorFlow, Hugging Face]

**Evaluation Metrics:**
- [e.g., Accuracy, Precision/Recall, RMSE, BLEU score]

---

## 📚 Resources to Get Started

The following resources will help your team understand the problem space and potential technical approaches for this project:

**Background Reading:**
- [e.g., Link to an article or blog post about the problem domain]
- [e.g., Link to an industry report or case study]

**Technical Tutorials:**
- [e.g., Link to a free tutorial on the ML technique(s) involved]
- [e.g., Link to documentation for a key library or tool]

**Code Examples:**
- [e.g., Link to a relevant GitHub repo]
- [e.g., Link to a sample implementation or starter code]

**Other:**
- [Links to any additional resources — e.g., papers, videos, podcasts, etc.]

*Feel free to explore beyond these, and share anything interesting you find with me!*

---

## 🤝 How We'll Work Together

**Official check-ins:** During our biweekly 45-minute AI Studio Lab Section meeting block (2nd and 4th week of every month)

 **Other ways to reach out to me with questions:** 
* [e.g., Your team's channel within Break Through Tech’s Discord space]
* [e.g., Email; please copy your teammates and AI Studio Coach]
* [e.g., Request a team check-in on Zoom]
* [Note: I will aim to respond within 48 hours. Please reach out to your AI Studio Coach with urgent questions.]

> 💡 **Challenge Advisor: Please update the above based on your availability and preference. If you are not able to answer questions or meet with fellows outside of the biweekly Lab Section check-ins, simply write in "N/A (only available during the official check-in times)"**

**Recommended free coding / collaboration tools**
* […]
* […]

---

## 🚀 Getting Started

1. **Review this overview document** and note any questions for our first meeting
2. **Begin reviewing the dataset** using the link above
3. **Read the GitHub Projects documentation** [here](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects)

I’m excited to work with you!

---

## ❓ Questions?

Please bring any questions to our first meeting during the week of August 24th (Break Through Tech’s Bridge to Studio - Session C). 
