---
title: 将多个用户移动到试点池
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
description: 您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序将多个用户从旧池移动到 Skype for Business Server 2019 试点池。
ms.openlocfilehash: fc4d14d26a76ff4dbfc690fc7517aba77afd253f
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726311"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>将多个用户移动到试点池

您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序将多个用户从旧池移动到 Skype for Business Server 2019 试点池。

 **本文内容：**
  
[使用 Skype for Business Server 2019 控制面板移动多个用户](#sectionSection0)
  
[使用 Skype for Business Server 命令行管理程序移动多个用户](#sectionSection1)
  
[使用命令行管理程序同时移动所有用户Skype for Business Server命令行管理程序](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype for Business Server 2019 控制面板移动多个用户
<a name="sectionSection0"> </a>

1. 打开Skype for Business Server控制面板"。
    
2. 依次单击“用户”、“搜索”和“查找”。
    
3. 选择要移动到 2019 池的两Skype for Business Server用户。 在本例中，我们将移动用户 Chen Yang 和 Claus Hansen。
    
     ![将用户移动到特定注册池。](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. 在“操作”菜单中，选择“将所选用户移动到池”。
    
5. 从下拉列表中，选择"Skype for Business Server 2019 池"。
    
6. 单击“操作”，然后单击“将所选用户移动到池”。单击“确定”。
    
     !["移动用户，目标注册器池"对话框。](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 确认用户的"**注册** 器池"列现在包含 Skype for Business Server 2019 池，这表明已成功移动用户。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 命令行管理程序移动多个用户
<a name="sectionSection1"> </a>

1. 打开 Skype for Business Server 2019 命令行管理程序。 
    
2. 在命令行中键入以下内容，将 **User1** 和 **User2** 替换为要移动的特定用户名，pool_FQDN替换为目标池的名称。 在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-CsUser cmdlet 的示例。](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 在命令行中键入： 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. **Registrar Pool** 标识现在应该指向在上一步中指定为 **pool_FQDN** 的池。 存在该标识即可确认已成功移动用户。 重复步骤以验证 **User2** 已移动。 
    
     ![PowerShell 输出Get-UsUser -Identity cmdlet。](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>使用命令行管理程序同时移动所有用户Skype for Business Server命令行管理程序
<a name="sectionSection2"> </a>

此示例中，所有用户已返回到旧池 (pool01.contoso.net) 。 使用 Skype for Business Server 2019 命令行管理程序，我们将所有用户同时移动到 Skype for Business Server 2019 池 (pool02.contoso.net) 。
  
1. 打开 Skype for Business Server 2019 命令行管理程序。
    
2. 在命令行中键入： 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 和结果在命令行管理程序中。](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 为试点用户之一运行 **Get-CsUser。** 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 每个用户 **的** 注册器池标识现在指向在上一步 **pool_FQDN指定的池** 。 存在该标识即可确认已成功移动用户。 
    
5. 此外，我们可以在 Skype for Business Server 2019 控制面板中查看用户列表，并验证 Registrar Pool 值现在是否指向 Skype for Business Server 2019 池。
    
     ![Skype for Business Server 2019 控制面板用户列表。](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

