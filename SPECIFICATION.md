# Semantic Fork Method - Technical Specification

**Version:** 1.0.0  
**Last Updated:** January 4, 2026  
**Author:** Ruth Aharon

---

## Abstract

The Semantic Fork Method (SFM) is a two-phase framework for optimizing natural language prompts through systematic disambiguation. Unlike traditional prompt rewriting systems that attempt to infer user intent, SFM surfaces decision points where a single phrase maps to multiple mutually exclusive intents, allowing users to make strategic choices before semantic compression occurs.

SFM introduces two key innovations:
1. **Pseudo-Antonyms**: Terms that appear interchangeable in casual language but represent fundamentally different strategies
2. **Fork-First Pattern**: Detecting and resolving strategic ambiguity before optimization

---

## 1. Core Definitions

### 1.1 Pseudo-Antonym

**Definition:** A pair or set of terms where:
1. They appear to address the same goal in natural language
2. They represent mutually exclusive strategies or paradigms
3. Selecting one precludes the others
4. They trigger different cascading terminology changes

**Formal Criteria:**
