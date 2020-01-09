---
title: 在 Skype for Business 服务器中创建会议配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 摘要：了解如何在 Skype for Business Server 中创建会议配置设置。
ms.openlocfilehash: bcf32d3e250a3bc8b29d34e4c2fd56173dcfd5a6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991877"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建会议配置设置
 
**摘要：** 了解如何在 Skype for Business Server 中创建会议配置设置。
  
可以使用 Skype for Business Server 控制面板或使用 Skype for business Server 命令行管理器创建会议配置设置。
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板创建会议配置设置

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议配置**”。
    
4. 在“**会议配置**”页上，单击“**新建**”，然后执行以下操作之一：
    
    - 若要创建站点级别的策略，请单击“**站点配置**”。在“**选择站点**”搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击“**确定**”。
    
    - 若要创建池级别的策略，请单击“**池配置**”。在“**选择服务**”搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击“**确定**”。
    
5. 若要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除“**PSTN 呼叫者绕过休息室**”复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。
    
6. 若要配置会议的演示者，请在“**指定为演示者**”中执行下列操作之一：
    
   - 若要禁止组织者以外的任何人成为演示者，请单击“**无**”。
    
   - 若要只允许属于组织成员的参与者成为演示者，请单击“**公司**”。这是默认设置。
    
   - 若要允许任何参与者成为演示者，请单击“**所有人**”。
    
7. 若要让组织者在安排会议时选择会议类型，请清除“**默认分配的会议类型**”复选框。默认情况下，会自动分配会议类型。
    
8. 若要阻止自动允许匿名（未经身份验证）用户参加会议，请清除“**默认允许匿名用户**”复选框。默认情况下，自动允许匿名用户参加会议。
    
9. 若要自定义发送给参与者的会议邀请，请执行以下操作。 请注意，URL 和自定义页脚文本的最大长度为 1KB。 除了“**帮助 URL**”外，如果不指定自定义的值，则它们不会包括在会议中。 如果不包含自定义帮助 URL，将在邀请中显示 Skype for Business 的默认帮助 URL。 
    
   - 若要自定义会议邀请中显示的徽标，请在“**徽标 URL**”中输入徽标的位置。徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。 
    
   - 若要自定义会议邀请中显示的帮助文本，请在“**帮助 URL**”中输入帮助文本的位置。
    
   - 若要自定义会议邀请中显示的法律文本，请在“**法律文本 URL**”中输入法律文本的位置。
    
   - 若要自定义会议邀请中显示的页脚文本，请在“**自定义页脚文本**”中输入文本。
    
10. 单击“**提交**”。
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序创建会议配置设置

若要创建会议配置设置，请使用 **New-CsMeetingConfiguration** cmdlet。
  
以下命令为 Redmond 站点创建一组新的会议配置设置：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的会议配置设置的所有属性将使用默认值。
  
要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建在默认情况下允许所有人以演示者身份加入会议的会议配置设置集合，请使用如下命令：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

可以通过包含多个参数来设置多个属性值。例如，以下命令允许所有人以演示者身份加入会议，同时强制 PSTN 用户在会议厅等待，直至他们被正式允许加入会议：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

有关详细信息，包括参数的完整列表，请参阅[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)。
  

