
---

# Threat Modeling: Voice Assistant Platform

## Context
Client: QuietCue (Voice assistant startup)  
Environment: AWS-based NLP backend, React frontend, mobile SDK

---

## Architecture Summary
[Frontend] → [API Gateway] → [Lambda NLP Engine] → [S3 Voice Archive]
                            ↘ [Logs → CloudWatch → Elasticsearch]

## Threat Table
| Threat Vector           | Likelihood | Impact | Mitigation                     |
| ----------------------- | ---------- | ------ | ------------------------------ |
| Voice replay attack     | High       | High   | Nonce token per request        |
| API key leakage         | Medium     | High   | IAM scoped tokens              |
| PII in NLP logs         | High       | Medium | Redact and encrypt logs        |
| SDK reverse engineering | Medium     | Medium | Obfuscation and token rotation |

Tip: Use tshark to simulate and test audio replay edge cases before production deployment.

## Security Recommendations
# Enable full log encryption at rest
aws logs associate-kms-key --log-group-name NLP-Logs --kms-key-id alias/quietcue-logkey

Add a SECURITY.md policy file to all client SDK repositories.
