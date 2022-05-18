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
description: 了解如何使用呼叫寄存和检索将呼叫置于Microsoft Teams中。
ms.openlocfilehash: a2a70515bbe263716fab8e2deded75e44d12fd6e
ms.sourcegitcommit: 3cb40132e36717dfbdc6dfe83e7ea319f3ec9347
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/18/2022
ms.locfileid: "65465443"
---
# <a name="call-park-and-retrieve-in-microsoft-teams"></a>Microsoft Teams 中的呼叫寄存和取回

呼叫寄存和检索是一项功能，允许用户保留呼叫。 停靠呼叫时，服务会生成用于检索呼叫的唯一代码。 然后，寄存呼叫的用户或其他人可以将该代码与受支持的应用或设备配合使用，以检索呼叫。  (请参阅[Teams中的寄存呼叫](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)，了解详细信息。) 

使用呼叫寄存的一些常见方案包括：

- 接待员给在工厂工作的人打电话。 接待员随后通过公共地址系统宣布呼叫和代码号。 然后，呼叫所在的用户可以在工厂车间拿起一个Teams电话，并输入代码来检索呼叫。
- 用户在移动设备上停用呼叫，因为设备电池耗尽。 然后，用户可以输入代码，从Teams桌面电话检索呼叫。
- 支持代表将客户呼叫停靠，并在Teams频道上发送公告，让专家检索呼叫并帮助客户。 专家在Teams客户端中输入代码以检索调用

若要寄存和检索呼叫，用户必须是企业语音用户，并且必须包含在呼叫寄存策略中。

> [!NOTE]
> 呼叫寄存和检索仅在[Teams部署模式](teams-and-skypeforbusiness-coexistence-and-interoperability.md)下可用，Skype for Business IP 电话不支持。

## <a name="configure-call-park-and-retrieve"></a>配置呼叫寄存和检索

必须是Teams管理员才能配置呼叫寄存和检索。 默认情况下会禁用它。 可以为用户启用它，并使用呼叫寄存策略创建用户组。 将相同的策略应用到一组用户时，他们可以将呼叫寄存并检索到它们之间。

默认情况下，呼叫取件号码的范围为 10-99。 还可以在 10-9999 之间创建自己的自定义范围。 第一个寄存呼叫将呈现范围 (的起始代码（例如 10) ）。 下一个寄存呼叫将呈现一个以 1 递增的取件代码;即 11 等，直到范围的末尾呈现为皮卡代码。 之后，呈现的取件代码再次从范围的开头重新开始。 

可以将超时指定为等待的秒数，然后在未接听已寄存的呼叫时回响。 允许的范围为 120-1800 秒，默认值为 300 秒。

若要启用呼叫寄存策略，请执行以下操作：

1. 在Microsoft Teams管理中心的左侧导航中，转到 **VoiceCall** >  **公园策略**。
2. 在“ **管理策略** ”选项卡上，单击 **“添加**”。
3. 为策略命名，然后将 **“允许”呼叫寄** 存切换为 **“打开**”。
4. 根据需要更改范围和停放超时。
5. 选择“**保存**”。

可以通过在列表中选择策略并单击“ **编辑**”来编辑策略。

若要使策略正常工作，必须将其分配给用户。 可以 [将策略单独分配给用户](assign-policies-users-and-groups.md) ，也可以将其分配给组。

将呼叫寄存策略分配给组

1. 在 **“呼叫寄存策略** ”页上的“ **组策略分配** ”选项卡上，单击 **“添加组**”。
2. 搜索要使用的组，然后单击 **“添加**”。
3. 选择与其他组分配相比的排名。
4. 在 **“选择策略**”下，选择要将此组分配到的策略。

    ![寄存策略映像。](media/call-park-assign-policy-to-group.png)

5. 选择 **“应用**”。

## <a name="related-topics"></a>相关主题

[将呼叫寄入Teams](https://support.office.com/article/park-a-call-in-teams-8538c063-d676-4e9a-8045-fc3b7299bb2f)

[向 Teams 中的用户分配策略](policy-assignment-overview.md)

[New-CsTeamsCallParkPolicy](/powershell/module/skype/new-csteamscallparkpolicy)

[Set-CsTeamsCallParkPolicy](/powershell/module/skype/set-csteamscallparkpolicy)

[Grant-CsTeamsCallParkPolicy](/powershell/module/skype/grant-csteamscallparkpolicy)
