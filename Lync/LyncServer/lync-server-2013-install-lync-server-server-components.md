---
title: Lync Server 2013：安装 Lync Server 服务器组件
TOCTitle: 安装 Lync Server 服务器组件
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398239(v=OCS.15)
ms:contentKeyID: 49312140
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 安装适用于 Lync Server 2013 的服务器组件

 

_**上一次修改主题：** 2014-05-05_

在执行这些步骤之前，请确保使用属于本地管理员和 Active Directory 中 RTCUniversalReadOnlyAdmins 组的成员的域用户帐户登录服务器。

Lync Server 部署向导 用于安装每个 Lync 服务器角色所需的组件和激活服务器。此文章指导您完成在 Lync 基础结构中部署 Standard Edition Server或前端服务器 的步骤。

## 安装 Lync Server 组件

1.  如果 Lync Server 部署向导没有运行，请在要安装 Lync 的服务器上启动它。

2.  单击“安装或更新 Lync Server 系统”。

3.  在部署向导中，确认“步骤 1：安装本地配置存储”是否具有绿色复选标记，此标记表示此服务器已成功安装存储的本地副本。如果未选中，您需要在服务器上安装本地配置存储。按照[在 Lync Server 2013 中安装本地配置存储](lync-server-2013-install-the-local-configuration-store.md)中的步骤执行操作，然后返回这里。

4.  当您准备好在服务器上安装 Lync Server 2013 组件时，请单击“步骤 2：安装或删除 Lync Server 组件”旁边的“运行”。

5.  在“安装 Lync Server 组件”页上，单击“下一步”根据发布的拓扑中的定义安装组件。

6.  “正在执行命令”页将显示安装过程中的命令和安装信息摘要。完成后，可以使用列表选择要查看的日志，然后单击“查看日志”。

7.  当 Lync Server 2013 组件安装完成并且您已根据需要查看日志后，请单击“完成”以完成安装中的此步骤。
    
    > [!NOTE]  
    > 如果提示重新启动服务器（如果需要安装 Windows 桌面体验则可能会发生这种情况），请执行此操作。如果计算机已备份并且正在运行，您需要从上面列出的步骤 3 开始再次执行这些步骤（基本上是再次运行部署向导中的步骤 2）。
    

