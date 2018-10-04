---
title: 创建或修改规范化规则中的业务的 Skype
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 摘要： 了解如何定义、 创建和修改企业服务器中 Skype 的规范化规则。
ms.openlocfilehash: ff43185da86693c230b6b238222e0fcd922a411c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375285"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>创建或修改规范化规则中的业务的 Skype

**摘要：** 了解如何定义、 创建和修改企业服务器中 Skype 的规范化规则。

定义、 创建和修改企业服务器中 Skype 的规范化规则。

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>使用“建立规范化规则”定义规范化规则

1. 打开 Skype 业务 Server Control Panel

2. （可选）请按照本文[创建或修改拨号计划中 Skype Business Server](dial-plans.md)通过步骤 11 或[修改拨号计划](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)前 10 个步骤。

3. 在**新的规范化规则**或**编辑规范化规则**中，键入描述要进行规范化**名称**(例如，5DigitExtension) 中的号码模式的名称。

4. （可选）在“描述”**** 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。

5. 在“建立规范化规则”**** 的以下字段中输入值：

   - **起始数字**（可选）指定您希望模式与之匹配已拨号码的前导位数字。 例如，type425 如果您想要匹配的模式拨打号码 425 开头的字符串。

   - **长度**匹配模式中指定的位数，选择您想要完全匹配此长度的模式、 匹配的拨打号码的至少此长度，或匹配的拨打号码的任何长度。

   - **要删除的数字**（可选）指定数量的起始数字要从已拨号码中删除您想要匹配的模式。

   - **要添加的数字**（可选）指定要添加到已拨号码您想要匹配的模式的数字。

     这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 中。 例如，如果**长度**字段保留为空，type7**起始数字**和选择**完全**，并指定**要删除的数字**0，在**要匹配模式**中生成的正则表达式是：

     ^(\d{7})$

6. 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式，如下所示：

   - 代表匹配模式中指定的号码位数的值。 例如，如果匹配模式 ^(\d{7})$ 然后 $1 转换规则代表 7 位数字表示已拨的号码。

   - （可选）键入**要添加的数字**字段来指定要附加到转换后的号码 （例如 + 1425年） 前面的数字值。

     例如，如果**模式与之匹配**包含 ^(\d{7}) 拨打号码中为的模式 $ 和**转换规则**包含 + 1425年$ 1 为模式的 E.164 电话号码，该规则会规范化为 + 14255550100 将 5550100。

7. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。

8. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。

    > [!NOTE]
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。 有关详细信息，请参阅[测试语音路由](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。

9. 单击“确定”**** 保存规范化规则。

10. 单击“确定”**** 保存拨号计划。

11. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。

    > [!NOTE]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。

### <a name="to-define-a-normalization-rule-manually"></a>手动定义规范化规则

1. 打开 Skype 业务 Server Control Panel

2. （可选）请按照本文[创建或修改拨号计划中 Skype Business Server](dial-plans.md)。

3. 在**新的规范化规则**或**编辑规范化规则**中，键入描述要进行规范化在**名称**（例如，名称规范化 rule5DigitExtension） 的号码模式的名称。

4. （可选）在“说明”**** 字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。

5. 在“建立规范化规则”**** 中，单击“编辑”****。

6. 在“键入正则表达式”**** 中输入以下内容：

   - 在“匹配此模式”**** 中，指定要用于匹配拨打的电话号码的模式。

   - 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式。

     例如，如果输入 ^(\d{7})$，在**匹配此模式**和 + 1425年$ 1，在**转换规则**，该规则会为 + 14255550100 将 5550100 规范化。

7. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。

8. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。

9. 单击“确定”**** 保存规范化规则。

10. 单击“确定”**** 保存拨号计划。

11. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。

    > [!NOTE]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。


