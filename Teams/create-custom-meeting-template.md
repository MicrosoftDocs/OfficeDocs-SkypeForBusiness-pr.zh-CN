---
title: 在 Microsoft Teams 中创建自定义会议模板
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ralphmaamari
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
description: 了解 Microsoft Teams 管理员如何创建自定义会议模板来设置或强制实施会议组织者设置，以提高会议安全性和合规性。
ms.openlocfilehash: ec9e836474032d5bb9fde0aed6c81a231788d1bf
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800267"
---
# <a name="create-a-custom-meeting-template-in-microsoft-teams"></a>在 Microsoft Teams 中创建自定义会议模板

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Microsoft Teams 自定义会议模板 (Teams 高级版功能) 允许你为会议组织者可用的许多会议设置指定值。 模板可以配置会议组织者可以更改的设置，也可以锁定设置，以便会议组织者无法更改这些设置。 有关自定义会议模板的详细信息，请参阅 [Microsoft Teams 中的自定义会议模板概述](custom-meeting-templates-overview.md)。

最多可以创建 50 个自定义模板。 有关如何管理可供用户使用的模板的信息，请参阅 [在 Microsoft Teams 中管理会议](manage-meeting-templates.md) 模板。

对于模板中的每个选项，可以定义以下内容：

- **默认值** - 这是在使用模板时应用于会议的值。
- **可见** - 这决定了会议组织者是否可以在会议选项中看到此设置。 
- **锁定状态** - 确定会议组织者是否可以更改模板设置的设置。 如果设置已锁定，则会议组织者无法对其进行更改。

创建自定义会议模板

1. 在 Teams 管理中心中，展开 **“会议”** 并选择“ **会议模板**”。
1. 选择 **“添加”**
1. 键入模板的名称和说明。
1. 选择要用于此模板的设置。  (有关每个设置的说明，请参阅以下部分。) 
1. 若要防止会议组织者更改设置，请选择设置，然后选择 **“锁定**”。
1. 若要防止会议组织者看到某个设置，请选择设置，然后选择“ **隐藏**”。
1. 选择“**保存**”。

创建模板后，用户最多可能需要 24 小时才能使用。

#### <a name="security"></a>安全性

|设置|说明|
|:------|:----------|
|敏感度标签|指定要用于会议的会议敏感度标签。 请注意，敏感度标签可能会覆盖模板中的某些设置。|
|谁可以绕过大厅？|指定谁可以绕过大厅并直接加入会议。|
|人员拨入可以绕过大厅|指定通过电话呼叫的人员是否可以绕过大厅直接加入会议。|
|呼叫者加入和离开时发出通知|指定你希望当通过电话呼叫加入或离开会议时播放声音。|
|启用会议端到端加密|指定是否希望会议使用端到端加密。 如果启用，录制和听录将不起作用。|
|对共享内容应用水印|指定是否在会议屏幕上共享的内容上覆盖水印。|
|对每个人的视频源应用水印|指定是否在会议中的与会者视频源上叠加水印。|

#### <a name="audio-and-video"></a>音频和视频

|设置|说明|
|:------|:----------|
|允许与会者使用麦克风|**打开** 时，与会者可以取消静音。|
|允许与会者使用摄像头|**打开** 时，与会者可以打开其相机。|

#### <a name="recording-and-transcription"></a>录制和听录

|设置|说明|
|:------|:----------|
|自动录制会议|当“ **会议** ”自动录制时。|
|谁可以录制会议？|指定会议是只能由组织者录制，还是由组织者和演示者录制。|

#### <a name="meeting-engagement"></a>会议参与

|设置|说明|
|:------|:----------|
|与会者可以聊天|指定会议聊天是否可用。 还可用于在会议前后阻止聊天。|
|与会者可以使用反应|指定与会者是否可以在会议中使用反应。 这必须为 **“打开** ”，才能使举手功能正常工作。|
|启用 Q&A|指定与会者是否可以在会议期间使用 Q&A 功能提问。|
|管理与会者看到的内容|**打开时**，会议组织者可以在其他会议参与者看到内容之前预览和批准在屏幕上共享的内容。|

## <a name="related-topics"></a>相关主题

[Microsoft Teams 中的自定义会议模板概述](custom-meeting-templates-overview.md)

[将 Teams 会议模板、敏感度标签和管理策略结合使用](meeting-templates-sensitivity-labels-policies.md)

[使用三层保护配置 Teams 会议](configure-meetings-three-tiers-protection.md)
