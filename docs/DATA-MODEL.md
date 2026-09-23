# Suggested production data model

users: id, email, name, role, status, created_at
products: id, type, game, title, description, price, seller_id, status
orders: id, user_id, total, status, payment_status, delivery_status, created_at
payment_submissions: id, order_id, method, utr, screenshot_object_key, amount, submitted_at, reviewed_at, reviewed_by, decision, rejection_reason
digital_inventory: id, product_id, secret_ciphertext, reserved_order_id, delivered_at
audit_log: id, actor_id, action, entity_type, entity_id, metadata_json, created_at
delivery_log: id, order_id, channel, recipient, sent_at, provider_message_id

Encrypt credentials at rest and enforce role-based authorization for admin payment review and delivery.