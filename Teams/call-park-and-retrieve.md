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
description: 了解如何使用呼叫暂停和检索在呼叫中保持Microsoft Teams。
ms.openlocfilehash: ad35f5bdfa6cb60a842705c150f0f511ba45cb63
ms.sourcegitcommit: 31da77589ac82c43a89a9c53f2a2de5ab52f93c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2021
ms.locfileid: "60356500"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams 中的呼叫寄存和取回

呼叫暂停和检索是允许用户保留呼叫的一项功能。 当呼叫被停时，服务会生成一个唯一的代码用于调用检索。 然后，将呼叫停放在一起的用户或其他人可以将该代码与受支持的应用或设备一起用于检索呼叫。  (有关详细信息，请参阅[在](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)Teams 中Teams呼叫。) 

使用呼叫公园的一些常见方案包括：

- 接待员为在工厂中工作的人拨打了电话。 然后，接待员通过公用地址系统报出呼叫和代码号。 然后，呼叫的用户可以在工厂车间Teams电话，并输入代码以检索呼叫。
- 用户将呼叫放在移动设备上，因为设备电池电量不足。 然后，用户可以输入代码，从桌面电话Teams呼叫。
- 支持代表将客户呼叫发送给客户，并Teams渠道发送公告，让专家检索呼叫并帮助客户。 专家在客户端中Teams代码以检索调用

要停放和检索呼叫，用户必须是企业语音用户，并且必须包含在呼叫停放策略中。

> [!NOTE]
> 呼叫停放和检索仅在Teams[模式下可用](teams-and-skypeforbusiness-coexistence-and-interoperability.md)，在 IP 电话上不受Skype for Business支持。

## <a name="configure-call-park-and-retrieve"></a>配置呼叫停放和检索

只有管理员Teams才能配置呼叫停放和检索。 默认情况下，它处于禁用状态。 你可以为用户启用它，然后使用呼叫允许策略创建用户组。 将同一策略应用到一组用户时，他们可以在用户之间停放和检索调用。

默认情况下，呼叫取件号码的范围为 10-99。 还可以在 10-9999 之间创建自己的自定义范围。 对于实例 10，将呈现第一个已停放调用的范围 (的上车) 。 下一个已停接调用将呈现递增 1 的上车代码;即 11 等，直到范围的末尾呈现为取件代码。 之后，呈现的提货代码再次从范围的开始重新开始。 

可以将超时指定为在未选取已暂停呼叫时响铃之前要等待的秒数。 允许的范围为 120-1800 秒，默认值为 300 秒。

若要设置自定义公园范围和公园超时，请使用 Teams PowerShell 模块 2.6.0 或更高版本中提供的 new- 和 Set-CsTeamsCallParkPolicy cmdlet。  (管理中心中无法管理自定义公园范围和Teams更改。 请注意，Teams管理中心将继续显示默认值。) 

若要启用呼叫允许策略，请执行：

1. 在管理中心的左侧导航Microsoft Teams，转到 **"语音**  >  **呼叫""公园策略"。**
2. 在"**管理策略"选项卡** 上，单击"**添加"。**
3. 为策略命名，然后将"允许 **呼叫停放"切换** 为"**开"。**  (无法自定义呼叫取件范围和超时。) 

    ![呼叫公园策略设置的屏幕截图。](media/call-park-add-policy.png)

4. 选择“**保存**”。

可以通过在列表中选择策略并单击"编辑"来编辑 **策略**。

若要使策略正常工作，必须将其分配给用户。 可以 [单独向用户分配策略](assign-policies.md) 或将其分配到组。

将呼叫停放策略分配给组

1. 在"**呼叫公园策略"** 页上的"组 **策略分配**"选项卡上，单击"**添加组"。**
2. 搜索想要使用的组，然后单击"添加 **"。**
3. 选择与其他组作业相比的排位。
4. 在 **"选择策略**"下，选择要将该组分配到的策略。

    ![公园策略图像。](media/call-park-assign-policy-to-group.png)

5. 选择"**应用"。**

## <a name="related-topics"></a>相关主题

[将呼叫停放在Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[向 Teams 中的用户分配策略](assign-policies.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
