---
name: venice-ai-chat-completion
description: Pick a text model from the live catalog and run an OpenAI-compatible chat completion on Venice.ai.
api: Venice.ai API
operations: [listModels, createChatCompletion]
generated: 2026-10-13
method: generated
source: openapi/venice-ai-openapi.yml
---
1. `listModels` (GET /models) to choose a model id and read its pricing and capabilities.
2. `createChatCompletion` (POST /chat/completions) with `model` and `messages`; stream when needed.
3. On 400 `TOO_MANY_TOKENS` shorten the prompt; on 429 honour `x-ratelimit-reset-requests`.
Base URL: https://api.venice.ai/api/v1. Auth: Bearer API key.
