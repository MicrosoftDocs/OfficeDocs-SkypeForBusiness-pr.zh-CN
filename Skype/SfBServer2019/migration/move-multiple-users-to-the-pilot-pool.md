---
title: 将多个用户移动到 "引导" 池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 你可以使用 Skype for business Server 2019 控制面板或 Skype for business Server 2019 Management Shell, 将多个用户从旧版池移动到 Skype for business Server 2019 试验池。
ms.openlocfilehash: 3798525145776c61eed6b1dabebe657538d7c9db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282222"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>将多个用户移动到 "引导" 池

你可以使用 Skype for business Server 2019 控制面板或 Skype for business Server 2019 Management Shell, 将多个用户从旧版池移动到 Skype for business Server 2019 试验池。

 **在本文中**
  
[使用 Skype for Business Server 2019 控制面板移动多个用户](#sectionSection0)
  
[使用 Skype for Business Server 2019 命令行管理程序移动多个用户](#sectionSection1)
  
[使用 Skype for Business Server 2019 命令行管理程序同时移动所有用户](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype for Business Server 2019 控制面板移动多个用户
<a name="sectionSection0"> </a>

1. 打开 "Skype for Business 服务器" 控制面板。
    
2. 单击 "**用户**", 单击 "**搜索**", 然后单击 "**查找**"。
    
3. 选择要移动到 Skype for business Server 2019 池的两个用户。 在此示例中, 我们将用户移动 Chen's 的 Hansen 和 Claus。
    
     ![将用户移动到特定注册池](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. 从 "**操作**" 菜单中, 选择 "**将所选用户移至池**"。
    
5. 从下拉列表中, 选择 Skype for business Server 2019 池。
    
6. 单击 "**操作**", 然后单击 "**将所选用户移至池**"。 单击“**确定**”。
    
     !["移动用户"、"目标注册机构池" 对话框](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 验证用户的**注册池**列现在是否包含 Skype For business Server 2019 池, 这表示用户已成功移动。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序移动多个用户
<a name="sectionSection1"> </a>

1. 打开 Skype for Business Server 2019 命令行管理程序。 
    
2. 在命令行中, 键入以下内容并将**User1**和**** 用户2替换为要移动的特定用户名, 然后将**pool_FQDN**替换为目标池的名称。 在此示例中, 我们将在 Hao Chen's 和 Katie 约旦之间移动用户。 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Move-csuser cmdlet 示例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 在命令行中键入： 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. **注册机构池**标识现在应指向您在上一步中指定为**pool_FQDN**的池。 此标识的存在可确认用户已成功移动。 重复步骤以验证您**** 的服务2是否已被移动。 
    
     ![PowerShell UsUser-Identity cmdlet 的输出](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序同时移动所有用户
<a name="sectionSection2"> </a>

在此示例中, 所有用户都已返回到旧版池 (pool01.contoso.net)。 使用 Skype for Business Server 2019 命令行管理程序, 我们将同时将所有用户同时移动到 Skype for business Server 2019 池 (pool02.contoso.net)。
  
1. 打开 Skype for Business Server 2019 命令行管理程序。
    
2. 在命令行中键入： 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 和结果在管理外壳程序中](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 为一个试验用户运行**move-csuser** 。 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. 每个用户的**注册池**标识现在指向您在上一步中指定为**pool_FQDN**的池。 此标识的存在可确认用户已成功移动。 
    
5. 此外, 我们可以在 Skype for Business Server 2019 控制面板中查看用户列表, 并验证注册机构池值是否现在指向 Skype for business Server 2019 池。
    
     ![Skype for Business 服务器2019控制面板用户列表](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

