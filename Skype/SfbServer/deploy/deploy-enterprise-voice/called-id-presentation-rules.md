---
title: 创建或修改转换规则的呼叫 ID 演示文稿中 Skype 业务服务器
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 摘要： 了解如何使用生成的转换规则工具中 Skype 业务服务器定义转换规则。
ms.openlocfilehash: 768538f861ec3c020b02fc9df4498350f9c13a4b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246793"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>创建或修改转换规则的呼叫 ID 演示文稿中 Skype 业务服务器

**摘要：** 了解如何使用生成的转换规则工具中 Skype 业务服务器定义转换规则。

如果您想要在**建立转换规则**工具中输入的一组值和启用业务 Server 控制面板为您生成的相应匹配模式和转换规则的 Skype 定义转换规则，请按照以下步骤。 或者，可以手动编写正则表达式来定义匹配模式和转换规则。 有关详细信息，请参阅[创建或修改转换规则手动](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用“构建转换规则”工具定义规则

1. 打开 Skype 业务 Server Control Panel。

2. 要开始定义转换规则，请按照中的步骤[配置与媒体中继绕过 Skype 业务服务器中](configure-trunk-with-media-bypass.md)通过 10 个步骤或[配置无媒体中继绕过中的业务服务器 Skype](configure-trunk-without-media-bypass.md)前 9 个步骤。

3. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 下，键入描述要转换的号码模式的名称。

4. （可选）在**说明**，键入转换规则，例如，美国国际长途拨号的说明。

5. 在对话框的“构建转换规则”**** 部分的以下字段中输入值：

   - **起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。例如，在此字段输入 +，可与 E.164 格式（以 + 开头）的号码匹配。

   - **长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。 例如，输入 11 和 selectAt 最匹配的长度至少 11 位数字的号码下拉列表中。

   - **要删除的数字**：（可选）指定要删除的起始数字的位数。 例如，输入 1 去掉 + 从编号的开头。

   - **要添加的数字**：（可选）指定要附加到转换号码前面的数字。例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 011。

    这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 字段中。例如，如果指定前面示例中的值，则“要匹配的模式”**** 字段中生成的正则表达式为：

    ^\+(\d{9}\d+)$

    “转换规则”**** 字段指定转换号码格式的模式。该模式由两部分组成：

   - 代表匹配模式中数字位数的值（例如，$1）

   - （可选）可以通过在“要添加的数字”**** 字段中输入来附加的值

    使用前面示例中的值，011$ 1 显示在**转换规则**字段。

    应用此转换规则后，+441235551010 将变为 011441235551010。

6. 单击“确定”**** 保存转换规则。

7. 单击“确定”**** 保存中继配置。

8. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。

   > [!NOTE]
   > 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。

### <a name="to-define-a-translation-rule-manually"></a>手动定义转换规则

1. 打开 Skype 业务 Server Control Panel

2. 要开始定义转换规则，请按照中的步骤[配置与媒体中继绕过 Skype 业务服务器中](configure-trunk-with-media-bypass.md)通过 10 个步骤或[配置无媒体中继绕过中的业务服务器 Skype](configure-trunk-without-media-bypass.md)前 9 个步骤。

3. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 字段中，键入描述要转换的号码模式的名称。

4. （可选）在**说明**框中，键入说明的转换规则，例如，美国国际长途拨号。

5. 单击“构建转换规则”**** 部分底部的“编辑”****。

6. 在“键入正则表达式”**** 中输入以下内容：

   - 在“匹配此模式”**** 中，指定将用于匹配要转换的号码的模式。

   - 在“转换规则”**** 中，指定转换号码格式的模式。

    例如，如果输入 ^\+(\d{9}中**匹配此模式**and011 \d+)$ $1，在**转换规则**，该规则会将 + 441235551010 转换为 011441235551010。

7. 单击“确定”**** 保存转换规则。

8. 单击“确定”**** 保存中继配置。

9. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。

    > [!NOTE]
    > 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。

## <a name="see-also"></a>另请参阅

[为业务 Server 使用 Skype 中的媒体旁路配置中继](configure-trunk-with-media-bypass.md)

[配置无媒体绕过中 Skype 业务服务器的中继](configure-trunk-without-media-bypass.md)

[发布挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)

[为业务服务器部署中 Skype 的媒体绕过](deploy-media-bypass.md)

