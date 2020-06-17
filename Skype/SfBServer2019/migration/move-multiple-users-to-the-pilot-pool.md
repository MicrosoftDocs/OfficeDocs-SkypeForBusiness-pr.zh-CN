---
title: 将多个用户移动到引导池
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
description: 您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将多个用户从旧版池移动到 Skype for business Server 2019 试点池。
ms.openlocfilehash: d1b003c5630a0917fbecbd9b04196675657fef83
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753424"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>将多个用户移动到引导池

您可以使用 Skype for Business Server 2019 控制面板或 Skype for Business Server 2019 命令行管理程序，将多个用户从旧版池移动到 Skype for business Server 2019 试点池。

 **本文内容：**
  
[使用 Skype for Business Server 2019 控制面板移动多个用户](#sectionSection0)
  
[使用 Skype for Business Server 2019 命令行管理程序移动多个用户](#sectionSection1)
  
[使用 Skype for Business Server 2019 命令行管理程序同时移动所有用户](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype for Business Server 2019 控制面板移动多个用户
<a name="sectionSection0"> </a>

1. 打开 "Skype for Business Server 控制面板"。
    
2. 依次单击“用户”****、“搜索”**** 和“查找”****。
    
3. 选择要移到 Skype for Business Server 2019 池的两个用户。 在本例中，我们将移动用户 Chen Yang 和 Claus Hansen。
    
     ![将用户移动到特定的注册池](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. 在“操作”**** 菜单中，选择“将所选用户移动到池”****。
    
5. 从下拉列表中，选择 "Skype for Business Server 2019" 池。
    
6. 单击“操作”****，然后单击“将所选用户移动到池”****。 单击“确定”****。
    
     !["移动用户，目标注册器池" 对话框](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 确认用户的 "**注册器池**" 列现在包含 Skype For business Server 2019 池，这表明已成功移动了用户。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序移动多个用户
<a name="sectionSection1"> </a>

1. 打开 Skype for Business Server 2019 命令行管理程序。 
    
2. 在命令行中，键入以下内容，并**User1**将 User1**和用户2替换为要**移动的特定用户名，并将**pool_FQDN**替换为目标池的名称。 在本例中，我们将移动用户 Hao Chen 和 Katie Jordan。 
    
   ```PowerShell
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-csuser cmdlet 示例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 在命令行中键入： 
    
   ```PowerShell
   Get-CsUser -Identity "User1"
   ```

4. **Registrar Pool** 标识现在应该指向在上一步中指定为 **pool_FQDN** 的池。 存在该标识即可确认已成功移动用户。 重复步骤以验证是否**已移动**到 "2"。 
    
     ![PowerShell UsUser cmdlet 的输出](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序同时移动所有用户
<a name="sectionSection2"> </a>

在此示例中，所有用户都已返回到旧版池（pool01.contoso.net）。 使用 Skype for Business Server 2019 命令行管理程序，我们将同时将所有用户移动到 Skype for Business Server 2019 池（pool02.contoso.net）。
  
1. 打开 Skype for Business Server 2019 命令行管理程序。
    
2. 在命令行中键入： 
    
   ```PowerShell
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 和命令行管理程序中的结果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 为试用用户之一运行**get-csuser** 。 
    
   ```PowerShell
   Get-CsUser -Identity "Hao Chen"
   ```

4. 每个用户的**注册器池**标识现在指向您在上一步中指定为**pool_FQDN**的池。 存在该标识即可确认已成功移动用户。 
    
5. 此外，我们还可以查看 Skype for business Server 2019 控制面板中的用户列表，并验证注册器池值是否现在指向 Skype for Business Server 2019 池。
    
     ![Skype for Business Server 2019 控制面板用户列表](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

