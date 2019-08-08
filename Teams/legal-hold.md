---
title: 将 Microsoft Teams 用户或团队置于法定保留状态
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anach
search.appverid: MET150
description: 了解如何使用安全性和合规性中心将 Microsoft Teams 用户或团队置于法定保留状态，以及了解根据数据要求哪些内容需要法定保留。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 097161fee62e4d0c0339cc5b6bbc2399e86ac959
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244867"
---
<a name="place-a-microsoft-teams-user-or-team-on-legal-hold"></a>将 Microsoft Teams 用户或团队置于法定保留状态
==================================================

要将用户或团队置于法定保留状态，请导航到[安全性和合规性中心](https://go.microsoft.com/fwlink/?linkid=854628)。 在你创建新案例时，系统会为你提供用于将邮箱或网站置于保留状态的选项。

> [!NOTE]
> 将用户置于保留状态并不会自动将组置于保留状态，反之亦然。

> [!IMPORTANT]
> 当用户或组处于保留状态时, 将保留所有邮件副本。 示例：Clay 在某个频道中发布了一条消息，之后修改了该消息。 在保留应用场景中，会保留该消息的两个副本。 如果未处于法定保留状态，则只保留最新消息。



在下图中，有一个涉及 Clay 的调查。 Clay 是 Brokers-Dealers 团队的成员。

如果我们需要将 Clay 可能讨论了 Brokering 计划的所有地方置于法定保留状态，请确保将该团队的 SharePoint 网站以及 Clay 的 OneDrive for Business 网站添加到法定保留网站列表。

![“创建新保留”对话框屏幕截图。](media/Place_a_Microsoft_Teams_user_or_team_on_legal_hold_image3.png)

概括起来，使用下表了解根据数据要求需要将哪些内容置于法定保留状态：

|应用场景  |置于保留状态的内容  |
|---------|---------|
|**Microsoft Teams 私人聊天**     |用户邮箱         |
|**Microsoft Teams 频道聊天**    |用于团队的组邮箱         |
|**Microsoft Teams 内容（例如 Wiki、文件）**     |团队使用的 SharePoint 网站         |
|**私密内容**     |用户的 OneDrive for Business 网站         |
