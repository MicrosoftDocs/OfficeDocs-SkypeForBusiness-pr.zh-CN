---
title: 将单个用户移动到试点池
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以将用户从旧池移动到您 Skype 的 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序的业务服务器 2019年试点池。 下面的示例中，在注册器池列中，在 pool01.contoso.net 旧池中，且所有六个这些用户连接到该池。 使用以下过程将用户移至您 Skype 业务服务器 2019年池 Skype 业务 Server 2019 Control Panel 和 Skype 用于业务 Server Management Shell。
ms.openlocfilehash: 94896ce2ea05a3102d5a7643e3f26430e74bfe19
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880247"
---
# <a name="move-a-single-user-to-the-pilot-pool"></a>将单个用户移动到试点池

您可以将用户从旧池移动到您 Skype 的 Skype 业务 Server 2019 控制面板或 Skype 用于业务服务器 2019年命令行管理程序的业务服务器 2019年试点池。 下面的示例中，在**注册器池**列中，在**pool01.contoso.net**旧池中，且所有六个这些用户连接到该池。 使用以下过程将用户移至您 Skype 业务服务器 2019年池 Skype 业务 Server 2019 Control Panel 和 Skype 用于业务 Server Management Shell。 
  
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-control-panel"></a>使用 Skype 业务 Server 2019 控制面板移动用户
  
1. 使用具有 RTCUniversalServerAdmins 组成员身份或 CsAdministrator 或 CsUserAdministrator 管理角色成员身份的帐户登录到前端服务器。
    
2. 打开**Skype 的业务 Server Control Panel**。
    
3. 单击**用户**，单击**搜索**，然后单击**查找**。
    
4. 选择您想要将移动到 Skype 业务服务器 2019年池的用户。 在此示例中，将移动用户 Sara Davis。
    
5. 在“操作”**** 菜单中，选择“将所选用户移动到池”****。
    
6. 从下拉列表中，选择业务服务器 2019年池 Skype。
    
7. 单击**操作**，然后单击**移动所选的用户移动到池**。 单击“**确定**”。
  
8. 确认该用户的**注册器池**列现在包含业务服务器 2019年池，这表明已成功移动该用户的 Skype。 
    
## <a name="to-move-a-user-by-using-the-skype-for-business-server-2019-management-shell"></a>使用 Skype 业务服务器 2019年命令行管理程序移动用户

1. 打开 Skype 业务 Server 命令行管理程序。
    
2. 在命令行中键入： 
    
   ```
   Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"
   ```

3. 接下来，在命令行中，键入以下命令： 
    
   ```
   Get-CsUser -Identity "David Pelton"
   ```

4. **RegistrarPool**标识现在指向业务服务器 2019年池 Skype。 该标识的状态，确认已成功移动该用户。 

    > [!NOTE]
    > 有关**Get-csuser** cmdlet 的详细信息，请运行： **Get-help Get-csuser-详细**
  

