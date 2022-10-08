---
title: 配置直接路由
ms.reviewer: filippse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
- highpri
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 了解如何配置 Microsoft 直接路由以将本地电话基础结构连接到 Teams 电话系统。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2adb6e9263cb573d661677b1a36b5cd24d2c8065
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999367"
---
# <a name="configure-direct-routing"></a>配置直接路由

通过直接路由，可以将本地电话基础结构连接到 Microsoft Teams。 本文列出了将受支持的本地会话边界控制器 (SBC) 连接到直接路由所需的高级步骤，以及如何将 Teams 用户配置为使用直接路由连接到公共交换电话网络 (PSTN) 。 本文链接到相关文章以获取详细信息。  

有关直接路由是否适合组织的信息，请参阅 [PSTN 连接选项](pstn-connectivity.md)。 有关先决条件和规划部署的信息，请参阅 [计划直接路由](direct-routing-plan.md)。

若要完成本文中介绍的步骤，管理员需要熟悉 PowerShell cmdlet。 有关使用 PowerShell 的详细信息，请参阅[为Windows PowerShell设置计算机](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。 

在执行这些文章中的步骤之前，Microsoft 建议你确认 SBC 已按照 SBC 供应商的建议进行配置： 

- [AudioCodes 部署文档](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 部署文档](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [功能区通信部署文档](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-Systems (任何节点) 部署文档](https://www.anynode.de/anynode-and-microsoft-teams/)
- [Metaswitch 部署文档](https://www.metaswitch.com/products/core-network/perimeta-sbc)

有关支持的 SBC 的完整列表，请参阅 [经直接路由认证的会话边界控制器](direct-routing-border-controllers.md)。

若要配置电话系统并使用户能够使用直接路由，请执行以下步骤： 

- **第 1 步** [将 SBC 与电话系统连接并验证连接](direct-routing-connect-the-sbc.md)
- **第 2 步** [为用户启用直接路由、语音和语音邮件](direct-routing-enable-users.md)
- **第 3 步** [配置呼叫路由](direct-routing-voice-routing.md)
- **第 4 步** [将数字转换为备用格式](direct-routing-translate-numbers.md) 

如果要为多个租户配置 SBC，则还需要读取[为多个租户配置 SBC。](direct-routing-sbc-multiple-tenants.md)

## <a name="support-boundaries"></a>支持边界
Microsoft 仅在与认证设备一起使用时支持具有直接路由的电话系统。 如果出现问题，必须先联系 SBC 供应商的客户支持部门。 如果需要，SBC 供应商将通过内部渠道将问题呈报给 Microsoft。 Microsoft 保留在非认证设备通过直接路由连接电话系统的情况下拒绝提供支持的权利。 如果 Microsoft 确定客户的直接路由问题与供应商的 SBC 设备有关，则客户需要重新联系 SBC 供应商以获得支持。

## <a name="related-topics"></a>相关主题

[规划语音解决方案](cloud-voice-landing-page.md)

[PSTN 连接选项](pstn-connectivity.md)

[规划直接路由](direct-routing-plan.md)
