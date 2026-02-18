# MnemoShare

> Secure, Zero Trust MFT with Hardware Security Keys, SIEM/WORM, Compliance Dashboard Faster and more secure than SFTP

MnemoShare is a comprehensive file-sharing platform designed for secure, auditable file transfers with dynamic sender and recipient validation through customizable questionnaires. Built with regulated industries in mind, it provides enterprise-grade security with encryption at rest, comprehensive audit logging, and fine-grained role-based access control.

[![Go Version](https://img.shields.io/badge/Go-1.25+-00ADD8?logo=go)](https://golang.org/)
[![React Version](https://img.shields.io/badge/React-19-61DAFB?logo=react)](https://react.dev/)

---

## Features

### Core Functionality
- **Secure File Transfer**: Upload and share files with end-to-end encryption (AES-256-GCM)
- **Chunked Uploads**: 20MB chunks with concurrent upload support (works with any file size)
- **Dynamic Questionnaires**: Customizable sender and recipient questions with immutable audit snapshots
- **Hierarchical Question Scopes**: Questions can be shared_files, organization, or folder-scoped
- **Multi-Organization Storage**: Isolated S3 backends and encryption keys per organization
- **Download Links**: Secure, expiring download links with revocation and password protection
- **Shared Folders**: Persistent folders for recurring file transfers with sender/recipient questions
- **Audit Logging**: Immutable audit trails with complete Q&A snapshots (HIPAA-compliant)
- **Archive Management**: Query and retrieve archived files with full audit history

### User Management
- **Three-Tier Role System**: Admin, User, and Guest roles with distinct permissions
- **Invitation System**: Invite-only registration with email invitations
- **Access Request System**: Public form for requesting access with admin approval workflow
- **User Activity Tracking**: Detailed activity logs per user
- **User Deletion**: Cascade deletion with granular options (files, folders, audit logs)
- **Password Management**: Self-service password reset and admin password reset
- **Token Revocation**: Ability to revoke all user tokens for security
- **Guest Domain Restrictions**: Configurable whitelist for guest-to-guest file visibility

### Security
- **Encryption at Rest**: Files encrypted with AES-256-GCM before storage
- **Multi-Factor Authentication**: TOTP-based MFA with QR codes and backup codes
- **SSO/OAuth2 Integration**: Keycloak integration with PKCE flow and JIT provisioning
- **JWT Authentication**: Secure token-based authentication with HS256
- **Password Hashing**: Bcrypt with cost factor 12
- **Role-Based Access Control**: Fine-grained permissions for admin, user, and guest
- **Virus Scanning**: ICAP protocol for AV and DLP scanning (per-chunk + final scan)
- **Checksum Verification**: SHA256 checksums for file integrity
- **Password Protected Links**: Optional password protection for download links
- **License Validation**: Deployment tracking and license enforcement

### User Experience
- **Dark Mode**: Full dark mode support with localStorage persistence
- **Responsive Design**: Mobile-friendly interface with Tailwind CSS
- **Progress Tracking**: Real-time upload/download progress with speed indicators
- **Concurrent Transfers**: Parallel file uploads/downloads for improved performance
- **Quiet Mode**: CLI flag for automation and scripting

### Deployment
- **Docker Support**: Full Docker Compose stack for development and production
- **Docker Images**: All-in-one, CLI-only, ClamAV ICAP, Inbound Gateway, and Postfix Inbound images on Docker Hub
- **Kubernetes Native**: Helm charts, Kubernetes operator, and deployment manifests for production clusters
- **Package Managers**: Homebrew (macOS/Linux), APT (Debian/Ubuntu), Chocolatey (Windows)
- **S3-Compatible Storage**: Works with MinIO, AWS S3, Google Cloud Storage
- **Email Integration**: SendGrid support for invitations and password reset
- **CI/CD Pipeline**: Automated release and distribution with GitHub Actions
- **Multi-Platform CLI**: Cross-platform binaries for Windows, macOS (Intel/ARM), Linux (amd64/arm64)

---

## What's New (Latest Release)

### Security & Authentication
- 🔐 **Multi-Factor Authentication (v0.3.0+)** - TOTP with QR codes, backup codes, long-lived tokens for CLI
- 🔐 **SSO/OAuth2 Integration (v0.5.0+)** - Keycloak with PKCE flow, JIT user provisioning
- 🔐 **License System** - Deployment tracking, tier-based limits, certificate pinning validation
- 🦠 **Virus Scanning** - ICAP protocol for AV and DLP scanning (per-chunk + optional final scan)

### Multi-Organization (v0.4.0+)
- 🏢 **Isolated Storage** - Separate S3 backends per organization
- 🔑 **Per-Org Encryption** - Independent AES-256-GCM keys per organization
- 🔐 **Per-Org SSO/OIDC/SAML** - Support for multiple IdP solutions
- 🎯 **Dynamic Routing** - Automatic storage client selection based on organization
- 🖥️ **Web UI Support** - Organization selector in header, upload targeting, file filtering

### Q&A System (v0.6.0+)
- 📋 **Hierarchical Question Scopes** - shared_files (one-time transfers), organization (all folders), folder (specific folder)
- 📸 **Complete Answer Snapshots** - Immutable question copies in audit trail (HIPAA compliance)
- 🎯 **Source Tracking** - Every answer tagged with origin (shared_files/organization/folder)
- 📁 **Shared Folders Integration** - Sender and recipient questions for recurring file transfers
- 🔍 **File Detail View** - Upload and download Q&As with complete audit trail

### CLI Distribution & Performance
- 📦 **Package Managers** - Homebrew, APT repository, and Chocolatey
- 🐳 **Docker Images** - All-in-one, CLI-only, ClamAV ICAP, Inbound Gateway, and Postfix Inbound on Docker Hub
- ☸️ **Kubernetes Native** - Helm charts, operator, and deployment manifests
- 🚀 **Streaming uploads** - Zero memory buffering (handles multi-GB files)
- 🚀 **Concurrent transfers** - 3x faster with parallel uploads/downloads
- 🚀 **Chunked uploads** - 20MB chunks with concurrent upload streams, works with any file size

### User Management & Authentication (v0.7.0+)
- ✨ **Three-tier role system** (admin, user, guest) with permission controls
- ✨ **Invitation system** with email notifications and invite resend
- ✨ **Password reset flow** (forgot password + email token validation)
- ✨ **User activity tracking** with detailed audit logs
- ✨ **Token revocation** for security management
- 🚪 **Access Request System** - Public form for users to request access, admin approval workflow
- 🗑️ **User Deletion** - Cascade deletion with options for files, folders, and audit logs
- 🔐 **Guest Domain Restrictions** - Configurable domain whitelist for guest user file sharing
- 👥 **Guest User Invitations** - Guests can invite other guests from their domain (if enabled)

### UI/UX Improvements
- 🎨 **Dark mode** with localStorage persistence
- 🎨 **Organization selector** in navigation (multi-org support)
- 🎨 **MFA setup interface** with QR code display
- 🎨 **SSO login flow** with Keycloak integration
- 🎨 **Settings page** with MFA management

---

## Architecture

### Technology Stack

**Backend**
- Go 1.25+ with Chi router
- MongoDB, PostgreSQL, and SQLite options for data persistence
- MinIO/S3 for object storage (multi-org isolation support)
- OAuth2/OIDC for SSO (Keycloak integration)
- TOTP for multi-factor authentication
- ICAP protocol for AV and DLP scanning
- SMTP/SendGrid/Amazon SES for email notifications
- Zerolog for structured logging

**Frontend**
- React 19 with TypeScript
- Vite 6 for build tooling
- TailwindCSS 3.3.0 for styling
- React Router DOM 7 for navigation
- Dark mode with CSS custom properties

**CLI**
- Cobra framework for commands
- Viper for configuration management
- Streaming I/O with io.Pipe
- Concurrent transfers with goroutines
- Cross-platform compilation (CGO disabled)

**Infrastructure**
- Kubernetes Native
- Docker containerization
- Docker Compose for orchestration

---

### System Components

```
┌──────────────────────────────────────────────────────────┐
│  Web UI + API Server (Single Go Process)                 │
│  Port: 8080                                              │
│  - Serves React SPA (static files)                       │
│  - REST API endpoints                                    │
│  - JWT + SSO Auth, MFA, RBAC                             │
└─────────┬────────────────────────────────────────────────┘
          │
          ├──────────────────┬──────────────────┬───────────────────┐
          ▼                  ▼                  ▼                   ▼
    ┌───────────┐      ┌───────────┐     ┌──────────┐      ┌──────────────┐
    │ MongoDB   │      │ Keycloak  │     │ ClamAV   │      │ MinIO/S3     │
    │ :27017    │      │ :8081     │     │ ICAP     │      │ :9000        │
    │ - Users   │      │ (Optional)│     │ :1344    │      │ - Multi-org  │
    │ - Sessions│      │ - SSO/    │     │ - Virus  │      │ - Encrypted  │
    │ - Audits  │      │   OAuth2  │     │   Scan   │      │ - Per-org    │
    │ - Orgs    │      └───────────┘     └──────────┘      │   buckets    │
    └───────────┘                                          └──────────────┘
          ▲
          │
          │
┌─────────┴────────┐
│  CLI (mnemocli)  │
│  - MFA support   │
│  - Org selection │
│  - Streaming I/O │
│  - Concurrent    │
└──────────────────┘
```

---

## Usage

### Web UI

1. **Login**
   - Login with credentials (no public registration)
   - Invitation-only system for new users

2. **Upload Files**
   - Click "Upload Files"
   - Answer sender questions (if configured)
   - Select files to upload
   - Configure recipient questions
   - Set expiration and optional password
   - Generate download link

3. **Manage Users** (Admin only)
   - View all users with roles
   - Create and invite new users
   - Edit user details and roles
   - Reset user passwords
   - Revoke user tokens
   - View user activity

4. **Settings**
   - Toggle dark/light mode
   - View account information
   - Change password

---

## License

This software is proprietary. See [mnemoshare.com](https://mnemoshare.com) for licensing information.


## Support

### Getting Help
- **Documentation**: Check [docs/](docs/) directory
- **Issues**: [GitHub Issues](https://github.com/dwoolworth/mnemoshare/issues)
- **Discussions**: [GitHub Discussions](https://github.com/dwoolworth/mnemoshare/discussions)

### Reporting Security Issues
Report security vulnerabilities privately to the maintainers. Do not open public issues for security concerns.

---

**MnemoShare** - Secure file sharing with confidence

*Last updated: November 20, 2025*
