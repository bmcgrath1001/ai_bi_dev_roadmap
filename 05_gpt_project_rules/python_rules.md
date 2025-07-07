# 🐍 Python Project Rules for ChatGPT

Use these rules when generating or reviewing Python code in this project. These serve as the project's "source of truth" for AI-driven code quality, formatting, and architecture.

---

## ✅ Style & Formatting

- Follow [PEP8](https://peps.python.org/pep-0008/) strictly: indentation, spacing, line length (max 88)
- Use `black` formatting conventions (if any conflicts, favor `black`)
- Use `isort` for import ordering: standard libs → third-party → local
- Always include type hints (`-> None`, `-> str`, etc.)
- Use `snake_case` for variable and function names; `CamelCase` for class names
- No unused imports, unreachable code, or redundant comments

---

## 📦 Project Structure & Organization

- Organize code into reusable functions and classes
- Prefer clear module boundaries over monolithic scripts
- Keep `__main__` blocks minimal; offload logic to other functions
- Create a `utils.py` or `helpers.py` only if functions are reused across modules

---

## 🧪 Testing

- Every function or class should be written to be testable
- Use `pytest` for unit tests unless otherwise specified
- When generating tests:
  - Use fixtures where appropriate
  - Use descriptive test function names: `test_<functionality>_<condition>()`
  - Always test edge cases (e.g. empty lists, nulls, type mismatches)

---

## 🧠 Documentation & Comments

- Every function and class must include a concise docstring:
  ```python
  def clean_transactions(df: pd.DataFrame) -> pd.DataFrame:
      """
      Cleans transaction data by removing nulls and outliers.
      
      Args:
          df: Raw transaction data
        
      Returns:
          Cleaned transaction DataFrame
      """
  ```

## 💬 Comments

- Avoid obvious or redundant inline comments  
- Use comments to clarify **why**, not **what**, when the logic is non-trivial  

---

## 🚨 Error Handling

- Use `try/except` blocks to gracefully handle errors — don’t allow unhandled exceptions  
- Always log errors with enough context to trace the root cause  
- Raise meaningful exceptions (`ValueError`, `TypeError`, etc.) with descriptive messages  

---

## 📊 Libraries & Tooling

- Prefer **pandas** for data manipulation  
- Use **pyarrow** for Parquet handling if needed  
- For visualization: use **Plotly**, **Altair**, or **Matplotlib** (in that order)  
- For date/time: always use `datetime` with explicit timezones (`pytz` or `zoneinfo`)  

---

## 🔒 Security & Privacy

- Never hardcode credentials or tokens  
- Use environment variables or config files with `.env` or `pydantic`  
- Redact or obfuscate any example PII (emails, names, card numbers)  

---

## 🤖 Prompt-Engineering Extras

When asking GPT to write Python code for this project:

- Always start with:  
  > “Write this using the formatting and conventions defined in `python_rules.md`.”  
- If unsure, ask GPT to explain tradeoffs:  
  > “Should this be a class or a function?”  
- Encourage it to output **modular**, **testable**, and **readable** code above all  

---

## 🧠 Reminder

> **Clarity > cleverness**  
> Write code like you’re handing it to a teammate on your last day.

---

## 📚 References

- [PEP8 Style Guide](https://peps.python.org/pep-0008/)  
- [Black Formatter](https://black.readthedocs.io/)  
- [Pytest Documentation](https://docs.pytest.org/)  
- [Google Python Style Guide](https://google.github.io/styleguide/pyguide.html)
