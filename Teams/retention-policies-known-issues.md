---
title: 有关 Microsoft 团队中的保留策略的已知的问题
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: 当前的 Microsoft 团队保留策略的已知问题的列表。
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2b6d71a1b2422dfadfbc7ae0fb87e607fd288152
ms.sourcegitcommit: 5e8d04bbc3eb1a57fed893e5ff929674b4297851
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "25004583"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>有关 Microsoft 团队中的保留策略的已知的问题

以下已知问题被的团队中的保留策略的跟踪，调查。

- 下选择工作组添加工作组通道消息位置行中，您可能会看到的 Office 365 组不还团队。 这将在将来解决。

- 下团队聊天位置行中选择用户，您可能会看到来宾和非邮箱用户。 保留策略不打算为来宾，设置，而且我们正在这些从列表中删除。

- Exchange 生命周期助理 (ELC)，每日，运行，但它具有 7 天的 SLA。 因此，很可能，如果您有删除早于 60 天的项目工作组保留策略，这些项目无法达 67 天保留。 这不是新情况-遵循 Exchange 模型。 当然，在大多数情况下，没有延迟。


| | | |
|---------|---------|---------|
|![决策点图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织需要哪些安全性和合规性功能？ 贵组织是否有所需的许可证来满足安全性和合规性业务需求？         |
|![后续步骤图标。](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |后续步骤         |文档所需的安全性和遵从性功能。         |
