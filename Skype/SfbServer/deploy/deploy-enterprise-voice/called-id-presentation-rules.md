---
title: 在 Skype for Business Server 中创建或修改呼叫 ID 演示文稿的翻译规则
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: '摘要: 了解如何使用 Skype for Business Server 中的 "构建翻译规则" 工具定义翻译规则。'
ms.openlocfilehash: 3c72e53044abe44660423bbd9bc1adbbeed2a3ed
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233782"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a>在 Skype for Business Server 中创建或修改呼叫 ID 演示文稿的翻译规则

**摘要:** 了解如何使用 Skype for Business Server 中的 "生成翻译规则" 工具定义翻译规则。

如果要定义翻译规则, 请执行以下步骤: 在 "**生成翻译规则**" 工具中输入一组值, 并启用 "Skype For Business 服务器" 控制面板为你生成相应的匹配模式和转换规则。 或者，可以手动编写正则表达式来定义匹配模式和转换规则。 有关详细信息，请参阅[Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用“构建转换规则”工具定义规则

1. 打开 "Skype for Business 服务器" 控制面板。

2. 若要开始定义翻译规则, 请按照在 Skype for business[服务器的 skype For Business 服务器中配置具有媒体旁路的主干](configure-trunk-with-media-bypass.md)中的步骤, 在 skype For business 服务器中通过步骤 9[配置一个干线而不使用媒体旁路](configure-trunk-without-media-bypass.md)。

3. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 下，键入描述要转换的号码模式的名称。

4. 可选在 "**说明**" 下, 键入翻译规则的描述, 例如 "美国国际长途拨号"。

5. 在对话框的“构建转换规则”**** 部分的以下字段中输入值：

   - **起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。 例如，在此字段输入 +，可与 E.164 格式（以 + 开头）的号码匹配。

   - **长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。 例如, 在下拉列表中最少输入11和 selectAt, 以匹配长度至少为11位的数字。

   - **要删除的数字**：（可选）指定要删除的起始数字的位数。 例如, 输入 "1" 将从号码的开头去掉 +。

   - **要添加的数字**：（可选）指定要附加到转换号码前面的数字。 例如，如果要在应用规则时将 011 附加到转换号码的前面，则输入 011。

     这些字段中输入的值将反映在“要匹配的模式”**** 和“转换规则”**** 字段中。例如，如果指定前面示例中的值，则“要匹配的模式”**** 字段中生成的正则表达式为：

     ^\+(\d{9}\d +) $

     “转换规则”**** 字段指定转换号码格式的模式。 该模式由两部分组成：

   - 代表匹配模式中数字位数的值（例如，$1）

   - （可选）可以通过在“要添加的数字”**** 字段中输入来附加的值

     使用前面的示例值, 011 $ 1 显示在 "**翻译规则**" 字段中。

     应用此转换规则后，+441235551010 将变为 011441235551010。

6. 单击“确定”**** 保存转换规则。

7. 单击“确定”**** 保存中继配置。

8. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。

   > [!NOTE]
   > 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。

### <a name="to-define-a-translation-rule-manually"></a>手动定义转换规则

1. 打开 "Skype for Business 服务器" 控制面板

2. 若要开始定义翻译规则, 请按照在 Skype for business[服务器的 skype For Business 服务器中配置具有媒体旁路的主干](configure-trunk-with-media-bypass.md)中的步骤, 在 skype For business 服务器中通过步骤 9[配置一个干线而不使用媒体旁路](configure-trunk-without-media-bypass.md)。

3. 在“新建转换规则”**** 或“编辑转换规则”**** 页上的“名称”**** 字段中，键入描述要转换的号码模式的名称。

4. 可选在 "**说明**" 中, 键入翻译规则的描述, 例如 "美国国际长途拨号"。

5. 单击“构建转换规则”**** 部分底部的“编辑”****。

6. 在“键入正则表达式”**** 中输入以下内容：

   - 在“匹配此模式”**** 中，指定将用于匹配要转换的号码的模式。

   - 在“转换规则”**** 中，指定转换号码格式的模式。

     例如, 如果在 "**翻译规则**" 中{9}输入 "^\+" (\D \d +) $ 以**匹配此模式**and011 $ 1, 则规则会将 + 441235551010 转换为011441235551010。

7. 单击“确定”**** 保存转换规则。

8. 单击“确定”**** 保存中继配置。

9. 在“Trunk 配置”**** 页上，单击“提交”****，然后单击“全部提交”****。

    > [!NOTE]
    > 每当创建或修改转换规则时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息, 请参阅操作文档中的[Skype For business 中的 "发布待处理的语音路由配置更改"](voice-route-config-changes.md) 。

## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中使用 "媒体绕过" 配置主干](configure-trunk-with-media-bypass.md)

[在 Skype for Business 服务器中配置不使用媒体的主干](configure-trunk-without-media-bypass.md)

[发布 Skype for Business 中的语音路由配置的待处理更改](voice-route-config-changes.md)

[在 Skype for Business 服务器中部署媒体旁路](deploy-media-bypass.md)

