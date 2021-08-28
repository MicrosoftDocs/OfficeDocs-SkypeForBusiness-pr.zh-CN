---
title: 创建或修改呼叫者 ID 演示文稿的转换规则Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 摘要：了解如何使用"控制面板"Skype for Business Server呼叫者 ID。
ms.openlocfilehash: 7accfe11c22a8b453ac767c80a0c9269fe638c45
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58605591"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>创建或修改呼叫者 ID 演示文稿的转换规则Skype for Business Server

**摘要：** 了解如何使用"控制面板"Skype for Business Server呼叫者 ID。

使用 Skype for Business Server，被叫方的电话号码 (即，称为) 的电话号码可以从 E.164 格式转换为中继对等方 _(（_ 即关联网关、专用交换机 (PBX) 或 SIP 中继) ）所需的本地拨号格式。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

Skype for Business Server 还为您提供了将呼叫者的电话号码 (即呼叫者从) 呼叫的电话号码从 E.164 格式转换为中继对等方所需的本地拨号格式的选项。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>使用控制面板配置呼叫Skype for Business Server ID

1. 打开Skype for Business Server控制面板"。

2. 在左侧导航栏中，单击“语音路由”，然后单击“Trunk 配置”。

3. 在“Trunk 配置”页上，双击一个现有中继（例如，“全局”中继）以显示“编辑 Trunk 配置”对话框。

4. 配置呼叫者 ID 显示：

   - 要从企业语音部署中提供的所有转换规则列表中选择一个或多个规则，请单击 **“选择”**。 在“主叫号码转换规则”中，单击要与中继关联的规则，然后单击“确定”。

   - 要定义新的转换规则并将其与中继相关联，请单击“新建”。 有关定义新规则的详细信息，请参阅部署文档中的[Defining Translation Rules。](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)

   - 要编辑已经与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”。有关详细信息，请参阅部署文档中的[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)。

   - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”，然后单击“粘贴”。有关详细信息，请参阅[Defining Translation Rules](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)。

   - 要从中继中删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”。

     > [!CAUTION]
     > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。