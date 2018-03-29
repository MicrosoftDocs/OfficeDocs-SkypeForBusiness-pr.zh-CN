---
title: 在 Skype for Business 2015 中创建或修改语音路由
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 摘要： 了解如何创建或修改业务服务器 2015年在 Skype 语音路由通过 Skype 业务服务器的控制面板。
ms.openlocfilehash: 2adc4d2a1277f229c1fcfbf230a49d5e91855a97
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business-2015"></a>在 Skype for Business 2015 中创建或修改语音路由
 
**摘要：**了解如何创建或修改业务服务器 2015年在 Skype 语音路由通过 Skype 业务服务器的控制面板。
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>若要创建语音路由通过 Skype 业务服务器的控制面板

1. 以 RTCUniversalServerAdmins 组成员或者 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开 Skype 业务服务器的控制面板。
    
3. 在左侧导航栏中，单击“语音路由”****。
    
4. 单击“路由”****。
    
5. 单击“新建”****以显示“新建语音路由”****对话框。
    
6. 在“名称”****中，键入语音路由的描述性名称。
    
7. （可选）在“说明”****中，为语音路由键入其他描述性信息。
    
8. 要指定希望此路由满足的模式，可以使用“建立匹配的模式”****工具生成正则表达式，或手动写入正则表达式。
    
   - 要使用“建立匹配的模式”****工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
    
   - **希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。 例如，键入 +425，并单击**添加**。 对希望包含在路由中的每个前缀值重复此过程。
    
   - **例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击“例外”****。 匹配模式，您在一个或多个值类型执行的操作*不*需要该路由来适应。 例如，若要排除编号从工艺路线从 +425237 开始，在**例外**字段中，输入值为 + 425237，然后单击**确定**。
    
   - 若要手动定义匹配模式，请在“构建要匹配的模式”****工具中单击“编辑” ****，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。 有关如何编写正则表达式的详细信息，请参见[".NET Framework 正则表达式"](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
9. 如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”****。 如果您选择此选项，必须指定将出现在收件人的呼叫方 ID 显示**备用的呼叫方 ID** 。
    
10. 要将一个或多个中继与语音路由相关联，请单击“添加”****，然后从列表中选择中继。
    
11. 要将一个或多个公用电话交换网 (PSTN) 用法记录与语音路由相关联，请单击“**选择**”，然后从已为企业语音部署定义的 PSTN 用法记录列表中选择一条记录。
    
    > [!NOTE]
    > 若要查看每个可用的 PSTN 使用记录的属性，请参阅[视图 PSTN 使用 Skype 业务 2015年的记录](view-pstn-usage-records.md)。 > 为创建或编辑 PSTN 使用记录，请参阅[创建或修改语音策略和业务 2015年的 Skype 在配置 PSTN 使用记录](voice-policy-and-pstn-usage-records.md)
  
12. 排列 PSTN 用法记录以获得最佳性能。 要更改列表中的记录的位置，请突出显示的记录的名称并单击向上或向下箭头。
    
    > [!NOTE]
    > 在语音策略中，PSTN 用法记录的列出顺序非常重要，而在语音路由中，PSTN 用法记录的列出顺序则无关紧要。 但是，建议您按使用频率来组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational 和 RedmondBackup。 例如： RedmondLocal、 RedmondLongDist、 RedmondInternational、 RedmondBackup。 （Skype 业务服务器遍历该列表从顶部向下。） 
  
13. （可选）在“输入转换后的号码以进行测试”****字段中键入一个值，然后单击“执行”****。测试结果将显示在该字段下面。
    
14. 单击“确定”****保存语音路由。
    
    > [!IMPORTANT]
    > 任何时候创建语音路由，都必须运行“全部提交”****命令以发布配置更改。 有关详细信息，请参阅[发布挂起更改的业务 2015年的 Skype 语音路由配置](voice-route-config-changes.md)。 
  
### <a name="to-modify-a-voice-route"></a>修改语音路由

1. 打开 Skype 业务服务器的控制面板。
    
2. 在左侧导航栏中，单击“语音路由”****，然后单击“路由”****。
    
3. 在“路由”****页上，使用以下任意一种方式修改语音路由：
    
   - 单击语音路由名称，再单击“编辑”****，然后单击“显示详细信息”****。
    
   - 单击语音路由名称，再单击“编辑”****、“复制”****，然后单击“粘贴”****。单击刚创建的新语音路由副本，再单击“编辑”****，然后单击“显示详细信息”****。
    
4. 在“编辑语音路由”****页上的“名称”****字段中，为语音路由键入一个描述性名称。
    
5. （可选）在“说明”****字段中，为语音路由键入其他描述性信息。
    
6. 要指定希望此路由满足的模式，可以使用“建立匹配的模式”****工具生成正则表达式，或手动写入正则表达式。
    
   - 要使用“建立匹配的模式”****工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
    
   - **希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。 例如，键入 +425，然后单击**添加**。 对希望包含在路由中的每个前缀值重复此过程。
    
   - **例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击“例外”****。 匹配模式，您在一个或多个值类型执行的操作*不*需要该路由来适应。 例如，若要排除编号从工艺路线从 +425237 开始，在**例外**字段中，输入值为 + 425237，然后单击**确定**。
    
   - 若要手动定义匹配的模式，**要匹配的模式生成**工具中单击**编辑**，然后键入.NET Framework 正则表达式中指定目标电话号码路由应用于的匹配模式。有关如何编写正则表达式的详细信息，请参见[".NET Framework 正则表达式"](https://go.microsoft.com/fwlink/p/?linkId=140927)。 
    
7. 如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择“隐藏呼叫者 ID”****。 如果您选择此选项，必须指定将出现在收件人的呼叫方 ID 显示**备用的呼叫方 ID** 。
    
8. 要将一个或多个公用电话交换网 (PSTN) 中继与语音路由相关联，请单击“添加”****，然后从列表中选择中继。
    
9. 要将一个或多个 PSTN 用法关联与语音路由，单击**选择**并从 PSTN 使用记录企业语音部署已定义的列表中选择的记录。
    
    > [!NOTE]
    > 若要查看每个可用的 PSTN 使用记录的属性，请参阅[视图 PSTN 使用 Skype 业务 2015年的记录](view-pstn-usage-records.md)。 > 为创建或编辑 PSTN 使用记录，请参阅[创建或修改语音策略和配置 PSTN 使用情况记录在 Skype 业务 2015年的](voice-policy-and-pstn-usage-records.md)。 
  
10. 排列 PSTN 用法记录以获得最佳性能。 要更改列表中的记录的位置，请突出显示的记录的名称并单击向上或向下箭头。
    
    > [!NOTE]
    > 语音策略的 PSTN 使用记录中列出的顺序是十分重要的位置，与语音路由中的 PSTN 使用记录的顺序是无关紧要。 但是，我们建议，您组织列表的频繁使用，例如： RedmondLocal、 RedmondLongDist、 RedmondInternational、 RedmondBackup。 （Skype 业务服务器遍历该列表从顶部向下。） 
  
11. （可选）在“输入转换后的号码以进行测试”****字段中键入一个值，然后单击“执行”****。测试结果将显示在该字段下面。
    
12. 单击“**确定**”。
    
13. 在“路由”****页上，单击“提交”****，然后单击“全部提交”****。 
    
    > [!NOTE]
    > 每当创建或修改语音路由时，都必须运行“全部提交”****命令以发布配置更改。 有关详细信息，请参阅[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)操作文档。
  
## <a name="see-also"></a>另请参阅

#### 

[查看业务 2015年的 Skype 在 PSTN 使用记录](view-pstn-usage-records.md)
  
[创建或修改语音策略和业务 2015年的 Skype 在配置 PSTN 使用记录](voice-policy-and-pstn-usage-records.md)
  
[挂起更改的业务 2015年的 Skype 语音路由配置发布](voice-route-config-changes.md)

