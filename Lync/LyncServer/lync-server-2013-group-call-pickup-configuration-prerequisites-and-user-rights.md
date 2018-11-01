---
title: 组内呼叫应答配置先决条件和用户权限
TOCTitle: 组内呼叫应答配置先决条件和用户权限
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945641(v=OCS.15)
ms:contentKeyID: 52061065
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 组内呼叫应答配置先决条件和用户权限

 

_**上一次修改主题：** 2013-01-30_

组内呼叫应答是在您部署企业语音时默认安装的一项呼叫管理功能。本主题介绍配置组内呼叫应答之前需具备的条件，以及执行配置任务所需的用户权限。

本节假定您已阅读与组内呼叫应答相关的规划文档（请参阅[规划组内呼叫应答](lync-server-2013-planning-for-group-call-pickup.md)）。

## 组内呼叫应答配置先决条件

组内呼叫应答需要以下组件：

  - 应用程序服务

  - 呼叫寄存应用程序

部署企业语音时，会自动安装这些组件。

## 组内呼叫应答配置用户权限

可以使用以下管理工具配置组内呼叫应答：

  - Lync Server 命令行管理程序

  - SEFAUtil 资源工具包工具

使用 Lync Server 命令行管理程序在呼叫寄存轨道表中创建和管理呼叫应答组。使用 SEFAUtil 资源工具包工具分配呼叫应答组以及为用户启用或禁用组内呼叫应答。

配置组内呼叫应答需要以下任一管理角色，具体取决于任务：

  - **CsVoiceAdministrator：** 此管理员角色可以创建、配置和管理所有语音相关的设置和策略。

  - **CsUserAdministrator：** 此管理员角色可以为用户启用组内呼叫应答。此管理员角色还具有对所有语音配置的只读查看访问权限。

  - **CsServerAdministrator：** 此管理员角色可以管理、监控服务器和服务，以及排除服务器和服务的故障。

  - **CsAdministrator：** 此管理员角色可以执行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有任务。

> [!NOTE]  
> 有关管理权限的详细信息，请参阅规划文档中的<a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。



## 另请参阅

#### 概念

[在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)  

#### 其他资源

[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)

