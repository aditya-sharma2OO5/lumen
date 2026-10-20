# Security Policy

## Supported Versions

Currently, Lumen is in early development (Phase 1). Only the latest commit on the `main` branch is actively supported for security updates.

| Version | Supported          |
| ------- | ------------------ |
| v1.0.x  | ❌ (Not Released)    |
| main    | ✅                 |

## Reporting a Vulnerability

Because Lumen's architecture is designed to handle sensitive ambient sensor data (camera frame sampling, voice transcription, and personal spatial location memory), data privacy and system security are top priorities. 

If you discover a security vulnerability within Lumen—particularly anything related to AWS IAM privilege escalation, AgentCore prompt injection escaping guardrails, or unauthorized access to the Neptune/DynamoDB memory stores—please **do not report it by creating a public GitHub issue.**

Instead, please report the vulnerability directly to the repository owner via email. 

You should receive a response within 48 hours acknowledging receipt of the vulnerability. We will prioritize assessing and deploying a patch before public disclosure.