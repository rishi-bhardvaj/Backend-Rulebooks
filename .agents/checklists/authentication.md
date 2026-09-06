# Authentication Checklist

- [ ] Server-side credential verification
- [ ] Passwords securely hashed and verified
- [ ] Token/session signature validation
- [ ] Algorithm allowlist
- [ ] Expiry validation
- [ ] Required claims validated
- [ ] Issuer/audience validated when configured
- [ ] Secure key/secret management and rotation plan
- [ ] Refresh-token/session rotation and revocation policy
- [ ] Brute-force/rate-limit controls
- [ ] Wrong password rejected
- [ ] Unknown user rejected
- [ ] No token rejected
- [ ] Invalid token rejected
- [ ] Expired token rejected
- [ ] Valid authorized token accepted
- [ ] Logout/revocation behavior verified
- [ ] No development auth bypass