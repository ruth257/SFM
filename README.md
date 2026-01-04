# Semantic Fork Method

> A framework for eliminating ambiguity in prompt optimization through strategic disambiguation

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)](https://github.com/ruthaharon/semantic-fork-method)

## The Problem

When you say **"help me grow my business,"** you might mean:
- 📈 Increase revenue per customer (monetization)
- 👥 Acquire more users (growth marketing)
- 🌍 Expand to new markets (geographic expansion)

These require **completely different strategies** and **different terminology**.

Traditional prompt optimization tools:
- ❌ Pick one for you (often wrong)
- ❌ Try to include all three (generic bloat: "optimize operations to scale infrastructure by expanding market reach...")
- ❌ Ask vague clarifying questions with no structured options

## The Solution

The **Semantic Fork Method** detects hidden decision points and surfaces them as structured choices.

### Example

**Before (Traditional tool):**
```
Input:  "Help me grow my SaaS startup faster in Asia"

Output: "Optimize operations to scale SaaS infrastructure by expanding 
         market reach to target new customer segments in Asian markets"

Problem: 
- 80% MORE tokens (16 → 29)
- Generic buzzword soup
- No strategic clarity
```

**After (Semantic Fork Method):**
```
Input:  "Help me grow my SaaS startup faster in Asia"

System: ⚠️  FORK DETECTED - "grow faster" has multiple meanings:
        → User Acquisition Velocity [Growth Marketing]
        → Revenue Expansion [Monetization]  ← User picks this
        → Market Penetration [Go-to-Market]

System: 🔍 Refine terms:
        • "startup" → 🔥 Series A venture [+42%]
        • "Asia" → 🔥 SEA digital economy [+58%]

Output: "ARPU expansion strategy for Series A SaaS in SEA digital economy"

Result:
- 60% FEWER tokens (16 → 10)
- Surgically precise
- Clear strategic direction
```

---

## Core Concepts

### 1. **Pseudo-Antonym**
Terms that appear interchangeable in casual language but represent **mutually exclusive strategies**.

**Example:**
```
"make money off my firm" → [exit strategy | IPO | M&A]

These aren't synonyms:
- Exit strategy → Sell the company (terminal event)
- IPO → Raise capital while staying involved (growth event)  
- M&A → Strategic consolidation (expansion event)
```

### 2. **Semantic Fork**
A decision point where user intent branches into 2+ mutually exclusive paths. Requires user decision to proceed.

### 3. **Fulcrum Token**
A low-resolution term that can be sharpened while maintaining the same intent.

**Example:**
```
Fulcrum: "countries"
Alternatives: [Global South | OECD nations | coastal regions]
Same intent, different strategic anchors
```

---

## How It Works
```
USER INPUT → PHASE 1: Detection
              ├─ Protect tokens
              ├─ Detect forks
              ├─ Locate fulcrums  
              └─ Audit noise
                  ↓
              Forks found?
                  ↓
              SHOW FORK UI
              WAIT for user choice
                  ↓
           PHASE 2: Resolution
              ├─ Apply choice
              ├─ Cascade changes
              └─ Strip noise
                  ↓
           OPTIMIZED PROMPT
```

---

## Key Principles

### 1. Never Synthesize Across Forks
**Wrong:** "Optimize operations to scale infrastructure by expanding market reach"  
**Right:** Detect fork → User picks ONE → Optimize on that path

### 2. Pseudo-Antonyms Trigger Cascades
User picks "IPO" → "firm" becomes "issuer", "profit" becomes "EBITDA"

### 3. Cohesion Through Constraint
Alternatives pre-filtered for semantic alignment (embedding similarity >0.70)

---

## Documentation

- 📖 [Full Specification](SPECIFICATION.md) - Complete technical documentation
- 📊 [Flowchart](FLOWCHART.md) - Visual process diagram
- 💡 [Examples](EXAMPLES.md) - Real-world use cases
- 🔧 [Implementation Guide](implementation/) - How to integrate
- 🧪 [Test Cases](tests/) - Validation suite

---

## Quick Start

### System Prompts

Pre-written prompts for Phase 1 (detection) and Phase 2 (resolution) are in [`/prompts`](prompts/).

Compatible with:
- ✅ Claude (Anthropic)
- ✅ GPT-4 (OpenAI)
- ✅ Gemini (Google)

### Basic Usage Pattern
```javascript
// Phase 1: Detect forks
const analysis = await llm({
  system: phase1_prompt,
  user: userPrompt
});

// If forks found, show UI and wait for user
if (!analysis.can_proceed_to_resolution) {
  const userChoice = await showForkUI(analysis);
  
  // Phase 2: Resolve with user input
  const result = await llm({
    system: phase2_prompt,
    user: JSON.stringify({prompt: userPrompt, choices: userChoice})
  });
}
```

---

## Applications Beyond Prompts

The pattern generalizes to any ambiguous optimization request:

- **Code refactoring:** "optimize function" → [speed | memory | readability]
- **Document editing:** "improve section" → [accuracy | accessibility | brevity]
- **Product design:** "better UX" → [reduce friction | increase engagement]

---

## Metrics

| Metric | Target | How to Measure |
|--------|--------|----------------|
| **Token Efficiency** | 20-50% reduction | (original - optimized) / original |
| **Precision Gain** | +50-80% | Expert terminology density increase |
| **Cohesion Score** | >0.75 | Average embedding similarity |

---

## Contributing

Contributions welcome! Priority areas:

- 🎯 Domain-specific fork taxonomies (legal, medical, technical)
- 🎨 UI implementations (React, CLI)
- 🌍 Non-English adaptations
- 🧪 Additional test cases

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## Citation
```bibtex
@misc{semantic-fork-method-2026,
  author = {Ruth Aharon},
  title = {Semantic Fork Method: A Framework for User-Guided Prompt Disambiguation},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/ruthaharon/semantic-fork-method}
}
```

---

## License

MIT License - see [LICENSE](LICENSE)

Copyright (c) 2026 Ruth Aharon

---

## Author

**Ruth Aharon**  
📧 ruth@thedatacoach.net  
🌐 [The Data Coach](https://thedatacoach.net)

*Developed while building a prompt optimization tool on Base44*

---

## Acknowledgments

- Inspired by active learning patterns in machine learning
- Disambiguation concepts from computational linguistics
- Design pattern thinking from software architecture

---

⭐ **Star this repo if you find it useful!**

[Report Bug](https://github.com/ruthaharon/semantic-fork-method/issues) · [Request Feature](https://github.com/[ruthaharon/semantic-fork-method](https://github.com/ruth2)/issues)
```

---

### **FILE 3: `.gitignore`**

Create file: `.gitignore`
```
# Dependencies
node_modules/
__pycache__/
*.pyc
.venv/
venv/

# IDE
.vscode/
.idea/
*.swp
*.swo
*~

# OS
.DS_Store
Thumbs.db

# Build
dist/
build/
*.egg-info/

# Secrets
.env
secrets.json
api_keys.txt

# Test outputs
test_outputs/
*.log
