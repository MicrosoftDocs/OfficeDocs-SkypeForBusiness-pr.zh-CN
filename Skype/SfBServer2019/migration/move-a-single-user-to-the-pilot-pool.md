---
title: 将单个用户移动到 "引导" 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 你可以使用 Skype for Business Server 2019 控制面板或 Skype for business Server 2019 命令行管理程序将用户从旧版池中移动到 Skype for business Server 2019 试验池。 在下面的示例中，在 "注册机构池" 列中，pool01.contoso.net 是旧版池，并且所有六个用户都连接到该池。 使用以下过程，使用 Skype for business Server 2019 控制面板和 Skype for business Server Management Shell 将用户移动到 Skype for business Server 2019 池。
ms.openlocfilehash: 8964dd3dc868c22cd14389ba70b88d32b6bd145a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40988957"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>将单个用户移动到 "引导" 池

你可以使用 Skype for Business Server 2019 控制面板或 Skype for business Server 2019 命令行管理程序将用户从旧版池中移动到 Skype for business Server 2019 试验池。 在下面的示例中，在 "**注册机构池**" 列中， **pool01.contoso.net**是旧版池，并且所有六个用户都连接到该池。 使用以下过程，使用 Skype for business Server 2019 控制面板和 Skype for business Server Management Shell 将用户移动到 Skype for business Server 2019 池。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype for Business Server 2019 控制面板移动用户
  
1. 使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开 **"Skype For Business 服务器" 控制面板**。
    
3. 单击 "**用户**"，单击 "**搜索**"，然后单击 "**查找**"。
    
4. 选择要移动到 Skype for business Server 2019 池的用户。 在此示例中，将移动用户 Sara Davis。
    
5. 在“操作”**** 菜单中，选择“将所选用户移动到池”****。
    
6. 从下拉列表中，选择 Skype for business Server 2019 池。
    
7. 单击 "**操作**"，然后单击 "**将所选用户移至池**"。 单击“**确定**”。
  
8. 验证用户的**注册池**列现在是否包含 Skype For business Server 2019 池，这表示用户已成功移动。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序移动用户

1. 打开 Skype for Business 服务器命令行管理程序。
    
2. 在命令行中键入： 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 接下来，在命令行键入以下命令： 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool**标识现在指向 Skype For business Server 2019 池。 此标识的存在可确认用户已成功移动。 

    > [!NOTE]
    > 有关**move-csuser** cmdlet 的详细信息，请运行： **Get-help move-csuser-详细**信息
  

