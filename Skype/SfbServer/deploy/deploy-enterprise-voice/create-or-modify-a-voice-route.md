---
title: 创建或修改 Skype for Business 中的语音路由
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 摘要： 了解如何创建或修改业务服务器使用适用于业务 Server Control Panel Skype Skype 中的语音路由。
ms.openlocfilehash: d3265f3864e01391598b11ab5466c96f41a123ae
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886352"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>创建或修改 Skype for Business 中的语音路由
 
**摘要：** 了解如何创建或修改业务服务器使用适用于业务 Server Control Panel Skype Skype 中的语音路由。
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 创建语音路由

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 单击“路由”****。
    
5. 单击“新建”**** 以显示“新建语音路由”**** 对话框。
    
6. 在“名称”**** 中，键入语音路由的描述性名称。
    
7. （可选）在“说明”**** 中，为语音路由键入其他描述性信息。
    
8. 要指定希望此路由满足的模式，可以使用“建立匹配的模式”**** 工具生成正则表达式，或手动写入正则表达式。
    
   - 要使用“建立匹配的模式”**** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
    
   - **希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。 例如，键入 +425，，，然后单击**添加**。 对希望包含在路由中的每个前缀值重复此过程。
    
   - **例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击“例外”****。 键入一个或多个值的匹配模式，您*不*需要此路由来容纳不断。 例如，若要排除 +425237 路由从开头的号码，请在**例外**字段中，输入的值为 + 425237，然后单击**确定**。
    
   - 若要手动定义匹配模式，请在“构建要匹配的模式”**** 工具中单击“编辑” ****，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。 有关如何编写正则表达式的详细信息，请参阅[".NET Framework 正则表达式"](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
9. 如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”****。 如果选择此选项，您必须指定将显示在收件人的呼叫者 ID 显示**备用呼叫者 ID** 。
    
10. 要将一个或多个中继与语音路由相关联，请单击“添加”****，然后从列表中选择中继。
    
11. 要将一个或多个公用电话交换网 (PSTN) 用法记录与语音路由相关联，请单击“**选择**”，然后从已为企业语音部署定义的 PSTN 用法记录列表中选择一条记录。
    
    > [!NOTE]
    > 若要查看每个可用 PSTN 用法记录的属性，请参阅[查看 PSTN 用法记录中的业务的 Skype](view-pstn-usage-records.md)。 > 到创建或编辑 PSTN 用法记录，请参阅[创建或修改语音策略和配置 PSTN 用法记录中的业务的 Skype](voice-policy-and-pstn-usage-records.md)
  
12. 排列 PSTN 用法记录以获得最佳性能。 若要更改列表中的记录的位置，请突出显示相应的记录名称并单击向上或向下箭头。
    
    > [!NOTE]
    > 在语音策略中，PSTN 用法记录的列出顺序非常重要，而在语音路由中，PSTN 用法记录的列出顺序则无关紧要。 但是，建议您按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。 例如： RedmondLocal RedmondLongDist、 RedmondInternational、 RedmondBackup。 （业务服务器 Skype 遍历该列表从上向下。） 
  
13. （可选）在“输入转换后的号码以进行测试”**** 字段中键入一个值，然后单击“执行”****。测试结果将显示在该字段下面。
    
14. 单击“确定”**** 保存语音路由。
    
    > [!IMPORTANT]
    > 任何时候创建语音路由，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅[发布挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。 
  
### <a name="to-modify-a-voice-route"></a>修改语音路由

1. 打开 Skype 业务 Server Control Panel。
    
2. 在左侧导航栏中，单击“语音路由”****，然后单击“路由”****。
    
3. 在“路由”**** 页上，使用以下任意一种方式修改语音路由：
    
   - 单击语音路由名称，再单击“编辑”****，然后单击“显示详细信息”****。
    
   - 单击语音路由名称，再单击“编辑”****、“复制”****，然后单击“粘贴”****。单击刚创建的新语音路由副本，再单击“编辑”****，然后单击“显示详细信息”****。
    
4. 在“编辑语音路由”**** 页上的“名称”**** 字段中，为语音路由键入一个描述性名称。
    
5. （可选）在“说明”**** 字段中，为语音路由键入其他描述性信息。
    
6. 要指定希望此路由满足的模式，可以使用“建立匹配的模式”**** 工具生成正则表达式，或手动写入正则表达式。
    
   - 要使用“建立匹配的模式”**** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
    
   - **希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。 例如，键入 +425，然后单击**添加**。 对希望包含在路由中的每个前缀值重复此过程。
    
   - **例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击“例外”****。 键入一个或多个值的匹配模式，您*不*需要此路由来容纳不断。 例如，若要排除 +425237 路由从开头的号码，请在**例外**字段中，输入的值为 + 425237，然后单击**确定**。
    
   - 手动定义匹配模式，在**生成要匹配的模式**工具中单击**编辑**，然后键入.NET Framework 正则表达式指定向其应用此路由的目标电话号码的匹配模式中。有关如何编写正则表达式的详细信息，请参阅[".NET Framework 正则表达式"](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
7. 如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”****。 如果选择此选项，您必须指定将显示在收件人的呼叫者 ID 显示**备用呼叫者 ID** 。
    
8. 要将一个或多个公用电话交换网 (PSTN) 中继与语音路由相关联，请单击“添加”****，然后从列表中选择中继。
    
9. 若要将一个或多个 PSTN 用法与语音路由相关联，单击**选择**并从已定义为企业语音部署的 PSTN 用法记录的列表中选择一条记录。
    
    > [!NOTE]
    > 若要查看每个可用 PSTN 用法记录的属性，请参阅[查看 PSTN 用法记录中的业务的 Skype](view-pstn-usage-records.md)。 > 到创建或编辑 PSTN 用法记录，请参阅[创建或修改语音策略和配置 PSTN 用法记录中的业务的 Skype](voice-policy-and-pstn-usage-records.md)。 
  
10. 排列 PSTN 用法记录以获得最佳性能。 若要更改列表中的记录的位置，请突出显示相应的记录名称并单击向上或向下箭头。
    
    > [!NOTE]
    > 语音策略，其中的 PSTN 用法记录中列出的顺序很重要，与 PSTN 用法记录在语音路由的顺序无关紧要。 但是，我们建议您在列表的频率的使用，例如： RedmondLocal RedmondLongDist、 RedmondInternational、 RedmondBackup。 （业务服务器 Skype 遍历该列表从上向下。） 
  
11. （可选）在“输入转换后的号码以进行测试”**** 字段中键入一个值，然后单击“执行”****。测试结果将显示在该字段下面。
    
12. 单击“**确定**”。
    
13. 在“路由”**** 页上，单击“提交”****，然后单击“全部提交”****。 
    
    > [!NOTE]
    > 每当创建或修改语音路由时，都必须运行“全部提交”**** 命令以发布配置更改。 有关详细信息，请参阅操作文档中的[Publish 挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)。
  
## <a name="see-also"></a>另请参阅

[查看 PSTN 用法记录中的业务的 Skype](view-pstn-usage-records.md)
  
[创建或修改语音策略和配置 PSTN 用法记录中的业务的 Skype](voice-policy-and-pstn-usage-records.md)
  
[发布挂起的 Skype for Business 中的语音路由配置更改](voice-route-config-changes.md)

