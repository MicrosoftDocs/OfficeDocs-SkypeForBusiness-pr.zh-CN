---
title: 创建或修改规范化规则Skype for Business
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 摘要：了解如何在规则中定义、创建和修改Skype for Business Server。
ms.openlocfilehash: 3e06aa9821761803c033255c4da3f636ba296dda
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626204"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>创建或修改规范化规则Skype for Business

**摘要：** 了解如何在规则中定义、创建和修改Skype for Business Server。

定义、创建和修改规则中的Skype for Business Server。

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>使用"建立规范化规则"定义规范化规则

1. 打开Skype for Business Server控制面板

2.  (可选) 按照在[Skype for Business Server](dial-plans.md)中创建或修改拨号计划中的步骤操作，或按照步骤 10 中的修改拨号计划中的[](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan)步骤操作。

3. 在 **"新建****规范化规则**"或"编辑规范化规则"中，键入描述正在规范化的号码模式 **的名称 (例如**，5DigitExtension) 。

4. （可选）在“描述”中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。

5. 在“建立规范化规则”的以下字段中输入值：

   - **起始 (** 可选) 指定希望模式匹配的拨打号码的前导数字。 例如，如果希望模式与以 425 开头的拨打号码匹配，请键入 425。

   - **长度** 指定匹配模式中的数字位数，然后选择是希望模式完全匹配此长度、匹配至少包含此长度的拨打号码，还是匹配任意长度的拨打号码。

   - **要删除的** (可选) 指定要从希望模式匹配的拨打号码中删除的起始位数。

   - **要添加的数字** (可选) 指定要添加到希望模式匹配的拨打号码的数字。

     这些字段中输入的值将反映在“要匹配的模式”和“转换规则”中。 例如，如果将"起始数字"留空，请在"长度"字段中键入 7 并选择"完全"，在"要删除的数字"中指定 0，则"要匹配的模式"中生成的 **正则表达式为：** 

     ^(\d{7})$

6. 在“转换规则”中，指定转换后的 E.164 电话号码格式的模式，如下所示：

   - 代表匹配模式中指定的号码位数的值。 例如，如果匹配模式为 ^ (\d) $ ，则转换规则中的 {7} $1 表示 7 位拨打的号码。

   -  (可选) 在"要添加的数字"字段中键入一个值，以指定要预置在转换号码之前的数字 (例如，+1425) 。

     例如，如果"要匹配的模式"包含^ (\d) $ 作为拨打号码的模式，而转换规则包含 {7} +1425$1 作为 E.164 电话号码的模式，则规则将 5550100 规范化为 +14255550100。 

7. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”。

8. （可选）输入一个号码以测试规范化规则，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。

    > [!NOTE]
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。有关详细信息，请参阅[Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing)。

9. 单击“确定”保存规范化规则。

10. 单击“确定”保存拨号计划。

11. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作[文档中](voice-route-config-changes.md)的 Publish pending changes to the voice routing configuration in Skype for Business in the Operations documentation。

### <a name="to-define-a-normalization-rule-manually"></a>手动定义规范化规则

1. 打开Skype for Business Server控制面板

2.  (可选) 按照创建[或修改](dial-plans.md)拨号计划中的步骤操作Skype for Business Server。

3. 在 **"新建** 规范化规则"或"编辑规范化规则"中，键入描述要规范化的号码模式 **的名称 (例如**，将规范化规则5DigitExtension) 。

4. （可选）在“说明”字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。

5. 在“建立规范化规则”中，单击“编辑”。

6. 在“键入正则表达式”中输入以下内容：

   - 在“匹配此模式”中，指定要用于匹配拨打的电话号码的模式。

   - 在“转换规则”中，指定转换后的 E.164 电话号码格式的模式。

     例如，如果在"匹配此模式"中输入 ^ (\d) $，在"转换规则"中输入 {7} +1425$1，则规则将 5550100 规范化为 +14255550100。  

7. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”。

8. （可选）输入一个号码以测试规范化规则，然后单击“执行”。测试结果会显示在“输入要测试的号码”下。

9. 单击“确定”保存规范化规则。

10. 单击“确定”保存拨号计划。

11. 在“拨号计划”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作[文档中](voice-route-config-changes.md)的 Publish pending changes to the voice routing configuration in Skype for Business in the Operations documentation。