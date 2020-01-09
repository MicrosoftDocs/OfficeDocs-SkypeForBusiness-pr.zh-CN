---
title: 管理 Skype for Business 服务器中的服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何查看服务状态、启动和停止服务以及阻止服务的会话。
ms.openlocfilehash: 90acd45675277dad0f63db342217cf914c97109a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991517"
---
# <a name="manage-services-in-skype-for-business-server"></a>管理 Skype for Business 服务器中的服务

可以使用 Skype for Business Server 控制面板查看拓扑中运行 Skype for Business 服务器的所有计算机的列表、查看服务状态、启动或停止服务以及阻止服务会话。

- [查看运行 Skype for Business 服务器的计算机列表](#view-a-list-of-computers-running-skype-for-business-server)
- [查看 Skype for Business 计算机上运行的服务的状态](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [启动或停止 Skype for Business 服务](#start-or-stop-skype-for-business-services)
- [阻止服务的会话](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看运行 Skype for Business 服务器的计算机列表

使用 Skype for Business 服务器控制面板查看在你的拓扑中运行 Skype for Business 的所有计算机的列表，并查看每个计算机的服务状态。 你可以按计算机、池或网站对列表进行排序。 

1. 从分配给 Skype for business 服务器的任何预定义管理角色的用户帐户，登录到内部部署中的任何计算机。 有关详细信息，请参阅[Skype for Business 服务器的基于角色的访问控制（RBAC）](../../plan-your-deployment/security/role-based-access-control-rbac.md)。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 在 "状态" 页面上，根据需要执行下列操作之一：
    - 单击 "**计算机**"、"**池**" 或 "**网站**" 列标题，然后单击向上键或向下键，对列表进行排序。
    - 单击 "**刷新**" 以查看最新列表。
    - 通过在 "搜索" 字段中键入计算机名称来搜索特定计算机。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>查看 Skype for Business 计算机上运行的服务的状态

使用 Skype for Business 服务器控制面板查看 Skype for Business Server 拓扑中的特定计算机上运行的所有服务，并查看每个服务的状态。

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 在左侧导航栏中，单击 "**拓扑**"。
4. 在 "状态" 页面上，根据需要对列表进行排序或搜索，以查找感兴趣的计算机，然后单击计算机名称。
5. 执行下列任一操作：
    - 若要查看计算机上运行的服务的最新状态，请单击 "**获取服务状态**"。
    - 若要查看计算机上运行的特定服务的列表和每个服务的状态，请单击 "**属性**"，然后单击 "**关闭**" 以返回到列表。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看服务状态

你还可以使用 Windows PowerShell 和 CsWindowsService cmdlet 查看服务状态。 你可以从 Skype for Business Server Management Shell 或从 Windows PowerShell 的远程会话运行此 cmdlet。 有关详细信息，请参阅[Skype For Business Server 命令行管理程序](../management-shell.md)。

**查看服务状态**

若要查看计算机上的服务状态，请在 Skype for business Server 命令行管理器中键入类似于以下内容的命令，然后按 Enter：

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

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

有关详细信息，请参阅[CsWindowsService](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)。

## <a name="start-or-stop-skype-for-business-services"></a>启动或停止 Skype for Business 服务

使用 Skype for Business 服务器控制面板启动或停止在特定计算机上运行的所有 Skype for business 服务器服务，或者启动或停止特定服务。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>启动或停止计算机上的所有 Skype for Business 服务器服务

1. 从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机. 你可以通过运行如下所示的命令来确定你是否已分配 CsServerAdministrator 或 CsAdministrator RBAC 角色：

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 在 "状态" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。
5. 单击 "**操作**"。
6. 单击 "**启动所有服务**" 或 "**停止所有服务**"。

### <a name="start-or-stop-a-specific-service"></a>启动或停止特定服务

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 在 "状态" 页面上，根据需要对列表进行排序或搜索以查找运行要启动或停止的服务的计算机，然后单击它。
5. 单击 "**属性**"。
6. 对服务列表进行排序（如有必要），然后单击要启动或停止的服务。
7. 单击 "**操作**"。
8. 单击 "**开始服务**" 或 "**停止服务**"。
9. 单击“关闭”****。


## <a name="prevent-sessions-for-services"></a>阻止服务的会话

使用 "Skype for Business 控制面板" 阻止在特定计算机上运行的所有 Skype for business 服务器服务的新会话或阻止特定服务的新会话。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>阻止计算机上所有 Skype for Business 服务器服务的新会话

1. 从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 在左侧导航栏中，单击 "**拓扑**"，然后单击 "**状态**"。
4. 在 "状态" 页面上，根据需要对列表进行排序或搜索以查找运行要阻止新会话的服务的计算机，然后单击该计算机。
5. 单击 "**操作**"。
6. 单击 "**阻止所有服务的新会话**"。

### <a name="prevent-new-sessions-for-a-specific-service"></a>阻止针对特定服务的新会话

1. 从 RTCUniversalServerAdmins 组的成员（或具有等效用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到你部署了 Skype for Business 服务器的网络中的任何计算机.
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 "控制面板"。 有关可用于启动 Skype for Business 服务器控制面板的不同方法的详细信息，请参阅[安装和打开 "管理工具](../../management-tools/install-and-open-administrative-tools.md)"。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 单击 "**属性**"。
5. 对服务列表进行排序（如有必要），然后单击要阻止新会话的服务。
6. 单击 "**操作**"。
7. 单击 "**阻止新的服务会话**"。
8. 单击“关闭”****。
