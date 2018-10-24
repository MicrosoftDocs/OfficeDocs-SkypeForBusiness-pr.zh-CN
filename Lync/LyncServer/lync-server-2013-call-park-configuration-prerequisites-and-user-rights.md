---
title: Lync Server 2013：呼叫寄存配置先决条件和用户权限
TOCTitle: 呼叫寄存配置先决条件和用户权限
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425730(v=OCS.15)
ms:contentKeyID: 49312281
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫寄存配置先决条件和用户权限

 

_**上一次修改主题：** 2012-09-10_

呼叫寄存是部署 企业语音时默认安装的一项呼叫管理功能。本主题介绍配置 呼叫寄存之前必须具备的条件，以及执行配置任务所需的用户权限。

> [!IMPORTANT]  
> 呼叫寄存应用程序的自定义保持音乐在 Lync Server 2013 灾难恢复过程中不会得到备份，如果上载到池的文件已破坏、损坏或擦除，这些文件将会丢失。应始终单独保留一份为 呼叫寄存上载的自定义保持音乐文件的备份副本。


本节假设您已阅读有关呼叫寄存的规划文档（请参阅[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)）。

## 呼叫寄存配置先决条件

呼叫寄存需要以下组件：

  - 应用程序服务

  - 呼叫寄存应用程序

部署 企业语音时，会自动安装这些组件。

如果希望呼叫者在呼叫寄存时可以听到音乐，还需要保持音乐文件。部署 企业语音时，会自动安装默认的保持音乐文件。可以使用自己的保持音乐文件替换默认文件。 呼叫寄存使用文件存储保存音频文件。

## 呼叫寄存配置用户权限

可以使用以下管理工具配置 呼叫寄存：

  - Lync Server 控制面板

  - Lync Server 命令行管理程序

使用这些工具设置 呼叫寄存通道表和配置 呼叫寄存使用的其他设置。

配置 呼叫寄存可能需要以下任何管理角色，具体取决于任务：

  - **CsVoiceAdministrator ：** 此管理员角色可以创建、配置和管理所有语音相关的设置和策略。

  - **CsUserAdministrator ：** 此管理员角色可以在语音策略中启用 呼叫寄存。此管理员角色还具有对所有语音配置的只读访问权限。

  - **CsServerAdministrator ：** 此管理员角色可以管理、监控服务器和服务，以及排除服务器和服务的故障。

  - **CsAdministrator ：** 此管理员角色可以执行 CsVoiceAdministrator、CsServerAdministrator 和 CsUserAdministrator 的所有任务。

> [!NOTE]  
> 有关管理权限的详细信息，请参阅规划文档中的<a href="lync-server-2013-planning-for-role-based-access-control.md">在 Lync Server 2013 中规划基于角色的访问控制</a>。



## 另请参阅

#### 概念

[在 Lync Server 2013 中部署企业语音](lync-server-2013-deploying-enterprise-voice.md)  

#### 其他资源

[在 Lync Server 2013 中规划呼叫管理功能](lync-server-2013-planning-for-call-management-features.md)

