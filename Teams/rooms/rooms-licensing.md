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
description: 了解 Microsoft Teams 会议室中不同类型的呼叫和会议功能的可用许可证。
ms.openlocfilehash: 37f47e9b89abd87837b02f8a67c3c82eaa9c7a5c
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662477"
---
# <a name="teams-meeting-room-licensing-update"></a>Teams 会议室许可更新

## <a name="licensing-solutions-for-shared-communication-devices"></a>共享通信设备的许可解决方案

Microsoft 为会议室设备（如 Microsoft Teams 会议室、Microsoft Surface Hub 和 Microsoft Teams) 协作栏）提供专用 S (KU，用于按设备授权会议和通话。

||会议室 SKU |  
|:--- |:---: |
|Skype for Business |&#x2714;|
|Microsoft Teams|  &#x2714;|
|电话系统|  &#x2714;|
|音频会议|&#x2714; &sup1;|
|Microsoft Intune|&#x2714;|  
|全球可用性 | &#x2714; &sup2;|
|频道可用性 | EA、EAS、CSP、 <br/>Web Direct |
| | | |

&sup1;可用性和包含的分钟数可能因区域而异。 若要验证服务可用性，请参阅音频会议和通话计划的"国家[/地区"和"区域可用性"。](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans) 其他服务可能会收取使用费，例如免费、国内计划的国际分钟数等。客户可以禁用这些功能以避免产生额外的费用。  

&sup2;在主权云中不可用  


> [!NOTE]
> 如果你当前将 E1、E3、E4、E5 SUS 与带音频会议或 Office 365 电话系统和呼叫计划的 Skype for Business 计划 2 一起使用，这些 SKUS 将继续工作。 但是，应考虑在当前许可证过期后，迁移到上表中更简单的许可模型。

> [!IMPORTANT]
> 如果你使用的是 Skype for Business 计划 2，则只能在 Skype for Business 模式下使用 Microsoft Teams 会议室，这意味着你的所有会议都是 Skype for Business 会议。 若要为 Microsoft Teams 会议启用会议室，建议购买会议室许可证。 

下表列出了 Microsoft Teams 会议室中可用的功能，以及需要购买哪些许可证才能获取这些功能。
  
> [!NOTE]
> [!注释] 要设置的会议室需为用户对象，并且要为其分配这些许可证。

|  | 你拥有 Microsoft Teams 或 Skype for Business Online <br/> 需要购买以下产品：   |你在本地或混合 (Skype for Business Server 2015/2019) 。 <br/> 需要购买以下产品：|
|:-----|:-----|:-----|
|加入计划的会议  | 会议室 SKU  |Skype for Business Server 标准 CAL  |
|启动临时会议 | 会议室 SKU  |Skype for Business Server 标准 CAL  <br/> Skype for Business Server 企业 CAL|
|启动临时会议，然后从会议拨出到电话号码 |  会议室 SKU |Skype for Business 标准 CAL  <br/> Skype for Business Server 企业 CAL|
|为会议室提供电话号码，从会议室拨打或接听电话，或者使用电话号码加入音频会议  | 使用直接路由：会议室 SKU<br/>无直接路由：国内或国际呼叫计划<br/>Microsoft 365 商务语音  |Skype for Business Server 标准 CAL  <br/> Skype for Business Server Plus CAL  |
|使用 Microsoft Intune 管理会议室设备 |会议室 SKU  |使用本地 MDM[的](https://docs.microsoft.com/configmgr/mdm/plan-design/plan-on-premises-mdm)Microsoft Intune 订阅 |
| |||

> [!NOTE]
> 如果为会议室系统分配了现有许可证，这些许可证将继续正常工作，而不会中断。 当现有许可证过期时，应移动到使用新的会议室 SKU。  

 **使用正确的 Windows 10** 版本：对于想要将 Windows 10 映像部署到其设备的客户，请参阅" [配置 Microsoft Teams 会议室"控制台](https://docs.microsoft.com/microsoftteams/room-systems/console)。 可以从批量许可服务中心 [获取副本](https://www.microsoft.com/Licensing/servicecenter/)。
