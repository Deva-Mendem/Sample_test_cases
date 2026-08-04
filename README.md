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

## Test cases

| ID | File | Steps | Intent |
|----|------|-------|--------|
| TC001 | `TC001_User_Login.md` | 5 | OpenCart login |
| TC002 | `TC002_Add_Product_To_Cart.md` | 6 | OpenCart add to cart |
| TC003 | `TC003_Wishlist_Product.md` | 5+ | OpenCart wishlist |
| TC004 | `TC004_Search_Product.md` | 5+ | OpenCart search |
| login_smoke | `login_smoke.yaml` | 7 | the-internet login smoke |
| TC005 | `TC005_form_login.yaml` | 7 | Form authentication |
| TC006 | `TC006_checkboxes.yaml` | 8 | Checkboxes navigation |
| TC007 | `TC007_dropdown.yaml` | 6 | Dropdown select |
| TC008 | `TC008_add_remove_elements.yaml` | 7 | Add/Remove Elements |
| TC009 | `TC009_forgot_password.yaml` | 6 | Forgot password |
| TC010 | `TC010_inputs.yaml` | 6 | Number inputs |
| TC011 | `TC011_status_codes.yaml` | 7 | Status code links |
| TC012 | `TC012_key_presses.yaml` | 6 | Key presses |

OpenCart cases (TC001–TC004) need `APP_USERNAME` / `APP_PASSWORD`.  
the-internet cases (login_smoke, TC005–TC012) use public demo pages; login specs need demo creds `tomsmith` / `SuperSecretPassword!`.

## Pipeline

```bash
# From WestField-AI-Agent-Development
python main.py --phase explore --test-case ../Sample_test_cases/test-cases/TC005_form_login.yaml --no-llm --backend playwright --no-login
python main.py --phase generate
cd ../Sample_test_cases
npx playwright test
```
