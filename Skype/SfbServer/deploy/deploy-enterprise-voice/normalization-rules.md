---
title: 在 Skype for Business 中创建或修改规范化规则
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 摘要：了解如何在 Skype for Business 服务器中定义、创建和修改规范化规则。
ms.openlocfilehash: c206bd20c02053f4e3775f32b1ba61000bb59a63
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767085"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a>在 Skype for Business 中创建或修改规范化规则

**摘要：** 了解如何在 Skype for Business 服务器中定义、创建和修改规范化规则。

在 Skype for Business 服务器中定义、创建和修改规范化规则。

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a>使用“建立规范化规则”定义规范化规则

1. 打开 "Skype for Business 服务器" 控制面板

2. 可选按照在 " [Skype For Business 服务器" 中的步骤11创建或修改拨号计划](dial-plans.md)中的步骤操作，或通过步骤 10[修改拨号计划](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx)。

3. 在**新的规范化规则**或**编辑规范化规则**中，键入用于描述在**名称**中正常化的数字模式的名称（例如，5DigitExtension）。

4. （可选）在“描述”**** 中，键入规范化规则的描述（例如，“Translates 5-digit extensions”）。

5. 在“建立规范化规则”**** 的以下字段中输入值：

   - **起始数字**（可选）指定你希望模式匹配的已拨号码的前导数字。 例如，如果你希望模式匹配以425开头的拨号码，type425。

   - **长度**在匹配模式中指定数字的位数，并选择是希望模式完全匹配此长度、匹配至少具有此长度的电话号码，还是匹配任何长度的已拨打号码。

   - **要删除的数字**（可选）指定要从所需模式匹配的已拨号码的起始位数。

   - **要添加的数字**（可选）指定要为模式匹配的已拨号码的数字。

     这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 中。 例如，如果将开始的**数字**保留为空，type7 到 "**长度**" 字段中并选择 "**完全**"，并指定**要删除的数字**0，则**要匹配的模式**中的结果正则表达式如下所示：

     ^ （\d{7}） $

6. 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式，如下所示：

   - 代表匹配模式中指定的号码位数的值。 例如，如果匹配模式为 ^ （\d{7}） $，则转换规则中的 $ 1 表示7位拨号码。

   - 可选在 "**要添加的数字**" 中键入值以指定要在已翻译数字前预置的数字（例如 + 1425）。

     例如，如果**要匹配的模式**包含 ^ （\d{7}） $ 作为拨号号码和**翻译规则**的模式，则将 + 1425 $ 1 用作 E. 164 电话号码的模式，规则将5550100标准化到 + 14255550100。

7. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。

8. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。

    > [!NOTE]
    > 您可以保存尚未通过测试的规范化规则，并在稍后对其进行重新配置。有关详细信息，请参阅 [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx)。

9. 单击“确定”**** 保存规范化规则。

10. 单击“确定”**** 保存拨号计划。

11. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。

    > [!NOTE]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。

### <a name="to-define-a-normalization-rule-manually"></a>手动定义规范化规则

1. 打开 "Skype for Business 服务器" 控制面板

2. 可选按照在[Skype For Business 服务器中创建或修改拨号计划](dial-plans.md)中的步骤进行操作。

3. 在 "**新建规范化规则**" 或 "**编辑规范化规则**" 中，键入描述要在**名称**中规范化的数字模式的名称（例如，将规范化 rule5DigitExtension 命名为 "名称"）。

4. （可选）在“说明”**** 字段中，键入规范化规则的说明（例如，“Translates 5-digit extensions”）。

5. 在“建立规范化规则”**** 中，单击“编辑”****。

6. 在“键入正则表达式”**** 中输入以下内容：

   - 在“匹配此模式”**** 中，指定要用于匹配拨打的电话号码的模式。

   - 在“转换规则”**** 中，指定转换后的 E.164 电话号码格式的模式。

     例如，如果你在**翻译规则**中输入{7}"^ （\d） $" 与**此模式**+ 1425 $ 1，则规则会将5550100规范化到 + 14255550100。

7. （可选）如果规范化规则所生成的电话号码为组织内部号码，则选择“内部分机号”****。

8. （可选）输入一个号码以测试规范化规则，然后单击“执行”****。测试结果会显示在“输入要测试的号码”**** 下。

9. 单击“确定”**** 保存规范化规则。

10. 单击“确定”**** 保存拨号计划。

11. 在“拨号计划”**** 页上，单击“提交”****，然后单击“全部提交”****。

    > [!NOTE]
    > 无论何时创建或更改规范化规则，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。


