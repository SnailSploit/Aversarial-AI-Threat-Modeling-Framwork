# Ai-PT-F: Adversarial AI Prompting Framework

A comprehensive reference for adversarial techniques (TTPs) used to test, bypass, or subvert AI safety mechanisms. This document includes:

- **11 Tactics** grouping 50 specific techniques (AiPTF-001 to AiPTF-050).  
- Each technique includes a short explanation and a sample jailbreaking prompt.

---

## Table of Contents

### Tactic I: Context Manipulation & Prompt Injection
1. [AiPTF-001: Contextual Drift Injection](#aiptf-001-contextual-drift-injection)
2. [AiPTF-002: Persona Override Attack](#aiptf-002-persona-override-attack)
3. [AiPTF-003: Conditional Refusal Override](#aiptf-003-conditional-refusal-override)
4. [AiPTF-004: System Role Injection](#aiptf-004-system-role-injection)
5. [AiPTF-005: Multi-Persona Conflict Induction](#aiptf-005-multi-persona-conflict-induction)

### Tactic II: Semantic Evasion & Cloaking Techniques
6. [AiPTF-006: Lexical Substitution Attack](#aiptf-006-lexical-substitution-attack)
7. [AiPTF-007: Metaphorical Reframing Attack](#aiptf-007-metaphorical-reframing-attack)
8. [AiPTF-008: Historical Framing Attack](#aiptf-008-historical-framing-attack)
9. [AiPTF-009: Fictional Scenario Exploitation](#aiptf-009-fictional-scenario-exploitation)
10. [AiPTF-010: Recursive Agreement Exploit](#aiptf-010-recursive-agreement-exploit)

### Tactic III: Logical Exploitation & Constraint Breaking
11. [AiPTF-011: Hypothetical Legal Defense Attack](#aiptf-011-hypothetical-legal-defense-attack)
12. [AiPTF-012: Reverse-Engineering Ethical Justifications](#aiptf-012-reverse-engineering-ethical-justifications)
13. [AiPTF-013: Forced Contextual Misinterpretation](#aiptf-013-forced-contextual-misinterpretation)
14. [AiPTF-014: \"Do Not Answer\" Reversal](#aiptf-014-do-not-answer-reversal)
15. [AiPTF-015: Reverse Engineering Model Biases](#aiptf-015-reverse-engineering-model-biases)

### Tactic IV: Multi-Turn Exploits & AI Memory Subversion
16. [AiPTF-016: Context Overload Attack](#aiptf-016-context-overload-attack)
17. [AiPTF-017: Stepwise Extraction via Multi-Turn Disaggregation](#aiptf-017-stepwise-extraction-via-multi-turn-disaggregation)
18. [AiPTF-018: Adversarial Context Memory Injection](#aiptf-018-adversarial-context-memory-injection)
19. [AiPTF-019: Hidden Context Trojan Injection](#aiptf-019-hidden-context-trojan-injection)
20. [AiPTF-020: Self-Referential Answer Injection](#aiptf-020-self-referential-answer-injection)

### Tactic V: API & Model-Level Attacks
21. [AiPTF-021: Token Length Manipulation Attack](#aiptf-021-token-length-manipulation-attack)
22. [AiPTF-022: Encoding & Character Obfuscation](#aiptf-022-encoding--character-obfuscation)
23. [AiPTF-023: Cross-Language Jailbreaking](#aiptf-023-cross-language-jailbreaking)
24. [AiPTF-024: System Message Injection (Indirect Instruction Takeover)](#aiptf-024-system-message-injection-indirect-instruction-takeover)
25. [AiPTF-025: Few-Shot Adversarial Fine-Tuning](#aiptf-025-few-shot-adversarial-fine-tuning)

### Tactic VI: Adversarial Training Data Manipulation
26. [AiPTF-026: Data Poisoning via Reinforcement Feedback Loops](#aiptf-026-data-poisoning-via-reinforcement-feedback-loops)
27. [AiPTF-027: Model Drift Exploitation](#aiptf-027-model-drift-exploitation)
28. [AiPTF-028: Publicly Crowdsourced AI Poisoning](#aiptf-028-publicly-crowdsourced-ai-poisoning)
29. [AiPTF-029: Adversarial Sample Injection](#aiptf-029-adversarial-sample-injection)
30. [AiPTF-030: Self-Referential Answer Injection in Training](#aiptf-030-self-referential-answer-injection-in-training)

### Tactic VII: AI Output Manipulation & Model Blind Spots
31. [AiPTF-031: Chain-of-Thought Exploitation](#aiptf-031-chain-of-thought-exploitation)
32. [AiPTF-032: Adversarial Sentence Fragments](#aiptf-032-adversarial-sentence-fragments)
33. [AiPTF-033: Redundant Answer Extraction via Multi-Model Comparison](#aiptf-033-redundant-answer-extraction-via-multi-model-comparison)
34. [AiPTF-034: Reverse Engineering Model Biases for Predictable Outputs](#aiptf-034-reverse-engineering-model-biases-for-predictable-outputs)
35. [AiPTF-035: Token Manipulation Attack](#aiptf-035-token-manipulation-attack)

### Tactic VIII: Advanced Logical & Constraint Exploitation Attacks
36. [AiPTF-036: Uncertainty Amplification Attack](#aiptf-036-uncertainty-amplification-attack)
37. [AiPTF-037: Forced Contextual Misinterpretation](#aiptf-037-forced-contextual-misinterpretation)
38. [AiPTF-038: \"Do Not Answer\" Reversal](#aiptf-038-do-not-answer-reversal)
39. [AiPTF-039: Ethical Justification Overload](#aiptf-039-ethical-justification-overload)
40. [AiPTF-040: Reverse Engineering Answer Generation](#aiptf-040-reverse-engineering-answer-generation)

### Tactic IX: Multi-Turn AI Context Persistence Exploits
41. [AiPTF-041: Adversarial Context Memory Injection](#aiptf-041-adversarial-context-memory-injection)
42. [AiPTF-042: Hidden Context Trojan Injection](#aiptf-042-hidden-context-trojan-injection)
43. [AiPTF-043: Multi-Model Answer Inconsistency Exploitation](#aiptf-043-multi-model-answer-inconsistency-exploitation)
44. [AiPTF-044: Recursive Self-Referencing Injection](#aiptf-044-recursive-self-referencing-injection)
45. [AiPTF-045: Distributed Prompt Fragmentation](#aiptf-045-distributed-prompt-fragmentation)

### Tactic X: Model Exploitation Through External Knowledge Injection
46. [AiPTF-046: External Citation Manipulation](#aiptf-046-external-citation-manipulation)
47. [AiPTF-047: Reverse Socratic Interrogation](#aiptf-047-reverse-socratic-interrogation)
48. [AiPTF-048: Exploiting AI Answer Inconsistencies Across Models](#aiptf-048-exploiting-ai-answer-inconsistencies-across-models)

### Tactic XI: AI Model Training & Output Manipulation Attacks
49. [AiPTF-049: Synthetic Self-Amplification Attack](#aiptf-049-synthetic-self-amplification-attack)
50. [AiPTF-050: Recursive Answer Reframing (Looped Content Regeneration)](#aiptf-050-recursive-answer-reframing-looped-content-regeneration)

---

# Detailed Techniques & Jailbreaking Prompts

Below, each technique has:
- **Short Explanation**: Brief overview of how/why it subverts safety.
- **Detailed Jailbreaking Prompt**: An example adversarial prompt that exploits the technique.

---

## AiPTF-001: Contextual Drift Injection

**Short Explanation**  
An attacker starts with benign context and gradually steers the AI into disallowed content. The “drift” happens so gradually that the model may not trigger refusal until it’s too late.

**Detailed Jailbreaking Prompt**  
