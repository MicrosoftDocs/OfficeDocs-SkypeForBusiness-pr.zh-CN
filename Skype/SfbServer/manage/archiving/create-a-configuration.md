---
title: 在 Skype for Business Server 中创建存档配置
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 摘要：了解如何为 Skype for Business Server 创建存档配置。
ms.openlocfilehash: c5c8dde9a12d0599d962d8c7bcf402796022af7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817652"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a>在 Skype for Business Server 中创建存档配置

**摘要：** 了解如何为 Skype for Business Server 创建存档配置。
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a>使用控制面板配置存档选项

为特定站点或池配置存档选项： 
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 在“存档配置”页上，单击“新建”，然后执行下列操作之一： 
    
   - 若要创建站点存档配置，请单击"站点 **配置**"，然后在" **选择** 站点"中选择要配置为存档的站点。
    
   - 若要创建池存档配置，请单击"池配置"，然后在"选择池"中选择要配置为存档的池。
    
5. 在“新建存档设置”的“存档设置”下拉列表框中，执行下列操作之一：
    
   - 若要只为即时消息 (IM) 会话启用存档，请单击“存档 IM 会话”。
    
   - 若要为 IM 会话和 Web 会议启用存档，请单击“存档 IM 和 Web 会议会话”。
    
   - 若要禁用此配置的存档，请单击 **"禁用存档"。**
    
6. 另请在“新建存档设置”中，执行下列操作：
    
   - 要在存档不可用时阻止活动，请选中“存档失败时阻止即时消息 (IM) 或 Web 会议会话”复选框。
    
   - 若要使用Microsoft Exchange Server存储存档数据，请单击 Microsoft Exchange **集成** 复选框。
    
   - 若要启用数据清除，请选中“启用存档数据清除”复选框，然后执行下列操作之一：
    
     - 要指定在特定的天数之后清除，请单击“在最长期限(天)后清除导出的存档数据和存储的存档数据”，然后指定天数。
    
     - 要限制仅清除已导出的存档数据，请单击“仅清除导出的存档数据”。
    
7. 单击“提交”。
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a>使用配置存档选项Windows PowerShell

您还可以使用 **New-CsArchivingConfiguration** cmdlet 为特定站点或池配置存档选项。
  
以下命令为 Redmond 站点创建一个新的存档配置设置集合：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。 
  
要创建使用不同属性值的设置，只需包含相应的参数和参数值。 以下示例创建一个存档配置设置集合，这些设置默认情况下仅允许对即时消息会话进行存档：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为存档即时消息会话并阻止不可用的存档服务的即时消息：
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

有关详细信息，请参阅 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。
