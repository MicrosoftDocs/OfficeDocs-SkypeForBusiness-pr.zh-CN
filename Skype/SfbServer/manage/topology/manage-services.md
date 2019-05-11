---
title: Skype 中的服务管理业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解如何查看服务状态，启动和停止服务，并阻止服务的会话。
ms.openlocfilehash: 78d8b2a16204585a0ff403867617ff709666c4f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911964"
---
# <a name="manage-services-in-skype-for-business-server"></a>Skype 中的服务管理业务服务器

可以使用业务 Server Control Panel 的 Skype 查看列表的所有计算机的业务服务器拓扑中运行 Skype、 查看的服务的状态、 启动或停止服务，并阻止服务的会话。

- [查看业务服务器运行 Skype 的计算机列表](#view-a-list-of-computers-running-skype-for-business-server)
- [查看 Skype for Business 中的计算机上运行的服务的状态](#view-the-status-of-services-running-on-a-computer-in-skype-for-business)
- [启动或停止 Skype 业务服务](#start-or-stop-skype-for-business-services)
- [阻止服务的会话](#prevent-sessions-for-services)

## <a name="view-a-list-of-computers-running-skype-for-business-server"></a>查看业务服务器运行 Skype 的计算机列表

使用业务 Server Control Panel Skype 查看您的拓扑中运行 for Business 的 Skype 并查看每个服务状态的所有计算机的列表。 您可以通过计算机、 池或网站列表进行排序。 

1. 分配给任何预定义管理角色的 Skype 业务服务器的用户帐户，登录到内部部署中的任何计算机。 有关详细信息，请参阅[基于角色的访问控制 (RBAC) 的 Skype 业务服务器](../../plan-your-deployment/security/role-based-access-control-rbac.md)。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 在状态页上，执行根据需要以下任一操作：
    - 通过单击**计算机**、**池**或**网站**列标题，然后单击向上箭头或向下箭头对列表。
    - 单击**刷新**以查看最新的列表。
    - 通过在搜索字段中键入计算机名称来搜索特定的计算机。
   
## <a name="view-the-status-of-services-running-on-a-computer-in-skype-for-business"></a>查看 Skype for Business 中的计算机上运行的服务的状态

使用业务 Server Control Panel Skype 可以查看您 Skype 企业服务器拓扑中特定计算机上运行并查看每种服务的状态的所有服务。

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧的导航栏中，单击**拓扑**。
4. 在状态页上排序或搜索列表中，根据需要，以查找您感兴趣的计算机，然后单击计算机名称。
5. 请执行以下任一操作：
    - 若要查看的计算机上运行的服务的最新状态，请单击**获取服务状态**。
    - 要查看在每个服务的状态和计算机上运行的特定服务的列表，请单击**属性**，然后单击**关闭**以返回到列表。

### <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a>通过使用 Windows PowerShell Cmdlet 查看服务状态

您还可以使用 Windows PowerShell 和 Get-cswindowsservice cmdlet 查看服务状态。 从业务 Server 命令行管理程序 Skype 或 Windows PowerShell 远程会话，您可以运行此 cmdlet。 有关详细信息，请参阅[业务 Server Management Shell 的 Skype](../management-shell.md)。

**若要查看服务状态**

若要查看的计算机上的服务状态，Skype 的业务 Server Management Shell 中，键入类似于以下命令，然后按 Enter:

`Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status`

此命令会返回类似下列信息：

```
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

有关详细信息，请参阅[Get-cswindowsservice](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsWindowsService)。

## <a name="start-or-stop-skype-for-business-services"></a>启动或停止 Skype 业务服务

使用业务 Server Control Panel Skype 启动或停止特定计算机上运行的业务服务器服务的所有 Skype 或者启动或都停止特定服务。

### <a name="start-or-stop-all-skype-for-business-server-services-on-a-computer"></a>启动或停止所有 Skype 业务 Server 服务的计算机上

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机. 您可以确定是否已将您分配 CsServerAdministrator 或 CsAdministrator RBAC 角色通过运行类似于以下命令：

    `Get-CsAdminRoleAssignment -Identity "kenmyer"`

2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 状态页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。
5. 单击**操作**。
6. 单击**启动所有服务**或**停止所有服务**。

### <a name="start-or-stop-a-specific-service"></a>启动或停止特定服务

1. 使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 状态页、 排序或搜索列表根据需要查找运行服务的计算机上要启动或停止，然后单击它。
5. 单击**属性**。
6. 服务列表进行排序，如有必要，然后单击要启动或停止的服务。
7. 单击**操作**。
8. 单击**启动服务**或**停止服务**。
9. 单击“关闭”****。


## <a name="prevent-sessions-for-services"></a>阻止服务的会话

使用业务控制面板的 Skype 的业务服务器运行的服务特定计算机上的所有 Skype 阻止新会话或阻止特定服务的新会话。

### <a name="prevent-new-sessions-for-all--skype-for-business-server-services-on-a-computer"></a>为业务 Server 服务的计算机上的所有 Skype 阻止新会话

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧的导航栏中，单击**拓扑**，然后单击**状态**。
4. 在状态页上排序或列表作为搜索所需找到正在运行要为其阻止新会话，然后单击的服务的计算机。
5. 单击**操作**。
6. 单击**阻止所有服务的新会话**。

### <a name="prevent-new-sessions-for-a-specific-service"></a>阻止特定服务的新会话

1. 从用户帐户是 RTCUniversalServerAdmins 组的成员 （或具有同等用户权限），或分配给 CsServerAdministrator 或 CsAdministrator 角色，登录到在其中在部署 Skype Business Server 网络中的任一计算机.
2. 打开一个浏览器窗口，然后输入管理 URL 以打开控制面板。 有关可用于为业务 Server Control Panel 启动 Skype 的不同方法的详细信息，请参阅[安装和打开管理工具](../../management-tools/install-and-open-administrative-tools.md)。
3. 在左侧导航栏中，单击“**拓扑**”，然后单击“**状态**”。
4. 单击**属性**。
5. 如有必要，对服务，对列表进行排序，然后单击您要为其阻止新会话的服务。
6. 单击**操作**。
7. 单击**阻止服务的新会话**。
8. 单击“关闭”****。
