# Sample Test Cases

Git-backed test cases for the **UI Explorer Agent**.

The agent clones/pulls this repository and reads cases from `test-cases/`.

## Layout

```text
Sample_test_cases/
├── test-cases/          # Input Markdown / YAML (source of truth)
├── output/              # Extracted locator JSON (--phase explore)
├── generated/           # Playwright UI automation scripts (--phase generate)
├── .auth/               # Local storageState (gitignored)
└── README.md
```

Locators live in `output/`. Generated Playwright specs live in `generated/` (separate from test intent).

## Enrichment tags

Lifecycle tags track whether UI Explorer has frozen locators for a case:

| Tag | Meaning |
|-----|---------|
| `@enrichme` | Not explored yet — needs locator discovery |
| `@partially_enriched` | Explored, but some interactive steps still lack locators |
| `@enriched` | Explored — required fill/click/select steps have locators |

YAML:

```yaml
tags:
  - enriched
  - the-internet
```

Markdown:

```markdown
## Tags
- enrichme
- opencart
```

Explore stamps `enrichment_tag` + `tags` into `output/ui_explorer_*.json`.  
Generate emits Playwright tags on each `test(..., { tag: [...] })`.

Filter:

```bash
npx playwright test --grep @enriched
npx playwright test --grep @enrichme
```

## Test cases

| ID | File | Enrichment | Intent |
|----|------|------------|--------|
| TC001 | `TC001_User_Login.md` | `@enrichme` | OpenCart login |
| TC002 | `TC002_Add_Product_To_Cart.md` | `@enrichme` | OpenCart add to cart |
| TC003 | `TC003_Wishlist_Product.md` | `@enrichme` | OpenCart wishlist |
| TC004 | `TC004_Search_Product.md` | `@enrichme` | OpenCart search |
| login_smoke | `login_smoke.yaml` | `@enriched` | the-internet login smoke |
| TC005 | `TC005_form_login.yaml` | `@enriched` | Form authentication |
| TC006 | `TC006_checkboxes.yaml` | `@enriched` | Checkboxes navigation |
| TC007 | `TC007_dropdown.yaml` | `@enriched` | Dropdown select |
| TC008 | `TC008_add_remove_elements.yaml` | `@enriched` | Add/Remove Elements |
| TC009 | `TC009_forgot_password.yaml` | `@enriched` | Forgot password |
| TC010 | `TC010_inputs.yaml` | `@enriched` | Number inputs |
| TC011 | `TC011_status_codes.yaml` | `@enriched` | Status code links |
| TC012 | `TC012_key_presses.yaml` | `@enriched` | Key presses |

OpenCart cases (TC001–TC004) need `APP_USERNAME` / `APP_PASSWORD`.  
the-internet cases (login_smoke, TC005–TC012) use public demo pages; login specs need demo creds `tomsmith` / `SuperSecretPassword!`.

## Pipeline

```bash
# From WestField-AI-Agent-Development
python main.py --phase explore --test-case ../Sample_test_cases/test-cases/TC005_form_login.yaml --no-llm --backend playwright --no-login
python main.py --phase generate
cd ../Sample_test_cases
npx playwright test --grep @enriched
```
