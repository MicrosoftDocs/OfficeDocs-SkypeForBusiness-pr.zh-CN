---
title: 将单个用户移动到试点池
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序将用户从旧池移动到 Skype for Business Server 2019 试点池。 在下面的示例的"注册器池"列中，pool01.contoso.net 是旧池，这六个用户全部连接到此池。 使用以下过程使用 Skype for Business Server 2019 控制面板和命令行管理程序将Skype for Business Server 2019 Skype for Business Server池。
ms.openlocfilehash: 987eeec96d28257b995b5e27ce02e282df019980
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596156"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>将单个用户移动到试点池

您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序将用户从旧池移动到 Skype for Business Server 2019 试点池。 在下面的示例的"注册器池"列中，pool01.contoso.net是旧池，并且所有这六个用户都连接到此池。 使用以下过程使用 Skype for Business Server 2019 控制面板和命令行管理程序将Skype for Business Server 2019 Skype for Business Server池。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype for Business Server 2019 控制面板移动用户
  
1. 使用具有 RTCUniversalServerAdmins 组成员身份或者 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开 **Skype for Business Server控制面板"。**
    
3. 依次单击“用户”、“搜索”和“查找”。
    
4. 选择要移动到 2019 池Skype for Business Server用户。 在本示例中，我们将移动用户 Sara Davis。
    
5. 在“操作”菜单中，选择“将所选用户移动到池”。
    
6. 从下拉列表中，选择"Skype for Business Server 2019 池"。
    
7. 单击“操作”，然后单击“将所选用户移动到池”。单击“确定”。
  
8. 确认用户的"**注册** 器池"列现在包含 Skype for Business Server 2019 池，这表明已成功移动用户。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>使用命令行管理程序移动Skype for Business Server 2019

1. 打开"Skype for Business Server命令行管理程序"。
    
2. 在命令行中键入： 
    
   ```PowerShell
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 接下来，在命令行处键入： 
    
   ```PowerShell
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool** 标识现在指向 Skype for Business Server 2019 池。 存在该标识即可确认已成功移动用户。 

    > [!NOTE]
    > 有关 **Get-CsUser** cmdlet 的详细信息，请运行 **：Get-Help Get-CsUser -Detailed**
  

