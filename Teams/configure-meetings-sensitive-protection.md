---
title: 为 Teams 会议配置敏感数据保护
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 了解如何使用模板和敏感度标签配置 Teams 会议以保护敏感信息。
ms.openlocfilehash: 3aae927f29464f3e5d8a9e695c170ded06d3dd1f
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800087"
---
# <a name="configure-teams-meetings-with-protection-for-sensitive-data"></a>为 Teams 会议配置敏感数据保护

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

对于 *敏感* 级别的保护，我们将限制谁可以绕过大厅，谁可以演示，谁可以录制。 如果组织需要，也可以限制其他操作。

下表描述了我们将限制敏感会议的操作以及这些设置的配置位置。

|功能|设置|位置|执行|
|:------|:------|:-------|:-------|
|允许与会者使用摄像头|**打开**|模板|否|
|允许与会者使用麦克风|**打开**|模板|否|
|对每个人的视频源应用水印|**禁用**|模板|否|
|对共享内容应用水印|**禁用**|模板|否|
|端到端加密|**禁用**|模板|否|
|管理与会者看到的内容|**打开**|模板|否|
|会议聊天|**打开**|模板|否|
|人员拨入可以绕过大厅|**禁用**|模板|是|
|阻止将聊天内容复制到剪贴板|**禁用**|标签|否|
|自动录制|**禁用**|模板|否|
|谁可以绕过大厅|**仅受邀者**|标签|是|
|谁可以演示|**组织中用户和来宾**|标签|是|
|谁可以录制|**组织者和共同组织者**|标签|是|

列为强制的设置由敏感度标签或会议模板强制实施。 会议组织者可以更改未强制执行的设置。

> [!Note]
> 敏感度标签和自定义会议模板中的会议设置需要Teams 高级版。

## <a name="presentation-options-for-sensitive-meetings"></a>敏感会议的演示选项

对于 *敏感* 级别的保护，我们将对可以演示的人员以及内容的共享方式强制实施特定设置。

通过启用 **“管理与会者可以看到的内容**”，我们确保会议组织者可以在共享内容进入屏幕之前对其进行审核。 在此示例中，我们使用模板默认启用此功能，但如果需要，也可以在模板中强制启用它。

通过在敏感度标签中设置 **谁可以向****我的组织中的人员和来宾** 演示，我们消除了匿名参与者在会议中演示的机会。 如果需要，可以进一步限制为 **仅组织者和共同组织者** 。  (我们将针对 *高度敏感的* 保护级别执行此操作。) 

我们还将使用敏感度标签将录制限制为组织者和共同组织者。

## <a name="lobby-options-for-sensitive-meetings"></a>敏感会议的大厅选项

我们将使用敏感度标签来防止除受邀与会者以外的任何人 (组织者直接邀请的人员，或者邀请) 转发到的人员绕过大厅。 这提供了额外的保护级别，让组织者兽医任何人在允许他们参加会议之前没有直接发送邀请。 可以通过选择“ **仅组织者和共同组织者**”来进一步限制此设置。  (我们将针对 *高度敏感的* 保护级别执行此操作。) 


## <a name="sensitivity-labels"></a>敏感度标签

对于敏感级别的保护，我们将使用可直接在会议中使用的敏感度标签或作为会议模板的一部分。 根据所选的配置，此标签还可用于对团队和单个文件进行分类。

如果你已在组织中部署敏感度标签，请考虑此标签如何适合你的整体标签策略。 如果需要，可以更改名称或设置以满足组织的需求。 如果已有用于敏感信息的标签，可以编辑标签并向其添加 Teams 会议。

创建敏感度标签
1. 打开[Microsoft Purview 合规门户](https://compliance.microsoft.com)。
1. 在 **“解决方案**”下，单击“ **信息保护**”。
1. 单击“ **创建标签**”。
1. 为标签命名。 建议 **使用“敏感”**，但如果已使用其他名称，则可以选择其他名称。
1. 添加显示名称和说明，然后单击“ **下一步**”。
1. 在 **“定义此标签的范围** ”页上，选择“ **项目** ”和“ **包括会议**”。  (请注意，如果要将此标签用于其他目的，可以选择其他选项。) 
1. 选择“ **下一步**”。
1. 继续选择要用于此标签的选项，然后在 **“Teams 会议和聊天设置”** 页上，选择以下值：
    1. 选择“ **控制谁可以绕过大厅”** ，并从下拉列表中选择“ **仅受邀人员** ”。
    1. 选择“**控制谁可以演示**”，并从下拉列表 **中选择“我的组织和来宾中的人员**”。
    1. 选择 **“谁可以录制** ”，然后从下拉列表中选择“ **组织者和共同组织者** ”。
    1. 配置组织所需的任何其他设置。
    <!--:::image type="content" source="media/teams-meeting-sensitivity-label-sensitive-small.png" alt-text="Screenshot of sensitivity label meeting settings." lightbox="media/teams-meeting-sensitivity-label-sensitive-large.png":::-->
1. 选择“ **下一步**”。
1. 使用要使用的任何其他设置完成向导，然后选择“ **创建标签**”，然后选择“ **完成**”。

创建标签后，需要将其发布到将使用该标签的用户。 为了进行敏感保护，我们将向所有用户提供标签。 在 **“信息保护**”页的“**标签策略**”选项卡上的“Microsoft Purview 合规门户中发布标签。 如果现有策略适用于所有用户，请将此标签添加到该策略。 如果需要创建新策略，请参阅 [通过创建标签策略发布敏感度标签](/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy)。

有关在会议中使用敏感度标签的其他信息，请参阅 [使用敏感度标签保护日历项、Teams 会议和聊天](/microsoft-365/compliance/sensitivity-labels-meetings)。

## <a name="meeting-templates"></a>会议模板

使用模板的优点是，可以创建多个模板，这些模板使用相同的敏感度标签来锁定不同的设置。 例如，如果你的一些敏感会议是与会者交互最少的演示文稿，则可以创建一个模板来关闭与会者视频甚至聊天，另一个模板将这些选项留给会议组织者。 这两个模板都将使用 *敏感* 标签。

在 *敏感* 保护级别，我们将使用 模板来防止通过电话拨入的人员绕过大厅。 如果某些类型的会议希望允许通过电话呼叫的人员绕过大厅，请考虑为这些会议使用具有相同标签的单独模板。

创建自定义会议模板

1. 在 Teams 管理中心中，展开 **“会议”** 并选择“ **会议模板**”。
1. 选择 **“添加”**
1. 键入模板的名称和说明。
1. 在 **“应用敏感度标签** ”部分中，选择上面创建的标签。
1. 选择“ **应用敏感度标签**”，然后选择“ **锁定**”。
1. 确保 **人员我的手机中的呼叫可以绕过大厅** 设置为 **“关闭**”，然后选择“**锁定**”。
1. 根据需要更改任何其他设置。
1. 若要防止会议组织者更改设置，请选择设置，然后选择 **“锁定**”。
1. 若要防止会议组织者看到某个设置，请选择设置，然后选择“ **隐藏**”。
1. 选择“**保存**”。

## <a name="related-topics"></a>相关主题

[使用三层保护配置 Teams 会议](configure-meetings-three-tiers-protection.md)

[Microsoft Teams 中的自定义会议模板概述](custom-meeting-templates-overview.md)

[将 Teams 会议模板、敏感度标签和管理策略用于敏感会议](meeting-templates-sensitivity-labels-policies.md)
