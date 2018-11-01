---
title: Lync Server 2013：测试 Standard Edition 服务器
TOCTitle: 测试 Standard Edition 服务器
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412890(v=OCS.15)
ms:contentKeyID: 49314024
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中测试 Standard Edition 服务器

 

_**上一次修改主题：** 2012-10-01_

以下过程介绍如何测试 Standard Edition Server 的部署。

## 测试 Standard Edition Server 的部署

1.  使用“Active Directory 计算机和用户”将 Lync Server 2013 部署（其中已安装 Lync Server 控制面板）的管理员角色的 Active Directory 用户对象添加到 **CSAdministrator** 组。

2.  如果用户对象当前已登录，则注销后重新登录，以注册新的组分配。
    
    > [!NOTE]
    > 用户帐户不能是运行 Lync Server 2013 Standard Edition 的服务器的本地管理员。如果未将相应的用户和组添加到 CsAdministors 组，则在打开 Lync Server 2013 控制面板时会收到错误消息，指出“未授权:由于基于角色的访问控制 (RBAC) 授权失败，访问被拒绝”。


3.  使用管理帐户登录到已安装 Lync Server 控制面板的计算机。

4.  如果出现提示，请启动 Lync Server 控制面板并提供凭据。 Lync Server 2013 控制面板显示部署信息。

5.  在左侧导航栏中，单击“拓扑”，然后确认服务状态是带有绿色箭头的计算机图标，且已部署并恢复联机的每个 Lync Server 服务器角色旁边都有一个绿色复选标记。

6.  在左侧导航栏中，单击“用户”，然后为这两名用户启用 Lync Server 2013。

7.  使其中一个用户登录已加入域的计算机，另一个用户登录域中的其他计算机。

8.  在这两台客户端计算机上均安装 Lync Server 2013，然后验证两名用户是否都能登录到 Lync Server 2013，并互相发送即时消息。

## 另请参阅

#### 概念

[在 Lync Server 2013 中部署客户端和设备](lync-server-2013-deploying-clients-and-devices.md)

