---
title: Microsoft Teams 中的呼叫寄存和取回
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.date: 04/12/2019
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
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callparkpolicies.overview
ms.custom:
- Phone System
description: 使用呼叫驻留和检索将呼叫置于云中的团队服务中的 "暂候" 状态。
ms.openlocfilehash: 9a6f5b6a51a0193625ecd2dab294c2cf454cb21f
ms.sourcegitcommit: 5a7e273a3636322052e4a48a5a75513cbf5abb84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "39209178"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams 中的呼叫寄存和取回

呼叫寄存和检索是允许用户在云中的团队服务中将呼叫置于保持状态的功能。 当通话暂停时，该服务将生成一个唯一的通话检索代码。 停用呼叫或其他人的用户可以使用该代码和受支持的应用或设备来检索呼叫。 

使用呼叫寄存的一些常见方案是： 

- 在工厂中工作的一位接待员公园通话。 然后，接待员通过公共地址系统宣布呼叫和代码编号。 通话的用户可以在工厂车间中选择一个团队电话，并输入代码以检索呼叫。
- 由于设备电池电量用完，用户在移动设备上公园通话。 然后，用户可以输入代码以从团队桌面电话检索呼叫。
- 支持代表负责客户呼叫，并在团队频道上发送公告以检索呼叫和帮助客户。 专家输入团队客户的代码以检索呼叫

> [!IMPORTANT]
> 此功能仅适用于 "仅限团队" 部署模式。 有关团队部署模式的详细信息，请参阅[了解 Microsoft 团队和 Skype For business 共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)

## <a name="license-required"></a>需要许可证

若要寄存和检索呼叫，用户必须是企业语音用户，并且管理员必须向用户授予呼叫寄存策略。 有关许可模型的详细信息，请参阅[Microsoft 团队的 Office 365 授权](office-365-licensing.md)。

## <a name="call-park-and-retrieve-feature-availability"></a>呼叫寄存和检索功能可用性

电话寄存和检索目前由以下客户和设备支持。 （在 "仅限团队" 模式下受支持，有或没有 PSTN 连接。）

| 能 | 团队桌面版 | 团队 Mac 应用 | 团队 Web App （Edge） |团队移动 iOS/Android 应用程序 | 团队 IP 电话 | Skype for Business IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 寄存 a 呼叫 | 是 | 是 | 是 | 是 | 即将提供| 否 |
| 检索寄存的呼叫 | 是 | 是 | 是 | 是 | 即将提供| 否 |
| Unretrieved 电话铃声返回 | 是 | 是 | 是 | 是 | 即将提供| 否 |

## <a name="configuring-call-park-and-retrieve"></a>配置呼叫驻留和检索

只有管理员才能配置呼叫寄存和检索，并且默认情况下禁用该功能。 你可以为用户启用它，并使用呼叫寄存策略创建用户组。 将同一策略应用到一组用户时，他们可以在其自身间停止和检索呼叫。 若要为用户配置呼叫寄存和创建呼叫寄存用户组，请按照下面的[分配呼叫寄存策略](#assign-a-call-park-policy)流程操作。

有关如何使用通话寄存和检索功能的信息，请参阅[在团队中寄存通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。

### <a name="enable-a-call-park-policy"></a>启用呼叫寄存政策

请按照以下步骤启用呼叫寄存策略：

1. 转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。
2. 选择 "**新建策略**"。
3. 为策略命名，然后将 "**允许呼叫寄存**" 切换为 **"开"**。
4. 选择 "**保存**"。

### <a name="assign-a-call-park-policy"></a>分配呼叫寄存政策

按照以下步骤将呼叫寄存策略分配给一个或多个用户：

1. 转到**Microsoft 团队管理中心** > **语音** > **呼叫寄存策略**。
2. 通过单击策略名称的左侧，选择策略。
3. 选择 "**管理用户**"。
4. 在 "**管理用户**" 窗格中，按 "显示名称" 或 "按用户名搜索用户"，选择名称，然后选择 "**添加**"。 对要添加的每个用户重复此步骤。
5. 完成添加用户后，请选择 "**保存**"。
 
### <a name="configure-call-park-and-retrieve-with-powershell"></a>配置与 PowerShell 的通话寄存和检索

使用[全新的 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 创建呼叫寄存策略。

使用[grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps) PowerShell cmdlet 授予呼叫寄存策略。

可以使用 "[设置-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps) " 更改默认设置，如下所示：

`Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true`


## <a name="troubleshooting"></a>疑难解答

如果用户看不到 "寄存" 或 "检索" 按钮： 

- 检查用户是否已启用 "呼叫寄存" 策略。 

如果用户尝试检索呼叫，但未成功，请检查以下事项：

- 验证用户使用的是团队客户端还是启用团队的设备/电话
- 分组-用户是呼叫驻留组的成员，它基于分配了寄存策略的相同团队调用。 
- 岛模式-通话寄存和检索在团队岛模式下不可用。
- 通话已被检索或终止。

## <a name="more-information"></a>更多信息

[在团队中寄存 a 通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。
