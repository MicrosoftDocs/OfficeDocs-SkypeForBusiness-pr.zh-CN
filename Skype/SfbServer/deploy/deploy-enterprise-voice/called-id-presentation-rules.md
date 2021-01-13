---
title: 在 Skype for Business Server 中为被叫 ID 演示文稿创建或修改转换规则
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 摘要：了解如何使用 Skype for Business Server 中的"生成转换规则"工具定义转换规则。
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804192"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>在 Skype for Business Server 中为被叫 ID 演示文稿创建或修改转换规则

**摘要：** 了解如何使用 Skype for Business Server 中的"生成转换规则"工具定义转换规则。

如果要定义转换规则，请按照以下步骤操作：在"生成转换规则"工具中输入一组值，并启用 Skype for Business Server 控制面板来生成相应的匹配模式和转换规则。 或者，可以手动编写正则表达式来定义匹配模式和转换规则。 有关详细信息，请参阅[Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用“构建转换规则”工具定义规则

1. 打开 Skype for Business Server 控制面板。

2. 要开始定义转换规则，请按照步骤 10 中的步骤在 [Skype for Business Server](configure-trunk-with-media-bypass.md) 中配置具有媒体旁路的中继，或在 Skype for Business [Server](configure-trunk-without-media-bypass.md) 中通过步骤 9 配置没有媒体旁路的中继。

3. 在“新建转换规则”或“编辑转换规则”页上的“名称”下，键入描述要转换的号码模式的名称。

4.  (") "下的可选选项，键入转换规则的说明，例如美国国际长途拨号。

5. 在对话框的“构建转换规则”部分的以下字段中输入值：

   - **起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。 例如，在此字段输入 +，可与 E.164 格式（以 + 开头）的号码匹配。

   - **长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。 例如，在下拉列表中至少输入 11 和 selectAt，以匹配长度至少为 11 位数的号码。

   - **要删除的数字**：（可选）指定要删除的起始数字的位数。 例如，输入 1 可去除数字开头的 +。

   - **要添加的数字**：（可选）指定要附加到转换号码前面的数字。 例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 011。

     这些字段中输入的值将反映在“要匹配的模式”和“转换规则”字段中。例如，如果指定前面示例中的值，则“要匹配的模式”字段中生成的正则表达式为：

     ^\+ (\d {9} \d+) $

     “转换规则”字段指定转换号码格式的模式。 该模式由两部分组成：

   - 代表匹配模式中数字位数的值（例如，$1）

   - （可选）可以通过在“要添加的数字”字段中输入来附加的值

     使用前面的示例值，转换规则字段中将显示 011$1。 

     应用此转换规则后，+441235551010 将变为 011441235551010。

6. 单击“确定”保存转换规则。

7. 单击“确定”保存 Trunk 配置。

8. 在“Trunk 配置”页上，单击“提交”，然后单击“全部提交”。

   > [!NOTE]
   > 每当创建或修改转换规则时，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作文档中的"在 [Skype for Business 中](voice-route-config-changes.md) 发布对语音路由配置的挂起更改"。

### <a name="to-define-a-translation-rule-manually"></a>手动定义转换规则

1. 打开 Skype for Business Server 控制面板

2. 要开始定义转换规则，请按照步骤 10 中的步骤在 [Skype for Business Server](configure-trunk-with-media-bypass.md) 中配置具有媒体旁路的中继，或在 Skype for Business [Server](configure-trunk-without-media-bypass.md) 中通过步骤 9 配置没有媒体旁路的中继。

3. 在“新建转换规则”或“编辑转换规则”页上的“名称”字段中，键入描述要转换的号码模式的名称。

4.  (可选) 说明中，键入转换规则的说明，例如美国国际长途拨号。

5. 单击“构建转换规则”部分底部的“编辑”。

6. 在“键入正则表达式”中输入以下内容：

   - 在“匹配此模式”中，指定将用于匹配要转换的号码的模式。

   - 在“转换规则”中，指定转换号码格式的模式。

     例如，如果在"匹配此模式"中输入 ^ \+ {9} (\d \d+ ) $ ，在 **转换** 规则中输入 011$1，该规则将 +441235551010 转换为 011441235551010。

7. 单击“确定”保存转换规则。

8. 单击“确定”保存 Trunk 配置。

9. 在“Trunk 配置”页上，单击“提交”，然后单击“全部提交”。

    > [!NOTE]
    > 每当创建或修改转换规则时，都必须运行“全部提交”命令以发布配置更改。 有关详细信息，请参阅操作文档中的"在 [Skype for Business 中](voice-route-config-changes.md) 发布对语音路由配置的挂起更改"。

## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中配置带媒体旁路的中继](configure-trunk-with-media-bypass.md)

[在 Skype for Business Server 中配置无媒体旁路的中继](configure-trunk-without-media-bypass.md)

[在 Skype for Business 中发布对语音路由配置的挂起更改](voice-route-config-changes.md)

[在 Skype for Business Server 中部署媒体旁路](deploy-media-bypass.md)

