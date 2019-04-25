---
title: 创建或修改转换规则的呼叫者 ID 演示文稿中 Skype 业务服务器
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 摘要： 了解如何使用适用于业务 Server Control Panel Skype 配置呼叫者 ID。
ms.openlocfilehash: cfd6af9d31d165bc18f45439cf8925b0e47055d5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223709"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a>创建或修改转换规则的呼叫者 ID 演示文稿中 Skype 业务服务器

**摘要：** 了解如何使用适用于业务 Server Control Panel Skype 配置呼叫者 ID。

与 Skype 的企业服务器，调用的方的电话号码 （即，调用的电话号码） 可以由 E.164 格式转换为_中继对等方_（即，关联的网关、 private branch exchange （所需的本地拨号格式PBX)，或 SIP 中继)。 为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。

Skype 业务服务器还提供选项还平移呼叫方的电话号码 （即，呼叫者呼叫的电话号码） 从 E.164 格式为本地拨号格式所需的中继对等方。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 配置呼叫者 ID

1. 打开 Skype 业务 Server Control Panel。

2. 在左侧导航栏中，单击“语音路由”****，然后单击“Trunk 配置”****。

3. 在“Trunk 配置”**** 页上，双击一个现有中继（例如，“全局”**** 中继）以显示“编辑 Trunk 配置”**** 对话框。

4. 配置呼叫者 ID 显示：

   - 若要从企业语音部署中可用的所有转换规则的列表中选择一个或多个规则，请单击**选择**。 在“主叫号码转换规则”**** 中，单击要与中继关联的规则，然后单击“确定”****。

   - 要定义新的转换规则并将其与中继相关联，请单击“新建”****。 有关定义新的规则的详细信息，请参阅部署文档中的[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 。

   - 要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”****。有关详细信息，请参阅部署文档中的[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”****，然后单击“粘贴”****。有关详细信息，请参阅[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。

   - 要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”****。

     > [!CAUTION]
     > 如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。


