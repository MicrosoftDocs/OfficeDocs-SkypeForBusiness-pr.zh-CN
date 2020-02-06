---
title: 在 Skype for Business 服务器中启用或禁用电话拨入式会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 摘要：了解如何使用 "控制面板" 或 "管理外壳" 在 Skype for Business 服务器中启用或禁用电话拨入式会议。
ms.openlocfilehash: 8ce0fcfb4f785397075aa9d7b89b94eacb096167
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818553"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用或禁用电话拨入式会议
 
**摘要：** 了解如何使用 "控制面板" 或 "管理外壳" 在 Skype for Business 服务器中启用或禁用拨入式会议。
  
你可以使用 Skype for Business Server 控制面板或使用 Skype for Business Server 命令行管理器启用电话拨入式会议。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板启用或禁用电话拨入式会议

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 "Skype for Business 服务器" 控制面板。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
4. 在会议策略列表中，选择要为其启用电话拨入式会议的策略，单击“**编辑**”，然后单击“**显示详细信息**”。 
    
5. 若要允许用户通过电话拨入加入会议，请选中“**启用 PSTN 电话拨入式会议**”复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。
    
6. 单击“**提交**”。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序启用或禁用电话拨入式会议

若要启用或禁用电话拨入式会议，请如下使用带 EnableDialInConferencing 参数的 **Set-CsConferencingPolicy** cmdlet：
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

有关详细信息，请参阅[设置 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

