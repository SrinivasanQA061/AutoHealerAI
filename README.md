# 🤖 AutoHealerAI - Intelligent Self-Healing for Test Automation

**AutoHealerAI** is an intelligent self-healing framework designed to automatically resolve script failures in test automation—starting with handling the **NoSuchElementException** in Selenium-based UI tests.

## 🔍 Purpose

Modern test automation often suffers from brittle scripts due to dynamic locators, frequent UI changes, or inconsistent DOM structures. AutoHealerAI aims to:

- Minimize manual debugging and maintenance of failed scripts.
- Heal test scripts in real-time by identifying alternative strategies.
- Provide an extensible foundation to support multiple exception types.

Our initial focus is **automatically healing `NoSuchElementException`**.

---

## 🚀 Key Features

- 🛠️ **Auto-Healing for NoSuchElementException**
  - Intelligent DOM scanning and alternative locator strategies.
  - Uses historical execution data and element context to re-identify missing elements.

- 🔁 **Retry with Smart Locator Suggestions**
  - Replaces failed locators dynamically using fallback options: XPath variations, CSS selectors, neighbor-based heuristics, etc.

- 📊 **Failure Reporting and Auto-Heal Logs**
  - Generates reports on healed vs non-healed errors.
  - Provides traceability of what was healed and how.

- 🧠 **AI/ML Integration (Planned)**
  - Future releases will include ML models to predict and recommend healing options based on test history and DOM changes.

---

## 🧱 Tech Stack

- **Java** (Core Language)
- **Selenium WebDriver** (UI Automation)
- **TestNG** (Testing Framework)
- **Maven** (Build Tool)
- **Log4j** (Logging)
- *(Planned)* AI module using **Python/ONNX** for smart healing decisions

---

## 🧪 How It Works (Overview)

1. Test execution starts with standard locators.
2. On `NoSuchElementException`, AutoHealerAI intercepts the failure.
3. It analyzes the DOM and searches for similar elements using:
   - DOM structure similarity
   - Neighbor-based relations
   - Historical locator patterns
4. Applies the best-match locator to recover execution.
5. Logs the healing decision with a confidence score.

---

## 📁 Project Structure

```bash
AutoHealerAI/
│
├── src/
│   ├── main/java/com/autohealer/core         # Healing engine logic
│   ├── main/java/com/autohealer/utils        # DOM utilities and locators
│   └── test/java/com/autohealer/tests        # Sample test scripts
│
├── resources/
│   └── config.properties                     # Configurable properties
│
├── logs/
├── pom.xml
└── README.md
