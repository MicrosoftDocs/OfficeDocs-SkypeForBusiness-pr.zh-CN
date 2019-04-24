---
title: Skype 的服务管理业务服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文介绍如何管理企业服务器拓扑的 Skype 中运行的服务。
ms.openlocfilehash: 4f5e1c4d91d5412470edebf3ed8d320101153da1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225326"
---
# <a name="manage-services-for-skype-for-business-server"></a>Skype 的服务管理业务服务器

本文介绍如何管理企业服务器拓扑的 Skype 中运行的服务。
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看业务服务器运行 Skype 的计算机列表
<a name="view_list"> </a>

您可以使用业务 Server Control Panel 的 Skype 查看列表的所有计算机的业务服务器拓扑中运行 Skype 并查看每个服务状态。 您可以通过计算机、 池或网站列表进行排序。 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>若要查看的计算机的业务服务器运行 Skype 列表

1. 分配给任何预定义管理角色的 Skype 业务服务器的用户帐户，登录到内部部署中的任何计算机。 有关业务服务器 Skype 中提供的预定义管理角色的详细信息，请参阅**Planning for Role-based Access Control**。   
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。   
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。   
4. 在**状态**页上执行根据需要以下任一操作：
   - 通过单击**计算机**、**池**或**网站**列标题，然后单击向上箭头或向下箭头对列表。 
   - 单击**刷新**以查看最新的列表。  
   - 通过在搜索字段中键入计算机名称来搜索特定的计算机。
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>查看 Business server Skype 上运行的服务的状态
<a name="view-status"> </a>

您可以使用业务 Server Control Panel 的 Skype 查看您 Skype 企业服务器拓扑中特定计算机上运行并查看每种服务的状态的所有服务。
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>若要查看的计算机上运行的服务的状态

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3. 在左侧的导航栏中，单击**拓扑**。 
4. 在**状态**页上排序或搜索列表中，根据需要，以查找您感兴趣的计算机，然后单击计算机名称。
5. 请执行以下任一操作：
   - 若要查看的计算机上运行的服务的最新状态，请单击**获取服务状态**。
   - 要查看在每个服务的状态和计算机上运行的特定服务的列表，请单击**属性**，然后单击**关闭**以返回到列表。
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>使用 Windows Powershell cmdlet 查看服务状态

您还可以使用 Windows PowerShell 和**Get-cswindowsservice** cmdlet 查看服务状态。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Skype 业务服务器的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 过程是相同的 Skype 业务服务器。
  
### <a name="to-view-service-status"></a>若要查看服务状态

若要查看的计算机上的服务状态，业务 Server 命令行管理程序中 Skype 键入类似于以下命令，然后按 Enter:
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

此命令会返回类似下列信息：
  
|**RoleName**|**状态**|
|:-----|:-----|
|{W3SVC}  <br/> |运行  <br/> |
|{CentralManagement}  <br/> | 运行 <br/> |
|{Clsagent 的通信}  <br/> |运行  <br/> |
|{注册器，UserServer，EdgeServer}  <br/> |运行  <br/> |
|{ApplicationServer}  <br/> |运行  <br/> |
|{ConferencingServer}  <br/> |运行  <br/> |
|{MediationServer}  <br/> |运行  <br/> |
   
有关详细信息，请参阅[Get-cswindowsservice](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。
  
## <a name="view-details-about-a-service"></a>查看有关服务的详细信息
<a name="view_details"> </a>

您可以使用业务 Server Control Panel 的 Skype 查看有关您的拓扑中特定计算机运行每个服务的详细信息。 您可以查看每个服务和详细信息，如关联的数据库、 端口和相关服务的状态。
  
### <a name="to-view-details-for-a-service"></a>若要查看服务详细信息

1. 分配给任何预定义管理角色的 Skype 业务服务器的用户帐户，登录到内部部署中的任何计算机。 有关业务服务器 Skype 中提供的预定义管理角色的详细信息，请参阅**Planning for Role-based Access Control**。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. 在**状态**页中，进行排序或搜索列表，然后单击您想要查看的计算机。
5. 单击**属性**。
6. 在**查看计算机详细信息**窗口中，有必要，对服务，对列表进行排序，然后单击您想要查看的服务。
7. 执行根据需要以下任一操作：
   - 若要查看特定服务的最新状态，请单击**获取服务状态**。
   - 要查看特定服务的详细信息，请单击**属性**，然后单击**关闭**。
   - 要返回拓扑中的所有计算机的列表，请单击**关闭**。
    
## <a name="start-or-stop-skype-for-business-server-services"></a>启动或停止 Skype 业务 Server 服务
<a name="StartStop"> </a>

您可以使用业务 Server Control Panel 的 Skype 启动或停止特定计算机上运行的业务服务器服务的所有 Skype 或者启动或都停止特定服务。
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>若要启动或停止所有 Skype 业务服务的计算机上

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机. 您可以确定是否已将您分配 CsServerAdministrator 或 CsAdministrator RBAC 角色通过运行类似于以下命令：
    
   ```
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. **状态**页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。
5. 单击**操作**。
6. 单击**启动所有服务**或**停止所有服务**。
    
### <a name="to-start-or-stop-a-specific-service"></a>若要启动或停止特定服务

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. **状态**页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。
5. 单击**属性**。
6. 服务列表进行排序，如有必要，然后单击要启动或停止的服务。
7. 单击**操作**。
8. 单击**启动服务**或**停止服务**。
9. 单击“关闭”****。
    
## <a name="prevent-sessions-for-services"></a>阻止服务的会话
<a name="prevent_session"> </a>

为特定计算机上运行的业务服务器服务的所有 Skype 阻止新会话或阻止新会话的特定业务服务器服务的 Skype，可以使用 Skype 的业务 Server Control Panel。
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>为业务服务的计算机上的所有 Skype 阻止新会话

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. 在**状态**页上排序或列表作为搜索所需找到正在运行要为其阻止新会话，然后单击的服务的计算机。
5. 单击**操作**。
6. 单击**阻止所有服务的新会话**。
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服务的新会话

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. **状态**页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。 
5. 单击**属性**。
6. 如有必要，对服务，对列表进行排序，然后单击您要为其阻止新会话的服务。
7. 单击**操作**。
8. 单击**阻止服务的新会话**。
9. 单击“关闭”****。
    

