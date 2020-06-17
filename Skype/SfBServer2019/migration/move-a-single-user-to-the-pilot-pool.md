---
title: 将单个用户移动到引导池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将用户从旧版池移动到 Skype for business Server 2019 试点池。 在下面的示例中，在 "注册器池" 列中，pool01.contoso.net 是旧池，所有这六个用户均连接到此池。 使用以下过程可使用 Skype for Business Server 2019 控制面板和 Skype for Business Server 命令行管理程序将用户移动到 Skype for business Server 2019 池。
ms.openlocfilehash: 6be30f37987cc31835a12178d32a8337d9fc5cae
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752504"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>将单个用户移动到引导池

您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将用户从旧版池移动到 Skype for business Server 2019 试点池。 在下面的示例中，在 "**注册器池**" 列中， **pool01.contoso.net**是旧池，所有这六个用户均连接到此池。 使用以下过程可使用 Skype for Business Server 2019 控制面板和 Skype for Business Server 命令行管理程序将用户移动到 Skype for business Server 2019 池。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype for Business Server 2019 控制面板移动用户
  
1. 使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开 **"Skype For Business Server 控制面板"**。
    
3. 依次单击“用户”****、“搜索”**** 和“查找”****。
    
4. 选择要移到 Skype for Business Server 2019 池的用户。 在本示例中，我们将移动用户 Sara Davis。
    
5. 在“操作”**** 菜单中，选择“将所选用户移动到池”****。
    
6. 从下拉列表中，选择 "Skype for Business Server 2019" 池。
    
7. 单击“操作”****，然后单击“将所选用户移动到池”****。 单击“确定”****。
  
8. 确认用户的 "**注册器池**" 列现在包含 Skype For business Server 2019 池，这表明已成功移动该用户。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序移动用户

1. 打开 Skype for Business Server 命令行管理程序。
    
2. 在命令行中键入： 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 接下来，在命令行处键入： 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool**标识现在指向 Skype For business Server 2019 池。 存在该标识即可确认已成功移动用户。 

    > [!NOTE]
    > 有关**get-csuser** cmdlet 的详细信息，请运行： **Get-help get-csuser-详细**信息
  

