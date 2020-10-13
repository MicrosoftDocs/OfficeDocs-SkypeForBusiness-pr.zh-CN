---
title: Microsoft Teams 中的呼叫寄存和取回
ms.author: mikeplum
author: MikePlumleyMSFT
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 了解如何使用呼叫驻留和检索在 Microsoft 团队中将呼叫置于保持状态。
ms.openlocfilehash: e64d9dafec0f3a4b65abc532ecfa60583fe6da84
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424576"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams 中的呼叫寄存和取回

呼叫寄存和检索是允许用户将呼叫置于保持状态的功能。 当通话暂停时，该服务将生成一个唯一的通话检索代码。 停用呼叫的用户或其他人可以将该代码与受支持的应用或设备配合使用来检索呼叫。  (参阅有关详细信息，请参阅 [团队中的 "寄存 a 通话"](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 。 ) 

使用呼叫寄存的一些常见方案是：

- 在工厂中工作的一位接待员公园通话。 然后，接待员通过公共地址系统宣布呼叫和代码编号。 通话的用户可以在工厂车间中选择一个团队电话，并输入代码以检索呼叫。
- 由于设备电池电量用完，用户在移动设备上公园通话。 然后，用户可以输入代码以从团队桌面电话检索呼叫。
- 支持代表负责客户呼叫，并在团队频道上发送公告以检索呼叫和帮助客户。 专家输入团队客户的代码以检索呼叫

要寄存和检索呼叫，用户必须是企业语音用户，并且必须包含在呼叫寄存策略中。

> [!NOTE]
> 呼叫驻留和检索仅在 " [仅限团队" 部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 中可用，在 Skype FOR business IP 手机上不受支持。

## <a name="configure-call-park-and-retrieve"></a>配置通话寄存和检索

您必须是团队管理员才能配置通话寄存和检索。 默认情况下，它处于禁用状态。 你可以为用户启用它，并使用呼叫寄存策略创建用户组。 将同一策略应用到一组用户时，他们可以在其自身间停止和检索呼叫。

启用呼叫寄存策略

1. 在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **呼叫驻留策略**"。
2. 在 " **管理策略** " 选项卡上，单击 " **添加**"。
3. 为策略命名，然后将 " **允许呼叫寄存** " 切换为 **"开"**。

    ![呼叫寄存策略设置的屏幕截图](media/call-park-add-policy.png)

4. 选择 " **保存**"。

您可以通过在列表中选择该策略，然后单击 " **编辑**" 来对其进行编辑。

要使策略正常工作，必须将其分配给用户。 你可以 [单独向用户分配策略](assign-policies.md) ，也可以将策略分配给组。

向组分配呼叫部件策略

1. 在 " **呼叫驻留策略** " 页面上的 " **组策略分配** " 选项卡上，单击 " **添加组**"。
2. 搜索要使用的组，然后单击 " **添加**"。
3. 选择与其他组工作分配的排名。
4. 在 " **选择策略**" 下，选择要向其分配此组的策略。

    ![](media/call-park-assign-policy-to-group.png)

5. 单击“**应用**”。

## <a name="related-topics"></a>相关主题

[在团队中寄存 a 通话](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[向团队中的用户分配策略](assign-policies.md)

[新-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[授权-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)