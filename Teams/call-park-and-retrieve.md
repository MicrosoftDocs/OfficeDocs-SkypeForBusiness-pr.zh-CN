---
title: Microsoft Teams 中的呼叫寄存和取回
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: srividhc
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 了解如何使用呼叫寄存和检索在 Microsoft Teams 中暂停呼叫。
ms.openlocfilehash: c541f92b265d5794df4513eb0cda5d2ff2969f20
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2022
ms.locfileid: "68614235"
---
# <a name="configure-call-park-and-retrieve"></a>配置呼叫寄存和检索

通过呼叫寄存和检索，用户可以暂停呼叫。 停靠呼叫时，服务会生成用于检索呼叫的唯一代码。 然后，寄存呼叫的用户或其他人可以将该代码与受支持的应用或设备配合使用，以检索呼叫。  (有关详细信息，请参阅 Teams.) [中的寄存呼叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

使用呼叫寄存的一些常见方案包括：

- 接待员给在工厂工作的人打电话。 接待员随后通过公共地址系统宣布呼叫和代码号。 然后，呼叫所在的用户可以在工厂车间拿起 Teams 电话并输入用于检索呼叫的代码。

- 用户在移动设备上停用呼叫，因为设备电池耗尽。 然后，用户可以输入代码以从 Teams 桌面电话中检索呼叫。

- 支持代表将客户呼叫停靠，并在 Teams 频道上发送公告，让专家检索呼叫并帮助客户。 专家在 Teams 客户端中输入代码以检索调用。

若要寄存和检索呼叫，用户必须是企业语音用户，并且必须包含在呼叫寄存策略中。

默认情况下，呼叫取件号码的范围为 10-99。 还可以在 10-9999 之间创建自己的自定义范围。 第一个寄存呼叫将呈现范围 (的起始代码（例如 10) ）。 下一个寄存呼叫将呈现一个以 1 递增的取件代码;即 11 等，直到范围的末尾呈现为皮卡代码。 之后，呈现的取件代码再次从范围的开头重新开始。 

可以将超时指定为等待的秒数，然后在未接听已寄存的呼叫时回响。 允许的范围为 120-1800 秒，默认值为 300 秒。

若要配置呼叫寄存和检索，必须是 Teams 管理员。 默认情况下会禁用它。 可以使用呼叫寄存策略为用户启用它并创建用户组。 将相同的策略应用到一组用户时，他们可以将呼叫寄存并检索到它们之间。

> [!NOTE]
> 呼叫寄存和检索仅在 [Teams 部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md)下可用。 SKYPE FOR BUSINESS IP 电话不支持此功能。

可以使用 Teams 管理中心或 PowerShell 配置呼叫寄存和检索。

## <a name="use-teams-admin-center"></a>使用 Teams 管理中心

若要创建新的呼叫寄存策略实例，请执行以下操作：

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音** > **呼叫寄存策略**。

2. 在“ **管理策略** ”选项卡上，单击 **“添加**”。

3. 为策略命名，然后将 **“允许”呼叫寄** 存切换为 **“打开**”。

4. 根据需要更改范围和停放超时。

5. 选择“**保存**”。

可以通过在列表中选择策略并单击“ **编辑**”来编辑策略。

若要使策略正常工作，必须将其分配给用户。 可以 [将策略单独分配给用户](assign-policies-users-and-groups.md) ，也可以将其分配给组。

若要将呼叫寄存策略分配给组，请执行以下操作：

1. 在 **“呼叫寄存策略** ”页上的“ **组策略分配** ”选项卡上，单击 **“添加组**”。

2. 搜索要使用的组，然后单击 **“添加**”。

3. 选择与其他组分配相比的排名。

4. 在 **“选择策略**”下，选择要将此组分配到的策略。

5. 选择“**应用**”。

## <a name="use-powershell"></a>使用 PowerShell

若要使用 PowerShell 管理呼叫寄存和检索策略，请使用以下 Teams PowerShell 模块 cmdlet：

- [New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

- [Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

- [Get-CsTeamsCallParkPolicy](/powershell/module/skype/get-csteamscallparkpolicy)

- [Remove-CsTeamsCallParkPolicy](/powershell/module/skype/remove-csteamscallparkpolicy)

- [Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)

### <a name="examples"></a>示例

#### <a name="new-custom-call-park-policy"></a>新的自定义呼叫寄存策略

下面的示例创建一个自定义呼叫寄存策略，该策略生成从 500 到 1500 的取件号码，如果未接听寄存的呼叫，该策略将在 600 秒后回响帕克。

```powershell
PS C:\> New-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $true -PickupRangeStart 500 -PickupRangeEnd 1500 -ParkTimeoutSeconds 600
```

#### <a name="change-a-call-park-policy"></a>更改呼叫寄存策略

以下示例禁用呼叫寄存策略：

```powershell
PS C:\> Set-CsTeamsCallParkPolicy -Identity "SalesPolicy" -AllowCallPark $false
```

#### <a name="grant-a-call-park-policy-to-a-user"></a>向用户授予呼叫寄存策略

以下示例将呼叫寄存策略授予用户：

```powershell
PS C:\> Grant-CsTeamsCallParkPolicy -PolicyName "SalesPolicy" -Identity Ken.Myer@contoso.com
```

#### <a name="remove-a-call-park-policy"></a>删除呼叫寄存策略

以下示例删除呼叫寄存策略：

```powershell
PS C:\> Remove-CsTeamsCallParkPolicy -Identity "SalesPolicy"
```

## <a name="related-topics"></a>相关主题

[在 Teams 中寄存呼叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)

