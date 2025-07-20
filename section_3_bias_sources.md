# Fairness Audit Playbook
## Section 3: Identifying Where Bias Comes From

---

## 📍 Section Navigation
**Previous:** [Section 2: Fairness Definitions - Choosing What "Fair" Means](./section-2-fairness-definitions.md)

**Current:** Section 3: Identifying Where Bias Comes From ✅

**Next:** [Section 4: Measuring Fairness - The Technical Audit](./section-4-measuring-fairness.md)

---

## 🎯 Sources of AI Bias 

**Executive Overview:** Bias can enter our AI systems at six different stages. Understanding these helps us know where to look for problems and how to prevent them.

---

## 🔴 Critical Priority Bias Sources

### Source 1: Historical Bias (Priority: 🔴 Critical)
**What It Is:** Past discrimination baked into our training data

**Example:** Historical hiring data shows fewer women in leadership because of past discrimination

**Why It's Critical:** Reproduces societal inequities in our decisions

**Business Impact:** Creates legal liability and excludes qualified candidates

**Detection Method:** Compare historical data patterns to known demographic distributions

**Academic Foundation:** Reflects the "Technological Continuity of Discrimination" principle

**Executive Action Required:** Audit all historical training data for known discrimination patterns

### Source 2: Representation Bias (Priority: 🔴 Critical)
**What It Is:** Some groups are missing or underrepresented in our data

**Example:** Training data has mostly young urban users, few elderly rural users

**Why It's Critical:** AI doesn't learn to serve underrepresented groups well

**Business Impact:** Excludes potential market segments and creates poor user experiences

**Detection Method:** Analyze demographic distribution in training vs. target population

**Academic Foundation:** Related to "Strategic Ignorance & Data Gaps" concept

**Executive Action Required:** Mandate representative data collection across all user segments

### Source 3: Measurement Bias (Priority: 🔴 Critical)
**What It Is:** We measure the same thing differently for different groups

**Example:** Credit scores are calculated differently in different regions, affecting loan decisions

**Why It's Critical:** Creates systematic errors that appear as neutral differences

**Business Impact:** Leads to discriminatory outcomes while appearing objective

**Detection Method:** Audit measurement processes and data quality across groups

**Academic Foundation:** Reflects the "Power Asymmetries in Data Production" principle

**Executive Action Required:** Standardize measurement processes across all demographic groups

### Source 6: Deployment Bias (Priority: 🔴 Critical)
**What It Is:** Using AI differently than originally intended

**Example:** Using hiring screening AI as a final decision-maker instead of an initial filter

**Why It's Critical:** Can amplify bias beyond original design assumptions

**Business Impact:** Creates new forms of discrimination and legal exposure

**Detection Method:** Monitor actual usage patterns vs. intended use cases

**Academic Foundation:** Reflects real-world complexity vs. laboratory conditions

**Executive Action Required:** Establish strict usage guidelines and monitoring for AI deployment

---

## 🟡 High Priority Bias Sources

### Source 4: Aggregation Bias (Priority: 🟡 High)
**What It Is:** Using one model for diverse populations without customization

**Example:** Using the same medical diagnostic AI for all ethnicities when disease presentation varies

**Why It's High Priority:** Reduces effectiveness for minority populations

**Business Impact:** Creates subpar service quality for some customer segments

**Detection Method:** Test model performance separately for each demographic group

**Academic Foundation:** Related to "Selective Optimization" for the majority groups

**Executive Action Required:** Consider group-specific model tuning for diverse populations

### Source 5: Evaluation Bias (Priority: 🟡 High)
**What It Is:** Testing our AI on data that doesn't match real-world usage

**Example:** Testing hiring AI on historical candidate pool, not current applicant demographics

**Why It's High Priority:** Gives false confidence in system performance

**Business Impact:** Deployment failures and unexpected discrimination patterns

**Detection Method:** Compare test data demographics to deployment environment

**Academic Foundation:** Addresses the gap between development and deployment contexts

**Executive Action Required:** Require representative test data that matches deployment demographics

---

## 🔍 Bias Detection Process 

### Phase 1: System Mapping 
**Executive Involvement Required:** Approve scope and resource allocation

**Activities:**
- Map data flow from collection to decision output
- Identify all human touchpoints in the process
- Document intended vs. actual system usage
- Assess potential impact on different user groups

**Key Questions:**
- Who are our primary and secondary user groups?
- What decisions does our AI make that affect people's lives?
- How does our system interact with human decision-makers?
- What are the consequences of wrong decisions for different groups?

### Phase 2: Pipeline Audit 
**Executive Decision Points:** Prioritize which bias sources to address first

**Activities:**
- Examine each stage using the six-source framework
- Quantify representation gaps in training data
- Assess measurement consistency across groups
- Identify proxy variables that might enable discrimination

**Key Questions:**
- Where in our process are we most vulnerable to bias?
- What historical discrimination patterns might affect our system?
- Do we have adequate representation of all user groups in our data?
- Are we measuring outcomes consistently across different populations?

### Phase 3: Risk Prioritization 
**Executive Approval Needed:** Sign off on risk assessment and action plan

**Activities:**
- Classify each identified bias source by priority level
- Estimate potential business impact and legal exposure
- Develop a mitigation timeline and resource requirements
- Establish monitoring and evaluation procedures

**Key Questions:**
- What level of bias risk is acceptable for our business?
- How should we prioritize limited resources across different bias sources?
- What timeline is reasonable for addressing identified issues?
- How will we monitor for new bias sources over time?

---

## 🎯 Priority Action Framework

### 🔴 Critical Priority Actions (Immediate - Week 1)
**Business Justification:** These biases create immediate legal liability and reputational risk

**Required Actions:**
- Halt system deployment if a critical bias is detected
- Implement emergency review processes for affected decisions
- Begin immediate data collection to address representation gaps
- Establish measurement standardization protocols

**Resource Allocation:** Highest priority for engineering and leadership time

**Success Metrics:** 
- Zero critical bias incidents
- Representative data collection across all groups
- Standardized measurement processes

### 🟡 High Priority Actions (Short-term - Month 1)
**Business Justification:** These biases create operational inefficiency and market limitations

**Required Actions:**
- Develop group-specific model performance benchmarks
- Create representative test datasets
- Implement demographic performance monitoring
- Design bias mitigation strategies

**Resource Allocation:** Significant engineering effort and specialized expertise

**Success Metrics:**
- Consistent model performance across demographic groups
- Representative evaluation datasets
- Automated bias monitoring systems

### 🟢 Medium Priority Actions (Long-term - Quarter 1)
**Business Justification:** These biases require ongoing monitoring and gradual improvement

**Required Actions:**
- Establish regular bias assessment cycles
- Develop advanced bias detection tools
- Create bias prevention training programs
- Build organizational bias monitoring capabilities

**Resource Allocation:** Sustained but moderate investment in tools and training

**Success Metrics:**
- Regular bias assessment completion
- Reduced bias incidents over time
- Improved organizational bias awareness

---

## 🔄 Intersectionality Considerations

**Why Simple Categories Aren't Enough:**
People aren't just "women" or "minorities" - they're often both. A fair system for women and fair system for minorities might still be unfair to minority women.

**Business Example:** Our hiring AI might perform well for:
- White women (get opportunities in "female-friendly" roles)
- Black men (succeed in traditionally male roles)
- But fail for Black women (caught between racial and gender biases)

**Academic Foundation:** Based on Crenshaw's intersectionality theory and Buolamwini & Gebru's intersectional bias research

**Implementation Requirements:**
- Test all meaningful combinations of demographic characteristics
- Collect sufficient data for intersectional subgroups
- Monitor performance across intersectional categories
- Design interventions that address compound discrimination

**Business Impact:**
- **Legal Risk:** Intersectional discrimination is legally recognized
- **Market Opportunity:** Intersectional groups are often underserved markets
- **Talent Pool:** We miss candidates with multiple diverse perspectives

---

## 🛠️ Technical Implementation Tools

### Proxy Variable Detection
```python
# Example correlation analysis for proxy detection
import pandas as pd
from scipy.stats import chi2_contingency

def detect_proxies(df, protected_attr, features):
    """Identify features that may serve as proxies for protected attributes"""
    proxy_scores = {}
    for feature in features:
        # Calculate mutual information or correlation
        contingency_table = pd.crosstab(df[feature], df[protected_attr])
        chi2, p_val, _, _ = chi2_contingency(contingency_table)
        proxy_scores[feature] = {'chi2': chi2, 'p_value': p_val}
    return proxy_scores
```

### Bias Source Documentation Template
**For Each Identified Bias Source:**
1. **Source Type:** (Historical, Representation, Measurement, etc.)
2. **Priority Level:** (Critical, High, Medium)
3. **Affected Groups:** (Specific demographic groups impacted)
4. **Business Impact:** (Quantified risk and opportunity cost)
5. **Detection Method:** (How bias was identified)
6. **Mitigation Strategy:** (Proposed remediation approach)
7. **Timeline:** (Expected resolution timeframe)
8. **Owner:** (Responsible team/individual)
9. **Success Metrics:** (How improvement will be measured)

---

## ✅ Implementation Checklist

**Pre-Assessment Preparation:**
- [ ] Assemble bias detection team (ML engineer + domain expert + stakeholder rep)
- [ ] Gather system documentation and data flow diagrams
- [ ] Identify all demographic groups served by the system
- [ ] Review historical discrimination patterns in your domain

**System Mapping Phase:**
- [ ] Document complete data pipeline from collection to decision
- [ ] Identify all human decision points and interventions
- [ ] Map intended vs. actual system usage patterns
- [ ] Assess potential impact on different user groups

**Bias Source Identification:**
- [ ] Audit each pipeline stage using the six-source framework
- [ ] Run proxy variable detection analysis
- [ ] Assess representation across all demographic groups
- [ ] Evaluate measurement consistency across groups
- [ ] Map feedback loops and amplification risks

**Risk Assessment and Prioritization:**
- [ ] Classify each bias source by priority level
- [ ] Estimate business impact and legal exposure
- [ ] Develop mitigation timeline and resource requirements
- [ ] Get executive approval for the action plan

**Documentation and Next Steps:**
- [ ] Complete bias source documentation for all findings
- [ ] Establish monitoring procedures for ongoing detection
- [ ] Schedule regular reassessment cycles
- [ ] Prepare for technical fairness metric calculation

---

## 🔄 Complete Playbook Navigation

**Previous Section:** [2. Fairness Definitions - Choosing What "Fair" Means](./section-2-fairness-definitions.md)

**Current Section:** 3. Identifying Where Bias Comes From ✅

**Next Section:** [4. Measuring Fairness - The Technical Audit](./section-4-measuring-fairness.md)

**Remaining Sections:**
- **Section 5:** [Case Study - Mental Health Crisis Detection AI](./section-5-case-study.md)
- **Section 6:** [Implementation Guide for Organizations](./section-6-implementation.md)
- **Section 7:** [Organizational Integration Strategy](./section-7-integration.md)

---

**📝 Section Summary:** This section provides a systematic framework for identifying the major sources of bias in AI systems, with priority levels and specific detection methods for each source.

**⏭️ Next Action:** Proceed to [Section 4: Measuring Fairness - The Technical Audit](./section-4-measuring-fairness.md) to learn how to quantitatively measure and validate fairness issues in your AI systems.
