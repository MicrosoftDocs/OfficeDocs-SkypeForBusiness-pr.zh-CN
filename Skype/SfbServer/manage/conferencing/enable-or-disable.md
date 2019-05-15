---
title: 启用或禁用业务服务器中 Skype 电话拨入式会议
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 摘要： 了解如何使用控制面板或命令行管理程序启用或禁用业务服务器中 Skype 电话拨入式会议。
ms.openlocfilehash: 1392c67e2b432a6acc9bca805367083d311fd7d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919799"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a>启用或禁用业务服务器中 Skype 电话拨入式会议
 
**摘要：** 了解如何使用控制面板或命令行管理程序启用或禁用业务服务器中 Skype 电话拨入式会议。
  
使用适用于业务 Server Control Panel Skype 或使用 Skype 业务 Server 命令行管理程序，您可以启用电话拨入式会议。
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a>启用或禁用使用适用于业务 Server Control Panel Skype 的电话拨入式会议

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2.  打开 Skype 业务 Server Control Panel。
    
3. 在左侧导航栏中，单击“**会议**”，然后单击“**会议策略**”。
    
4. 在会议策略列表中，选择要为其启用电话拨入式会议的策略，单击“**编辑**”，然后单击“**显示详细信息**”。 
    
5. 若要允许用户通过电话拨入加入会议，请选中“**启用 PSTN 电话拨入式会议**”复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。
    
6. 单击“**提交**”。 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a>启用或禁用使用 Skype 业务 Server Management Shell 的电话拨入式会议

若要启用或禁用电话拨入式会议，请如下使用带 EnableDialInConferencing 参数的 **Set-CsConferencingPolicy** cmdlet：
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

有关详细信息，请参阅[Set-csconferencingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)。
  

