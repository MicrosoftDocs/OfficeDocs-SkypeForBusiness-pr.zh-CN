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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: 确定哪种 Microsoft Phone 系统通话计划最适合你的组织在团队中的云语音服务。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1fb0abed3477039f4c19c0e2de0ea696626f35
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905024"
---
# <a name="which-calling-plan-is-right-for-you"></a>哪种通话套餐适合你？ 

您已完成 "[入门](get-started-with-teams-quick-start.md)"。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已将[会议部署 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在，你已准备好添加云语音工作负载，你已决定将 Microsoft Phone 系统与通话计划配合使用来连接到公共交换式电话网络（PSTN）。 

本文介绍调用计划的核心部署决策以及你可能希望根据组织的需求配置的其他注意事项。 您还应阅读[Microsoft 团队中的云语音](cloud-voice-landing-page.md)，了解有关 Microsoft 云语音服务的详细信息。


## <a name="learn-more-about-calling-plans"></a>了解有关通话计划的详细信息

以下文章提供了有关部署和使用 Microsoft 通话计划的详细信息：

- [Office 365 中的电话系统](what-is-phone-system-in-office-365.md)
- [Office 365 通话套餐](calling-plans-for-office-365.md)
- [设置通话套餐](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>核心部署决策

若要将 Microsoft 用作电话运营商，你需要获取呼叫计划许可证并将其分配给你的电话系统用户。 

有两种类型的通话计划可用：

- 国内通话计划 
- 国内和国际通话计划

|询问你自己|操作 |
|------------|-------|
|我所在区域是否有通话计划？ 哪些用户位置将具有呼叫计划服务？ | 有关详细信息，请参阅[音频会议和通话计划的国家和地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 | 
我的用户是否需要国际通话？ | 有关详细信息，请参阅[Office 365 的呼叫计划](calling-plans-for-office-365.md)。 |
我的用户是否有通话计划许可证？ | 要购买和分配许可证，请参阅[步骤2：购买和分配许可证](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
我的用户是否每个都有直接拨入电话号码？ | 若要获取电话号码，请参阅[步骤3：获取电话号码](set-up-calling-plans.md#step-3-get-phone-numbers)。 |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>将电话号码转接到 Office 365

将您的电话号码从当前服务提供商转移到团队非常简单。 将您的电话号码移植到团队后，Microsoft 将成为您的服务提供商，并向您收取这些电话号码。 有关详细信息，请参阅[将电话号码转移给团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。


### <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

使用 Office 365 中的呼叫计划，您的组织中的每个用户都需要有一个唯一的直接向内拨号（已拨）电话号码和相应的已验证的紧急地址。 您还可以指定紧急地址内的紧急位置（例如，办公室号码或楼层号）。 

|询问你自己|操作 |
|:------------|:-------|
|我需要有关紧急地址和位置信息的详细信息？ |有关详细信息，请参阅[什么是紧急位置、地址和呼叫路由？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。


### <a name="calling-identity"></a>通话标识

默认情况下，所有出站呼叫均使用分配的电话号码作为呼叫标识（呼叫者 ID）。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。

|询问你自己|操作 |
|:------------|:-------|
|我是否希望屏蔽或禁用来电显示？ | 若要更改或阻止呼叫方 ID，请参阅[为用户设置来电显示](set-the-caller-id-for-a-user.md)。 |
|||




