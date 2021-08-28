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
description: 了解如何查看服务状态、启动和停止服务以及阻止服务会话。
ms.openlocfilehash: 8c1f527e32d50624fddc1b4b261f6fbd20e97a47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58604813"
---
# <a name="manage-services-in-skype-for-business-server"></a>管理服务Skype for Business Server

可以使用Skype for Business Server控制面板查看拓扑中运行 Skype for Business Server 的所有计算机的列表，查看服务状态，启动或停止服务，以及阻止服务会话。

- [查看运行 Skype for Business Server](#view-a-list-of-computers-running-skype-for-business-server)
- [查看运行在 Skype for Business 中的计算机上Skype for Business](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [启动或停止Skype for Business服务](#start-or-stop-skype-for-business-services)
- [阻止服务的会话](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看运行 Skype for Business Server

使用Skype for Business Server控制面板查看在拓扑中运行Skype for Business计算机的列表，并查看每台计算机的服务状态。 可以按计算机、池或站点对列表进行排序。 

1. 从分配给用户的任何预定义管理角色的用户帐户Skype for Business Server内部部署中的任意计算机。 有关详细信息，请参阅基于[角色的访问控制 (RBAC](../../plan-your-deployment/security/role-based-access-control-rbac.md)) for Skype for Business Server 。
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 有关可用于启动"控制面板"Skype for Business Server的详细信息，请参阅安装和[打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在"状态"页上，根据需要执行下列任一操作：
    - 单击“计算机”、“池”或“站点”列标题，然后单击向上箭头或向下箭头对列表进行排序。
    - 单击“刷新”查看最新列表。
    - 通过在搜索字段中键入计算机名称来搜索特定的计算机。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>查看运行在 Skype for Business 中的计算机上Skype for Business

使用Skype for Business Server控制面板查看在 Skype for Business Server 拓扑中的特定计算机上运行的所有服务，并查看每个服务的状态。

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于启动"控制面板"Skype for Business Server的详细信息，请参阅安装和[打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“拓扑”。
4. 在“状态”页上，根据需要对列表进行分类或搜索以查找您感兴趣的计算机，然后单击该计算机的名称。
5. 执行下列任一操作：
    - 要查看计算机上运行的服务的最新状态，请单击“获取服务状态”。
    - 要查看计算机上运行的特定服务的列表和每种服务的状态，请单击“属性”，然后单击“关闭”返回到列表。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>使用 Cmdlet 查看Windows PowerShell状态

您还可以使用 cmdlet 和 Windows PowerShell 查看Get-CsWindowsService状态。 还可从 Skype for Business Server Management Shell 或 Windows PowerShell 远程会话运行此 cmdlet。 有关详细信息，请参阅Skype for Business Server[命令行管理程序。](../management-shell.md)

**查看服务状态**

若要查看计算机上服务状态，请在命令行管理程序中键入与Skype for Business Server类似的命令，然后按 Enter：

```powershell
Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
```

此命令会返回类似下列信息：

```console
RoleName                                  Status
--------                                  ------
{W3SVC}                                   Running
{CentralManagement}                       Running
{ClsAgent}                                Running
{Registrar, UserServer, EdgeServer}       Running
{ApplicationServer}                       Running
{ConferencingServer}                      Running
{MediationServer}                         Running
```

有关详细信息，请参阅[Get-CsWindowsService。](/powershell/module/skype/Get-CsWindowsService)

## <a name="start-or-stop-skype-for-business-services"></a>启动或停止Skype for Business服务

使用Skype for Business Server控制面板启动或停止Skype for Business Server运行的所有服务，或启动或停止特定服务。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>启动或停止Skype for Business Server所有服务

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络中的任何计算机。 通过运行与以下内容类似的命令，您可以确定是否已分配了 CsServerAdministrator 或 CsAdministrator RBAC 角色：

    ```powershell
    Get-CsAdminRoleAssignment -Identity "kenmyer"`
    ```

2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 有关可用于启动"控制面板"Skype for Business Server的详细信息，请参阅安装和[打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。
5. 单击“操作”。
6. 单击“启动所有服务”或“停止所有服务”。

### <a name="start-or-stop-a-specific-service"></a>启动或停止特定服务

1. 使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于启动"控制面板"Skype for Business Server的详细信息，请参阅安装和[打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。
5. 单击“属性”。
6. 如有必要，对服务列表进行排序，然后单击要启动或停止的服务。
7. 单击“操作”。
8. 单击“启动服务”或“停止服务”。
9. 单击“关闭”。


## <a name="prevent-sessions-for-services"></a>阻止服务的会话

使用Skype for Business控制面板阻止特定计算机上运行的所有 Skype for Business Server 服务的新会话，或阻止特定服务的新会话。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>阻止计算机上所有 Skype for Business Server服务的新会话

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络中的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于启动"控制面板"Skype for Business Server的详细信息，请参阅安装和[打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 在“状态”页上，根据需要对列表进行排序或搜索，以查找正在运行要对其阻止新会话的服务的计算机，然后单击该计算机。
5. 单击“操作”。
6. 单击“阻止所有服务的新会话”。

### <a name="prevent-new-sessions-for-a-specific-service"></a>阻止特定服务的新会话

1. 从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到部署 Skype for Business Server 的网络中的任何计算机。
2. 打开浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于启动"控制面板"Skype for Business Server的详细信息，请参阅安装和[打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“拓扑”，然后单击“状态”。
4. 单击“属性”。
5. 如有必要，对服务列表进行排序，然后单击要对其阻止新会话的服务。
6. 单击“操作”。
7. 单击“阻止服务的新会话”。
8. 单击“关闭”。