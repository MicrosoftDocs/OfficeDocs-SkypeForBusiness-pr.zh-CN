---
title: 管理业务服务器 2015 Skype 的服务
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文介绍如何管理业务服务器 2015年拓扑 Skype 中运行的服务。
ms.openlocfilehash: f8406d473b1d2ae644ac56d071313d2b488169fa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-services-for-skype-for-business-server-2015"></a>管理业务服务器 2015 Skype 的服务

本文介绍如何管理业务服务器 2015年拓扑 Skype 中运行的服务。
  
## <a name="view-a-list-of-computers-running-skype-for-business-server-2015"></a>查看列表中的计算机运行 Skype 业务服务器 2015
<a name="view_list"> </a>

可以使用 Skype 业务服务器控件面板以查看列表中的所有计算机的 Skype 正在为您的拓扑结构中的业务服务器 2015年和查看每个服务的状态。 您可以通过计算机、 池或网站列表进行排序。 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>若要查看运行 Skype 业务服务器的计算机的列表

1. 从分配给任何预定义的管理角色的 Skype 进行业务服务器 2015年的用户帐户，登录到内部部署中的任何计算机。 有关业务服务器 2015年的 Skype 中可用的预定义管理角色的详细信息，请参阅**规划基于角色的访问控制**。   
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。   
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。   
4. 在**状态**页中，执行根据需要以下任一操作：
   - 对列表排序，单击**计算机**、**池**或**站点**列标题，然后单击向上箭头或向下箭头。 
   - 单击**刷新**以查看最新的列表。  
   - 通过在搜索字段中键入计算机名搜索特定的计算机。
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-2015-server"></a>查看在 Skype 业务 2015年服务器上运行的服务的状态
<a name="view-status"> </a>

可以使用 Skype 业务服务器控件面板来查看所有的服务的业务服务器拓扑结构您 Skype 在特定计算机上正在运行的每个服务的状态，请参阅。
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>若要查看计算机上运行的服务的状态

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
3. 在左侧的导航栏中，单击**拓扑**。 
4. 在**状态**页面上进行排序或搜索列表中的，根据需要，找到您感兴趣，该计算机，然后单击计算机名称。
5. 请执行以下任一操作：
   - 若要查看在计算机上运行的服务的最新状态，请单击**获取服务状态**。
   - 若要查看特定计算机和每个服务的状态上运行的服务的列表，单击**属性**，然后单击**关闭**返回到列表。
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>查看 Windows Powershell cmdlet 的服务状态

使用 Windows PowerShell 和**Get CsWindowsService** cmdlet，您还可以查看服务状态。 从业务服务器管理外壳的 Skype 或 Windows PowerShell 的远程会话，您可以运行该 cmdlet。 有关使用远程 Windows PowerShell Skype 业务服务器的连接的详细信息，请参阅博客文章["快速启动:: 管理 Microsoft Lync 服务器 2010年使用远程 PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876)。 该过程是相同的 Skype 业务服务器。
  
### <a name="to-view-service-status"></a>若要查看服务状态

若要查看计算机上的服务状态，键入类似于以下命令 Skype 业务服务器管理外壳程序，然后按 enter 键：
  
```
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

此命令会返回类似下列信息：
  
|**角色名**|**状态**|
|:-----|:-----|
|{W3SVC}  <br/> |运行  <br/> |
|{CentralManagement}  <br/> | 运行 <br/> |
|{ClsAgent}  <br/> |运行  <br/> |
|{注册，UserServer，EdgeServer}  <br/> |运行  <br/> |
|{应用程序服务器}  <br/> |运行  <br/> |
|{ConferencingServer}  <br/> |运行  <br/> |
|{MediationServer}  <br/> |运行  <br/> |
   
有关详细信息，请参阅[获取 CsWindowsService](https://docs.microsoft.com/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)。
  
## <a name="view-details-about-a-service"></a>查看有关服务的详细信息
<a name="view_details"> </a>

Skype 业务服务器控件面板用于查看有关每个服务的拓扑结构中的特定计算机上运行的详细信息。 您可以查看每个服务和详细信息，如关联的数据库、 端口和相关服务的状态。
  
### <a name="to-view-details-for-a-service"></a>若要查看服务详细信息

1. 从分配给任何预定义的管理角色的 Skype 进行业务服务器 2015年的用户帐户，登录到内部部署中的任何计算机。 有关业务服务器 2015年的 Skype 中可用的预定义管理角色的详细信息，请参阅**规划基于角色的访问控制**。
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. 在**状态**页面排序或搜索列表，然后单击您想要查看的计算机。
5. 单击**属性**。
6. 在**查看计算机详细信息**窗口中，排序列表中的服务，如有必要，并单击您要查看的服务。
7. 执行根据需要下列任一操作：
   - 若要查看该特定服务的最新状态，请单击**获取服务状态**。
   - 若要查看有关该特定服务的详细信息，请单击**属性**，然后单击**关闭**。
   - 若要返回到您的拓扑中的所有计算机的列表，请单击**关闭**。
    
## <a name="start-or-stop-skype-for-business-server-2015-services"></a>启动或停止 Skype 业务服务器 2015年服务
<a name="StartStop"> </a>

可以使用 Skype 业务服务器控制面板启动或停止的业务服务器 2015年服务在特定计算机上运行的所有 Skype 或要启动或都停止某个特定服务。
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>若要启动或停止计算机上的所有 Skype 业务服务

1. 从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。 您可以确定是否您分配了 CsServerAdministrator 或 CsAdministrator RBAC 角色通过运行与以下类似的命令：
    
  ```
  Get-CsAdminRoleAssignment -Identity "kenmyer"

  ```

2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. **状态**页面、 排序或搜索列表根据需要找到运行服务的计算机上您要开始或停止，然后再单击它。
5. 单击**操作**。
6. 单击**启动所有服务**或**全部停止服务**。
    
### <a name="to-start-or-stop-a-specific-service"></a>若要启动或停止特定服务

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. **状态**页面、 排序或搜索列表根据需要找到正在运行服务的计算机上您要开始或停止，然后再单击它。
5. 单击**属性**。
6. 排序列表中的服务，如有必要，并单击您要启动或停止的服务。
7. 单击**操作**。
8. 单击**启动服务**或**停止服务**。
9. 单击“关闭”****。
    
## <a name="prevent-sessions-for-services"></a>防止会话服务
<a name="prevent_session"> </a>

可以使用业务服务器控件面板的 Skype 业务服务器 2015年服务在特定计算机上运行的所有 Skype 为防止新的会话，或为特定业务服务器 2015年服务 Skype 防止新的会话。
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>为所有业务服务的计算机上的 Skype 防止新会话

1. 从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. 在**状态**页面上进行排序或搜索列表需要找到该计算机正在运行的服务，要防止新的会话，然后单击它。
5. 单击**操作**。
6. 单击**防止新会话中的所有服务**。
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>若要防止特定服务的新会话

1. 从一个用户帐户，是 RTCUniversalServerAdmins 组的成员 （或具有相当的用户的权限），或者是指派到 CsServerAdministrator 或 CsAdministrator 的角色，在其中您部署 Skype 业务服务器的网络中任何计算机的登录2015。
2. 打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。 
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. **状态**页面、 排序或搜索列表根据需要找到正在运行服务的计算机上您要开始或停止，然后再单击它。 
5. 单击**属性**。
6. 排序列表中的服务，如有必要，并单击您要防止新会话的服务。
7. 单击**操作**。
8. 单击**防止新会话的服务**。
9. 单击“关闭”****。
    

