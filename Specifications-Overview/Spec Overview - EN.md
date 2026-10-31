# Functional Specifications – Student Labor Market Insertion Analysis

## 1. Project Overview

This project aims to establish a structured and sustainable graduate employment survey framework to monitor the integration of **Compétences & Développement (C&D)** graduates into the labor market.

It provides a process to collect, centralize and analyze reliable data about graduates' professional journeys, employment status and job characteristics. The results help assess the alignment between educational programs and labor market needs, supporting strategic decisions and continuous improvement.

## 2. Business Objectives

The overall objective is to automate the survey process, from response collection to reporting through interactive dashboards.

Specific objectives include:

- **O1 – Survey Forms:** design and provide 100% of the required survey forms.
- **O2 – Distribution:** automate questionnaire delivery to 100% of eligible students.
- **O3 – Data Collection:** correctly receive and record at least 95% of submitted responses.
- **O4 – Data Quality:** ensure at least 95% of data is compliant and usable.
- **O5 – Reporting:** make 100% of priority indicators available through dashboards.
- **O6 – Decision Support:** cover 100% of priority analytical requirements for business and academic stakeholders.

## 3. Functional Scope and Business Process

The solution covers six main stages:

1. **Reference Data Preparation:** extract and validate student registration data and transfer the required information from IGOR to a dedicated SQL Server database.
2. **Survey Design:** define questionnaires, questions and analytical dimensions, and assign forms to the relevant student populations.
3. **Survey Automation:** automate questionnaire distribution, response monitoring, reminders and response collection.
4. **Data Centralization:** store survey responses in a dedicated database and link them to reference data.
5. **Data Transformation and Preparation:** clean, normalize and validate data, then prepare analytical indicators.
6. **Reporting:** develop interactive Power BI dashboards tailored to business and academic reporting needs.

## 4. Key Performance Indicators (KPIs)

The dashboards track the following indicators:

| KPI | Definition / Calculation | Target |
|---|---|---:|
| Total Responses | Number of completed and validated questionnaires | Ongoing monitoring |
| Total Notifications | Number of survey invitations and reminders sent | Ongoing monitoring |
| Response Rate | Responses / unique notifications × 100 | ≥ 70% |
| Total Employed Students | Number of respondents reporting employment | To be defined |
| Total Unemployed Students | Number of respondents reporting job-seeking status | 0% (theoretical objective) |
| Unknown Employment Situation | Targeted students − valid responses | ≤ 30% |
| Unemployment Rate | Unemployed / (employed + unemployed) × 100 | < 10% |
| Employability Rate | Employed / (employed + unemployed) × 100 | ≥ 85% |

*Targets are indicative and may be adjusted based on survey results and Group standards.*

## 5. Data Architecture and Sources

### Data Sources

| Source | Description | Access |
|---|---|---|
| IGOR – SQL Server | Student registrations, student records, programs and analytical dimensions | Read access subject to authorization |
| Data Analytics SQL Server Database | Centralized and prepared analytical data | Controlled read and write access |

Reference data is extracted from IGOR and transferred to the dedicated analytical database according to a frequency defined by project requirements.

### Data Quality

Data quality controls cover six dimensions:

- **Completeness:** required information is available, including student email addresses and analytical dimensions.
- **Accuracy:** student contact details are valid and correctly associated.
- **Consistency:** registration, program and analytical data are aligned across sources.
- **Uniqueness:** surveys and submissions are uniquely identified, with duplicate checks.
- **Freshness:** data is refreshed according to a documented schedule.
- **Traceability:** sources, permissions and processing activities are documented.

## 6. Business Rules

| ID | Rule | Description | Status |
|---|---|---|---|
| RG-DEF-001 | Eligibility | A student must be registered in IGOR, linked to an eligible training period and have the required information for questionnaire delivery. | Under review |
| RG-CAL-001 | Response Rate | Calculated using valid respondents among recipients who actually received the questionnaire. | Under review |
| RG-PER-001 | Scope | Students, school brands and training periods included in the campaign are considered; ineligible populations and cancelled campaigns are excluded. | Under review |
| RG-QUA-001 | Data Quality | Student identifiers, training periods and email addresses must be checked before distribution. | Draft |
| RG-EXC-001 | Exceptions | Missing data, unlinked responses and duplicates are flagged and reviewed before being included again. | Draft |
| RG-TMP-001 | Timing | Initial distribution at J+6M, followed by reminders at J+7M and J+8M after the end of the training period. No reminders after a valid response or campaign closure. | Draft |
| RG-SEC-001 | Security | Access to identifiable student data and survey results is restricted according to authorized roles and scopes. | Draft |

## 7. Project Value

The solution provides a shared KPI framework and interactive dashboards to:

- Monitor employment, unemployment and graduate integration rates.
- Compare outcomes by institution, school brand, program and graduating cohort.
- Analyze time to first employment and job-search duration.
- Examine employment status, contract types and responsibility levels.
- Identify employing companies and their geographical distribution.
- Analyze occupations, industries and sub-industries.
- Monitor salary levels.
- Assess the alignment between educational programs, skills and jobs.
- Compare trends across cohorts and institutions.
- Support strategic management and continuous improvement of educational programs.

---

**Project:** Student Labor Market Insertion Analysis  
**Organization:** Compétences & Développement Group  
**Reporting Tool:** Microsoft Power BI
