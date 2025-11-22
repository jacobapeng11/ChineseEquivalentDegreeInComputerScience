# Chapter 5: Expert Systems and Their Structure

## Overview

Expert systems are AI programs that embody the knowledge of human experts and can solve problems in a specific domain. They are rule-based systems designed to mimic the decision-making abilities of a human expert. Expert systems were among the first successful applications of AI technology and remain important in many specialized domains.

## 1. Introduction to Expert Systems

### Definition and Characteristics

**Expert System:** A computer program that models the decision-making ability of a human expert in a specific domain by using knowledge representation and reasoning mechanisms.

**Key Characteristics:**
1. **Knowledge-based:** Contains expert knowledge in a specific domain
2. **Symbolic processing:** Uses symbols and rules rather than algorithms
3. **Problem-solving:** Addresses complex problems in a specific domain
4. **Explanation capability:** Can explain how conclusions were reached
5. **Uncertainty handling:** Can deal with incomplete or uncertain information

### Applications of Expert Systems

- **Medical diagnosis:** MYCIN for bacterial infections, INTERNIST for internal medicine
- **Geological exploration:** PROSPECTOR for mineral exploration
- **Financial planning:** Loan application evaluation, investment advice
- **Manufacturing:** Quality control, design assistance
- **Computer systems:** Network configuration, fault diagnosis

## 2. Structure of Expert Systems

### The Five Components

1. **Knowledge Base**
   - Contains facts and rules from domain experts
   - Represents domain-specific knowledge
   - Includes general facts, heuristic rules, and case examples

2. **Inference Engine**
   - Controls the reasoning process
   - Applies rules to facts to derive new conclusions
   - Implements forward and backward chaining

3. **User Interface**
   - Facilitates communication between user and system
   - Presents information and queries in user-friendly format
   - May include explanation facilities

4. **Explanation Facility**
   - Explains how the system reached its conclusions
   - Tracks reasoning steps
   - Justifies the system's recommendations

5. **Knowledge Acquisition Facility**
   - Helps knowledge engineers extract knowledge from experts
   - Builds and maintains the knowledge base
   - Often includes tools for rule editing and validation

## 3. Knowledge Representation in Expert Systems

### Rule-Based Representation

The most common representation in expert systems uses IF-THEN rules:

```
IF condition(s) THEN conclusion(s)
```

**Example:**
```
IF patient has fever AND patient has cough AND patient has fatigue
THEN patient may have flu
```

### Rule Structure
- **Antecedent (IF part):** Conditions that must be satisfied
- **Consequent (THEN part):** Actions or conclusions to take
- **Confidence factor:** Measure of uncertainty (in uncertain systems)

### Types of Rules
1. **Classification rules:** Determine what category an item belongs to
2. **Causal rules:** Represent cause-and-effect relationships
3. **Inference rules:** Derive new facts from existing ones
4. **Action rules:** Specify what actions to take

## 4. Reasoning in Expert Systems

### Forward Chaining (Data-Driven)
- Starts with known facts and applies rules to derive new facts
- Continues until a goal is reached or no more rules can be applied
- Works well when facts are known but conclusions are not

**Algorithm:**
```
1. Place facts into working memory
2. Match rules to facts in working memory
3. Select rule to fire
4. Fire rule (add new facts to working memory)
5. Repeat steps 2-4 until goal is reached or no rules fire
```

### Backward Chaining (Goal-Driven)
- Starts with a hypothesis and works backwards to find supporting evidence
- More efficient when specific goals need to be proven
- Works well when there are many possible conclusions

**Algorithm:**
```
1. Start with goal to prove
2. Find rules whose consequent matches the goal
3. Recursively prove the antecedents of these rules
4. If antecedents are known facts, goal is proven
```

### Comparison of Chaining Methods

| Forward Chaining | Backward Chaining |
|------------------|-------------------|
| Starts with facts | Starts with goals |
| Data-driven | Goal-driven |
| Good for monitoring | Good for diagnosis |
| May explore many paths | Only explores relevant paths |

## 5. Handling Uncertainty in Expert Systems

### Certainty Factor Approach

**Certainty Factor (CF):** A measure of belief in a hypothesis given evidence.

**Formula:** CF(H, E) = MB(H, E) - MD(H, E)
- MB: Measure of increased belief in H due to E
- MD: Measure of increased disbelief in H due to E
- CF value ranges from -1.0 (certainly false) to +1.0 (certainly true)

### Combining Certainty Factors

For AND: CF_combined = min(CF1, CF2, ..., CFn)
For OR: CF_combined = max(CF1, CF2, ..., CFn)

For rules: CF(H) = CF(E) × CF(rule) where E is the evidence CF

**Example from exam material:**
Given: if E3 AND (E1 OR E2) THEN H={h1} cf={0.7}
CER(E3)=0.9, CER(E1)=0.5, CER(E2)=0.8

Step 1: CER(E1 OR E2) = max(0.5, 0.8) = 0.8
Step 2: CER(E3 AND (E1 OR E2)) = min(0.9, 0.8) = 0.8
Step 3: CER(H) = 0.8 × 0.7 = 0.56

### Bayesian Networks
Alternative approach using probability theory to handle uncertainty.

## 6. Expert System Development Process

### Phase 1: Problem Identification
- Define the domain and scope
- Identify target users
- Determine feasibility
- Establish requirements

### Phase 2: Knowledge Acquisition
- Interview domain experts
- Analyze documents and cases
- Identify important concepts and relationships
- Structure the knowledge

### Phase 3: Knowledge Encoding
- Select appropriate representation
- Implement rules in the knowledge base
- Validate knowledge accuracy
- Test initial system

### Phase 4: System Development
- Choose development platform
- Implement inference engine
- Design user interface
- Build explanation facility

### Phase 5: Testing and Validation
- Test with real cases
- Validate against expert decisions
- Refine knowledge base
- Perform sensitivity analysis

### Phase 6: Deployment and Maintenance
- Deploy in operational environment
- Monitor system performance
- Update knowledge as needed
- Provide ongoing support

## 7. Advantages and Limitations of Expert Systems

### Advantages
1. **Availability:** Available 24/7, don't get tired
2. **Cost-effective:** Once developed, can be used multiple times
3. **Consistency:** Provide consistent reasoning
4. **Documentation:** Make expert knowledge explicit
5. **Explanation:** Can explain their reasoning process
6. **Distributed expertise:** Can incorporate knowledge from multiple experts

### Limitations
1. **Limited domain:** Usually restricted to narrow domain
2. **Brittle:** May fail when faced with novel situations
3. **Knowledge acquisition bottleneck:** Difficult to extract knowledge from experts
4. **Maintenance:** Knowledge base requires regular updates
5. **Common sense:** Lack of common-sense reasoning
6. **Learning:** Most systems can't learn from experience

## 8. Expert System Shells

### Definition
An expert system shell is a software environment that provides the basic functions needed in an expert system without the domain-specific knowledge.

### Popular Shells
- **EMYCIN:** Extension of MYCIN system
- **CLIPS:** C Language Integrated Production System
- **Jess:** Java Expert System Shell
- **Prolog:** Logic programming language often used for expert systems

### Features of Shells
- Built-in inference engines
- User interface tools
- Explanation facilities
- Knowledge editing tools
- Debugging aids

## 9. Case Study: MYCIN System

### Overview
MYCIN was one of the first successful expert systems, developed at Stanford University in the 1970s for diagnosing bacterial infections and recommending antibiotics.

### Structure
- 60+ rules for identifying infectious organisms
- 300+ rules for selecting therapy
- Handled uncertainty using certainty factors
- Included 15 parameters for patient data

### Key Features
- Used forward chaining
- Handled complex medical reasoning
- Provided explanations for recommendations
- Demonstrated expert system potential

### Impact
- Influenced expert system research
- Led to development of rule-based systems
- Showed practical applications of AI

## Practice Problems and Solutions

### Problem 1: Forward vs Backward Chaining
**Question:** A medical expert system needs to determine if a patient has a rare disease. The system has many symptoms as input but only wants to determine if the specific disease is present. Which chaining method would be more appropriate and why?

**Solution:** Backward chaining would be more appropriate because:
- The goal (disease presence) is specific
- There are many possible symptoms but only one conclusion to verify
- Backward chaining will only explore paths relevant to confirming the specific disease
- It's more efficient when you have specific goals and extensive data

### Problem 2: Rule-Based Reasoning
**Question:** Given these rules:
- R1: IF fever AND cough THEN pneumonia
- R2: IF pneumonia THEN prescribe_antibiotics
- R3: IF headache THEN rest

If a patient has fever and cough, what conclusions can be drawn?

**Solution:**
Using forward chaining:
1. From fever and cough, and rule R1: patient has pneumonia
2. From pneumonia, and rule R2: prescribe antibiotics
3. No conclusion about rule R3 (headache not present)

Conclusions: pneumonia, prescribe_antibiotics

### Problem 3: Certainty Factors
**Question:** Given: IF A AND B THEN H with CF = 0.9. If CF(A) = 0.7 and CF(B) = 0.6, calculate CF(H).

**Solution:**
Step 1: CF(A AND B) = min(0.7, 0.6) = 0.6
Step 2: CF(H) = 0.6 × 0.9 = 0.54

### Problem 4: Expert System Components
**Question:** Match the expert system component with its function:
A. Knowledge Base
B. Inference Engine
C. Explanation Facility
D. User Interface

Functions:
1. Controls reasoning process
2. Contains domain knowledge
3. Explains reasoning steps
4. Enables user interaction

**Solution:**
A. Knowledge Base → 2. Contains domain knowledge
B. Inference Engine → 1. Controls reasoning process
C. Explanation Facility → 3. Explains reasoning steps
D. User Interface → 4. Enables user interaction

### Problem 5: System Design
**Question:** For a car diagnosis expert system, which knowledge representation approach would be most suitable and why?

**Solution:** A rule-based approach would be most suitable because:
- Car diagnosis involves many if-then rules (e.g., IF engine won't start AND battery is good THEN problem_is_starter)
- Symptom-to-cause relationships can be naturally expressed as rules
- Multiple symptoms may point to the same cause, which rule-based systems handle well
- Forward chaining can process multiple symptoms simultaneously
- Rules are easy for mechanics (domain experts) to understand and validate
- The system can provide step-by-step diagnostic procedures

## Key Takeaways

- Expert systems model human expertise using knowledge bases and inference engines
- They consist of five main components: knowledge base, inference engine, user interface, explanation facility, and knowledge acquisition facility
- Forward chaining is data-driven; backward chaining is goal-driven
- Certainty factors provide a way to handle uncertainty in expert systems
- Expert systems have clear advantages but also significant limitations
- The development process requires careful knowledge acquisition and validation

## Additional Practice Problems

### Advanced Problem 1: Conflict Resolution
**Question:** In a forward-chaining expert system, if multiple rules match the working memory, what are the strategies for selecting which rule to fire?

**Solution:**
Common conflict resolution strategies:
1. **Priority/Lexicographic ordering:** Higher priority rules fire first
2. **Recency:** Most recently added facts have higher priority
3. **Specificity:** More specific rules fire before general ones
4. **PEAS (Problem Environment Actuators Sensors)**: Based on the PEAS description of the agent

### Advanced Problem 2: Uncertainty in Expert Systems
**Question:** Given three rules:
- Rule 1: IF A THEN B (CF = 0.7)
- Rule 2: IF C THEN B (CF = 0.5)
- Rule 3: IF D THEN B (CF = -0.4)

If A, C, and D are all true, what is the final CF(B) assuming initial CF(B) = 0?

**Solution:**
Step 1: Rule 1 fires: CF(B) = 0 + 0.7*(1-0) = 0.7
Step 2: Rule 2 fires: Combined CF = 0.7 + 0.5*(1-0.7) = 0.7 + 0.15 = 0.85
Step 3: Rule 3 fires: Since CF is negative, use different formula
CF(B) = 0.85 + (-0.4) = 0.85 - 0.4 = 0.45
Or using proper combination: CF_combined = (CF1 + CF2) / (1 - min(|CF1|, |CF2|)) when signs are same, but when different signs:
CF_combined = (CF1 + CF2) / (1 - min(|CF1|, |CF2|)) = (0.85 - 0.4) / (1 - 0.4) = 0.45 / 0.6 = 0.75

Final CF(B) = 0.75