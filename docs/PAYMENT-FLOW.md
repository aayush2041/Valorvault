# ValorVault payment flow

1. Customer creates an order.
2. Backend locks/reserves inventory.
3. Checkout displays configured UPI, QR or bank-transfer instructions.
4. Customer transfers the exact amount.
5. Customer submits UTR and screenshot.
6. Backend stores the proof in private storage and sets payment status to PENDING_VERIFICATION.
7. Admin independently checks the payment against the merchant bank/UPI record.
8. Admin approves or rejects.
9. Approval changes the order to PAID / DELIVERY_PENDING.
10. Server-side delivery retrieves the purchased digital item and records an audit event.
11. Transactional email confirms fulfillment.

Never treat a screenshot or UTR submitted by the customer as proof of settlement by itself. Keep merchant credentials, uploaded proofs and digital inventory out of public frontend assets.