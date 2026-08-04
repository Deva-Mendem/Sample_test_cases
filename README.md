# Sample Test Cases

Git-backed Markdown test cases for the **UI Explorer Agent**.

The agent clones/pulls this repository and reads cases from `test-cases/`.

## Layout

```text
Sample_test_cases/
├── test-cases/          # Input Markdown (source of truth)
├── output/              # Locator JSON from --phase explore
├── generated/           # Playwright specs from --phase generate
├── .auth/               # Local storageState (gitignored)
└── README.md
```

## Test cases

| ID | File | Intent |
|----|------|--------|
| TC001 | `TC001_User_Login.md` | Login |
| TC002 | `TC002_Add_Product_To_Cart.md` | Add to cart |
| TC003 | `TC003_Wishlist_Product.md` | Wishlist |
| TC004 | `TC004_Search_Product.md` | Search |
| login_smoke | `login_smoke.md` | Simple login (the-internet) |

Credentials use `${APP_USERNAME}` / `${APP_PASSWORD}` placeholders — real values come from the agent `.env`.

## Sync from the agent

```bash
# Agent clones/pulls this repo automatically before explore
python main.py --phase explore --no-llm --backend playwright

# Or force sync only
python -m scripts.sync_sample_test_cases
```
