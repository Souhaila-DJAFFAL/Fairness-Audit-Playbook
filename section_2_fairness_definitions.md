# Fairness Audit Playbook
## Section 2: Fairness Definitions - Choosing What "Fair" Means

---

## 📍 Section Navigation
**Previous:** [Section 1: Executive Overview & Problem Understanding](./section-1-overview.md)
**Current:** Section 2: Fairness Definitions - Choosing What "Fair" Means ✅
**Next:** [Section 3: Identifying Where Bias Comes From](./section-3-bias-sources.md)

---

## 🎯 Why We Must Choose Our Definition of Fairness

**For Leadership: The Strategic Decision**

"Fairness" isn't one thing - it's multiple competing concepts. We must explicitly choose which type of fairness matters most for our business context, because it's mathematically impossible to achieve all types simultaneously.

**Academic Foundation:** Based on Kleinberg et al. (2016) impossibility results showing that fairness definitions mathematically conflict when group base rates differ.

**Executive Decision Required:** This isn't a technical choice - it's a business strategy decision that requires leadership input.

---

## 📊 Five Types of Fairness Explained for Executives

### Option 1: Demographic Parity (Equal Outcomes)
**What It Means:** Equal percentages of all groups receive positive decisions

**Example:** If 10% of white applicants get hired, 10% of Black applicants should also get hired

**When To Choose This:** Resource allocation, outreach programs, representation goals

**Business Rationale:** Ensures proportional access to opportunities

**Limitation:** May require lowering standards for some groups

**Legal Context:** Often required for government programs and public accommodations

### Option 2: Equal Opportunity (Equal Success Detection)
**What It Means:** Among truly qualified candidates, all groups have equal chances of being selected

**Example:** Of all qualified candidates, 80% get hired regardless of group membership

**When To Choose This:** Hiring, admissions, merit-based decisions

**Business Rationale:** Maintains quality standards while ensuring fair treatment of qualified individuals

**Limitation:** Ignores different error rates for unqualified candidates

**Legal Context:** Aligns with employment law focus on not missing qualified candidates

### Option 3: Equalized Odds (Equal Treatment Overall)
**What It Means:** All groups have equal rates of both correct positive and correct negative decisions

**Example:** Loan approvals are equally accurate for all groups, both for good and bad credit risks

**When To Choose This:** High-stakes decisions where both types of errors matter

**Business Rationale:** Provides consistent accuracy across all groups

**Limitation:** May reduce overall accuracy to achieve parity

**Legal Context:** Strongest protection against discrimination claims

### Option 4: Calibration (Equal Prediction Accuracy)
**What It Means:** When the AI says "80% chance of success," it should be correct 80% of the time for all groups

**Example:** Risk scores mean the same thing across all demographic groups

**When To Choose This:** Risk assessment, probability-based decisions

**Business Rationale:** Ensures predictions are equally reliable for all groups

**Limitation:** May allow different treatment levels if properly calibrated

**Legal Context:** Important for regulatory compliance in financial services

### Option 5: Individual Fairness (Similar Treatment for Similar People)
**What It Means:** Similar individuals should receive similar decisions regardless of group membership

**Example:** Two candidates with identical qualifications get similar scores

**When To Choose This:** Personalized services, individual assessments

**Business Rationale:** Provides most intuitive sense of fairness

**Limitation:** Requires defining what makes people "similar"

**Legal Context:** Aligns with civil rights principle of equal treatment

---

## 🎯 Selection Framework for Executives

**Business Context Decision Matrix:**

| Your Business Context | Recommended Fairness Type | Strategic Rationale |
|----------------------|---------------------------|-------------------|
| **High-stakes individual decisions** (hiring executives, loan approvals) | Individual Fairness + Equalized Odds | Protects against discrimination lawsuits while maintaining decision quality |
| **Mass screening processes** (resume filtering, application processing) | Equal Opportunity | Ensures we don't miss qualified candidates while maintaining efficiency |
| **Resource allocation** (scholarship distribution, program access) | Demographic Parity | Ensures proportional access and supports diversity goals |
| **Risk assessment** (credit scoring, fraud detection) | Calibration + Individual Fairness | Maintains prediction reliability while ensuring equal treatment |
| **Customer-facing services** (recommendations, personalization) | Individual Fairness | Provides consistent user experience across all customer segments |

---

## 📋 Decision Process for Leadership

### Step 1: Identify Primary Business Goal
**Questions to Ask:**
- What outcome matters most for business success?
- Are we optimizing for quality, quantity, or representation?
- What are our key performance indicators?

### Step 2: Assess Legal Requirements
**Questions to Ask:**
- What regulations apply to our industry and use case?
- Are there specific fairness requirements we must meet?
- What are the consequences of non-compliance?

### Step 3: Consider Stakeholder Priorities
**Questions to Ask:**
- What do affected communities expect from our system?
- What do advocacy groups and regulators prioritize?
- How do internal stakeholders (engineering, product, legal) view trade-offs?

### Step 4: Evaluate Trade-offs
**Questions to Ask:**
- What business metrics are we willing to sacrifice for fairness?
- How much accuracy reduction is acceptable?
- What operational changes can we accommodate?

### Step 5: Document Decision Rationale
**Requirements:**
- Written justification for chosen fairness definition
- Explanation of rejected alternatives and why
- Sign-off from relevant stakeholders
- Regular review and update schedule

---

## 🔍 Multi-Framework Ethical Analysis

**Utilitarian Perspective (Greatest Good for Greatest Number):**
- Focus on overall benefit maximization
- May justify some individual unfairness for greater collective good
- Important for resource allocation decisions

**Deontological Perspective (Inherent Rights and Duties):**
- Emphasizes individual rights and equal treatment
- Prohibits using people merely as means to an end
- Critical for individual fairness assessments

**Virtue Ethics Perspective (Character and Moral Excellence):**
- Focuses on what a virtuous organization would do
- Considers long-term character and reputation impacts
- Guides organizational culture and values

**Justice-Based Perspective (Rawlsian "Veil of Ignorance"):**
- Design systems not knowing which group you'll belong to
- Tends toward protecting most vulnerable populations
- Useful for policy and system design decisions

---

## ✅ Implementation Checklist

**Pre-Selection Activities:**
- [ ] Assemble decision-making team (leadership, legal, product, engineering)
- [ ] Review applicable regulations and legal requirements
- [ ] Identify and consult key stakeholders
- [ ] Analyze business goals and success metrics

**Selection Process:**
- [ ] Evaluate each fairness definition against business context
- [ ] Assess feasibility and resource requirements
- [ ] Consider trade-offs and limitations
- [ ] Conduct multi-framework ethical analysis
- [ ] Document decision rationale and alternatives considered

**Post-Selection Activities:**
- [ ] Communicate decision to all relevant teams
- [ ] Establish success metrics and monitoring procedures
- [ ] Set review and update schedule
- [ ] Begin technical implementation planning

---

## 🔄 Complete Playbook Navigation

**Previous Section:** [1. Executive Overview & Problem Understanding](./section-1-overview.md)
**Current Section:** 2. Fairness Definitions - Choosing What "Fair" Means ✅
**Next Section:** [3. Identifying Where Bias Comes From](./section-3-bias-sources.md)

**Remaining Sections:**
- **Section 4:** [Measuring Fairness - The Technical Audit](./section-4-measuring-fairness.md)
- **Section 5:** [Case Study - Mental Health Crisis Detection AI](./section-5-case-study.md)
- **Section 6:** [Implementation Guide for Organizations](./section-6-implementation.md)
- **Section 7:** [Organizational Integration Strategy](./section-7-integration.md)

---

**📝 Section Summary:** This section guides leadership through the strategic decision of selecting appropriate fairness definitions based on business context, legal requirements, and stakeholder priorities.

**⏭️ Next Action:** Proceed to [Section 3: Identifying Where Bias Comes From](./section-3-bias-sources.md) to learn how to systematically identify potential sources of bias in your AI systems.