# AMH Link Studio 🌐

> Privacy-First Software. Cryptographic Sovereignty. Local-First Architecture.

Welcome to **AMH Link Studio** ([amhlink.com](https://amhlink.com)). We engineer zero-knowledge, local-first applications designed for families, crews, and teams who refuse to trade privacy for convenience.

---

## 🏛️ Ecosystem & Repository Map

| Repository | Scope | Description |
| :--- | :--- | :--- |
| [**amhlink/amhlink**](https://github.com/amhlink/amhlink) | **Flagship Gateway & Hub** | The public company site (`amhlink.com`), Cloudflare Pages edge gateway, universal deep-link join routing, and cross-app issue intake hub. |
| [**amhlink/Flock**](https://github.com/amhlink/Flock) | **Flock Radar Client** | Privacy-first circle radar and trip coordination mobile application for iOS and Android. Zero third-party tracking, end-to-end encrypted relay sync. |
| [**amhlink/.github**](https://github.com/amhlink/.github) | **Organization Hub** | Studio governance, organization profile, and global contributor standards. |

---

## ⚡ Edge & Relay Architecture

All AMH Link products share a unified edge routing layer hosted on Cloudflare Pages and low-latency Railway relay backends:

```
                      ┌──────────────────────────────────────────────┐
                      │              Cloudflare Edge                 │
                      │               amhlink.com                    │
                      └───────┬──────────────────────────────┬───────┘
                              │                              │
             ┌────────────────▼───────────────┐     ┌────────▼────────────────────┐
             │       Public Static Site       │     │       Edge Functions        │
             │   public/                      │     │   functions/                │
             │   ├── amhlink.com (Studio)     │     │   ├── [app]/join/[[code]]   │
             │   └── amhlink.com/flock        │     │   ├── [app]/relay/[[path]]  │
             │                                │     │   └── .well-known/          │
             └────────────────────────────────┘     └────────┬────────────────────┘
                                                             │
                                                  ┌──────────▼──────────┐
                                                  │   Railway Relays    │
                                                  │   (flock-relay,     │
                                                  │    telemetry-hub)   │
                                                  └─────────────────────┘
```

- **Universal App Links (`/.well-known/`)**: Dynamic iOS Universal Links (`apple-app-site-association`) and Android Digital Asset Links (`assetlinks.json`) configured centrally across apps.
- **Relay Proxy (`/<app>/relay/*`)**: Secure websocket and API proxy shielding origin IPs and minimizing egress latency.
- **Universal Join Previews (`/<app>/join/<code>`)**: Edge-rendered OpenGraph previews with instant app deep-links.

---

## 🔐 Security & Responsible Disclosure

We prioritize privacy and cryptographic integrity above all else:

- **Security Advisories**: Report vulnerabilities privately via [GitHub Security Advisories](https://github.com/amhlink/amhlink/security/advisories/new).
- **Security Contact**: Email [`triton@amhlink.com`](mailto:triton@amhlink.com) for direct security disclosures.
- **Zero-Knowledge Invariant**: Zero tracking SDKs, zero third-party analytics, and client-side encryption across all client communications.

---

© 2026 AMH Link Studio · AMHLink Contributors. All rights reserved.
