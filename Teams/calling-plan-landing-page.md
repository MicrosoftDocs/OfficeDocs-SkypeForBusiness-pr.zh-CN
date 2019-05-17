---
title: Microsoft Teams 中的通话套餐
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 调用计划登录页
appliesto:
- Microsoft Teams
ms.openlocfilehash: d85546df76b7699986d28152ff08003612df8331
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108752"
---
# <a name="which-calling-plan-is-right-for-you"></a>哪些调用规划最适合您？ 

您已完成的[开始](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许您已经部署了[会议 & 会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在已准备好添加云语音工作负荷，因而您已决定使用调用计划与 Microsoft 电话系统连接到公共公用电话交换网 (PSTN)。 

本文介绍数据调用计划以及其他注意事项核心部署决策可能想要配置，根据组织的需要。 有关 Microsoft 云语音产品的详细信息，您还应阅读[Microsoft 团队中的云语音功能](cloud-voice-landing-page.md)。


## <a name="learn-more-about-calling-plans"></a>了解有关调用计划

以下文章提供有关部署和使用 Microsoft 调用计划的详细信息：

- [Office 365 中的电话系统](what-is-phone-system-in-office-365.md)
- [Office 365 通话套餐](calling-plans-for-office-365.md)
- [设置通话套餐](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>核心部署决策

若要使用 Microsoft 为您的电话运营商，您需要获得调用规划许可证并将其分配给您电话系统的用户。 

有两种类型的调用计划：

- 国内呼叫计划 
- 国内和国际呼叫计划

|询问你自己|操作 |
|------------|-------|
|有调用计划在我的区域中？ 哪些用户位置会调用规划服务？ | 有关详细信息，请参阅[国家和地区音频会议和调用计划的可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 | 
我的用户是否需要国际呼叫？ | 有关详细信息，请参阅[调用 Office 365 的计划](calling-plans-for-office-365.md)。 |
我的用户是否具有调用计划许可证？ | 若要购买并分配许可证时，请参阅[步骤 2： 购买和分配许可证](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
每个我用户是否有直接向内拨打 (DID) 电话号码？ | 若要获取电话号码，请参阅[步骤 3： 获取电话号码](set-up-calling-plans.md#step-3-get-phone-numbers)。 |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>将电话号码转接到 Office 365

很容易将您的电话号码从您当前的服务提供商转接到团队。 端口您向工作组的电话号码后，Microsoft 将成为服务提供商，将向您为这些电话号码。 有关详细信息，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。


### <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

与调用计划在 Office 365 中，每个用户在您的组织需要具有唯一直接拨入 (DID) 电话号码和相应的验证紧急地址。 您还可以指定紧急地址 （例如，办公室号码或楼层号） 中的紧急位置。 

|询问你自己|操作 |
|:------------|:-------|
|如何详细我是否需要为的紧急地址和位置信息？ |有关详细信息，请参阅[紧急位置、 地址和呼叫路由是什么？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)。


### <a name="calling-identity"></a>调用标识

默认情况下，所有出站呼叫的分配的电话号码用作调用 identity (呼叫者 ID)。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。

|询问你自己|操作 |
|:------------|:-------|
|我想要屏蔽或禁用呼叫者 ID 吗？ | 若要更改或阻止呼叫者 ID，请参阅[设置用户的呼叫者 ID](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-the-caller-id-for-a-user)。 |
|||




