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
description: 详细了解如何配置运营商连接会议。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ade65551ad30c15fd209aa542781edce44bd76dd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676024"
---
# <a name="configure-operator-connect-conferencing"></a>配置运营商连接会议

本文详细介绍如何为组织和用户配置运营商连接会议。

在配置运营商连接会议之前，请阅读[运营商连接会议计划](operator-connect-conferencing-plan.md)，了解有关权益和许可要求的信息。

本文中介绍的主题包括：

- [设置运算符](#set-up-an-operator)
- [获取音频会议桥的数字](#acquire-numbers-for-your-audio-conferencing-bridge)
- [更改用户会议邀请中包含的默认电话号码](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [通过操作员从Microsoft Teams会议发送出站呼叫](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [管理运算符](#manage-your-operators)
- [从音频会议桥释放号码](#release-numbers-from-your-audio-conferencing-bridge)
- [有关管理 Microsoft 音频会议的其他信息](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>设置运算符

可以在Teams管理中心设置、编辑和删除运算符。 在左侧导航窗格中，转到 **语音>运算符**。

若要设置运算符，请执行以下操作：

1. **选择运算符。** 在“ **所有运算符** ”选项卡中，按区域或服务筛选可用运算符，以查找适合语音需求的运算符。 然后，选择要使用的运算符。 对于运营商连接会议，请验证操作员是否已将 **会议** 列为可用产品。

2. **选择国家/地区。** 在 **“操作员”设置** 下，选择要使用所选运算符启用的国家/地区。

3. **提供联系人信息** 您的联系人信息（包括您的全名和电子邮件地址）将与您的操作员共享。 稍后可以更改此信息。 此外，还需要提供公司规模，并提供提供电话号码的选项。 操作员使用此信息与你联系，了解有关运营商连接会议的更多详细信息。

4. 接受数据传输通知。

5. **添加运算符。** 选择 **“添加为我的运算符** ”进行保存。

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>获取音频会议桥的数字

组织音频会议网桥包括组织中所有用户使用 PSTN 电话号码加入Microsoft Teams会议的电话号码。 可以在会议>会议桥下的Teams 管理员中心看到与组织 **音频会议桥** 关联的电话号码。

若要获取音频会议网桥的电话号码，请执行以下步骤：

1. **音频会议标准订阅或运营商连接会议许可证。** 需要运营商连接会议号码才能加入其组织的会议的用户需要分配音频会议标准订阅许可证或运营商连接会议许可证。 有关详细信息，请参阅[计划运营商连接会议](operator-connect-conferencing-plan.md)。

2. **获取数字。** 转到操作员的网站以订购和获取电话号码。 有关操作员网站的列表，请转到[Microsoft 365 运营商连接目录](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 需要提供租户 ID。 如果不知道租户 ID，请参阅[“查找Microsoft 365租户 ID](/onedrive/find-your-office-365-tenant-id)。 操作员完成订单后，会将数字上传到租户。 可以通过转到语音> 电话数字来查看Teams管理中心 **中的数字** 和提供程序。

3. **将数字分配给音频会议桥。** 可以在会议>会议桥>“添加”下的Teams管理中心将数字分配到 **音频会议桥**。 有关详细信息，请参阅[更改音频会议桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)。

>[!NOTE]
>不能将运营商连接会议数字分配为桥的默认数字。 将电话号码分配到音频会议网桥后，该号码将列在“**查找本地号码”页** 中，该页包含在组织中具有音频会议许可证或运营商连接会议许可证的用户的会议邀请中。
>
>若要通过操作员路由出站呼叫，请参阅本文后面的 [**操作员部分从Teams会议发送出站呼叫**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)。

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>更改用户会议邀请中包含的默认电话号码

 此步骤是可选的。

用户的默认电话号码是在安排会议时包含在会议邀请中的电话号码。 可以在“**用户>管理** 用户”下更新Teams 管理员中心用户的会议邀请中包含的电话号码。 若要更新用户会议邀请中包含的电话号码，请选择用户，然后在 **“音频会议**”部分中选择 **“编辑**”。

应用更改后，组织者的新会议邀请将包括新的默认电话号码。 但是，在更改之前安排的现有会议邀请将保留原始默认号码。

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>通过操作员从Microsoft Teams会议发送出站呼叫

如果你有 Microsoft 音频会议 标准订阅或运营商连接会议许可证，则可以通过设置音频会议路由策略，将音频会议服务配置为通过操作员路由Teams会议的所有或一组出站呼叫。

>[!NOTE]
>使用运营商连接会议许可证，出站呼叫只能通过操作员进行。 如果有运营商连接会议许可证，则需要按如下所述配置服务，以启用从Teams会议到电话号码的出站呼叫。

可以在用户级别应用音频会议路由策略，这意味着操作员仅路由用户组织的Teams会议的出站呼叫。 还可以在全局级别应用这些策略，这意味着操作员从组织中所有用户组织的Teams会议路由出站呼叫。

使用 PowerShell 创建组织的新音频会议路由策略。 若要将运算符指定为来自Teams会议的出站呼叫的主要路由，请按照以下步骤使用指示的 PowerShell 命令执行以下步骤：

1. [步骤 1：向联机 PSTN 使用策略添加新字符串](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [步骤 2：创建新的联机语音路由策略](#step-2-create-a-new-online-voice-route-policy)
3. [步骤 3：创建新的联机音频会议路由策略](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [步骤 4：将新策略分配给用户](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>步骤 1：向联机 PSTN 使用策略添加新字符串

有关使用此 cmdlet 的详细信息，请阅读 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage) 。

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>步骤 2：创建新的联机语音路由策略

有关使用此 cmdlet 的详细信息，请阅读 [Set-CsOnlineVoiceRoute](/powershell/module/skype/set-csonlinevoiceroute) 。

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>步骤 3：创建新的联机音频会议路由策略

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>步骤 4：将新策略分配给用户

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy"
```

>[!NOTE]
>若要将音频会议路由策略设置为全局，并将其应用于组织中的所有用户，可以使用``-Global``该参数而不是``-Identity``参数。 例如， ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy"``.

创建音频会议路由策略并将其应用到用户时，提供参数路由中``BridgeSourcePhoneNumber``指定的电话号码的操作员Teams到 PSTN 电话号码的出站呼叫。 此外， ``BridgeSourcePhoneNumber`` 该参数指定要用作对 PSTN 电话号码的出站呼叫的呼叫行标识电话号码的电话号码。

在正则表达式形式中指定的 ``NumberPattern`` 模式，它指定要通过运算符路由的调用。 ``"\d+"``上述示例中的模式与来自Teams会议的所有出站调用匹配。 还可以将 NumberPattern 参数设置为  ``"^\+1(425|206)(\d{7})$"``与以下格式的拨号匹配的号码：+1 425 XXX XX XX 或 +1 206 XXX XX XX，或者 ``"^\+1(\d{10})$"``将拨号号码与以下格式相匹配：+1 425 XXX XX XX。

向用户分配音频会议路由策略后，其会议中的所有呼叫都指向一个电话号码，该电话号码与通过运营商的音频会议路由策略路由中指定的正则表达式相匹配，包括通过“邀请某人 **”** 发起的呼叫和呼叫呼叫 **或拨打号码** 会议选项。

## <a name="manage-your-operators"></a>管理运算符

在“ **我的运算符** ”选项卡中，可以查看运算符及其状态，并针对所选内容进行以下更改：

- 按国家/地区管理运营商服务
- 挂起运算符
- 删除运算符

>[!NOTE]
>在从组织或国家/地区删除操作员之前，必须删除分配给用户和音频会议网桥的所有电话号码，然后与运营商联系以释放号码。

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>从音频会议桥释放号码

若要从Teams管理中心释放音频会议桥的电话号码，请参阅在 [更改音频会议桥上的电话号码](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)**时为会议桥取消分配服务电话号码的步骤**。

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>有关管理 Microsoft 音频会议的其他信息

有关如何为组织管理 Microsoft 音频会议的其他信息，请参阅以下文章：

- 管理组织的 Microsoft 音频会议 服务设置：[在Microsoft Teams中管理组织的音频会议设置](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)

- 管理组织中用户的 Microsoft 音频会议 服务设置：[在Microsoft Teams中管理用户的音频会议设置](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)

- 更改音频会议电话号码的自动助理语言：[为音频会议设置自动助理语言Microsoft Teams](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)
