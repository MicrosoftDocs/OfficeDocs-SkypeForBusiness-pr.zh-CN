---
title: 在 Skype for Business Server 中创建或修改呼叫者 ID 演示文稿的翻译规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: '摘要: 了解如何使用 Skype for Business 服务器控制面板配置呼叫方 ID。'
ms.openlocfilehash: ca35b3398732296f435196ffeb38d915472b303d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233765"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>在 Skype for Business Server 中创建或修改呼叫者 ID 演示文稿的翻译规则

**摘要:** 了解如何使用 Skype for Business 服务器控制面板配置呼叫方 ID。

使用 Skype for Business 服务器, 被呼叫方的电话号码 (即电话号码) 可以从164种格式转换为_中继对等_(即关联网关、专用分支交换 () 所需的本地拨号格式。PBX) 或 SIP 主干。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

Skype for Business 服务器还为你提供选项, 你还可以选择将呼叫方的电话号码 (即呼叫者呼叫的电话号码) 从 E-164 格式转换为主干对等所需的本地拨号格式。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板配置呼叫者 ID

1. 打开 "Skype for Business 服务器" 控制面板。

2. 在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。

3. 在“Trunk 配置”**** 页上，双击一个现有中继（例如，“全局”**** 中继）以显示“编辑 Trunk 配置”**** 对话框。

4. 配置呼叫者 ID 显示：

   - 若要从您的企业语音部署中可用的所有翻译规则列表中选择一个或多个规则, 请单击 "**选择**"。 在“主叫号码转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。

   - 要定义新的转换规则并将其与中继相关联，请单击“新建”****。 有关定义新规则的详细信息, 请参阅在部署文档中[定义翻译规则](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。有关详细信息，请参阅部署文档中的[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。有关详细信息，请参阅[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。

     > [!CAUTION]
     > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。


