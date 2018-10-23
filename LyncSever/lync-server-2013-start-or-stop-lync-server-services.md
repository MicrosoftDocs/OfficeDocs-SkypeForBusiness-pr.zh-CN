---
title: 启动或停止 Lync Server 2013 服务
TOCTitle: 启动或停止 Lync Server 2013 服务
ms:assetid: 1c70b4ec-9de5-4f7a-a3c9-c0eb76710505
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520958(v=OCS.15)
ms:contentKeyID: 49312184
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启动或停止 Lync Server 2013 服务

 

_**上一次修改主题：** 2014-02-05_

可以使用 Lync Server 控制面板启动或停止特定计算机上运行的所有 Lync Server 2013 服务，或者启动或停止特定服务。

## 启动或停止计算机上的所有 Lync Server 服务

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“拓扑”，然后单击“状态”。

4.  在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。

5.  单击“操作”。

6.  单击“启动所有服务”或“停止所有服务”。

## 启动或停止特定服务

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“拓扑”，然后单击“状态”。

4.  在“状态”页上，根据需要对列表进行排序或搜索列表，以查找正在运行要启动或停止的服务的计算机，然后单击该计算机。

5.  单击“属性”。

6.  如有必要，请对服务列表进行排序，然后单击要启动或停止的服务。

7.  单击“操作”。

8.  单击“启动服务”或“停止服务”。

9.  单击“关闭”。

## 另请参阅

#### 任务

[在 Lync Server 2013 中阻止服务的会话](lync-server-2013-prevent-sessions-for-services.md)  

#### 其他资源

[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)

