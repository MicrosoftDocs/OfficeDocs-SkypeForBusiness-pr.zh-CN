---
title: Microsoft Teams 会议室许可证
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 了解会议中不同类型的呼叫和会议功能的可用Microsoft Teams 会议室。
ms.openlocfilehash: ff6c36d0ded93ffa2231b6fd54a32658ce477d143c2fab4812446c4b88d50cd0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328967"
---
# <a name="teams-meeting-room-licensing-update"></a>Teams 会议室许可更新

## <a name="licensing-solutions-for-shared-communication-devices"></a>共享通信设备的许可解决方案

Microsoft 为会议室设备（例如 Microsoft Teams 会议室、Microsoft Surface Hub 和协作栏）提供两个专用的 SKUS，用于为会议授权会议以及按设备进行呼叫 (例如 Microsoft Teams) 。

|&nbsp;|Microsoft Teams 会议室标准 |Microsoft Teams 会议室 高级版 |
|:--- |:---: |:---: |
|Skype for Business |&#x2714;| &#x2714;|
|Microsoft Teams|  &#x2714;|  &#x2714;|
|电话系统|  &#x2714;|  &#x2714;|
|音频会议|&#x2714; &sup1;|&#x2714; &sup1;|
|Microsoft Intune|&#x2714;|&#x2714;|  
|全球可用性 | &#x2714; &sup2;| &#x2714; &sup2;|
|频道可用性 | EA、EAS、CSP、 <br/>Web Direct | EA、EAS、CSP、 <br/>Web Direct |
|托管服务 | | &#x2714; &sup3;|
| | | |

&sup1;可用性和包含的分钟数可能因区域而异。 若要验证服务可用性，请参阅音频会议和呼叫计划的"国家/地区["和"区域可用性"。](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans) 其他服务可能会收取使用费，例如免费、国内计划的国际分钟数等。客户可以禁用这些功能以避免产生额外的费用。  

&sup2;在主权云中不可用  

&sup3;有关详细信息和可用性，请参阅托管[Microsoft Teams 会议室服务](microsoft-teams-rooms-premium.md)。

> [!NOTE]
> 如果当前使用具有音频会议计划 2 的 E1、E3、E4、E5 SKUS 和 Skype for Business 计划 2，或者使用 Office 365 电话系统 和呼叫计划，这些将继续工作。 但是，应考虑在当前许可证过期后迁移到上表中更简单的许可模型。

> [!IMPORTANT]
> 如果使用计划 2 Skype for Business，则只能在Microsoft Teams 会议室模式下Skype for Business会议，这意味着所有会议都将Skype for Business会议。 若要为会议室启用会议Microsoft Teams，建议购买会议室许可证。 

下表列出了产品/服务中可用的Microsoft Teams 会议室以及需要购买哪些许可证才能获取这些功能。
  
> [!NOTE]
> [!注释] 要设置的会议室需为用户对象，并且要为其分配这些许可证。

| &nbsp; | 你拥有 Microsoft Teams 或 Skype for Business Online <br/> 需要购买以下产品：   |你拥有Skype for Business Server 2015/2019 (或混合) 。 <br/> 需要购买以下产品：|
|:-----|:-----|:-----|
|加入计划的会议  | Microsoft Teams 会议室标准或高级版  |Skype for Business Server 标准 CAL  |
|启动临时会议 | Microsoft Teams 会议室标准或高级版  |Skype for Business Server 标准 CAL  <br/> Skype for Business Server 企业 CAL|
|启动临时会议，然后从会议拨出到电话号码 |  Microsoft Teams 会议室标准或高级版 |Skype for Business 标准 CAL  <br/> Skype for Business Server 企业 CAL|
|为会议室提供电话号码，然后从会议室拨打或接听电话，或者使用电话号码加入音频会议  | 使用直接路由：Microsoft Teams 会议室标准或高级版<br/>无直接路由：国内或国际呼叫计划<br/>Microsoft 365 商务语音  |Skype for Business Server 标准 CAL  <br/> Skype for Business Server Plus CAL  |
|使用设备管理会议室Microsoft Intune |Microsoft Teams 会议室标准或高级版  |Microsoft Intune本地[MDM 创建订阅](/configmgr/mdm/plan-design/plan-on-premises-mdm) |
|Microsoft Teams 会议室托管服务 | Microsoft Teams 会议室 高级版 ||
| |||

> [!NOTE]
> 如果为会议室系统分配了现有许可证，这些许可证将继续工作，而不会中断。 当现有许可证过期时，会议室新版 SKU。  

 **使用正确的版本Windows 10：** 对于想要将 Windows 10 部署到其设备的客户，请参阅配置 Microsoft Teams 会议室 [控制台](./console.md)。 可以从批量许可 [服务中心获取副本](https://www.microsoft.com/Licensing/servicecenter/)。 
 
 另请参阅[出色的会议室体验：了解新的Microsoft Teams 会议室标准高级版。](https://www.microsoft.com/microsoft-365/blog/2020/07/21/microsoft-teams-meetings-hybrid-workplace-options/)