---
title: Microsoft Teams 中保留策略的已知问题
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
description: Microsoft 团队保留策略的已知问题的当前列表。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38fd76bff3309655cb7d2fa1f0acf18559f15220
ms.sourcegitcommit: b92b673e718e34b6ebda6de57ad69eb6651faa98
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "34433364"
---
# <a name="known-issues-for-retention-policies-in-microsoft-teams"></a>Microsoft Teams 中保留策略的已知问题

以下是正在跟踪和调查的团队中的保留策略的已知问题。

- 在 "团队频道消息位置" 行中的 "选择团队" 下, 你可能会看到不是团队的 Office 365 组。 未来将对此进行寻址。

- 在 "在团队聊天位置中选择用户" 行中, 你可能会看到来宾和非邮箱用户。 保留策略不适于为来宾设置, 我们正在努力从列表中删除这些保留策略。

- Exchange 生命周期助理 (ELC) 每天运行, 但其 SLA 为7天。 因此, 如果你有一个团队保留策略来删除超过60天的项目, 这些项目最多可持续67天。 这不是一种新情况-它遵循 Exchange 模型。 当然, 在大多数情况下, 不会有延迟。


| | | |
|---------|---------|---------|
|![表示决策点的图标](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |决策点         |贵组织需要哪些安全性和合规性功能？ 贵组织是否有所需的许可证来满足安全性和合规性业务需求？         |
|![表示后续步骤的图标](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |后续步骤         |记录所需的安全和合规性功能。         |
