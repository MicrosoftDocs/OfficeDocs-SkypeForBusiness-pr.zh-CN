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
description: 了解如何在 Microsoft Teams 中使用呼叫暂停和检索来暂停通话。
ms.openlocfilehash: 7474b80975c5fc78285a8bba5a90de782f24ba5b
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260324"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams 中的呼叫寄存和取回

呼叫暂停和检索是一项功能，允许用户保留呼叫。 当调用被停放时，服务会生成用于调用检索的唯一代码。 然后，将该代码用于受支持的应用或设备以检索呼叫的已停放用户或其他用户。  (有关详细信息，请参阅"在 [Teams 中叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f) 停通话"。) 

使用呼叫公园的一些常见方案包括：

- 接待员为在工厂中工作的人拨打了电话。 然后，接待员通过公用地址系统报出呼叫和代码号。 然后，呼叫方用户可以在工厂车间拿起 Teams 电话，并输入用于检索呼叫的代码。
- 由于设备电池电量不足，用户在移动设备上将呼叫放在了一个电话上。 然后，用户可以输入代码以从 Teams 桌面电话检索呼叫。
- 支持代表将客户呼叫组织到一起，在 Teams 频道上发送公告，让专家检索呼叫并帮助客户。 专家在 Teams 客户端中输入代码以检索呼叫

要停放和检索呼叫，用户必须是企业语音用户，并且必须包含在呼叫公园策略中。

> [!NOTE]
> 呼叫暂停和检索仅在 [Teams](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 部署模式下可用，在 Skype for Business IP 电话上不受支持。

## <a name="configure-call-park-and-retrieve"></a>配置呼叫停放和检索

你必须是 Teams 管理员才能配置呼叫公园和检索。 默认情况下，它处于禁用状态。 可以使用呼叫公园策略为用户启用它并创建用户组。 将同一策略应用到一组用户时，他们可以在用户之间停放和检索调用。

启用呼叫公园策略

1. 在 Microsoft Teams 管理中心的左侧导航中，转到 **语音**  >  **呼叫公园策略**。
2. 在"**管理策略"** 选项卡上，单击"**添加"。**
3. 为策略命名，然后将"允许呼叫 **停放"切换** 为 **"开"。**

    ![呼叫公园策略设置的屏幕截图](media/call-park-add-policy.png)

4. 选择 **"保存"。**

可以通过在列表中选择策略并单击"编辑"来编辑 **策略**。

若要使策略正常工作，必须将其分配给用户。 可以 [单独将策略分配给用户](assign-policies.md) 或将其分配到组。

将呼叫部分策略分配给组

1. 在"**呼叫公园策略"** 页上的"组 **策略分配**"选项卡上，单击"**添加组"。**
2. 搜索想要使用的组，然后单击"添加 **"。**
3. 选择与其他组分配相比的排位。
4. 在 **"选择策略**"下，选择要将该组分配到的策略。

    ![](media/call-park-assign-policy-to-group.png)

5. 单击“**应用**”。

## <a name="related-topics"></a>相关主题

[在 Teams 中将通话停放在](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[向 Teams 中的用户分配策略](assign-policies.md)

[New-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
