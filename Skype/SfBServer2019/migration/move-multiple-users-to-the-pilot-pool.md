---
title: 将多个用户移至试点池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 可以将多个用户从旧池移动到您 Skype 业务服务器 2019年试点池 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序中。
ms.openlocfilehash: c77598d531fa4640d64a61e22ace17e39d87b005
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888299"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>将多个用户移至试点池

可以将多个用户从旧池移动到您 Skype 业务服务器 2019年试点池 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序中。

 **本文中**
  
[使用 Skype 业务 Server 2019 控制面板移动多个用户](#sectionSection0)
  
[使用 Skype 业务服务器 2019年命令行管理程序移动多个用户](#sectionSection1)
  
[要使用 Skype 业务服务器 2019年命令行管理程序同时移动所有用户](#sectionSection2)
  
  
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype 业务 Server 2019 控制面板移动多个用户
<a name="sectionSection0"> </a>

1. 打开 Skype 业务 Server Control Panel。
    
2. 单击**用户**，单击**搜索**，然后单击**查找**。
    
3. 选择您想要业务服务器 2019年池移动到 Skype 的两个用户。 本示例中，我们将移动用户 Chen Yang 和来了 Hansen。
    
     ![将用户移至特定的注册池](../media/Migration_LyncServer_CPanel_fromLyncServer2010_MoveMultipleUsersList.JPG)
  
4. 从**操作**菜单中，选择**移动所选的用户移动到池**。
    
5. 从下拉列表中，选择业务服务器 2019年池 Skype。
    
6. 单击**操作**，然后单击**移动所选的用户移动到池**。 单击“**确定**”。
    
     ![移动用户，目标注册器池对话框](../media/Migration_LyncServer_from_LyncServer2010_CPanelMoveUserSelectPoolDialog.png)
  
7. 确认用户的**注册器池**列现在包含业务服务器 2019年池，这表明已成功移动用户的 Skype。 
    
## <a name="to-move-multiple-users-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype 业务服务器 2019年命令行管理程序移动多个用户
<a name="sectionSection1"> </a>

1. 打开 Skype 业务服务器 2019年命令行管理程序。 
    
2. 在命令行中，键入以下命令并**User1**和**User2**替换为您想要移动的具体用户名**pool_FQDN**替换为目标池的名称。 在此示例中，我们将移动用户 Hao Chen 和 Katie 约旦。 
    
   ```
   Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
   ```

    ![PowerShell Get-csuser cmdlet 的示例](../media/Migration_LyncServer_from_LyncServer2010_move2users.jpg)
  
3. 在命令行中键入： 
    
   ```
   Get-CsUser -Identity "User1"
   ```

4. **注册器池**标识现在应指向为**pool_FQDN**上一步骤中指定的池。 该标识的状态，确认已成功移动该用户。 重复步骤以验证已移动**User2** 。 
    
     ![输出的 PowerShell Get-UsUser-Identity cmdlet](../media/Migration_LyncServer_from_LyncServer2010_showuser.jpg)
  
## <a name="to-move-all-users-at-the-same-time-by-using-the-skype-for-business-server-2019-management-shell"></a>要使用 Skype 业务服务器 2019年命令行管理程序同时移动所有用户
<a name="sectionSection2"> </a>

本示例中，所有用户已都返回到旧池 (pool01.contoso.net)。 使用 Skype 业务服务器 2019年命令行管理程序，我们将移动所有用户在同一时间到业务服务器 2019年池 (pool02.contoso.net) Skype。
  
1. 打开 Skype 业务服务器 2019年命令行管理程序。
    
2. 在命令行中键入： 
    
   ```
   Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
   ```

     ![PowerShell cmdlet 和命令行管理程序中的结果](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserMultipleAll.png)
  
3. 运行**Get-csuser**为试点用户之一。 
    
   ```
   Get-CsUser -Identity "Hao Chen"
   ```

4. 为每个用户的**注册器池**标识现在指向为**pool_FQDN**上一步骤中指定的池。 该标识的状态，确认已成功移动该用户。 
    
5. 此外，我们可以业务 Server 2019 控制面板的 Skype 中查看用户列表，并验证 Registrar Pool 值现在指向业务服务器 2019年池 Skype。
    
     ![Skype 业务 Server 2019 Control Panel 用户列表](../media/Migration_LyncServer_CPanel_fromLyncServer2010_Move-CSUserVerifyHao.JPG)
  

