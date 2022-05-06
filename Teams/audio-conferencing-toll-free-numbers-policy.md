---
title: 音频会议免费号码策略
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: mshaikh
ms.topic: conceptual
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
search.appverid: MET150
audience: admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.overview
description: 了解Microsoft 365或Office 365中的音频会议如何允许用户通过手机呼叫会议。
ms.openlocfilehash: 11e1e493db38b5e830b3334f659d23f86b6b56ba
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016994"
---
# <a name="audio-conferencing-policy-settings-for-toll-and-toll-free-numbers"></a>用于收费和免费号码的音频会议策略设置

## <a name="teams-audio-conferencing-policy"></a>Teams音频会议策略

使用音频会议策略管理音频会议收费和免费号码，以显示在组织内用户创建的会议邀请中。 可以使用两个自动创建的策略之一，也可以创建和分配自定义策略。 两个自动创建的策略是全局 (组织范围内的默认) 和 AllowTollFreeDialinFalse (分配给组织内所有未启用免费拨入号码) 的现有用户。 在Microsoft Teams管理中心或使用 [PowerShell](teams-powershell-overview.md) 管理音频会议策略。

- 无法再通过Teams管理中心或 PowerShell 为单个用户管理 AllowTollFreeDialin 的设置。 租户管理员只能通过新的音频会议策略管理此设置。
- 无法从Teams管理中心修改全局策略。

在租户中启用Teams音频会议策略时，租户中将提供两个自动创建的策略。 两个自动创建的策略及其默认设置为：

### <a name="global-org-wide-default"></a>全局 (组织范围的默认) 

在此策略中， **AllowTollfreedialin** 的值将设置为 ON，并且策略中不会定义任何电话号码。 对于在启动时 **已将 AllowTollfreedialin** 设置为 **On** 的租户中的所有用户，这将是默认策略。
由于该策略未定义任何电话号码，因此当此策略的用户创建Teams会议时，其会议中提供的电话号码将与用户在策略之前的电话号码相同。 这些电话号码通常默认为用户的国家/地区，除非租户管理员更改了单个用户。

例如，如果基于德国的用户在启动音频会议策略之前分配了德国通行费和免费电话号码，则在启动时将为用户分配全局策略，并且他们在会议邀请中继续看到的电话号码将与应用策略之前相同 (也就是说， 德国通行费和免费号码) 。 启动策略时，最终用户不会看到任何更改。 但是，如果租户管理员修改了全局策略，并将特定电话号码包含到与之前不同的策略中，则策略的所有用户将只看到策略中所安排的任何会议中包含的电话号码。

> [!NOTE]
> 如果租户管理员不是修改全局策略，而是创建自定义策略并将其应用于用户，则自定义策略中定义的设置将是最终用户在其会议邀请中看到的设置。

例如，如果自定义策略具有“AllowTollFreeDialinFalse”且未定义电话号码，则此策略的用户将无法拥有免费电话号码，并且由于策略中未定义电话号码，因此将在此类用户创建的会议邀请中使用的收费电话号码将与用户在策略之前的电话号码相同。 这些电话号码通常默认为用户的国家/地区，除非租户管理员更改了单个用户。

### <a name="allowtollfreedialinfalse"></a>AllowTollfreedialinFalse

在此策略中， **AllowTollfreedialin** 的值将设置为 **“关闭** ”，并且不会在策略中定义任何电话号码。 对于在启动时已将 **AllowTollfreedialin** 设置为 **Off** 的租户中的所有用户，此策略将是默认策略。

由于该策略未定义任何电话号码，因此当此策略的用户创建团队会议时，其会议中提供的电话号码将与用户在策略之前的电话号码相同。 这些电话号码通常默认为用户的国家/地区或位置，除非租户管理员更改了单个用户的电话号码。

例如，如果基于德国的用户在启动音频会议策略之前分配了德国收费电话号码，则在启动时将为用户分配“AllowTollfreedialinFalse”策略，并且他们在会议邀请中继续看到的电话号码将与 (之前相同， 德国通行费) 。 启动策略时，最终用户不会看到任何更改。 但是，如果租户管理员修改 **AllowTollfreedialinFalse** 策略并将特定电话号码包含到策略中，则所有策略用户只会看到策略中包含在他们安排的任何会议中的电话号码。

## <a name="create-a-custom-audio-conferencing-policy"></a>创建自定义音频会议策略

步骤概述：

1. 在Microsoft Teams管理中心的左侧导航中，转到会议>音频会议。
1. 选择“添加”。
1. 输入策略的名称和说明。 名称不能包含特殊字符或超过 64 个字符。
1. 选择想要的设置。
1. 选择“保存”。

例如，你可能有一组用户定期与来自多个国家/地区的参与者会面。 在我们的示例中，参与者来自加拿大、博茨瓦纳和新加坡，他们都希望通过拨打电话号码通过音频会议加入会议。 你可以创建名为“加拿大博茨瓦纳新加坡”的新自定义策略，并通过“ **添加电话号码** ”选项从这三个国家选择要包含在策略中的电话号码，并保存此策略。 然后，可以将此策略分配给所需的用户。

这可确保为加拿大、博茨瓦纳和新加坡选择的电话号码将包含在此策略的用户创建的会议邀请中。

### <a name="step-by-step-instructions-on-creating-a-custom-policy-based-on-the-example"></a>有关基于示例创建自定义策略的分步说明

1. 在Microsoft Teams管理中心的左侧导航中，转到 **MeetingsAudio** >  会议。
2. 选择“**添加**”。
3. 输入策略的名称和说明。 名称不能包含特殊字符或超过 64 个字符。
4. 选择是否在此策略的用户创建的会议中包含免费号码。 将此设置为 **“打开”** 可在此策略中添加免费电话号码。
5. 选择“添加电话号码”。
6. 屏幕右侧将打开一个窗格，其中包含“ **按位置搜索** ”框。
7. 输入加拿大，然后从结果中选择来自加拿大的电话号码。
8. 选择“**添加**”。
9. 重复步骤 6 和 7，以相同的方式搜索和添加来自博茨瓦纳和新加坡的电话号码。
10. 如果已启用在步骤 4 **中此策略的用户创建的会议中包含免费号码** 的设置，请选择免费号码。
11. 选择窗格右下角的 **“添加** ”。 你选择的三个国家的电话号码将列出。
12. 有一个排名列，用于确定此策略的用户在会议邀请中显示电话号码的顺序。 可以通过选择电话号码并分别使用 **“向上移动** ”和“下移”按钮向上或 **向下** 移动来更改订单。
13. 将电话号码按首选项顺序排列后，选择 **“保存**”。
14. 创建名为“加拿大博茨瓦纳新加坡”的自定义策略。
15. 创建完成后，可以将此策略分配给用户。

## <a name="edit-a-meeting-policy"></a>编辑会议策略

可以编辑创建的任何自定义策略。  (请注意，无法从Teams管理中心编辑全局策略) 

1. 在Microsoft Teams管理中心的左侧导航中，转到 **MeetingsAudio** >  会议。
1. 选择要编辑的策略，选择策略名称左侧，然后选择 **“编辑**”。
1. 进行编辑。
1. 选择“**保存**”。

> [!NOTE]
> 如果已将它分配给用户，则无法删除该策略。 需要为所有受影响的用户分配不同的策略，然后才能删除原始策略。

## <a name="assign-a-meeting-policy-to-users"></a>将会议策略分配给用户

> [!IMPORTANT]
> 向用户应用新的音频会议策略后，策略中定义的电话号码将仅在用户使用此策略创建的新会议中可用。 在策略之前安排的任何旧会议和定期会议将继续显示旧设置，例如，如果为该用户) 启用了免费收费，则 (一个收费和一个免费号码。 此处的一个方案可能是，用户启用了 **允许免费收费** ，并分配了免费号码，并且他们为将来创建了定期会议。 在此方案中，如果使用 AllowTollfreeDialIn 创建自定义策略并将其应用到此用户，则此用户创建的任何新会议将不包括免费号码，但旧会议和定期会议仍将显示免费号码。 因此，如果呼叫者拨打此免费号码加入会议，则呼叫将失败，因为由于该策略，此用户现在已禁用免费电话。 若要防止这种情况，可在为用户分配新的音频会议策略后迁移其旧会议。 请查看 [使用会议迁移服务 (彩信) ](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)。

如果策略类型) 支持，则可以将策略直接分配给用户或用户为 (成员的组，如果策略类型) 支持，则可通过批处理分配 (单独或以较大数量分配。

若要了解可向用户分配策略的不同方式，请参阅 [向用户和组分配策略](assign-policies-users-and-groups.md)。

> [!NOTE]
> 用户一次只能分配一个音频会议策略。

### <a name="known-issue"></a>已知问题

当你使用“**立即开会**”选项从Microsoft Teams >日历>会议母版开始会议时，如果然后选择省略号...菜单选项，然后会议信息，将有一个问题，在或调用下的部分的下半部分 **(音频只)**。 将显示策略中定义的所有电话号码，但号码的对齐使得读取变得困难。