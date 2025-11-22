# Chapter 3: Reasoning Methods (Deductive, Inductive, Uncertain)

## Overview

Reasoning is the process of drawing conclusions from available knowledge using various methods. In artificial intelligence, reasoning methods are crucial for problem-solving, decision-making, and inference. This chapter covers the major reasoning approaches: deductive, inductive, and uncertain reasoning.

## 1. Deductive Reasoning

### Definition
Deductive reasoning is a logical process where conclusions are drawn from general principles or premises. If the premises are true and the logic is valid, the conclusion must also be true.

### Structure
- **Major premise:** General statement
- **Minor premise:** Specific statement
- **Conclusion:** Logical outcome

### Examples
**Classic Example:**
- Major premise: All humans are mortal
- Minor premise: Socrates is a human
- Conclusion: Socrates is mortal

**Formal Logic Example:**
```
∀x (Human(x) → Mortal(x))
Human(Socrates)
∴ Mortal(Socrates)
```

### Rules of Inference
1. **Modus Ponens:** If P then Q; P is true; therefore Q
2. **Modus Tollens:** If P then Q; not Q; therefore not P
3. **Hypothetical Syllogism:** If P then Q; if Q then R; therefore if P then R
4. **Disjunctive Syllogism:** Either P or Q; not P; therefore Q

### Resolution in Deductive Reasoning
Resolution is a rule of inference used in automated theorem proving. It works by converting statements to clause form and applying the resolution principle.

**Resolution Process:**
1. Convert all statements to clause form (disjunctions of literals)
2. Negate the goal statement and add to the set of clauses
3. Repeatedly apply resolution rule until empty clause is derived (proof by contradiction)

**Example:**
Given:
- ¬P ∨ Q
- P
- Goal: Q

Resolution:
- From ¬P ∨ Q and P, we can derive Q
- This proves that Q follows from the premises

## 2. Inductive Reasoning

### Definition
Inductive reasoning involves drawing general conclusions from specific examples or observations. Unlike deductive reasoning, the conclusions are probabilistic rather than certain.

### Characteristics
- **Probabilistic:** Conclusions are likely but not guaranteed to be true
- **Ampliative:** New information is added beyond what was in the premises
- **Empirical:** Based on observation and experience

### Types of Inductive Reasoning
1. **Generalization:** Drawing broad conclusions from specific cases
2. **Analogical reasoning:** Reasoning based on similarities
3. **Causal inference:** Inferring cause-and-effect relationships

### Examples
**Generalization:**
- Observation: Every swan I've seen is white
- Conclusion: All swans are white

**Scientific Method:**
- Collect data from experiments
- Form hypotheses from patterns in data
- Test hypotheses with additional experiments

### Machine Learning Connection
Inductive reasoning is fundamental to machine learning:
- **Training:** Learning patterns from examples
- **Generalization:** Applying learned patterns to new examples
- **Overfitting vs. Underfitting:** Balancing between specific and general patterns

## 3. Uncertain Reasoning

### Need for Uncertain Reasoning
Real-world problems rarely provide complete, certain information. Uncertain reasoning approaches help handle:
- Incomplete knowledge
- Noisy or unreliable data
- Vague or imprecise information
- Conflicting evidence

### Approaches to Uncertain Reasoning

### 3.1 Probability Theory
Probability theory provides a mathematical framework for reasoning with uncertainty.

**Basic Concepts:**
- P(A): Probability of event A occurring
- 0 ≤ P(A) ≤ 1
- P(A) + P(¬A) = 1
- Conditional probability: P(A|B) = P(A ∧ B) / P(B)

**Bayes' Theorem:**
```
P(H|E) = P(E|H) × P(H) / P(E)
```
Where:
- P(H|E): Posterior probability of hypothesis H given evidence E
- P(E|H): Likelihood of evidence given hypothesis
- P(H): Prior probability of hypothesis
- P(E): Prior probability of evidence

**Example:**
```
P(Disease|PositiveTest) = P(PositiveTest|Disease) × P(Disease) / P(PositiveTest)
```

### 3.2 Certainty Factor Theory
Certainty factors are used in expert systems to represent the degree of belief in a hypothesis given evidence.

**Formula:**
```
CF(H, E) = MB(H, E) - MD(H, E)
```
Where:
- MB: Measure of increased belief in H due to E
- MD: Measure of increased disbelief in H due to E
- CF: Value between -1 and +1

**Combining Certainty Factors:**
- For AND: CF_combined = min(CF1, CF2)
- For OR: CF_combined = max(CF1, CF2)
- For rules: CF(H) = CF(E) × CF(rule)

**Example from your exam material:**
Given: if E3 AND (E1 OR E2) THEN H={h1} cf={0.7}
CER(E3)=0.9, CER(E1)=0.5, CER(E2)=0.8
Calculate CER(H):

Step 1: Calculate CER(E1 OR E2) = max(0.5, 0.8) = 0.8
Step 2: Calculate CER(E3 AND (E1 OR E2)) = min(0.9, 0.8) = 0.8
Step 3: Calculate CER(H) = 0.8 × 0.7 = 0.56

### 3.3 Fuzzy Logic
Fuzzy logic allows for degrees of truth between 0 and 1, representing partial membership in sets.

**Key Concepts:**
- Fuzzy sets: Objects can have partial membership
- Membership function: Degree of membership (0 to 1)
- Linguistic variables: Terms like "hot," "cold," "tall"

**Operations:**
- Union: μA∪B(x) = max(μA(x), μB(x))
- Intersection: μA∩B(x) = min(μA(x), μB(x))
- Complement: μĀ(x) = 1 - μA(x)

### 3.4 Dempster-Shafer Theory
This theory extends probability by allowing for ignorance and combining evidence from different sources.

**Key Concepts:**
- Basic probability assignment
- Belief and plausibility functions
- Evidence combination

## 4. Theorem Proving

### Resolution Theorem Proving
Resolution is a complete inference procedure for first-order logic.

**Steps:**
1. Convert premises and negated goal to conjunctive normal form (CNF)
2. Apply resolution rule until an empty clause is derived
3. Empty clause indicates contradiction, proving the goal

**Example:**
Prove that Socrates is mortal given:
- All humans are mortal: ∀x (Human(x) → Mortal(x))
- Socrates is human: Human(Socrates)

1. Convert to CNF: ¬Human(x) ∨ Mortal(x)
2. Add negated goal: ¬Mortal(Socrates)
3. Apply resolution: From ¬Human(x) ∨ Mortal(x) and Human(Socrates), derive Mortal(Socrates)
4. From Mortal(Socrates) and ¬Mortal(Socrates), derive empty clause

### Unification
Unification is the process of finding substitutions that make two expressions identical.

**Example:**
- Expression 1: P(x, f(y))
- Expression 2: P(a, f(b))
- Unifying substitution: {x/a, y/b}

## 5. Practical Applications

### Expert Systems
- Use certainty factors for uncertain reasoning
- Apply logical inference for conclusion drawing
- Combine different reasoning methods

### Natural Language Processing
- Parse ambiguous sentences
- Infer meaning from context
- Resolve references and anaphora

### Planning and Decision Making
- Uncertain reasoning under incomplete information
- Probabilistic planning in uncertain environments

## Practice Problems and Solutions

### Problem 1: Deductive Reasoning
**Question:** Using the rule "If it rains, the ground gets wet" and the fact "It is raining," what can you conclude using modus ponens?

**Solution:**
- Premise: If it rains → ground gets wet (P → Q)
- Fact: It is raining (P)
- Using modus ponens: P → Q, P ⊢ Q
- Conclusion: The ground gets wet

### Problem 2: Resolution Theorem Proving
**Question:** Prove that "Marcus is not loyal to Caesar" given:
1. Marcus is a person
2. Marcus is a Pompeian
3. All Pompeians are Romans
4. Caesar is a ruler
5. All Romans are either loyal to Caesar or hate him
6. People only try to assassinate rulers they are not loyal to
7. Marcus tried to assassinate Caesar

**Solution:**
Convert to clause form:
1. Person(Marcus)
2. Pompeian(Marcus)
3. ¬Pompeian(x) ∨ Roman(x)
4. Ruler(Caesar)
5. ¬Roman(x) ∨ Loyal(x, Caesar) ∨ Hate(x, Caesar)
6. ¬Ruler(y) ∨ ¬Person(x) ∨ Loyal(x, y) ∨ ¬TryAssassinate(x, y)
7. TryAssassinate(Marcus, Caesar)
8. Goal: ¬Loyal(Marcus, Caesar) (negated)

Apply resolution:
- From (2) and (3): Roman(Marcus)
- From (4), (1), and (7) applied to (6): Loyal(Marcus, Caesar)
- From Roman(Marcus) applied to (5): Loyal(Marcus, Caesar) ∨ Hate(Marcus, Caesar)
- But we derived Loyal(Marcus, Caesar) from rule (6), which contradicts the assassination attempt
- Therefore, ¬Loyal(Marcus, Caesar) must be true

### Problem 3: Certainty Factors
**Question:** Given the rule "IF E1 AND E2 THEN H with CF = 0.8" and evidence CER(E1) = 0.7 and CER(E2) = 0.9, calculate CER(H).

**Solution:**
Step 1: Calculate CER(E1 AND E2) = min(0.7, 0.9) = 0.7
Step 2: Calculate CER(H) = 0.7 × 0.8 = 0.56

### Problem 4: Bayes' Theorem
**Question:** In a medical test, if a person has the disease, the test is positive 95% of the time. If a person doesn't have the disease, the test is positive 5% of the time. The disease occurs in 1% of the population. If someone tests positive, what's the probability they have the disease?

**Solution:**
Given:
- P(Positive|Disease) = 0.95
- P(Positive|No Disease) = 0.05
- P(Disease) = 0.01
- P(No Disease) = 0.99

Using Bayes' Theorem:
P(Disease|Positive) = [P(Positive|Disease) × P(Disease)] / P(Positive)

P(Positive) = P(Positive|Disease) × P(Disease) + P(Positive|No Disease) × P(No Disease)
P(Positive) = 0.95 × 0.01 + 0.05 × 0.99 = 0.0095 + 0.0495 = 0.059

P(Disease|Positive) = (0.95 × 0.01) / 0.059 = 0.0095 / 0.059 ≈ 0.161 or 16.1%

### Problem 5: Fuzzy Logic
**Question:** If temperature is represented as a fuzzy set with membership function for "hot" as:
- μ_hot(x) = 0 if x ≤ 20°C
- μ_hot(x) = (x-20)/10 if 20°C < x ≤ 30°C
- μ_hot(x) = 1 if x > 30°C

What is the membership value for 25°C?

**Solution:**
Since 20°C < 25°C ≤ 30°C, we use the second case:
μ_hot(25) = (25-20)/10 = 5/10 = 0.5

The temperature of 25°C has a membership value of 0.5 in the "hot" set.

## Key Takeaways

- Deductive reasoning moves from general principles to specific conclusions with certainty
- Inductive reasoning moves from specific observations to general conclusions with probability
- Uncertain reasoning methods handle incomplete or unreliable information
- Certainty factors, probability theory, and fuzzy logic are important tools for uncertain reasoning
- Resolution theorem proving provides a systematic method for automatic reasoning
- Different reasoning methods are appropriate for different types of problems

## Additional Practice Problems

### Advanced Problem 1: Resolution Proof
**Question:** Given: (1) All humans are mortal (2) Socrates is human. Prove Socrates is mortal using resolution.

**Solution:**
1. Convert to CNF: ¬Human(x) ∨ Mortal(x)
2. Fact: Human(Socrates)
3. Negated goal: ¬Mortal(Socrates)
4. Apply resolution:
   - From ¬Human(x) ∨ Mortal(x) and Human(Socrates): ¬Mortal(Socrates) and Mortal(Socrates)
   - Result: Empty clause, proving the goal

### Advanced Problem 2: Bayesian Network
**Question:** In a medical diagnosis system, 5% of people have a disease. The test is 90% accurate when the disease is present, and 95% accurate when it's not. If someone tests positive, what's the probability they have the disease?

**Solution:**
Using Bayes' theorem:
- P(D) = 0.05
- P(Pos|D) = 0.90
- P(Pos|~D) = 0.05
- P(D|Pos) = [P(Pos|D) × P(D)] / [P(Pos|D) × P(D) + P(Pos|~D) × P(~D)]
- P(D|Pos) = [0.90 × 0.05] / [0.90 × 0.05 + 0.05 × 0.95] = 0.045 / (0.045 + 0.0475) = 0.486 or ~48.6%