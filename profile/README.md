<h1>Secure data exchange for a zero-trust world</h3>

<h4>
MnemoShare replaces static credentials and standing access with identity-bound,
ephemeral exchange — fully auditable, Kubernetes-native,
and designed for modern compliance.
</h4>

<p>
  <a href="https://mnemoshare.com">Website</a> &middot;
  <a href="https://mnemoshare.com/docs">Documentation</a> &middot;
  <a href="https://mnemoshare.com/pricing">Pricing</a> &middot;
  <a href="mailto:sales@mnemoshare.com">Contact Sales</a>
</p>

---

### Why MnemoShare?

Traditional managed file transfer tools rely on shared credentials, permanent access, and bolt-on security. MnemoShare is built differently — security is an **architectural property**, not a feature checkbox.

- **AES-256-GCM encryption** at rest, TLS 1.3 in transit
- **Hardware-backed identity** — YubiKey, Secure Enclave, TPM support
- **Ephemeral, identity-bound access** — no standing credentials
- **Approval workflows** with structured recipient verification
- **Real-time malware scanning** — ClamAV and YARA integration
- **PHI/PII detection** with automatic quarantine
- **Structured audit events** exportable to SIEM and WORM storage
- **SSO integration** — OIDC and SAML with Azure AD, Okta, Ping, and more
- **High-throughput parallel transfers** with zero memory overhead

### Built for Regulated Industries

MnemoShare is designed to meet and exceed the requirements of:

**HIPAA** &middot; **HITRUST** &middot; **SOC 2** &middot; **ISO 27001** &middot; **NIST**

Common use cases include PHI/PII transfers, vendor onboarding without permanent credentials, financial document exchange, insurance underwriting, tax and audit reporting, and legal discovery with chain of custody.

### Deploy Anywhere

MnemoShare is self-hosted and cloud-native. You retain full control over your data, logs, and encryption keys.

- **Orchestration**: Docker, Kubernetes, Helm
- **Storage**: AWS S3, Google Cloud Storage, MinIO, any S3-compatible backend
- **Database**: MongoDB 6.0+
- **Platforms**: Linux, macOS, Windows

### Open Source Tools

| Repository | Description |
|---|---|
| [`helm-charts`](https://github.com/MnemoShare/helm-charts) | Public Helm charts for deploying MnemoShare on Kubernetes |
| [`homebrew-tap`](https://github.com/MnemoShare/homebrew-tap) | Homebrew tap for installing the MnemoShare CLI on macOS/Linux |
| [`apt`](https://github.com/MnemoShare/apt) | APT repository for Debian/Ubuntu packages |
| [`releases`](https://github.com/MnemoShare/releases) | Cross-platform CLI binaries for manual download |
| [`mnemocli-releases`](https://github.com/MnemoShare/mnemocli-releases) | MnemoShare CLI releases for Chocolatey (Windows) |
| [`kind-cluster`](https://github.com/MnemoShare/kind-cluster) | Kind cluster setup for local Kubernetes development |
| [`mnemoshare-keycloak-mcp`](https://github.com/MnemoShare/mnemoshare-keycloak-mcp) | Keycloak MCP server — 134 admin tools for Model Context Protocol |

---

<p align="center">
  <a href="https://mnemoshare.com">mnemoshare.com</a> &middot;
  <a href="mailto:support@mnemoshare.com">support@mnemoshare.com</a>
</p>
