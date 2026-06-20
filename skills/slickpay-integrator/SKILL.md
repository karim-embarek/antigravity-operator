---
name: slickpay-integrator
description: An expert in integrating the Algerian SlickPay API (SATIM/EDAHABIA). Handles invoice creation, commission calculation, and webhooks securely.
---

# SlickPay API Integrator Workflow

## When to Use
Trigger this skill when the user asks to "integrate SlickPay", "add Algerian payments", or "setup SATIM/EDAHABIA".

## Prerequisites
- You must have the `SLICKPAY_KEY` environment variable configured.
- Determine if the user is in a Sandbox or Production environment.

## Integration Rules & Workflow

1. **Calculate Commission First (`POST /users/invoices/commission`)**:
   - Never guess the commission. The `fees` parameter (0-100) only determines *who* pays the commission, not the rate.
   - Always call the commission endpoint to get the final price before presenting it to the user.

2. **Create the Invoice (`POST /users/invoices`)**:
   - Ensure `amount` is > 100 DZD.
   - Include the `items` array (name, price, quantity).
   - If no default account is set, you must fetch the account UUID via `GET /users/accounts` and pass it.
   - Add `webhook_url` and `webhook_signature` for secure background processing.

3. **Redirect to SATIM**:
   - After creating the invoice, extract the `url` at the **root** of the response (NOT `invoice.url`). 
   - Redirect the user's browser to this URL.

4. **Verify Payment (Webhook or Polling)**:
   - Listen for the webhook or call `GET /users/invoices/{id}`.
   - A payment is successful ONLY if `completed === 1`.
   - If `completed === 0`, read the `rejection_reason` to inform the user.

## Verification
- Ensure the API keys are never hardcoded in the frontend.
- Generate a clear Markdown architecture showing how the webhook will be handled by the backend before writing the implementation code.
