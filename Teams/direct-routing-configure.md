---
title: 配置直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft Phone 系统直接路由以将本地电话基础结构连接到 Microsoft 团队。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12eb67fd63a3d1bbed3ddcd0c4fadce16529083
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904824"
---
# <a name="configure-direct-routing"></a>配置直接路由

Microsoft 手机系统直接路由使你能够将本地电话基础结构连接到 Microsoft 团队。 本文列出了将受支持的本地会话边界控制器（SBC）连接到直接路由以及如何将团队用户配置为使用直接路由连接到公共交换电话网络（PSTN）所需的高级别步骤。 本文将链接到相关文章以了解详细信息。  

有关直接路由选择是否适合你的组织的信息，请参阅[手机系统直接路由](direct-routing-landing-page.md)。 有关先决条件和规划部署的信息，请参阅[规划直接路由](direct-routing-plan.md)。

> [!Tip]
> 你还可以观看以下会话，了解直接路由的好处、如何为其规划以及如何部署它：[在 Microsoft 团队中直接路由](https://aka.ms/teams-direct-routing)。

为了完成本文中介绍的步骤，管理员需要熟悉 PowerShell cmdlet。 有关使用 PowerShell 的详细信息，请参阅[设置适用于 Windows powershell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

在执行这些文章中的步骤之前，Microsoft 建议你确认你的 SBC 已按照 SBC 供应商的建议进行配置： 

- [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-系统（anynode）部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 部署文档](https://www.metaswitch.com/products/core-network/perimeta-sbc)

有关支持的 SBCs 的完整列表，请参阅为[直接路由认证的会话边框控制器列表](direct-routing-border-controllers.md)。

若要配置 Microsoft Phone 系统并使用户能够使用直接路由，请按照下列步骤操作： 

- **第 1 步** [将 SBC 连接到 Microsoft Phone 系统并验证连接](direct-routing-connect-the-sbc.md)
- **第 2 步** [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)
- **第 3 步** [配置语音路由](direct-routing-voice-routing.md)
- **第 4 步** [将数字转换为备用格式](direct-routing-translate-numbers.md) 

如果你要为多个租户配置 SBC，你还需要阅读[为多个租户配置 sbc](direct-routing-sbc-multiple-tenants.md)。


## <a name="related-topics"></a>相关主题

[电话系统直接路由](direct-routing-landing-page.md)

[规划直接路由](direct-routing-plan.md)

