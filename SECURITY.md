# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability in rollout-bucket, please report it via [GitHub Security Advisories](https://github.com/vnykmshr/rollout-bucket/security/advisories/new).

**Please do not report security vulnerabilities through public GitHub issues.**

### What to Include

When reporting a vulnerability, please include:

- Description of the vulnerability
- Steps to reproduce the issue
- Potential impact
- Suggested fix (if any)

### Response Timeline

- **Initial Response**: Within 48 hours
- **Status Update**: Within 7 days
- **Fix Timeline**: Depends on severity
  - Critical: Within 7 days
  - High: Within 30 days
  - Medium/Low: Next release cycle

## Supported Versions

| Version | Supported          |
| ------- | ------------------ |
| 0.1.x   | :white_check_mark: |

## Security Considerations

### What rollout-bucket Does

rollout-bucket is a **deterministic bucketing library** for feature flags and A/B testing. It:

- Uses MurmurHash3 (non-cryptographic hash) for deterministic user assignment
- Has no network communication
- Stores no data or state
- Has no authentication or authorization

### What rollout-bucket Does NOT Do

- **Not cryptographically secure**: MurmurHash3 is designed for speed, not security
- **Not for security-sensitive operations**: Do not use for password hashing, token generation, or cryptographic purposes
- **Not for user authentication**: This is a bucketing library, not an auth system

### Safe Usage

✅ **Safe for:**
- Feature flag rollouts
- A/B test variant assignment
- Canary deployment bucketing
- Experimentation frameworks

❌ **Unsafe for:**
- Password hashing
- Cryptographic token generation
- Security-sensitive randomization
- Anything requiring unpredictability

## Dependencies

This package has minimal dependencies:

- **Production**: `murmur-hash` (hashing implementation)
- **Development**: Standard TypeScript/testing tools

We regularly update dependencies and monitor for security advisories via Dependabot.
