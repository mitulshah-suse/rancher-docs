---
title: 功能开关
---

为了让你试用默认关闭的实验功能，我们引入了功能开关（feature flag）。

如需了解功能的值以及如何启用功能，请参阅[此处](../../pages-for-subheaders/enable-experimental-features.md)。

:::note

某些功能需要重启 Rancher Server 容器才能生效。我们在文档的表格和 UI 中对这些功能进行了标记。

:::

以下是 Rancher 中可用的功能开关列表：

- `harvester`：从 2.6.1 开始可用。Harvester 用于管理 Virtualization Management 页面的访问。用户可以在该页面直接导航到 Harvester 集群并访问 Harvester UI。详情请参见[本页](../../explanations/integrations-in-rancher/harvester.md#功能开关)。
- `rke2`：用于启用配置 RKE2 集群的功能。这个功能开关默认开启，即允许用户尝试配置此类集群。
- `fleet`：由于 Fleet 功能已应用到新的配置框架中，因此我们需要启用先前的 `fleet` 功能开关。如果你在早期版本中禁用了此功能开关，升级到 Rancher 2.6 后，该功能开关会自动启用。详情请参见[此页](../../how-to-guides/new-user-guides/deploy-apps-across-clusters/fleet.md)。
- `continuous-delivery`：在 Rancher v2.5.x 中，Fleet 带有 GitOps 功能，该功能不能与 Fleet 分开禁用。在 Rancher 2.6 中，我们引入了 `continuous-delivery` 功能开关，让你可以单独禁用 Fleet 的 GitOps 功能。详情请参见[本页](../../getting-started/installation-and-upgrade/advanced-options/enable-experimental-features/continuous-delivery.md)。
- `legacy`：Rancher 会逐渐淘汰之前版本中的某些功能，以实现功能迭代。此处包括已弃用，以及之后会转移到其他地方的功能。默认情况下，新安装会禁用此功能开关。如果你从先前的版本升级，此功能开关会启用。
- `token-hashing`：用于启动新的 token-hashing 功能。启用后，会使用 SHA256 算法对现有 Token 和所有新 Token 进行哈希处理。一旦对 Token 进行哈希处理，就无法撤消操作。该功能开关启用后无法被禁用。详情请参见[哈西处理 Token](../../reference-guides/about-the-api/api-tokens.md)。
- `unsupported-storage-drivers`：该功能[允许使用不支持的存储驱动](../../getting-started/installation-and-upgrade/advanced-options/enable-experimental-features/unsupported-storage-drivers.md)。换言之，此功能允许你使用默认情况下未启用的存储提供商和卷插件。
- `istio-virtual-service-ui`：此功能让你[启动用于管理 Istio 流量的 UI，其中包括创建、读取、更新和删除 Istio 虚拟服务（Virtual Service）和目标规则（Destination Rule）](../../getting-started/installation-and-upgrade/advanced-options/enable-experimental-features/istio-traffic-management-features.md)。
- `multi-cluster-management`：用于配置和管理多个 Kubernetes 集群。此功能开关只能在安装时设置，之后不能更改。

下表介绍了 Rancher 中功能开关的可用版本和默认值：

| 功能开关名称 | 默认值 | 状态 | 可用于 | 是否需要重启 Rancher |
| ----------------------------- | ------------- | ------------ | --------------- |---|
| `istio-virtual-service-ui` | `false` | 实验功能 | v2.3.0 | |
| `istio-virtual-service-ui` | `true` | GA* | v2.3.2 | |
| `unsupported-storage-drivers` | `false` | 实验功能 | v2.3.0 | |
| `fleet` | `true` | GA* | v2.5.0 |   |
| `fleet` | `true` | 不能禁用 | v2.6.0 | N/A |
| `continuous-delivery` | `true` | GA* | v2.6.0 | |
| `token-hashing` | 新安装：`false`；升级：`true` | GA* | v2.6.0 | |
| `legacy` | 新安装：`false`；升级：`true` | GA* | v2.6.0 | |
| `multi-cluster-management` | `false` | GA* | v2.5.0 | |
| `harvester` | `true` | 实验功能 | v2.6.1 | |
| `rke2` | `true` | 实验功能 | v2.6.0 | |

\* 一般情况下可用。此功能包含在 Rancher 中，不是实验功能的。