---
title: 在会议环境中创建会议Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 摘要：了解如何在会议环境中创建会议Skype for Business Server。
ms.openlocfilehash: 03a9194a5b4015d9434641e7946b66c57ff4df77
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747148"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a>在会议环境中创建会议Skype for Business Server
 
**摘要：** 了解如何在会议环境中创建会议Skype for Business Server。
  
可以使用控制面板或命令行管理程序Skype for Business Server会议配置Skype for Business Server设置。
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a>使用"控制面板"Skype for Business Server会议配置设置

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开Skype for Business Server控制面板"。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"会议 **配置"。**
    
4. 在 **“会议配置”** 页上，单击 **“新建”**，然后执行下列操作之一：
    
    - 要创建站点级别的策略，请单击 **“站点配置”**。在 **“选择站点”** 搜索字段中，键入要为其定义与会设置的站点的全部或部分名称。在结果站点列表中，单击所需的站点，然后单击 **“确定”**。
    
    - 要创建池级别的策略，请单击 **“池配置”**。在 **“选择服务”** 搜索字段中，键入要为其定义与会设置的池服务的全部或部分名称。在结果服务列表中，单击所需的池，然后单击 **“确定”**。
    
5. 要路由从公用电话交换网 (PSTN) 通过会议厅拨入的参与者，请清除 **“PSTN 呼叫者绕过会议厅”** 复选框。默认情况下，从 PSTN 拨入的参与者可直接参加会议。
    
6. 要配置会议的演示者，请在 **“指定为演示者”** 中执行下列操作之一：
    
   - 要禁止组织者以外的任何人成为演示者，请单击 **“无”**。
    
   - 要只允许组织成员参与者成为演示者，请单击 **“公司”**。这是默认设置。
    
   - 要允许任何参与者成为演示者，请单击 **“所有人”**。
    
7. 要让组织者在安排会议时选择会议类型，请清除 **“默认分配的会议类型”** 复选框。默认情况下，会自动分配会议类型。
    
8. 要阻止自动允许匿名（未经身份验证）用户参加会议，请清除 **“默认允许匿名用户”** 复选框。默认情况下，自动允许匿名用户参加会议。
    
9. 若要自定义发送给参与者的会议邀请，请执行下列操作。 请注意，URL 和自定义页脚文本的最大长度为 1KB。 帮助 **URL** 除外，如果不为自定义项指定值，它们将不会包含在会议中。 如果不包括自定义帮助 URL，则邀请中将显示Skype for Business的默认帮助 URL。 
    
   - 若要自定义会议邀请中出现的徽标，请在"徽标 **URL"** 中输入徽标的位置。 徽标必须是大小为 188 x 30 像素的 GIF 或 JPG 图像。 
    
   - 若要自定义会议邀请中显示的帮助文本，请在"帮助 **URL"** 中输入帮助文本的位置。
    
   - 若要自定义会议邀请中显示的法律文本，请在"法律文本 **URL"** 中输入法律文本的位置。
    
   - 若要自定义会议邀请中出现的页脚文本，请在"自定义页脚文本" **中** 输入文本。
    
10. 单击“提交”。
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序Skype for Business Server会议配置设置

若要创建会议配置设置，请使用 **New-CsMeetingConfiguration** cmdlet。
  
以下命令为 Redmond 站点创建一组新的会议配置设置：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

由于除了 (Identity 参数参数) ，因此新的会议配置设置将在其所有属性中都使用默认值。
  
要创建使用不同属性值的设置，只需包含相应的参数和参数值。 例如，若要创建默认情况下允许所有人以演示者角色加入会议的会议配置设置集合，请使用类似如下的命令：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

可以通过包含多个参数来设置多个属性值。 例如，以下命令允许所有人以演示者形式加入会议，并强制 PSTN 用户在会议厅等待，直到正式允许他们参加会议：
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

有关详细信息，包括参数的完整列表，请参阅[New-CsMeetingConfiguration。](/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps)
