---
title: 管理服务Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c99ee134-8294-4481-bb4e-710fe85a39ca
description: 本文介绍如何管理在拓扑中Skype for Business Server服务。
ms.openlocfilehash: 45af8756feda61d0a0bac06beedddcc693591346
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593636"
---
# <a name="manage-services-for-skype-for-business-server"></a>管理服务Skype for Business Server

本文介绍如何管理在拓扑中Skype for Business Server服务。
  
## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看运行 Skype for Business Server
<a name="view_list"> </a>

可以使用Skype for Business Server控制面板查看在拓扑中运行Skype for Business Server计算机的列表，并查看每台计算机的服务状态。 可以按计算机、池或站点对列表进行排序。 
  
### <a name="to-view-a-list-of-computers-running-skype-for-business-server"></a>查看运行 Skype for Business Server

1. 从分配给用户的任何预定义管理角色的用户帐户Skype for Business Server内部部署中的任意计算机。 有关这些角色中可用的预定义管理角色Skype for Business Server，请参阅 Planning **for Role-Based Access Control**。   
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。   
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。   
4. 根据需要，在“状态”页上执行下列任意操作：
   - 单击“计算机”、“池”或“站点”列标题，然后单击向上箭头或向下箭头对列表进行排序。 
   - 单击“刷新”查看最新列表。  
   - 通过在搜索字段中键入计算机名称来搜索特定的计算机。
    
## <a name="view-the-status-of-services-running-on-a-skype-for-business-server"></a>查看服务器上运行的服务Skype for Business状态
<a name="view-status"> </a>

可以使用Skype for Business Server控制面板查看在 Skype for Business Server 拓扑中的特定计算机上运行的所有服务，并查看每个服务的状态。
  
### <a name="to-view-the-status-of-services-running-on-a-computer"></a>查看计算机上运行的服务的状态

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3. 在左侧导航栏中，单击“拓扑”。 
4. 在 **"状态** "页上，根据要求对列表进行排序或搜索以查找感兴趣的计算机，然后单击计算机名称。
5. 执行下列任意操作：
   - 要查看计算机上运行的服务的最新状态，请单击“获取服务状态”。
   - 要查看计算机上运行的特定服务的列表和每种服务的状态，请单击“属性”，然后单击“关闭”返回到列表。
    
### <a name="viewing-service-status-with-windows-powershell-cmdlets"></a>使用 Powershell cmdlet Windows服务状态

您还可以使用 **Get-CsWindowsService** cmdlet 和 Windows PowerShell查看服务状态。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell连接到 Skype for Business Server 的详细信息，请参阅博客文章"快速入门：使用远程[PowerShell 管理 Microsoft Lync Server 2010"。](https://go.microsoft.com/fwlink/p/?linkId=255876) 此过程在 Skype for Business Server 中Skype for Business Server。
  
### <a name="to-view-service-status"></a>查看服务状态

若要查看计算机上服务状态，请在命令行管理程序中键入与Skype for Business Server类似的命令，然后按 Enter：
  
```PowerShell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

此命令会返回类似下列信息：
  
|**RoleName**|**状态**|
|:-----|:-----|
|{W3SVC}  <br/> |正在运行  <br/> |
|{CentralManagement}  <br/> | 正在运行 <br/> |
|{ClsAgent}  <br/> |正在运行  <br/> |
|{Registrar、UserServer、EdgeServer}  <br/> |正在运行  <br/> |
|{ApplicationServer}  <br/> |正在运行  <br/> |
|{ConferencingServer}  <br/> |正在运行  <br/> |
|{MediationServer}  <br/> |正在运行  <br/> |
   
有关详细信息，请参阅[Get-CsWindowsService。](/powershell/module/skype/get-cswindowsservice.md?view=skype-ps)
  
## <a name="view-details-about-a-service"></a>查看有关服务的详细信息
<a name="view_details"> </a>

可以使用"Skype for Business Server控制面板"查看有关拓扑中特定计算机上运行的每个服务的详细信息。 可以查看每个服务的状态和详细信息（如关联的数据库、端口和相关服务）。
  
### <a name="to-view-details-for-a-service"></a>查看服务的详细信息

1. 从分配给用户的任何预定义管理角色的用户帐户Skype for Business Server内部部署中的任意计算机。 有关这些角色中可用的预定义管理角色Skype for Business Server，请参阅 Planning **for Role-Based Access Control**。
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页中，对列表进行排序或搜索列表，然后单击要查看的计算机。
5. 单击“属性”。
6. 在“查看计算机详细信息”窗口中，根据需要对服务列表进行排序，然后单击要查看的服务。
7. 根据需要执行下列任意操作：
   - 要查看特定服务的最新状态，请单击“获取服务状态”。
   - 要查看特定服务的详细信息，请单击“属性”，然后单击“关闭”。
   - 要返回拓扑中所有计算机的列表，请单击“关闭”。
    
## <a name="start-or-stop-skype-for-business-server-services"></a>启动或停止Skype for Business Server服务
<a name="StartStop"> </a>

可以使用控制面板Skype for Business Server或停止特定计算机上运行的所有 Skype for Business Server 服务，或启动或停止特定服务。
  
### <a name="to-start-or-stop-all-skype-for-business-services-on-a-computer"></a>启动或停止Skype for Business所有服务

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署了 Skype for Business Server 的网络内的任何计算机。 通过运行与以下内容类似的命令，您可以确定是否已分配了 CsServerAdministrator 或 CsAdministrator RBAC 角色：
    
   ```PowerShell
   Get-CsAdminRoleAssignment -Identity "kenmyer"
   ```

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。
5. 单击“操作”。
6. 单击“启动所有服务”或“停止所有服务”。
    
### <a name="to-start-or-stop-a-specific-service"></a>启动或停止特定服务

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。
5. 单击“属性”。
6. 如有必要，对服务列表进行排序，然后单击要启动或停止的服务。
7. 单击“操作”。
8. 单击“启动服务”或“停止服务”。
9. 单击“关闭”。
    
## <a name="prevent-sessions-for-services"></a>阻止服务的会话
<a name="prevent_session"> </a>

可以使用"Skype for Business Server控制面板"阻止特定计算机上运行的所有 Skype for Business Server 服务的新会话，或阻止特定 Skype for Business Server 服务的新会话。
  
### <a name="to-prevent-new-sessions-for-all-skype-for-business-services-on-a-computer"></a>阻止计算机上所有 Skype for Business服务的新会话

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署了 Skype for Business Server 的网络内的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。
5. 单击“操作”。
6. 单击“阻止所有服务的新会话”。
    
### <a name="to-prevent-new-sessions-for-a-specific-service"></a>阻止特定服务的新会话

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署了 Skype for Business Server 的网络内的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。 
5. 单击“属性”。
6. 如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。
7. 单击“操作”。
8. 单击“阻止服务的新会话”。
9. 单击“关闭”。
