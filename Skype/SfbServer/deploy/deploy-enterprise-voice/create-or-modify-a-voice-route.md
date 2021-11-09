---
title: Create or modify a voice route in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: d189057d-cc9d-4622-9d10-f5385d703faf
description: 摘要：了解如何使用"Skype for Business Server控制面板"在 Skype for Business Server创建或修改语音路由。
ms.openlocfilehash: 28acf24352f2eb517f75a6afa5ce35a7d5166ab2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60831626"
---
# <a name="create-or-modify-a-voice-route-in-skype-for-business"></a>Create or modify a voice route in Skype for Business
 
**摘要：** 了解如何使用"控制面板"在 Skype for Business Server 创建Skype for Business Server语音路由。
  
### <a name="to-create-a-voice-route-by-using-the-skype-for-business-server-control-panel"></a>使用"控制面板"Skype for Business Server语音路由

1. 以 RTCUniversalServerAdmins 组成员或 **CsVoiceAdministrator**、**CsServerAdministrator** 或 **CsAdministrator** 管理角色成员的身份登录计算机。
    
2. 打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **“语音路由”**。
    
4. 单击“路由”。
    
5. 单击 **“新建”** 以显示 **“新建语音路由”** 对话框。
    
6. 在 **"名称**"中，键入语音路由的描述性名称。
    
7.  (可选) 在 **"** 说明"中，键入语音路由的其他描述性信息。
    
8. 若要指定希望此路由满足的模式，可以使用"生成匹配的模式"工具生成正则表达式，也可以手动编写正则表达式。
    
   - 要使用 **“建立匹配的模式”** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
    
   - **希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。 例如，键入 +425，然后单击"添加 **"。** 对希望包含在路由中的每个前缀值重复此过程。
    
   - **例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击 **“例外”**。 为不希望此路由适应的匹配模式  *键入一个或多个*  值。 例如，若要从路由中排除以 +425237 开始的数字，请在"例外"字段中输入+425237值，然后单击"确定 **"。**
    
   - 若要手动定义匹配模式，请在“构建要匹配的模式”工具中单击“编辑”，然后键入 .NET Framework 正则表达式，以便为应用路由的目标电话号码指定匹配模式。 若要详细了解如何编写正则表达式，请参阅[".NET Framework正则表达式"。](/dotnet/standard/base-types/regular-expressions) 
    
9. 如果不希望对呼叫接收人显示发起出站呼叫的电话的 ID，请选择 **“隐藏呼叫者 ID”**。 如果选择此选项，则必须指定将在收件人的呼叫者 **ID** 显示器上显示的备用呼叫者 ID。
    
10. 若要将一个或多个中继与语音路由关联，请单击"添加"，然后从列表中选择中继。
    
11. 若要将一个或多个公用电话交换网 (PSTN) 用法与语音路由关联，请单击"选择"，然后从为 企业语音 部署定义的 PSTN 用法记录列表中选择一条记录。
    
    > [!NOTE]
    > 若要查看每个可用的 PSTN 用法记录的属性，请参阅查看[PSTN 用法](view-pstn-usage-records.md)记录Skype for Business。 >创建或编辑 PSTN 用法记录，请参阅创建或修改语音策略和配置[PSTN 用法记录](voice-policy-and-pstn-usage-records.md)Skype for Business
  
12. 排列 PSTN 用法记录以获得最佳性能。 若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上箭头或向下箭头。
    
    > [!NOTE]
    > 与语音策略（其中 PSTN 用法记录的列出顺序非常重要）相反，PSTN 用法记录在语音路由中的列出顺序无关紧要。 但是，建议您按使用频率组织列表。 例如：RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。  (Skype for Business Server从上到下遍历列表。)  
  
13. （可选）在 **“输入转换后的号码以进行测试”** 字段中键入一个值，然后单击 **“执行”**。测试结果将显示在该字段下面。
    
14. 单击 **“确定”** 保存语音路由。
    
    > [!IMPORTANT]
    > 任何时候创建语音路由，都必须运行 **"全部提交** "命令以发布配置更改。 有关详细信息，请参阅在 Skype for Business 中[发布对语音路由配置的挂起Skype for Business。](voice-route-config-changes.md) 
  
### <a name="to-modify-a-voice-route"></a>修改语音路由

1. 打开Skype for Business Server控制面板"。
    
2. 在左侧导航栏中，单击“语音路由”，然后单击“路由”。
    
3. 在 **“路由”** 页上，使用以下任意一种方式修改语音路由：
    
   - 单击语音路由名称，再单击 **“编辑”**，然后单击 **“显示详细信息”**。
    
   - 单击语音路由名称，再单击 **“编辑”**、**“复制”**，然后单击 **“粘贴”**。单击刚创建的新语音路由副本，再单击 **“编辑”**，然后单击 **“显示详细信息”**。
    
4. 在 **“编辑语音路由”** 页上的 **“名称”** 字段中，为语音路由键入一个描述性名称。
    
5. （可选）在 **“说明”** 字段中，为语音路由键入其他描述性信息。
    
6. 要指定希望此路由满足的模式，可以使用 **“建立匹配的模式”** 工具生成正则表达式，或手动写入正则表达式。
    
   - 要使用 **“建立匹配的模式”** 工具生成正则表达式，请按如下所示输入值。可以指定两种匹配的模式类型：
    
   - **希望允许的号码起始数字**：输入此路由必须满足的前缀值（如有必要，包括前导 +）。例如，键入 +425，然后单击 **“添加”**。对希望包含在路由中的每个前缀值重复此过程。
    
   - **例外**：如果要为前缀值指定一个或多个例外，请突出显示相应的前缀并单击 **“例外”**。 为不希望此路由适应的匹配模式  *键入一个或多个*  值。 例如，若要从路由中排除以 +425237 开始的数字，请在"例外"字段中输入+425237值，然后单击"确定 **"。**
    
   - 若要手动定义匹配模式，请单击"生成匹配的模式"工具中的"编辑"，然后键入 .NET Framework 正则表达式以指定应用路由的目标电话号码的匹配模式。若要详细了解如何编写正则表达式，请参阅[".NET Framework正则表达式"。](/dotnet/standard/base-types/regular-expressions) 
    
7. 如果您 **不希望** 向呼叫接收人显示发起出站呼叫的电话的 ID，请选择"隐藏呼叫者 ID"。 如果选择此选项，则必须指定将在收件人的呼叫者 **ID** 显示器上显示的备用呼叫者 ID。
    
8. 若要将 PSTN (PSTN) 一个或多个公用电话交换网与语音路由关联，请单击"添加"，然后从列表中选择中继。
    
9. 若要将一个或多个 PSTN 用法与语音路由关联，请单击"选择"，然后从为部署定义的 PSTN 用法记录列表中选择企业语音记录。
    
    > [!NOTE]
    > 若要查看每个可用的 PSTN 用法记录的属性，请参阅查看[PSTN 用法](view-pstn-usage-records.md)记录Skype for Business。 >若要创建或编辑 PSTN 用法记录，请参阅创建或修改语音策略和配置[PSTN 用法记录Skype for Business。](voice-policy-and-pstn-usage-records.md) 
  
10. 排列 PSTN 用法记录以获得最佳性能。 若要更改记录在列表中的位置，请突出显示记录名称，然后单击向上箭头或向下箭头。
    
    > [!NOTE]
    > 与 PSTN 用法记录的列出顺序很重要的语音策略相反，语音路由中 PSTN 用法记录的顺序无关紧要。 但是，建议您按使用频率组织该列表，例如：RedmondLocal、RedmondLongDist、RedmondInternational、RedmondBackup。  (Skype for Business Server从上到下遍历列表。)  
  
11. （可选）在 **“输入转换后的号码以进行测试”** 字段中键入一个值，然后单击 **“执行”**。测试结果将显示在该字段下面。
    
12. 单击 **“确定”**。
    
13. 在 **“路由”** 页上，单击 **“提交”**，然后单击 **“全部提交”**。 
    
    > [!NOTE]
    > 任何时候创建或修改语音路由，都必须运行 **"全部提交** "命令以发布配置更改。 有关详细信息，请参阅操作[文档中的](voice-route-config-changes.md)Publish pending changes to the voice routing configuration in Skype for Business in the Operations documentation。
  
## <a name="see-also"></a>另请参阅

[查看 PSTN 用法记录Skype for Business](view-pstn-usage-records.md)
  
[创建或修改语音策略，并配置 PSTN 用法Skype for Business](voice-policy-and-pstn-usage-records.md)
  
[在语音路由配置中发布待处理Skype for Business](voice-route-config-changes.md)