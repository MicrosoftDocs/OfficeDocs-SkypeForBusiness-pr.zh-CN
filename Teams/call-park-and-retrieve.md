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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Phone System
- ms.teamsadmincenter.callparkpolicies.overview
- seo-marvel-apr2020
description: 了解如何使用呼叫暂停和检索在呼叫中保持Microsoft Teams。
ms.openlocfilehash: e58cf8ead120cb7265665abecc0683ea9a96f559
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732541"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams 中的呼叫寄存和取回

呼叫暂停和检索是允许用户保留呼叫的一项功能。 当呼叫被停时，服务会生成一个唯一的代码用于调用检索。 然后，将呼叫停放在一起的用户或其他人可以将该代码与受支持的应用或设备一起用于检索呼叫。  (有关详细信息，请参阅在 Teams[中) ](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

使用呼叫公园的一些常见方案包括：

- 接待员为在工厂中工作的人拨打了电话。 然后，接待员通过公用地址系统报出呼叫和代码号。 然后，呼叫的用户可以在工厂车间Teams电话，并输入用于检索呼叫的代码。
- 用户将呼叫放在移动设备上，因为设备电池电量不足。 然后，用户可以输入代码，从桌面电话Teams呼叫。
- 支持代表将客户呼叫发送给客户，并Teams渠道发送公告，让专家检索呼叫并帮助客户。 专家在客户端中Teams代码以检索调用

要停放和检索呼叫，用户必须是企业语音用户，并且必须包含在呼叫停放策略中。

> [!NOTE]
> 呼叫停放和检索仅在仅Teams[模式下可用](teams-and-skypeforbusiness-coexistence-and-interoperability.md)，在 IP 电话上不受Skype for Business支持。

## <a name="configure-call-park-and-retrieve"></a>配置呼叫停放和检索

只有管理员Teams才能配置呼叫停放和检索。 默认情况下，它处于禁用状态。 你可以为用户启用它，然后使用呼叫允许策略创建用户组。 将同一策略应用到一组用户时，他们可以在用户之间停放和检索调用。

呼叫取件号码的范围预定义为 10-99，不能修改。 将呈现第一个已停呼叫的取件代码 10，下一个已停呼叫将呈现 11 的取件代码，等等。 直到 99 呈现为取件代码。 之后，呈现的提货代码从 10 重新开始。  如果存在超过 89 个活动的已停接调用，则呈现的取件代码将不断递增超过 99，这样，对于提货代码，第 90 个活动的已停接调用将呈现 100，则第 91 个活动的已停接调用将呈现一个取件代码 101。

启用呼叫公园策略

1. 在管理中心左侧导航Microsoft Teams，转到 **"语音**  >  **呼叫""公园策略"。**
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

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy?view=skype-ps)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy?view=skype-ps)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy?view=skype-ps)
