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
description: 确定哪个Microsoft 电话系统呼叫计划最适合你的组织在云语音Teams。
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 798d119be837e5ab2aafbd26676dd7e26b641db6
ms.sourcegitcommit: 4847f24e8c644336d2b2f48aa09e2cf91360e4dd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64686299"
---
# <a name="which-calling-plan-is-right-for-you"></a>哪种通话套餐适合你？

你已完成[开始](get-started-with-teams-quick-start.md)。 你已在整个组织中部署了具有[聊天、团队、频道和应用](deploy-chat-teams-channels-microsoft-teams-landing-page.md)的 Teams。 也许你已 [部署会议&会议](deploy-meetings-microsoft-teams-landing-page.md)。 现在，你已准备好添加云语音工作负载，并决定将Microsoft 电话系统与呼叫计划配合使用，以连接到公共交换电话网络 (PSTN) 。

本文介绍通话套餐的核心部署决策，以及可能需要根据组织需求配置的其他注意事项。 还应[阅读Microsoft Teams中的 Cloud Voice](cloud-voice-landing-page.md)，以获取有关 Microsoft 云语音产品/服务的详细信息。

## <a name="learn-more-about-calling-plans"></a>详细了解通话套餐

以下文章提供有关部署和使用 Microsoft 通话套餐的详细信息：

- [Microsoft 365或Office 365中的电话系统](what-is-phone-system-in-office-365.md)
- [调用Microsoft 365或Office 365计划](calling-plans-for-office-365.md)
- [设置通话套餐](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>核心部署决策

若要将 Microsoft 用作电话运营商，需要获取通话套餐许可证并将其分配给电话系统用户。

有三种类型的通话套餐可用：

- 国内通话套餐
- 国际通话套餐
- 国内和国际通话套餐

|询问你自己|操作 |
|------------|-------|
|通话套餐是否在我的区域中可用？ 哪些用户位置将具有呼叫计划服务？ | 有关详细信息，请参阅 [音频会议和通话套餐的国家/地区可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)。 |
我的用户是否需要国际呼叫？ | 有关详细信息，请参阅[Microsoft 365或Office 365的通话套餐](calling-plans-for-office-365.md)。 |
我的用户是否具有通话套餐许可证？ | 若要购买和分配许可证，请参阅 [步骤 2：购买和分配许可证](set-up-calling-plans.md#step-2-buy-and-assign-licenses)。 |
我的用户是否都有直接向内拨号 () 电话号码？ | 若要获取电话号码，请参阅 [步骤 3：获取电话号码](set-up-calling-plans.md#step-3-get-phone-numbers)。 |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>将电话号码传输到Microsoft 365或Office 365

可以轻松地将电话号码从当前服务提供商传输到Teams。 将电话号码移植到Teams后，Microsoft 将成为你的服务提供商，并将向你收取这些电话号码的费用。 有关详细信息，请参阅[将电话号码转到Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。

### <a name="phone-numbers-and-emergency-locations"></a>电话号码和紧急位置

使用Microsoft 365或Office 365中的呼叫计划，组织中的每个用户都需要具有唯一的直接向内拨号 (DID) 电话号码和相应的验证紧急地址。 还可以在紧急地址内指定紧急位置 (例如办公号码或楼层编号) 。

|询问你自己|操作 |
|:------------|:-------|
|我希望紧急地址和位置信息有多详细？ |有关详细信息，请参阅[什么是紧急位置、地址和呼叫路由？](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)

### <a name="calling-identity"></a>调用标识

默认情况下，所有出站呼叫都使用分配的电话号码作为呼叫标识 (呼叫者 ID) 。 呼叫接收人可以快速识别呼叫方，并决定是接收还是拒绝呼叫。

|询问你自己|操作 |
|:------------|:-------|
|是否要屏蔽或禁用呼叫者 ID？ | 若要更改或阻止调用方 ID，请参阅 [设置用户的调用方 ID](set-the-caller-id-for-a-user.md)。 |
|||
