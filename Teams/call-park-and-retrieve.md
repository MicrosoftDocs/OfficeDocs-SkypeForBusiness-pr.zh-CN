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
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 了解如何使用呼叫驻留和检索在云中的团队服务中将呼叫置于保持状态。
ms.openlocfilehash: a9518705cd5edff3834be21732f78dd47352cd63
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938531"
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

若要寄存和检索呼叫，用户必须是企业语音用户，并且管理员必须向用户授予呼叫寄存策略。 有关许可模型的详细信息，请参阅[Microsoft 团队服务说明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。

## <a name="call-park-and-retrieve-feature-availability"></a>呼叫寄存和检索功能可用性

电话寄存和检索目前由以下客户和设备支持。 （在 "仅限团队" 模式下受支持，有或没有 PSTN 连接。）

| 功能 | 团队桌面版 | 团队 Mac 应用 | 团队 Web App （Edge） |团队移动 iOS/Android 应用程序 | 团队 IP 电话 | Skype for Business IP 电话 |
|------------|---------------|---------------|----------------------|-----------------------------|----------------|-----------------------------|
| 寄存 a 呼叫 | 必需 | 是  | 是  | 是  | 是 | 否 |
| 检索寄存的呼叫 | 必需 | 是  | 是  | 是  | 是 | 否 |
| Unretrieved 电话铃声返回 | 必需 | 是  | 是  | 是  | 是 | 否 |

## <a name="configure-call-park-and-retrieve"></a>配置通话寄存和检索

只有管理员才能配置呼叫寄存和检索，并且默认情况下禁用该功能。 你可以为用户启用它，并使用呼叫寄存策略创建用户组。 将同一策略应用到一组用户时，他们可以在其自身间停止和检索呼叫。 若要为用户配置呼叫寄存和创建呼叫寄存用户组，请按照下面的[分配呼叫寄存策略](#assign-a-call-park-policy)流程操作。

有关如何使用通话寄存和检索功能的信息，请参阅[在团队中寄存通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)。

### <a name="enable-a-call-park-policy"></a>启用呼叫寄存政策

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫驻留策略**"。
2. 选择 "**添加**"。
3. 为策略命名，然后将 "**允许呼叫寄存**" 切换为 **"开"**。
4. 选择 "**保存**"。

#### <a name="using-powershell"></a>使用 PowerShell

请参阅[新-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)。

### <a name="edit-a-call-park-policy"></a>编辑呼叫寄存政策

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫驻留策略**"。
2. 通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。
3. 切换**允许呼叫寄存**为**Off** "关 **" 或 "开"**。
4. 单击“**保存**”。

#### <a name="using-powershell"></a>使用 PowerShell

请参阅[设置-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)。 例如，若要更改默认设置，请运行以下操作：

  ```PowerShell
  Set-CsTeamsCallParkPolicy -Identity Global -AllowCallPark $true
  ```

### <a name="assign-a-call-park-policy"></a>分配呼叫寄存政策

[!INCLUDE [assign-policy](includes/assign-policy.md)]
 
另请参阅[授权 CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)。

## <a name="troubleshooting"></a>故障排除

如果用户看不到 "寄存" 或 "检索" 按钮： 

- 检查用户是否已启用 "呼叫寄存" 策略。 

如果用户尝试检索呼叫，但未成功，请检查以下事项：

- 验证用户使用的是团队客户端还是启用团队的设备/电话
- 分组-用户是呼叫驻留组的成员，它基于分配了寄存策略的相同团队调用。 
- 岛模式-通话寄存和检索在团队岛模式下不可用。
- 通话已被检索或终止。

## <a name="related-topics"></a>相关主题

[在团队中寄存 a 通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[向团队中的用户分配策略](assign-policies.md)
