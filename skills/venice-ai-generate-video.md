---
name: venice-ai-generate-video
description: Quote, queue, poll and complete an asynchronous video generation job on the Venice.ai API.
api: Venice.ai API
operations: [quoteVideo, queueVideo, retrieveVideo, completeVideo]
generated: 2026-10-13
method: generated
source: openapi/venice-ai-openapi.yml
---
1. `quoteVideo` (POST /video/quote) to get the price before spending balance.
2. `queueVideo` (POST /video/queue) with the model and prompt; keep the returned queue id.
3. Poll `retrieveVideo` (POST /video/retrieve) until the media is returned. Back off on 429 (`RATE_LIMIT_EXCEEDED`, `MODEL_OVERLOADED`).
4. `completeVideo` (POST /video/complete) once downloaded; this deletes server-side media.
Auth: `Authorization: Bearer <VENICE_API_KEY>`. A 402 `INSUFFICIENT_BALANCE` means top up USD/DIEM.
