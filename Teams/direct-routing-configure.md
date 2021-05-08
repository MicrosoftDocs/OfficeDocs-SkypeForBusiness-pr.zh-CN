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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置Microsoft 电话直接路由，将本地电话基础结构连接到 Microsoft Teams。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122236"
---
# <a name="configure-direct-routing"></a>配置直接路由

Microsoft 电话使用系统直接路由可将本地电话基础结构连接到 Microsoft Teams。 本文列出了将受支持的本地会话边界控制器 (SBC) 连接到直接路由所需的高级步骤，以及如何将 Teams 用户配置为使用直接路由连接到公共电话交换网 (PSTN) 。 本文链接到相关文章，了解详细信息。  

有关直接路由是否是适用于组织的解决方案的信息，请参阅直接电话系统[路由](direct-routing-landing-page.md)。 有关先决条件和规划部署的信息，请参阅 [规划直接路由](direct-routing-plan.md)。

> [!Tip]
> 还可以观看以下会话，了解直接路由的好处、如何规划它以及如何部署[它：直接](https://aka.ms/teams-direct-routing)路由在 Microsoft Teams。

若要完成本文中介绍的步骤，管理员需要熟悉 PowerShell cmdlet。 有关使用 PowerShell 的信息，请参阅为计算机设置[Windows PowerShell。](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) 

在执行这些文章中的步骤之前，Microsoft 建议确认 SBC 已根据 SBC 供应商的建议进行配置： 

- [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (anynode) 部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 部署文档](https://www.metaswitch.com/products/core-network/perimeta-sbc)

有关受支持的 SDC 的完整列表，请参阅通过直接路由 认证的 [会话边界控制器列表](direct-routing-border-controllers.md)。

若要配置Microsoft 电话系统并允许用户使用直接路由，请执行以下步骤： 

- **第 1 步** [连接系统Microsoft 电话 SBC 并验证连接](direct-routing-connect-the-sbc.md)
- **第 2 步** [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)
- **第 3 步** [配置语音路由](direct-routing-voice-routing.md)
- **第 4 步** [将数字转换为备用格式](direct-routing-translate-numbers.md) 

如果要为多个租户配置 SBC，则还需要阅读为多个租户[配置 SBC。](direct-routing-sbc-multiple-tenants.md)


## <a name="related-topics"></a>相关主题

[电话系统直接路由](direct-routing-landing-page.md)

[规划直接路由](direct-routing-plan.md)