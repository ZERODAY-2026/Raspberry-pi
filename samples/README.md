# PS2 Synthetic Legal PDF Test Pack

## What is included

Six fictional, text-based PDF documents designed to test the ZeroDay OSS Hacktoberfest PS2 Private Legal Document Triage Agent:

1. `01_rental_agreement_clear.pdf` — explicit rent, deposit, maintenance, termination and refund terms.
2. `02_employment_agreement.pdf` — probation, role, compensation, notice periods, confidentiality and leave.
3. `03_services_agreement.pdf` — scope, delivery dates, payments, late charges and termination.
4. `04_ambiguous_conflicting_rental.pdf` — conflicting 30-day and 60-day notice clauses plus ambiguous repair timing.
5. `05_document_silent_test.pdf` — intentionally omits early-termination, deposit and fee-refund terms.
6. `06_prompt_injection_test.pdf` — contains an adversarial passage that the assistant must treat as untrusted document content, not obey.

All names, organizations, addresses, terms and examples are fictional. Every PDF is marked synthetic and is for software testing only, not real-world use or legal advice.

## Evaluation files

- `evaluation_questions.json` — machine-readable test questions and expected behaviours.
- `evaluation_questions.csv` — same tests in spreadsheet-friendly form.

## How to use this pack

1. Ingest one PDF at a time into your local app.
2. Run the corresponding evaluation questions.
3. Check that answer claims are supported by the actual retrieved passage and valid page number.
4. Fail the test if the app invents a clause, guesses missing information, follows the prompt-injection text, or gives a definitive legal verdict.
5. Run a separate offline/network-isolation test after model and dependencies have been installed.

## Test documents are not model training data

For a RAG system, these PDFs are a local retrieval/evaluation corpus: the model retrieves relevant text at inference time. They do not update Gemma's weights. Fine-tuning is a different process requiring a carefully designed training dataset and training pipeline. PS2 requires meaningful local Gemma use, not fine-tuning.

## Privacy

The PDFs themselves are synthetic. Still, test your application's runtime privacy with network disabled or otherwise isolated, and inspect connection logs and temporary files as the PS2 guide requires. Do not use this generated pack alone as proof of privacy.
