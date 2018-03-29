---
title: 在 Skype for Business Server 2015 中创建或修改来电显示的转换规则
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 摘要： 了解如何通过在生成翻译规则工具中使用 Skype 业务服务器 2015年定义转换规则。
ms.openlocfilehash: aa433375ad4dfa2dcc0c141d36b6d51ae28647f1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建或修改来电显示的转换规则
 
**摘要：**了解如何定义转换规则生成一个转换规则的工具中使用 Skype 业务服务器 2015年。
  
如果您想要通过**转换规则生成**工具中输入的值集和启用 Skype 业务服务器控件面板为您生成相应的匹配模式和转换规则定义的转换规则，请执行以下步骤。 或者，可以手动编写正则表达式来定义匹配模式和转换规则。 有关详细信息，请参阅[创建或修改翻译规则手动](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx)。
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a>使用“构建转换规则”工具定义规则

1. 打开 Skype 业务服务器的控制面板。
    
2. 开始定义的转换规则，按照中的步骤[配置介质与干线绕过业务服务器 2015年的 Skype 在](configure-trunk-with-media-bypass.md)通过第 10 步，或[配置无介质干线绕过在 Skype 的业务服务器 2015年](configure-trunk-without-media-bypass.md)至步骤 9。
    
3. 在“新建转换规则”****或“编辑转换规则”****页上的“名称”****下，键入描述要转换的号码模式的名称。
    
4. （可选）**说明**，下键入示例美国国际长途的翻译规则，说明。
    
5. 在对话框的“构建转换规则”****部分的以下字段中输入值：
    
   - **起始数字**：（可选）指定要使模式与之匹配的号码的前导数字。 例如，输入 + 此字段以匹配中 E.164 编号格式 (其中开头 +)。
    
   - **长度**：指定匹配模式中的数字位数，并选择希望模式匹配的号码是必须具有此准确长度、至少具有此长度还是可以具有任何长度。 例如，输入 11 和 selectAt 至少在下拉列表中匹配的长度至少 11 位的数字。
    
   - **要删除的数字**：（可选）指定要删除的起始数字的位数。 例如，输入 1 以去除 + 从编号的开头。
    
   - **要添加的数字**：（可选）指定要附加到转换号码前面的数字。 如果您希望 011 应用规则时要预置为转换后的数字，例如，输入 011。
    
    这些字段中输入的值将反映在“要匹配的模式”****和“转换规则”****字段中。例如，如果指定前面示例中的值，则“要匹配的模式”****字段中生成的正则表达式为：
    
    ^\+(\d{9}\d+)$
    
    “转换规则”****字段指定转换号码格式的模式。该模式由两部分组成：
    
   - 表示匹配模式中小数位数的值 (例如，$1)
    
   - （可选）可以通过在“要添加的数字”****字段中输入来附加的值
    
    使用前面的示例值 011**翻译规则**字段中显示 $1。
    
    应用此转换规则后，+441235551010 将变为 011441235551010。
    
6. 单击“确定”****保存转换规则。
    
7. 单击“确定”****保存中继配置。
    
8. 在“Trunk 配置”****页上，单击“提交”****，然后单击“全部提交”****。 
    
   > [!NOTE]
   > 每当创建或修改转换规则时，都必须运行“全部提交”****命令以发布配置更改。 有关详细信息，请参阅[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)操作文档。
  
### <a name="to-define-a-translation-rule-manually"></a>手动定义转换规则

1. 打开 Skype 业务服务器的控制面板
    
2. 开始定义的转换规则，按照中的步骤[配置介质与干线绕过业务服务器 2015年的 Skype 在](configure-trunk-with-media-bypass.md)通过第 10 步，或[配置无介质干线绕过在 Skype 的业务服务器 2015年](configure-trunk-without-media-bypass.md)至步骤 9。
    
3. 在“新建转换规则”****或“编辑转换规则”****页上的“名称”****字段中，键入描述要转换的号码模式的名称。
    
4. （可选）在**说明**中，键入一个描述的翻译规则，例如美国国际长途拨号。
    
5. 单击“构建转换规则”****部分底部的“编辑”****。
    
6. 在“键入正则表达式”****中输入以下内容：
    
   - 在“匹配此模式”****中，指定将用于匹配要转换的号码的模式。
    
   - 在“转换规则”****中，指定转换号码格式的模式。
    
    例如，如果您输入 ^\+(以**匹配此模式**and011 \d{9}\d+)$ $1 在**翻译规则**，该规则将转换为 011441235551010 +441235551010。
    
7. 单击“确定”****保存转换规则。
    
8. 单击“确定”****保存中继配置。
    
9. 在“Trunk 配置”****页上，单击“提交”****，然后单击“全部提交”****。 
    
    > [!NOTE]
    > 每当创建或修改转换规则时，都必须运行“全部提交”****命令以发布配置更改。 有关详细信息，请参阅[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)操作文档。
  
## <a name="see-also"></a>另请参阅

#### 

[配置中继与媒体回避在 Skype 业务服务器 2015](configure-trunk-with-media-bypass.md)
  
[配置中继不跳过在 Skype 的媒体的业务服务器 2015](configure-trunk-without-media-bypass.md)
  
[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)
#### 

[为业务服务器 2015年部署 Skype 在媒体回避](deploy-media-bypass.md)

