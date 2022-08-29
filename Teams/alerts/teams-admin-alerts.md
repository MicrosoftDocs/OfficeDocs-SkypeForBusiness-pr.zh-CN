---
title: Microsoft Teams 监视和警报
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: vapati
f1.keywords: ''
ms.localizationpriority: medium
search.appverid: ''
ms.collection:
- M365-collaboration
description: 了解 Microsoft Teams 管理中心提供的 Teams 警报和通知功能。
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 452bcbebeffa3936b9d05270626e11923caf5cda
ms.sourcegitcommit: 72b6f7ab2a44dec395622bfe64119a48094960bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2022
ms.locfileid: "67283083"
---
# <a name="microsoft-teams-monitoring-and-alerting"></a>Microsoft Teams 监视和警报

Teams 管理中心提供了 Microsoft Teams 的新监视和警报功能。 使用 Teams 管理中心“ **通知&警报** ”部分下提供的不同规则集来监视 Teams 功能并接收警报。 例如，如果 Teams 设备（例如 IP Phone、协作栏等）意外脱机，则可以主动监视它们的运行状况。  

组织可以使用 Teams 监视和警报执行以下项：

- 自动管理 Teams 功能
- 如果显示意外内容，则会发出警报。
- 采取纠正措施，使事情回到正轨。

> [!NOTE]
> Teams 管理中心内的警报功能在 GCC/GCC-High 环境中不可用。

## <a name="how-to-manage-monitoring-and-alerting"></a>如何管理监视和警报

 你必须是 Microsoft 365 中的全局管理员或 Teams 服务管理员才能配置警报规则。 请参阅 [使用 Teams 管理员角色来管理 Teams](../using-admin-roles.md) ，详细了解 Teams 管理员角色以及每个管理员角色可以访问的报表。

1. 登录到 Teams 管理中心。
2. 在左侧导航栏中，选择 **通知&警报**。
3. 从 **“规则**”中选择要配置的规则。

## <a name="teams-monitoring-rules-reference"></a>Teams 监视规则参考

我们继续通过添加各种监视功能和配置功能来添加和改进 Teams 监视体验。 下面是 Teams 管理中心当前可用的 Teams 监视规则的列表。


|规则  |监视功能|监视的内容是什么？ |
|---------|---------|---------|
|应用提交  |Teams 应用 | 支持主动监视 Teams 应用（如果已提交审批）。|
|[设备状态规则](device-health-status.md)  |Teams 设备 | 支持主动监视 Teams 设备（如果设备脱机）。|
