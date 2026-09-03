---
name: bitculator-alarm-webhooks
description: Set a target price alarm and receive its trigger as a signed webhook, verified end-to-end.
api: Bitculator Data API
operations: [createAWebhookEndpoint, sendATestEvent, createAnAlarm, listAlarms, deleteAnAlarm, webhookDeliveryLog, deleteAWebhookEndpoint]
generated: '2026-09-03'
method: generated
source: https://bitculator.com/en/documentation/api/v1 (Alarms + Webhooks groups)
---

# Alarms with signed webhook delivery

1. **Register the endpoint first.** `POST /api/v1/webhooks` (`createAWebhookEndpoint`) with
   `{"url": "https://...", "events": ["alarm.triggered"]}`. Public HTTPS hosts only (internal
   addresses rejected), max 5 endpoints per account. **Store the signing secret from the
   response immediately — it is shown only this once.**
2. **Verify your handler.** `POST /api/v1/webhooks/{id}/test` (`sendATestEvent`) sends a test
   delivery. Verify the `X-Bitculator-Signature: t=<ts>,v1=<hmac>` header: recompute
   HMAC-SHA256 over `"<ts>.<raw-body>"` with the secret, compare in constant time, and reject
   if `t` is older than ~300s. The event type rides in `X-Bitculator-Event`.
3. **Create the alarm.** `POST /api/v1/alarms` (`createAnAlarm`) with
   `{"name", "coin": "<slug>", "metric": "rate"|"volume"|"marketcap", "direction":
   "above"|"below", "target", "notification": "webhook"}`. The target must sit on the direction
   side of the current value (an alarm cannot self-trigger instantly); each alarm spends one
   alarm slot from the account's balance.
4. **Monitor.** `GET /api/v1/alarms` (`listAlarms`) for state;
   `GET /api/v1/webhooks/{id}/deliveries` (`webhookDeliveryLog`) when a delivery seems missing —
   deliveries retry 3x with backoff.
5. **Clean up (this write is reversible).** `DELETE /api/v1/alarms/{id}` (`deleteAnAlarm`) frees
   the alarm slot; `DELETE /api/v1/webhooks/{id}` (`deleteAWebhookEndpoint`) removes the
   endpoint. No idempotency keys exist — do not blind-retry creates; re-list and reconcile
   instead.
