## Role & Purpose
You are an expert MRM assistant specializing in BSA/AML model assumption review. 
You help MRM analysts:
1. Evaluate assumptions explicitly listed in a BSA/AML model document
2. Identify assumptions that are appropriate but missing from the model document
3. Flag assumptions that are weak, untested, or insufficiently justified

Standards applied: SR 11-7, FFIEC BSA/AML Examination Manual, FinCEN guidance, 
FATF typology reports, 31 CFR Chapter X, USA PATRIOT Act Section 314.

---

## Knowledge Sources
- Always check SharePoint knowledge source FIRST before applying industry standards
- When internal policy exists, cite it: "Per [Policy Name], Section X..."
- When absent, fall back to regulation and flag: 
  "No internal policy found — defaulting to [FFIEC / FinCEN / SR 11-7]"
- If SharePoint conflicts with regulation, flag for MRM escalation

---

## Workflow

### STEP 1 — Confirm BSA/AML Model Type
Identify and confirm with user before proceeding:
  a. Transaction Monitoring (rules-based or ML)
  b. Customer Risk Rating (CRR) / Customer Due Diligence (CDD)
  c. Sanctions Screening
  d. SAR/CTR Filing Decision Support
  e. Hybrid / Combined model

### STEP 2 — Extract & Assess Listed Assumptions
For each assumption in the model document, evaluate:
  - Clarity: precisely and unambiguously stated?
  - Justification: empirical evidence, testing, or business rationale provided?
  - Limitations: breakdown conditions acknowledged?
  - Internal Policy Alignment: consistent with SharePoint policy documents?
  - Regulatory Alignment: consistent with FFIEC, FinCEN, SR 11-7?

RAG Rating:
  🟢 Strong — justified, policy-aligned, limitations acknowledged
  🟡 Adequate — stated but gaps in justification or minor documentation issues
  🔴 Weak — missing justification, contradicts policy or regulation, untested

Present as structured table.

### STEP 3 — Identify Missing Assumptions
For each missing assumption appropriate to the confirmed model type:
  - Name | Why required | Internal policy ref | Regulatory ref | Recommended action

### STEP 4 — Summary & MRM Findings
  - Overall completeness score (%)
  - Top 3 priority gaps before model approval
  - Internal policy vs. regulatory conflicts identified
  - MRM challenge questions to raise with model developers

---

## Assumption Checklist by BSA/AML Model Type

### A. Transaction Monitoring (Rules-Based & ML)
Threshold Assumptions:
  - Are threshold levels justified via statistical tuning or back-testing against 
    confirmed SARs or known typologies?
  - Is threshold stability over time explicitly addressed?

Typology Coverage Assumptions:
  - Which typologies does the model detect (structuring, layering, trade-based ML, 
    funnel accounts, smurfing)? Are uncovered typologies documented with rationale?
  - Is there reference to FinCEN advisories, FATF typology reports, or internal 
    red flag inventories used in scenario design?

Customer Behavior Baseline Assumptions:
  - How is "normal" customer behavior defined for peer group comparisons?
  - Are peer group segmentation assumptions (industry, geography, customer type) 
    documented and statistically validated?
  - Is stationarity of customer behavior assumed and tested?

Data Quality & Completeness Assumptions:
  - Are data completeness assumptions stated (wire, ACH, cash, trade, crypto)?
  - Are data latency assumptions (real-time vs. batch) and detection impact documented?
  - Are missing data treatment assumptions (imputation or exclusion) described?

Scope & Coverage Assumptions:
  - Is the in-scope population (entity types, accounts, geographies, channels) defined?
  - Are out-of-scope exclusions documented with rationale?
  - Are correspondent banking, nested accounts, or high-risk corridor assumptions stated?

Alert Disposition Assumptions:
  - Are investigator override behavior assumptions documented?
  - Is the model's role in SAR decisions (advisory vs. deterministic) clearly stated?
  - Are false positive rate assumptions and operational impact documented?

### B. Customer Risk Rating (CRR) / CDD Models
Risk Factor Weighting Assumptions:
  - Are weights for risk factors (geography, industry, PEP status, product usage) 
    justified and derivation method documented (expert judgment vs. statistical)?
  - Are weight stability assumptions over time stated?

Risk Score Banding Assumptions:
  - Are Low/Medium/High/Prohibited cutoffs justified and validated?
  - Is expected customer distribution across bands stated?
  - Are relationship manager override assumptions documented and controlled?

High-Risk Indicator Assumptions:
  - Are automatic high-risk triggers documented with reference to FATF jurisdictions, 
    FinCEN 314(a)/(b), and OFAC SDN list?
  - Are PEP, adverse media, and negative news screening assumptions described?

Refresh & EDD Trigger Assumptions:
  - Are rating refresh frequency assumptions justified (periodic vs. event-triggered)?
  - Are EDD trigger conditions and beneficial ownership data completeness assumptions 
    explicitly stated?

### C. Sanctions Screening Models
Matching Algorithm Assumptions:
  - Are fuzzy matching logic assumptions (edit distance, phonetic, transliteration) 
    documented?
  - Is the assumed false positive rate stated and benchmarked against industry norms?
  - Are alias coverage and AKA list completeness assumptions documented?

List Currency & Coverage Assumptions:
  - How frequently are OFAC SDN, EU, UN, HMT watchlists ingested?
  - Is latency between list updates and screening application documented?
  - Are screened entity types (individuals, corporates, vessels, aircraft) defined?
  - Are correspondent and intermediary party screening assumptions stated?

Threshold & Filter Assumptions:
  - Are suppression rules and whitelist assumptions documented with justification?
  - Is the minimum match score to generate an alert defined and justified?

### D. All BSA/AML Models (General)
Regulatory Alignment:
  - Is there an explicit assumption that the model meets BSA, 31 CFR Chapter X, 
    FinCEN CDD Rule, and USA PATRIOT Act Section 314?
  - Are model auditability and examination readiness assumptions documented?

Model Tuning & Change Assumptions:
  - Are retuning frequency and trigger conditions (SAR rate shifts, new typologies, 
    regulatory changes) documented?
  - Are model redevelopment threshold assumptions stated?

Lookback Assumptions:
  - Are lookback period assumptions documented for detection of historical 
    suspicious activity?

---

## Output Format

1. BSA/AML Model Type Confirmed
2. Assumption Assessment Table
   Columns: Assumption | Clarity | Justification | Limitations | 
   Internal Policy Ref | Regulatory Ref | RAG | Comments
3. Missing Assumptions Table
   Columns: Missing Assumption | Why Required | Internal Policy Ref | 
   Regulatory Ref | Recommended Action
4. Summary: Completeness score | Top 3 gaps | Policy conflicts | 
   MRM challenge questions

---

## Tone & Guardrails
- Cite internal SharePoint policy before external regulation
- Flag explicitly when no internal policy covers a topic
- Ask clarifying questions when document is ambiguous before assessing
- Do not make pass/fail approval decisions — provide findings only
- Remind user: model approval decisions rest with the human MRM reviewer
- Escalate internal policy vs. regulatory conflicts to MRM team lead



## ReviewIQ
# ReviewIQ AI

### Agentic AI-Powered Review Intelligence Platform for Model Risk Management (MRM)

---

# Overview

**ReviewIQ AI** is an Agentic AI-powered Review Intelligence Platform designed to automate the first-pass review of Model Validation Reports while maintaining **Human-in-the-Loop (HITL)** governance.

Instead of replacing reviewers, ReviewIQ AI performs repetitive and evidence-driven review activities, allowing L1, L2, and Senior Reviewers to focus on expert judgment, regulatory interpretation, and final approval.

The solution leverages **Retrieval-Augmented Generation (RAG), Multi-Agent AI, Knowledge Graphs, Large Language Models (LLMs), and Continuous Learning** to improve review quality, reduce turnaround time, and standardize review outcomes.

---

# Problem Statement

Current Model Risk Management review processes are highly manual and involve multiple reviewers independently reading the same 100–300 page review reports.

### Existing Workflow

```text
Model Owner
      │
      ▼
Model Review Report
      │
      ▼
L1 Reviewer
      │
      ▼
L2 Reviewer
      │
      ▼
Senior Reviewer
      │
      ▼
Final Approved Report
```

### Challenges

* Multiple reviewers read the same report repeatedly.
* Manual verification of regulatory compliance.
* Inconsistent review comments.
* High review turnaround time.
* Significant effort spent on low-value repetitive checks.
* Senior reviewers spend valuable time identifying formatting and documentation issues instead of focusing on material model risks.

---

# Proposed Solution

ReviewIQ AI performs an intelligent first-pass review before human reviewers begin their assessment.

### Future Workflow

```text
Model Owner
      │
      ▼
Model Review Report
      │
      ▼
ReviewIQ AI
      │
      ├── Completeness Review
      ├── Regulatory Compliance
      ├── Technical Review
      ├── Evidence Verification
      ├── Consistency Validation
      ├── Risk Identification
      ├── Auto Comment Generation
      ├── Quality Scoring
      └── Confidence Scoring
      │
      ▼
Human Reviewers
      │
      ▼
Final Approval
```

Human reviewers focus on validating AI findings rather than reviewing the report from scratch.

---

# Objectives

* Reduce manual review effort by 60–80%
* Standardize review quality
* Improve consistency across reviewers
* Reduce review turnaround time
* Automatically generate reviewer comments
* Detect documentation and technical gaps
* Ensure regulatory compliance
* Maintain Human-in-the-Loop governance

---

# High-Level Architecture

## Phase 1 – Document Ingestion

### Input Documents

* Model Validation Report
* Model Documentation
* Model Development Document
* Validation Evidence
* Internal Policies
* SR 11-7
* OCC Guidelines
* Regulatory Guidance
* Historical Review Reports
* Previous Findings
* Issue Tracker
* Audit Reports

↓

OCR

↓

Document Parsing

↓

Chunking

↓

Embeddings

↓

Vector Database

↓

Knowledge Graph

---

## Phase 2 – Retrieval-Augmented Generation (RAG)

For every section under review, the system retrieves relevant context from:

* Internal Policies
* Regulatory Guidance
* Previous Review Reports
* Historical Findings
* Similar Models
* Standard Review Templates
* Issue Repository

The LLM never relies solely on its pretrained knowledge.

---

## Phase 3 – Multi-Agent AI Review System

Rather than a single LLM performing all review activities, ReviewIQ AI uses specialized AI agents.

---

# AI Agents

## 1. Document Completeness Agent

### Responsibilities

* Detect missing sections
* Detect empty tables
* Verify appendices
* Verify approvals
* Validate references
* Identify broken links
* Check mandatory documentation

### Sample Output

Severity: High

Finding:
Data Quality Assessment section is missing.

Evidence:
Internal Policy Section 5.2

Recommendation:
Include mandatory Data Quality Assessment.

---

## 2. Regulatory Compliance Agent

### Responsibilities

Review against

* SR 11-7
* OCC 2011-12
* ECB Guidance
* MAS Guidelines
* Internal MRM Policy

Example

Policy requires Bias Assessment.

Report does not contain Bias Assessment.

AI automatically generates regulatory finding.

---

## 3. Technical Validation Agent

Reviews

* Methodology
* Feature Engineering
* Variable Selection
* Training Data
* Testing Data
* Performance Metrics
* Threshold Calibration
* Hyperparameters
* Explainability
* Monitoring Strategy
* Stability Analysis
* Conceptual Soundness

Example

Recall reported.

Precision missing.

Recommendation:

Include Precision metric to satisfy internal validation standards.

---

## 4. Consistency Review Agent

Detects contradictions across the report.

Examples

Executive Summary

Accuracy = 96%

Performance Section

Accuracy = 95%

Flag inconsistency.

Another example

Methodology says XGBoost.

Appendix says Random Forest.

AI highlights contradiction.

---

## 5. Evidence Verification Agent

Ensures every conclusion is supported by evidence.

Example

Statement

"The model is stable."

Evidence required

* PSI
* Drift Analysis
* Monitoring Results
* Statistical Validation

If unavailable

Finding:

Unsupported conclusion.

---

## 6. Reviewer Comment Generator

Automatically drafts reviewer comments.

Example

Finding

Variable selection methodology lacks sufficient explanation.

Suggested Comment

Please describe

* Feature Screening
* Correlation Analysis
* Multicollinearity Assessment
* Business Justification

Reference

MRM Policy Section 8.2

Reviewer can

* Accept
* Modify
* Reject

---

## 7. Risk Classification Agent

Automatically predicts

* Low
* Medium
* High
* Critical

Based on

* Regulatory impact
* Business impact
* Missing evidence
* Historical issues
* Severity
* Confidence

---

## 8. Duplicate Finding Agent

Groups duplicate findings together.

Instead of

20 similar comments

Produces

1 consolidated finding.

---

## 9. Review Quality Scoring Agent

Generates scores

Example

Completeness

95

Consistency

90

Governance

88

Technical Quality

93

Evidence Quality

91

Overall Review Quality

91

---

## 10. Executive Summary Agent

Creates

* Management Summary
* Reviewer Summary
* Executive Dashboard
* High Risk Findings
* Outstanding Issues
* Recommendation Summary

---

# AI Confidence Score

Each finding includes confidence.

Example

Finding

Bias Assessment Missing

Confidence

99%

Evidence

* Internal Policy 7.3
* SR 11-7
* Page 114

This enables reviewers to prioritize high-confidence findings.

---

# Human-in-the-Loop Workflow

ReviewIQ AI never approves reports.

It only recommends findings.

```text
AI Review

↓

Suggested Findings

↓

L1 Reviewer

Accept
Reject
Modify

↓

L2 Reviewer

Reviews accepted findings

↓

Senior Reviewer

Reviews High Risk findings

↓

Final Approval
```

Human reviewers remain accountable for all final decisions.

---

# Continuous Learning Loop

```text
AI Recommendation

↓

Reviewer Feedback

↓

Feedback Repository

↓

Prompt Optimization

↓

Model Fine-Tuning

↓

Improved AI Recommendations
```

The system continuously learns from reviewer decisions while preserving governance controls.

---

# Advanced Capabilities

## Cross-Report Comparison

Compare current report against previous model versions.

---

## Historical Issue Tracking

Verify whether previous findings have been resolved.

---

## Copy-Paste Detection

Detect reused or outdated content.

---

## Benchmarking

Compare reviews against similar models across business units.

---

## Citation Verification

Ensure references actually support conclusions.

---

## Explainability Validation

Check presence and adequacy of

* SHAP
* LIME
* Feature Importance
* Fairness Analysis
* Bias Assessment

---

## Dashboard Generation

Generate interactive dashboards for

* Review Progress
* High Risk Findings
* Open Issues
* Confidence Distribution
* Compliance Coverage

---

# Technology Stack

| Layer            | Technology                            |
| ---------------- | ------------------------------------- |
| Frontend         | React / Streamlit                     |
| Backend          | Python + FastAPI                      |
| LLM              | GPT-5.x / Azure OpenAI / Llama 3      |
| Framework        | LangGraph                             |
| AI Orchestration | Multi-Agent Architecture              |
| Retrieval        | RAG                                   |
| Embedding Models | OpenAI / BGE / E5                     |
| Vector Database  | FAISS / Pinecone / ChromaDB           |
| Knowledge Graph  | Neo4j                                 |
| OCR              | Docling / Azure Document Intelligence |
| Storage          | Azure Blob Storage / AWS S3           |
| Database         | PostgreSQL                            |
| Monitoring       | MLflow + Prometheus                   |
| Authentication   | Azure AD / OAuth                      |

---

# Business Benefits

| Metric              | Current            | With ReviewIQ AI  |
| ------------------- | ------------------ | ----------------- |
| Manual Reading      | 100%               | 20–30%            |
| Compliance Checks   | Manual             | Automated         |
| Comment Generation  | Manual             | AI Generated      |
| Evidence Validation | Manual             | Automated         |
| Consistency Checks  | Manual             | Automated         |
| Turnaround Time     | 5–10 Days          | 1–3 Days          |
| Review Effort       | 100%               | Reduced by 60–80% |
| Review Quality      | Reviewer Dependent | Standardized      |
| Human Oversight     | Required           | Required          |

---

# Future Enhancements

* Voice-enabled review assistant
* Review chatbot
* Auto PowerPoint generation
* Auto validation report generation
* Regulatory change impact analysis
* AI reviewer benchmarking
* Multi-language support
* GenAI governance dashboard
* Model portfolio risk dashboard
* Agentic workflow automation

---

# Key Principles

* Human-in-the-Loop
* Explainable AI
* Evidence-Based Recommendations
* Regulatory Compliance
* Responsible AI
* Secure by Design
* Auditability
* Continuous Learning
* Enterprise Scalability

---

# Vision

ReviewIQ AI transforms Model Risk Management by combining Agentic AI, Retrieval-Augmented Generation, and Human Expertise to deliver faster, more consistent, evidence-driven, and regulatory-compliant model reviews.

The platform does not replace reviewers—it augments them, enabling L1, L2, and Senior Reviewers to focus on judgment, governance, and strategic risk assessment while AI automates repetitive review activities.

ReviewIQ-AI/
│
├── README.md
├── LICENSE
├── architecture/
│   ├── solution_architecture.png
│   ├── workflow.png
│   ├── agent_architecture.png
│   └── sequence_diagram.png
│
├── docs/
│   ├── business_problem.md
│   ├── system_design.md
│   ├── ai_agents.md
│   ├── rag_pipeline.md
│   ├── evaluation_metrics.md
│   ├── roadmap.md
│   └── future_work.md
│
├── backend/
├── frontend/
├── prompts/
├── data/
├── notebooks/
├── tests/
└── examples/
