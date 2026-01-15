# API Requirements - [Project Name]

> **Purpose:** Document all API integrations needed for this project, ensuring consistent usage of centralized API providers.
>
> **Reference:** See `Claude.md` → "API Providers & Documentation" section for full provider documentation.

---

## API Summary

| API Provider | Use Case | Models/Endpoints | Status |
|--------------|----------|------------------|--------|
| OpenRouter | [Text/Chat/Code] | [Model name] | ⬜ Not started |
| Replicate | [Image/Audio/Video] | [Model name] | ⬜ Not started |

**Status Legend:**
- ⬜ Not started
- 🔄 In progress
- ✅ Implemented
- ❌ Blocked

---

## OpenRouter Integration

**Documentation:** https://openrouter.ai/docs

### Required for this project?
- [ ] Yes - Document details below
- [ ] No - Skip this section

### Use Cases

| Feature | Model | Purpose | Priority |
|---------|-------|---------|----------|
| [Feature name] | anthropic/claude-3.5-sonnet | [What it does] | High/Medium/Low |
| [Feature name] | [Model] | [Purpose] | |

### Models to Use

**Primary Model:**
- Model ID: `anthropic/claude-3.5-sonnet`
- Use for: [Primary use case]
- Fallback: `openai/gpt-4o`

**Secondary Model (if needed):**
- Model ID: `[model-id]`
- Use for: [Use case]
- Fallback: `[fallback-model]`

### Implementation Details

**Environment Variable:**
```bash
OPENROUTER_API_KEY=sk-or-...
```

**API Configuration:**
```javascript
const OPENROUTER_CONFIG = {
  baseUrl: 'https://openrouter.ai/api/v1',
  headers: {
    'Authorization': `Bearer ${process.env.OPENROUTER_API_KEY}`,
    'HTTP-Referer': '[Your site URL]',
    'X-Title': '[Project Name]'
  }
};
```

**Rate Limit Handling:**
- [ ] Implement exponential backoff
- [ ] Add request queuing if needed
- [ ] Log rate limit errors

### Sample Prompts

Document key prompts used in this project:

**Prompt 1: [Name]**
```
System: [System prompt]

User: [User prompt template]
```

**Prompt 2: [Name]**
```
System: [System prompt]

User: [User prompt template]
```

---

## Replicate Integration

**Documentation:** https://replicate.com/docs

### Required for this project?
- [ ] Yes - Document details below
- [ ] No - Skip this section

### Use Cases

| Feature | Model | Purpose | Priority |
|---------|-------|---------|----------|
| [Feature name] | [Model owner/name] | [What it does] | High/Medium/Low |
| [Feature name] | [Model] | [Purpose] | |

### Models to Use

**Image Generation:**
- Model: `black-forest-labs/flux-schnell` (fast) or `black-forest-labs/flux-dev` (quality)
- Version: `[version-hash]`
- Use for: [Use case]

**Image Editing (if needed):**
- Model: `[model-name]`
- Use for: [Use case]

**Audio (if needed):**
- Model: `openai/whisper` (transcription) or `[model]`
- Use for: [Use case]

**Video (if needed):**
- Model: `[model-name]`
- Use for: [Use case]

### Implementation Details

**Environment Variable:**
```bash
REPLICATE_API_TOKEN=r8_...
```

**API Configuration:**
```javascript
const REPLICATE_CONFIG = {
  baseUrl: 'https://api.replicate.com/v1',
  headers: {
    'Authorization': `Bearer ${process.env.REPLICATE_API_TOKEN}`,
    'Content-Type': 'application/json'
  }
};
```

**Webhook Setup (for production):**
```javascript
const prediction = {
  version: '[model-version]',
  input: { /* model inputs */ },
  webhook: 'https://[your-api]/webhooks/replicate',
  webhook_events_filter: ['completed', 'failed']
};
```

### Model Input Parameters

Document the input parameters for each model:

**Model: [Model Name]**
| Parameter | Type | Required | Default | Description |
|-----------|------|----------|---------|-------------|
| prompt | string | Yes | - | Text description |
| width | integer | No | 1024 | Image width |
| height | integer | No | 1024 | Image height |
| num_outputs | integer | No | 1 | Number of images |
| [param] | [type] | [req] | [default] | [description] |

---

## API Security Checklist

- [ ] API keys stored in environment variables (never in code)
- [ ] `.env` file added to `.gitignore`
- [ ] API keys not logged or exposed in error messages
- [ ] Rate limiting implemented on backend
- [ ] API calls made from backend only (not exposed to frontend)
- [ ] Webhook endpoints secured with signature verification

---

## Error Handling

### OpenRouter Errors

| Error Code | Cause | Resolution |
|------------|-------|------------|
| 401 | Invalid API key | Check OPENROUTER_API_KEY |
| 429 | Rate limit exceeded | Implement backoff/retry |
| 500 | Server error | Retry with exponential backoff |
| 503 | Model unavailable | Use fallback model |

### Replicate Errors

| Error Code | Cause | Resolution |
|------------|-------|------------|
| 401 | Invalid API token | Check REPLICATE_API_TOKEN |
| 404 | Model not found | Verify model name/version |
| 422 | Invalid input | Check input parameters |

---

## Cost Estimation

### OpenRouter

| Model | Cost per 1M tokens (input) | Cost per 1M tokens (output) | Est. Monthly Usage | Est. Cost |
|-------|---------------------------|-----------------------------|--------------------|-----------|
| claude-3.5-sonnet | $3.00 | $15.00 | [tokens] | $[cost] |
| [model] | | | | |

### Replicate

| Model | Cost per Run | Est. Runs/Month | Est. Cost |
|-------|-------------|-----------------|-----------|
| flux-schnell | ~$0.003 | [runs] | $[cost] |
| [model] | | | |

**Total Estimated Monthly Cost:** $[total]

---

## Implementation Progress

### Phase 1: Setup
- [ ] Environment variables configured
- [ ] API client/wrapper created
- [ ] Error handling implemented
- [ ] Logging added

### Phase 2: Core Features
- [ ] [Feature 1] - [Model/Endpoint]
- [ ] [Feature 2] - [Model/Endpoint]
- [ ] [Feature 3] - [Model/Endpoint]

### Phase 3: Production
- [ ] Webhooks configured (Replicate)
- [ ] Rate limiting implemented
- [ ] Cost monitoring set up
- [ ] Fallback models configured

---

## Testing

### Test Cases

| Test | API | Expected Result | Status |
|------|-----|-----------------|--------|
| Valid text generation | OpenRouter | Returns completion | ⬜ |
| Invalid API key | OpenRouter | 401 error handled | ⬜ |
| Rate limit handling | OpenRouter | Retries with backoff | ⬜ |
| Image generation | Replicate | Returns image URL | ⬜ |
| Webhook delivery | Replicate | Processes callback | ⬜ |

---

## Notes

[Any additional notes, considerations, or decisions about API usage]

---

*Last updated: [Date]*
