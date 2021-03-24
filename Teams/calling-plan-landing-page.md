---
title: Microsoft Teams 中的通话套餐
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: 在 Teams 中的云语音上确定哪个 Microsoft Phone 系统呼叫计划最适合你的组织。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102728"
---
# <a name="which-calling-plan-is-right-for-you"></a>哪种通话套餐适合你？ 

你已完成入门[。](get-started-with-teams-quick-start.md) 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已部署会议[&会议。](deploy-meetings-microsoft-teams-landing-page.md) 现在，你已准备好添加云语音工作负荷，并且你已决定将 Microsoft Phone System 与呼叫计划一起连接到公共电话交换网 (PSTN) 。 

本文介绍呼叫计划的核心部署决策，以及可能需要根据组织需求配置的其他注意事项。 还应阅读 [Microsoft Teams 中的云语音](cloud-voice-landing-page.md) ，了解有关 Microsoft 云语音产品/服务的信息。


## <a name="learn-more-about-calling-plans"></a>详细了解通话套餐

以下文章提供有关部署和使用 Microsoft 呼叫计划的信息：

- [Microsoft 365 或 Office 365 中的电话系统](what-is-phone-system-in-office-365.md)
- [针对 Microsoft 365 或 Office 365 的呼叫计划](calling-plans-for-office-365.md)
- [设置通话套餐](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>核心部署决策

若要将 Microsoft 用作电话运营商，需要获取呼叫计划许可证并将其分配给电话系统用户。 

有两种类型的通话套餐可用：

- 国内呼叫计划 
- 国内和国际呼叫计划

|询问你自己|Action |
|------------|-------|
|"通话套餐"在我的区域中是否可用？ 哪些用户位置将具有呼叫计划服务？ | 有关详细信息，请参阅音频会议和通话计划的"国家/地区["和"区域可用性"。](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
我的用户是否需要国际呼叫？ | 有关详细信息，请参阅 [Microsoft 365 或 Office 365 的呼叫计划](calling-plans-for-office-365.md)。 |
我的用户是否拥有通话套餐许可证？ | 若要购买和分配许可证，请参阅 [步骤 2：购买和分配许可证](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
我的用户是否都有直接拨入 (电话号码) 电话号码？ | 若要获取电话号码，请参阅 [步骤 3：获取电话号码](set-up-calling-plans.md#step-3-get-phone-numbers)。 |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>将电话号码转移到 Microsoft 365 或 Office 365

将电话号码从当前服务提供商转移到 Teams 很容易。 将电话号码移植到 Teams 后，Microsoft 将成为服务提供商，并针对这些电话号码计费。 有关详细信息，请参阅[将电话号码转移到 Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)


### <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

使用 Microsoft 365 或 Office 365 中的呼叫计划，您的组织中的每个用户都需要具有唯一的直接拨入 (DID) 电话号码和相应的已验证紧急地址。 还可以在紧急地址内指定紧急 (，例如办公室号码或楼层) 。 

|询问你自己|Action |
|:------------|:-------|
|希望紧急地址和位置信息有多详细？ |有关详细信息，请参阅[什么是紧急位置、地址和呼叫路由？。](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>调用标识

默认情况下，所有出站呼叫使用分配的电话号码作为呼叫标识 (呼叫者 ID) 。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。

|询问你自己|Action |
|:------------|:-------|
|是否要屏蔽或禁用来电显示？ | 若要更改或阻止来电显示，请参阅 [为用户设置来电显示](set-the-caller-id-for-a-user.md)。 |
|||