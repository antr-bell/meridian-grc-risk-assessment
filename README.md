MyMeridian Patient Portal: Risk Assessment (NIST SP 800-30)

A qualitative, Tier 3 risk assessment of a fictional patient portal, built to practice GRC methodology and documentation.

Notice: Meridian Health Partners is a fictional organization created for this portfolio project. No real systems, data, or personnel are involved. Because no real stakeholders were available, I used large language models to generate the source materials I assessed: the company profile, the AWS architecture diagram, and the simulated organizational conditions behind the Operational and Management findings (R-0014 through R-0025). Threat events are likewise constructed to align with each vulnerability.

Using these materials, I performed the assessment myself: I reviewed the documentation, identified the vulnerabilities, rated likelihood and impact, documented mitigating factors, mapped controls, and built the risk register and Risk Assessment Report following NIST SP 800-30 Rev. 1 and its Appendix K report structure, with the RAR formatted from a NIST-style template. The purpose of this project is to practice GRC methodology and documentation, not to represent a real assessment.

Scope
System: MyMeridian Patient Portal (web and mobile application, telehealth integration, billing/payment module, EHR interface layer)
Hosting: AWS us-east-2
Categorization: FIPS 199 High (Confidentiality: High, Integrity: Moderate, Availability: Moderate)
Approach: NIST SP 800-30 Rev. 1, qualitative scale (Very Low to Very High)
Out of scope: the core Epic EHR, the biomedical device network, and the corporate IT environment
Deliverables
File	Description
docs/MyMeridian-Patient-Portal-RAR.pdf	Risk Assessment Report: system description, scope, assumptions, results table, detailed analysis
register/risk_register_MyMeridian.xlsx	Risk register with 25 findings: threat event, vulnerability, mitigating factors, likelihood, impact, risk
diagrams/MyMeridian_Portal_Architecture_v2.png	AWS architecture diagram used as assessment evidence
Results summary

25 findings across three control classes (Technical, Operational, Management):

Risk level	Count
Very High	1
High	3
Moderate	13
Low	8

Findings rated High or Very High receive a detailed analysis in the RAR (description, business impact, NIST SP 800-53 and HIPAA control mapping, recommendation):

R-0002 (Very High): publicly accessible, unencrypted RDS database
R-0005 (High): no WAF in front of the public Application Load Balancer
R-0008 (High): overly broad IAM managed policies on the portal/billing task role
R-0011 (High): AdministratorAccess on the EHR-interface Lambda
Method
Reviewed the architecture diagram and simulated organizational conditions
Identified vulnerabilities and predisposing characteristics
Paired each vulnerability with a threat event and threat source type (NIST SP 800-30 Table 1)
Rated likelihood (Tables 2 and 3) and impact (Table 4), then derived risk (Tables 5 and 6)
Documented existing mitigating factors (existing controls only, not recommendations)
Wrote detailed analyses for High and Very High findings and mapped controls to NIST SP 800-53 and the HIPAA Security Rule
Limitations
Findings are based on a constructed architecture diagram and assumed organizational conditions, not a real environment
Threat events are illustrative; they are not drawn from threat intelligence, incident history, or sector advisories
No penetration testing, source code review, or independent control validation
References
NIST SP 800-30 Rev. 1, Guide for Conducting Risk Assessments
NIST SP 800-53 Rev. 5, Security and Privacy Controls
FIPS 199, Standards for Security Categorization
HIPAA Security Rule

## License

This work is licensed under [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/).

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)