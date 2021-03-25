---
title: 在 Skype for Business Server 中启用或禁用电话拨入式会议
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 摘要：了解如何使用控制面板或命令行管理程序在 Skype for Business Server 中启用或禁用电话拨入式会议。
ms.openlocfilehash: ade7753f480856d68535daadda40eac6296a5d6e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119461"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for Business Server 中启用或禁用电话拨入式会议
 
**摘要：** 了解如何使用控制面板或命令行管理程序在 Skype for Business Server 中启用或禁用电话拨入式会议。
  
可以使用 Skype for Business Server 控制面板或 Skype for Business Server 命令行管理程序启用电话拨入式会议。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板启用或禁用电话拨入式会议

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
    
2.  打开 Skype for Business Server 控制面板。
    
3. 在左侧导航栏中，单击 **"会议"，** 然后单击"**会议策略"。**
    
4. 在会议策略列表中，选择要为其启用电话拨入式会议的策略，单击“编辑”，然后单击“显示详细信息”。 
    
5. 若要允许用户通过电话拨入加入会议，请选中“启用 PSTN 电话拨入式会议”复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。
    
6. 单击“提交”。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序启用或禁用电话拨入式会议

若要启用或禁用电话拨入式会议，请使用带 EnableDialInConferencing 参数的 **Set-CsConferencingPolicy** cmdlet，如下所示：
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

有关详细信息，请参阅 [Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
