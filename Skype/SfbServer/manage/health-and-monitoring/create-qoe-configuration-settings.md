---
title: 在 Skype for Business 服务器中创建体验配置设置的质量
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
description: '摘要: 了解 Skype for Business 服务器中的体验质量 (QoE) 设置。'
ms.openlocfilehash: d87938fdab64f3a77b96f427363c846829081f44
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305806"
---
# <a name="create-quality-of-experience-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建体验配置设置的质量
 
**摘要:** 了解 Skype for Business 服务器中的体验质量 (QoE) 设置。
  
用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、"抖动"量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。
  
安装 Skype for Business 服务器时, 将为你创建一个 QoE 配置设置的单个全局集合。 管理员还具有创建站点作用域的自定义设置的选项。 使用这些站点作用域设置时，它们将优先于全局设置。 例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 QoE。
  
QoE 配置设置可使用 Skype for business 服务器控制面板或[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet 创建。 如果您使用的是 Skype for Business 服务器控制面板来创建新设置, 您将可以使用以下选项:
  
|**UI 设置**|**PowerShell 参数**|**说明**|
|:-----|:-----|:-----|
|名称  <br/> |Identity  <br/> |要创建的设置的唯一标识符。只能创建站点作用域的 QoE 配置设置。  <br/> |
|启用对 QoE 数据的监视  <br/> |EnableQoE  <br/> |指定是否收集 QoE 记录并将其保存到监控数据库。  <br/> |
|启用清除 QoE 数据功能  <br/> |EnablePurging  <br/> |指定经过在“**QoE 数据最长保留期限（天）**”中定义的持续时间后是否清除记录。 <br/> |
|QoE 数据最长保留期限(天)  <br/> |KeepQoEDataForDays  <br/> |从数据库清除 QoE 数据之前存储的天数。如果禁用清除，则忽略此值。  <br/> |
   
> [!NOTE]
> CsQoEConfiguration cmdlet 包括 Skype for Business Server 控制面板中不可用的其他选项。 有关详细信息, 请参阅[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps)帮助主题。
  
### <a name="to-create-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 "Skype for Business 服务器" 控制面板创建 QoE 配置设置

1. 以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。  
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。
    
4. 在“**用户体验质量数据**”页上，单击“**新建**”。
    
5. 在“**选择站点**”中，单击要应用此策略的站点，然后单击“**确定**”。
    
6. 在“**新建用户体验质量设置**”中，执行下列操作：
    
   - 选择“**启用对 QoE 数据的监视**”以启用监视。
    
   - 选择“**启用清除 QoE 数据功能**”以启用清除。
    
   - 在“**QoE 最长保留期限（天）**”中，选择应保留 QoE 记录的最长天数。
    
7. 单击“**提交**”。
    
## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 创建 QoE 配置设置

你可以使用 Windows PowerShell 和 CsQoEConfiguration cmdlet 创建 QoE 配置设置。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype for Business 服务器的详细信息, 请参阅博客文章["快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 在 Skype for Business 服务器中, 此过程是相同的。
  
### <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>创建新的 QoE 配置设置的集合

 以下命令将创建新的应用于 Redmond 站点的 QoE 配置设置的集合：
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>创建其中禁用 QoE 监视的 QoE 配置设置的新集合

 由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新的配置设置集合将对其所有属性使用默认值。若要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，若要创建用户体验质量配置设置的集合，默认情况下，允许禁用 QoE 记录使用与以下命令类似的命令：
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>创建新的 QoE 配置设置集合时指定多个属性值

 您可通过包含多个参数指定多个属性值。例如，此命令会将新设置配置为保留 QoE 数据 30 天并于上午 3:00 清除旧数据：
    
  ```
  New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3
  ```

有关详细信息, 请参阅[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csqoeconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

