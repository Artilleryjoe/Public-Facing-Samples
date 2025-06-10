
---

### `scenario-02-threat-model-voice-assistant.md`

```markdown
# Threat Modeling: Voice Assistant Platform

## Context
Client: QuietCue (Voice assistant startup)  
Environment: AWS-based NLP backend, React frontend, mobile SDK

---

## Architecture Summary
[Frontend] → [API Gateway] → [Lambda NLP Engine] → [S3 Voice Archive]
                            ↘ [Logs → CloudWatch → Elasticsearch]
