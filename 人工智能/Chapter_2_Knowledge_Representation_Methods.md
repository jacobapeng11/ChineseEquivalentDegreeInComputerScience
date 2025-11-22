# Chapter 2: Knowledge Representation Methods

## Overview

Knowledge representation is a fundamental aspect of artificial intelligence that deals with how to represent information about the world in a form that a computer system can use to solve complex tasks. It's the process of encoding knowledge in a formal structure that can be processed by computational systems.

### What is Knowledge Representation?

**Knowledge Representation** is the study of how knowledge about the world can be represented and used by programs to exhibit intelligent behavior. It involves the process of mapping knowledge from one form to another, usually into a symbolic form that can be manipulated by computer programs.

### Key Properties of Knowledge Representation Systems

1. **Representational Adequacy:** The ability to represent the required knowledge in a natural and intuitive way.
2. **Inferential Adequacy:** The ability to manipulate the knowledge to derive new information.
3. **Inferential Efficiency:** The ability to focus the inference mechanism on the most relevant knowledge.
4. **Acquisitional Efficiency:** The ability to acquire new knowledge easily.

### Types of Knowledge Representation Methods

## 1. Logic-Based Representations

### Propositional Logic
Propositional logic is the simplest form of logic where knowledge is represented using propositions (statements that are either true or false).

**Examples:**
- "It is raining" → Rain
- "The grass is wet" → Wet
- "If it is raining, the grass is wet" → Rain → Wet

**Advantages:**
- Simple to understand and implement
- Well-established mathematical foundation

**Disadvantages:**
- Limited expressiveness
- Cannot represent relationships between objects

### Predicate Logic (First-Order Logic)
Predicate logic extends propositional logic by allowing quantification over objects and the use of predicates.

**Components:**
- **Constants:** Specific objects (e.g., John, Mary)
- **Variables:** General objects (e.g., x, y, z)
- **Predicates:** Properties or relations (e.g., Human(x), Father(x,y))
- **Functions:** Mapping from objects to objects (e.g., Mother(x))
- **Quantifiers:** Universal (∀) and existential (∃)

**Example:**
```
∀x (Human(x) → Mortal(x))
Human(Socrates)
∴ Mortal(Socrates)
```

**Advantages:**
- More expressive than propositional logic
- Can represent relationships between objects
- Supports complex reasoning

**Disadvantages:**
- More complex to implement
- Computational complexity can be high

## 2. Network Representations

### Semantic Networks
Semantic networks represent knowledge as a network of interconnected nodes and labeled arcs.

**Structure:**
- **Nodes:** Represent concepts or objects
- **Arcs:** Represent relationships between concepts

**Example:**
```
    Bird
     |
   has-a
     |
   Wings
```

**Advantages:**
- Intuitive and visual representation
- Easy to understand
- Supports inheritance reasoning

**Disadvantages:**
- Limited inference mechanisms
- Can become complex for large knowledge bases

### Frames
Frames are data structures that represent stereotypical situations or objects.

**Components:**
- **Slots:** Attributes of the frame
- **Facets:** Properties of slots
- **Default values:** For incomplete information

**Example:**
```
Frame: Bird
  ISA: Animal
  has-wings: true
  flies: true
  lays-eggs: true
  
Frame: Penguin
  ISA: Bird
  flies: false  (overrides parent)
```

## 3. Production Systems

Production systems represent knowledge as a set of rules (IF-THEN statements).

**Components:**
- **Rules:** IF condition THEN action
- **Working Memory:** Current facts in the system
- **Control Strategy:** Determines which rules to fire

**Example:**
```
Rule 1: IF animal has hair THEN animal is mammal
Rule 2: IF animal gives milk THEN animal is mammal
Rule 3: IF animal has feathers THEN animal is bird
```

**Advantages:**
- Easy to understand and modify
- Good for reasoning with uncertain information
- Modular knowledge representation

**Disadvantages:**
- Can lead to inefficient reasoning
- Knowledge engineering can be difficult

## 4. Structured Knowledge Representations

### Scripts
Scripts represent knowledge about stereotypical sequences of events.

**Components:**
- **Entry conditions:** What must be true for script to apply
- **Props:** Objects involved in the script
- **Roles:** Participants in the script
- **Scenes:** Sequences of events
- **Results:** What is true after script execution

**Example: Restaurant script**
- Entry: Person is hungry, has money
- Props: Tables, menu, food, money
- Scenes: Ordering, eating, paying

## Applications of Knowledge Representation

1. **Expert Systems:** Representing domain-specific knowledge
2. **Natural Language Processing:** Understanding and generating language
3. **Knowledge Bases:** Storing and retrieving structured information
4. **Ontology Development:** Creating formal specifications of concepts in a domain
5. **Semantic Web:** Adding meaning to web content

## Issues in Knowledge Representation

1. **Expressiveness vs. Efficiency Trade-off:** More expressive representations often have higher computational costs
2. **Frame Problem:** How to represent what remains unchanged when an action occurs
3. **Qualification Problem:** The difficulty of listing all conditions under which a statement is true
4. **Scalability:** Handling large knowledge bases efficiently

## Practice Problems and Solutions

### Problem 1: Logic Representation
**Question:** Represent the following statement in first-order logic: "All students who study hard pass their exams."

**Solution:**
```
∀x (Student(x) ∧ StudyHard(x) → PassExam(x))
```

### Problem 2: Semantic Network
**Question:** Create a semantic network for the following knowledge: "A dog is a mammal. A dog has four legs. A mammal has hair."

**Solution:**
```
    Dog
     |
   is-a
     |
   Mammal
   /    \
has-hair  has-legs
  |        |
"covered"  "four"
```

### Problem 3: Frame Representation
**Question:** Create a frame representation for a car with the following attributes: has-engine (yes), number-of-wheels (4), fuel-type (gasoline), can-fly (no).

**Solution:**
```
Frame: Car
  has-engine: yes
  number-of-wheels: 4
  fuel-type: gasoline
  can-fly: no
```

### Problem 4: Rule-Based System
**Question:** Create a production rule for: "If the temperature is above 30°C and it's summer, then recommend wearing light clothes."

**Solution:**
```
IF (Temperature > 30) AND (Season = summer) 
THEN Recommend(light_clothes)
```

### Problem 5: Knowledge Representation Choice
**Question:** For a medical diagnosis system, which knowledge representation method would be most appropriate and why?

**Solution:** A production system would be most appropriate because:
- Medical knowledge can be naturally expressed as IF-THEN rules
- It allows for easy modification of diagnostic rules
- Supports reasoning with uncertainty through confidence factors
- Facilitates explanation of diagnostic decisions
- Rules can be organized by medical specialties or symptoms

## Key Takeaways

- Knowledge representation is fundamental to AI, enabling systems to store, retrieve, and reason with information
- Different methods have different strengths and weaknesses
- Logic-based representations offer formal reasoning capabilities
- Network representations provide intuitive visual structures
- Production systems are good for rule-based reasoning
- Choice of representation method depends on the application requirements

## Additional Practice Problems

### Advanced Problem 1: Predicate Logic Conversion
**Question:** Convert to predicate logic: "Every student loves at least one computer science course."

**Solution:**
∀x (Student(x) → ∃y (Course(y) ∧ Field(y, computer_science) ∧ Loves(x, y)))

### Advanced Problem 2: Frame Inheritance
**Question:** Consider:
- Frame: Bird, ISA: Animal, can-fly: default(T), lays-eggs: default(T)
- Frame: Penguin, ISA: Bird, can-fly: F
- Frame: Ostrich, ISA: Bird, can-fly: F

If we create an instance Tweety of type Bird, what are the default values for can-fly and lays-eggs? What if Tweety is of type Penguin?

**Solution:**
- Tweety (Bird): can-fly=T, lays-eggs=T (from inheritance)
- Tweety (Penguin): can-fly=F (overrides parent), lays-eggs=T (inherited from Bird)