# InfraWeave Platform

> _Seamless, serverless infrastructure-as-code for modern platform teams_

<div style="display: flex; align-items: center; justify-content: center; gap: 10px;" align="center">
    <a href="https://preview.infraweave.io" target="_blank">
        <img width="20%" src="https://preview.infraweave.io/img/infrabridge-logo.png" alt="InfraWeave">
    </a>
</div>

<p align="center">
  <a href="https://preview.infraweave.io/core-concepts/overview/"><img alt="Docs" src="https://img.shields.io/badge/docs-online-blue"></a>
  <a href="https://discord.gg/NWNE8ZXaRq"><img src="https://img.shields.io/discord/1332995139567878246?label=discord&style=flat-square&color=5a66f6" alt="Discord"></a>
  <a href="LICENSE"><img alt="License" src="https://img.shields.io/badge/license-Apache%202.0-blue"></a>
</p>

---

InfraWeave combines the power of **Terraform**/**OpenTofu** with a **Kubernetes‑inspired developer experience**—that runs completely in your own cloud. It is completely **serverless & cost‑free when idle**, meaning you can have it available in every account and region, ready to spin up infrastructure within seconds.

## ✨ Why InfraWeave?

| Pain                                                        | InfraWeave solution                                                                                       |
| ----------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Platform team overloaded** fielding one‑off infra tickets | Self‑service **Modules** and **Stacks** available for any app team to deploy via pull requests.           |
| **Complex Terraform codebases** hard to onboard new devs    | **Straight-forward Manifests** `kind: S3Bucket`‑style claims hide Terraform internals.                    |
| **Costly control planes**                                   | 100 % **serverless** tailored to each Cloud Service Provider (CSP). Pay \$0 when idle.                    |
| **Resources drift silently**                                | Built‑in **drift detection** + webhook alerts                                                             |
| **No single pane of glass for infra**                       | Visualize all Deployments and Modules in a unified interface                                              |
| **Fragmented tooling**                                      | One platform, multiple ways to use **CLI**, **Python SDK**, GitHub‑native workflows, or a K8s controller. |

## 👤 Who is InfraWeave for?

- **Internal platform teams** offering golden-path infrastructure modules to application teams without exposing terraform code
- Cloud-native teams that want git-driven, low-cost, serverless Terraform without leaving your own cloud.

```mermaid
---
config:
  layout: dagre
---
flowchart LR
    Dev["Developer"] -- Develop --> PR["GitHub Commit"]
 subgraph CSP["Cloud Service Provider"]
        PlatformState["Platform state, modules, etc"]
        API["InfraWeave API"]
        TF["Terraform Engine"]
        Infrastructure["Infrastructure"]
  end
    PR -- Webhook --> API
    Dev -- Browse --> Backstage["Backstage"]
    Backstage --> API
    Dev -- Interact using cli --> API
    API -- Read/write --> PlatformState
    PlatformState@{ shape: cyl}
    API <--> TF
    TF -- Manages --> Infrastructure
    API -- Status --> PR
    style CSP fill:#f0faff,stroke:#0284c7,stroke-width:2px
```

## 🌍 Supported Providers

| Provider          | Status                     |
| ----------------- | -------------------------- |
| **AWS**           | 🧪 Beta                    |
| **Azure**         | 🚧 Preview                 |
| **GCP**           | 🗺️ Planned in future       |
| **OCI**           | Not planned in near future |
| **Alibaba Cloud** | Not planned in near future |

## 🤝 Contributing

We want contributors! Check out [CONTRIBUTING.md](https://github.com/infraweave-io/infraweave/blob/main/CONTRIBUTING.md) to learn how to add value!

All contributors must follow our [Code of Conduct](https://github.com/infraweave-io/infraweave/blob/main/CODE_OF_CONDUCT).

## 📚 Learning & Community

- **Docs** – [https://preview.infraweave.io/core-concepts/overview/](https://preview.infraweave.io/core-concepts/overview/)
- **Discussions** – [https://github.com/orgs/infraweave-io/discussions](https://github.com/orgs/infraweave-io/discussions)

## 🪪 License

InfraWeave is licensed under the **Apache 2.0** license. See [LICENSE](LICENSE) for details.

---

<sub><sup>InfraWeave is not affiliated with HashiCorp, Terraform, the CNCF, or Kubernetes. All trademarks belong to their respective owners.</sup></sub>
