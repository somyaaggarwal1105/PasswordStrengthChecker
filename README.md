# 🔐 Password Strength Checker

A command-line tool built in Java that analyzes password strength in real time and provides clear, actionable feedback to help users create stronger, more secure passwords.

## Features

- **Weighted scoring system (0–7)** based on:
  - Length (8+, 12+, 16+ characters)
  - Presence of uppercase letters
  - Presence of lowercase letters
  - Presence of numbers
  - Presence of special characters
- **Strength classification** — WEAK / MEDIUM / STRONG, with color-coded terminal output
- **Visual strength meter** — a progress-bar style indicator for quick at-a-glance feedback
- **Criteria checklist** — shows exactly which requirements a password passes or fails (✔ / ✘)
- **Actionable suggestions** — tells the user specifically what to improve (e.g. "Add at least one UPPERCASE letter")
- **Interactive CLI loop** — test multiple passwords in a single session without restarting the program

## Demo

```
╔══════════════════════════════════════╗
║      PASSWORD STRENGTH CHECKER       ║
╚══════════════════════════════════════╝

Enter a password to check (or 'quit' to exit): MyP@ssw0rd123

══════════════ ANALYSIS RESULT ══════════════
  Password  : ************* (13 chars)
  Strength  : 🟢 STRONG
  Score     : 7/7
  Meter     : ██████████

──────── Criteria Check ────────
  Length ≥ 8   : ✔ Yes
  Length ≥ 12  : ✔ Yes
  Uppercase    : ✔ Yes
  Lowercase    : ✔ Yes
  Numbers      : ✔ Yes
  Special Char : ✔ Yes

  ✅ Excellent! Your password meets all criteria.
═════════════════════════════════════════════
```

## How It Works

The checker evaluates each password against six criteria and assigns a score out of 7. Strength is classified as:

| Score | Strength |
|-------|----------|
| 0–3   | 🔴 WEAK   |
| 4–5   | 🟡 MEDIUM |
| 6–7   | 🟢 STRONG |

If a password doesn't meet a criterion, the tool prints a specific suggestion (e.g. missing special characters, too short, etc.) rather than a generic "weak password" message.

## Tech Stack

- **Language:** Java
- **Libraries:** `java.util.Scanner`, `java.util.ArrayList`, Java Streams (`chars().anyMatch(...)`)
- **Interface:** Command-line (ANSI escape codes for colored output)

## Getting Started

### Prerequisites
- Java JDK 8 or higher installed

### Run it

```bash
# Compile
javac PasswordStrengthChecker.java

# Run
java PasswordStrengthChecker
```

Then enter any password to see its strength analysis, or type `quit` to exit.

> **Note:** Colored output relies on ANSI escape codes. These work natively on most Linux/macOS terminals and modern Windows terminals (Windows Terminal, VS Code integrated terminal). If you're using an older Windows `cmd.exe`, colors may not render correctly.

## Possible Future Improvements

- Check against a list of common/leaked passwords (e.g. via the [Have I Been Pwned API](https://haveibeenpwned.com/API/v3))
- Calculate true password entropy instead of rule-based scoring
- Add a GUI or web version for broader accessibility
- Detect predictable patterns (e.g. "Password123!", keyboard walks like "qwerty")
  
-------

⭐ If you found this useful, consider giving the repo a star!
