---
title: Create Quality of Experience configuration settings in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: 摘要：了解 Skype for Business Server 中的用户体验 (QoE) 设置。
ms.openlocfilehash: 2f9c233b46588bd70566606f538451063802f5f3d35c4ffef59a8d0f7e6d85f9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305434"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>Create Quality of Experience configuration settings in Skype for Business Server
 
**摘要：** 了解 Skype for Business Server 中的用户体验 (QoE) 设置。
  
用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、“抖动”量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。
  
在安装Skype for Business Server时，会为用户创建一个 QoE 配置设置的全局集合。 管理员还可以选择在站点范围创建自定义设置。 每当使用这些站点范围的设置时，它们优先于全局设置。 例如，如果为 Redmond 站点创建站点作用域设置，则这些设置 (（而不是全局设置) ）将用于管理 Redmond 中的 QoE。
  
可以使用控制面板或[New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet Skype for Business Server QoE 配置设置。 如果要使用Skype for Business Server控制面板创建新设置，可以使用以下选项：
  
|**UI 设置**|**PowerShell 参数**|**说明**|
|:-----|:-----|:-----|
|名称  <br/> |标识  <br/> |要创建的设置的唯一标识符。 QoE 配置设置只能在站点范围创建。  <br/> |
|启用 QoE 数据的监视  <br/> |EnableQoE  <br/> |指定是否收集 QoE 记录并将其保存到监控数据库。  <br/> |
|启用 QoE 数据的清除  <br/> |EnablePurging  <br/> |指定在"保留 **QoE** 数据"中定义的最长持续时间（ (天数后，) 清除记录。 <br/> |
|QoE 数据最长保留期限为 (天)   <br/> |KeepQoEDataForDays  <br/> |从数据库中清除 QoE 数据之前存储的天数。 如果禁用清除，则忽略此值。  <br/> |
   
> [!NOTE]
> 此New-CsQoEConfiguration cmdlet 包括"控制面板"中Skype for Business Server选项。 有关详细信息，请参阅 [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) 帮助主题。
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用"控制面板"Skype for Business Server QoE 配置设置

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅 **Delegate Setup Permissions**。
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。  
    
3. 在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。
    
4. 在"**用户体验质量数据"页上**，单击"新建 **"。**
    
5. 在 **"选择站点"** 中，单击要应用策略的站点，然后单击"确定 **"。**
    
6. 在 **"全新用户体验质量设置"** 中，执行以下操作：
    
   - 选择 **"启用 QoE 数据的监控** "以启用监控。
    
   - 选择 **"启用 QoE 数据清除** "以启用清除。
    
   - 在 **"QoE 最长保留** (天) "中，选择 QoE 记录应保留的最大天数。
    
7. 单击“提交”。
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 设置 QoE 配置Windows PowerShell

可以使用 Windows PowerShell cmdlet 和 New-CsQoEConfiguration cmdlet 创建 QoE 配置设置。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程[PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在Skype for Business Server。
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>创建新的 QoE 配置设置集合

 此命令创建应用于 Redmond 站点的 QoE 配置设置的新集合：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>创建禁用 QoE 监控的新 QoE 配置设置集合

 由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。 要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如，要创建用户体验质量配置设置集合，默认情况下允许禁用 QoE 记录，请使用类似这样的命令：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>在创建新的 QoE 配置设置集合时指定多个属性值

 可以通过包含多个参数来多个属性值。 例如，此命令将新设置配置为将 QoE 数据保留 30 天，在上午 3：00 清除旧数据：
    
  ```PowerShell
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

有关详细信息，请参阅 [New-CsQoEConfiguration](/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet 的帮助主题。
