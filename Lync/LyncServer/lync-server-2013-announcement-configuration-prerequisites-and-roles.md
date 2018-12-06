---
title: Lync Server 2013：通知配置先决条件和角色
TOCTitle: 通知配置先决条件和角色
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398658(v=OCS.15)
ms:contentKeyID: 49313444
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的通知配置先决条件和角色

 

_**上一次修改主题：** 2013-02-25_

通知是一种 企业语音呼叫管理功能。本主题介绍配置通知和执行配置任务所需角色分配之前的准备事项。

本节假定您已经阅读过与通知相关的规划文档（请参阅 [在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)）。

## 通知配置的先决条件

通知应用程序需要以下组件：

  - 应用程序服务

  - 响应组应用程序

  - 文件存储（用于保存音频文件）

在部署 企业语音时，默认情况下将安装所有这些组件。

## 通知配置角色

可以使用以下管理工具配置通知：

  - Lync Server 控制面板

  - Lync Server 命令行管理程序

配置 通知应用程序需要以下管理角色之一：

  - **CsVoiceAdministrator** 此管理员角色可以创建、配置和管理所有语音相关的设置和策略，包括通知设置。

  - **CsServerAdministrator** 此管理员角色可以管理和监控服务器和服务，并排除其故障，还可以配置所有通知设置。

  - **CsAdministrator** 此管理员角色可以执行所有管理任务和修改所有设置。

  - **CsViewOnlyAdministrator** 此管理员角色可以查看部署以监控部署运行状况。

> [!NOTE]  
> 有关管理用户权限的详细信息，请参阅规划文档中的 <a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。



## 另请参阅

#### 概念

[在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)  

#### 其他资源

[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)

