---
title: 配置运营商连接会议
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解如何配置会议连接运营商。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257498"
---
# <a name="configure-operator-connect-conferencing"></a>配置运营商连接会议

本文详细介绍如何为组织和连接配置运营商和会议。

在配置运营商连接会议之前，请阅读电话连接[计划](operator-connect-conferencing-plan.md)，了解权益和许可要求。

本文涵盖的主题包括：

- [设置操作员](#set-up-an-operator)
- [获取音频会议网桥的号码](#acquire-numbers-for-your-audio-conferencing-bridge)
- [更改用户的会议邀请中包含的默认电话号码](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [通过接线员从Microsoft Teams发送出站呼叫](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [管理操作员](#manage-your-operators)
- [音频会议网桥的发布号码](#release-numbers-from-your-audio-conferencing-bridge)
- [有关管理 Microsoft 音频会议的其他信息](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>设置操作员

可以在管理中心设置、编辑和删除Teams运算符。 在左侧导航窗格中，转到" **语音>运算符"。**

设置运算符：

1. **选择运算符。**  在" **所有运算符**"选项卡中，按区域或服务筛选可用的运算符   ，以查找满足语音需求的合适运算符。 然后，选择想要使用的运算符。 对于"连接会议"，请验证您的运营商是否将 **"** 会议"列为可用产品。

2. **选择国家/地区。**  在  **"操作员设置**"下，选择要通过所选操作员启用的国家/地区。

3. **提供联系信息**  您的联系信息（包括您的全名和电子邮件地址）将与您的运营商共享。 稍后可以更改此信息。 此外，你需要提供公司规模，并提供提供电话号码的选项。 运营商使用此信息来联系你，了解有关运营商连接的详细信息。

4. 接受数据传输通知。

5. **添加运算符。**  选择  **"添加为我的运算符"**   以保存。

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>获取音频会议网桥的号码

组织的音频会议网桥包括组织中所有用户可以使用 PSTN 电话号码Microsoft Teams会议的电话号码。 您可以在"会议"和"会议网桥"下的 Teams 管理中心内看到与>**音频会议网桥关联的电话号码**。

若要获取音频会议网桥的电话号码，请执行以下步骤：

1. **音频会议标准订阅或运营商连接会议许可证。** 需要接线员连接号码才能加入他们组织的会议的用户需要分配有音频会议标准订阅许可证或连接会议运营商许可证。 有关详细信息，请参阅[规划运营商连接会议。](operator-connect-conferencing-plan.md)

2. **获取数字。**  转到运营商的网站订购和获取电话号码。 有关操作员网站的列表，请转到"Microsoft 365 [运算符连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID。](/onedrive/find-your-office-365-tenant-id) 操作员完成订单后，会向租户上传号码。 可以通过在管理中心内通过语音Teams号码 **来查看号码> 电话提供商**。

3. **为音频会议网桥分配号码。** 你可以从"会议""会议网桥"下Teams"会议网桥"下>音频会议网桥 **>号码**。 有关详细信息，请参阅 [更改音频会议网桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

>[!NOTE]
>不能将会议号码连接号码分配为网桥的默认号码。 将电话号码分配给音频会议网桥后，该号码将列在"查找本地号码"页中，该页包含在组织中具有音频会议许可证或接线员 连接 会议许可证的用户的会议邀请中。
>
>若要通过接线员路由出站呼叫，请参阅本文中进一步Teams操作员 [**从**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)会议发送出站呼叫部分。

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>更改用户的会议邀请中包含的默认电话号码

 此步骤是可选的。

用户的默认电话号码是安排会议时包含在会议邀请中的号码。 您可以在"用户""管理用户"下的"Teams管理中心"中更新>**会议邀请中包含的电话号码**。 若要更新用户的会议邀请中包含的电话号码，请选择该用户，然后选择"音频会议"部分中的"**编辑**"。

应用更改后，组织者的新会议邀请将包括新的默认电话号码。 但是，在更改之前安排的现有会议邀请将保留原始默认号码。

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>通过接线员从Microsoft Teams发送出站呼叫

如果你有 Microsoft 音频会议标准订阅或接线员 连接 会议许可证，可以通过设置音频会议路由策略，将音频会议服务配置为通过运营商路由来自 Teams 会议的一组出站呼叫。

>[!NOTE]
>使用"连接"会议许可证，出站呼叫只能通过您的运营商。 如果你有"连接"会议许可证，则需要按如下所述配置服务，以启用从Teams到电话号码的出站呼叫。

您可以在用户级别应用音频会议路由策略，这意味着您的运营商仅从具有关联策略的用户组织的Teams路由出站呼叫。 还可以在全球级别应用这些策略，这意味着运营商从组织中所有用户组织的Teams路由出站呼叫。

使用 PowerShell 创建组织的新音频会议路由策略。 若要将操作员指定为从会议进行Teams的主要路由，请执行以下步骤，使用所示的 PowerShell 命令：

1. [步骤 1：向联机 PSTN 使用策略添加新字符串](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [步骤 2：创建新的联机语音路由策略](#step-2-create-a-new-online-voice-route-policy)
3. [步骤 3：创建新的联机音频会议路由策略](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [步骤 4：向用户分配新策略](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>步骤 1：向联机 PSTN 使用策略添加新字符串

有关使用此 cmdlet 的信息，请阅读[Set-CsOnlinePstnUsage。](/powershell/module/skype/set-csonlinepstnusage)

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>步骤 2：创建新的联机语音路由策略

有关使用此 cmdlet 的信息，请阅读[Set-CsOnlineVoiceRoute。](/powershell/module/skype/set-csonlinevoiceroute)

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>步骤 3：创建新的联机音频会议路由策略

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>步骤 4：向用户分配新策略

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>若要将音频会议路由策略设置为全局策略，并应用到组织中所有用户，可以使用 参数 ``-Global`` 而不是 ``-Identity`` 参数。 例如 ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` ，。

创建音频会议路由策略并应用于用户时，提供参数中指定电话号码的运营商将Teams ``BridgeSourcePhoneNumber`` 呼叫路由到 PSTN 电话号码。 此外，参数指定要用作 PSTN 电话号码的出站呼叫的呼叫线标识 ``BridgeSourcePhoneNumber`` 电话号码的电话号码。

中指定的模式为正则表达式形式，它 ``NumberPattern`` 指定要通过运算符路由的调用。 ``"\d+"``上述示例中的模式匹配来自会议的所有Teams呼叫。 还可以将 NumberPattern 参数设置为 ，该参数匹配采用以下格式的拨号号码  ``“^\+1(425|206)(\d{7})$”`` ：+1 425 XXX XX XX 或 +1 206 XXX XX XX，或 ，它匹配采用以下格式的拨号号码 ``“^\+1(\d{10})$”`` ：+1 425 XXX XX XX。

将音频会议路由策略分配给用户后，其会议的所有呼叫将匹配其音频会议路由策略中指定的正则表达式的电话号码通过您的运营商路由，包括通过"邀请某人或拨打号码会议"选项发起的呼叫和呼叫时呼叫我。 

## <a name="manage-your-operators"></a>管理操作员

在" **我的运算符**"选项卡中，可以查看运算符及其状态，并更改   所选内容：

- 按国家/地区管理运营商服务
- 暂停操作员
- 删除运算符

>[!NOTE]
>在从组织或国家/地区中删除接线员之前，必须删除分配给用户和音频会议网桥的所有电话号码，然后联系接线员释放号码。

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>音频会议网桥的发布号码

若要从 Teams 管理中心释放音频会议网桥的电话号码，请参阅更改音频会议网桥上的电话号码中取消为会议网桥分配服务电话号码[的步骤。](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>有关管理 Microsoft 音频会议的其他信息

有关如何为组织管理 Microsoft 音频会议的其他信息，请参阅以下文章：

- 管理组织的 Microsoft 音频会议服务设置[：在](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)Microsoft Teams

- 管理组织中用户的 Microsoft 音频会议服务设置：管理用户的音频会议[Microsoft Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 更改音频会议电话号码的自动助理语言：[为](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)音频会议设置自动助理语言Microsoft Teams
