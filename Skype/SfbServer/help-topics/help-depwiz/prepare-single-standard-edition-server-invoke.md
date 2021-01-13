---
title: 准备单个 Standard Edition Server（调用）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在"正在执行命令"页上，可以在任务窗格中查看安装 SQL Server Express 并配置为充当中央管理存储的任务。 默认情况下，将创建一SQL Server名为 RTC 的基于数据库的实例。 还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。 完成任务后，可从下拉列表中选择日志文件。 日志文件名为“Bootstrap local machine”。 选择此日志文件后，单击“查看日志”。 在日志文件中查看任何错误和警告信息。 准备好继续操作时，单击“完成”。 如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。
ms.openlocfilehash: adf980ec2576eb4e23983fcd99befb1fc6bfb6ee
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829742"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>准备单个 Standard Edition Server（调用）
 
在 **"正在执行命令** "页上，可以在任务窗格中查看安装 SQL Server Express 并配置为充当中央管理存储的任务。 默认情况下，将创建一SQL Server名为 RTC 的基于数据库的实例。 还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。 完成任务后，可从下拉列表中选择日志文件。 日志文件名为“Bootstrap local machine”。 选择此日志文件后，单击“查看日志”。 在日志文件中查看任何错误和警告信息。 准备好继续操作时，单击“完成”。 如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。
  
> [!IMPORTANT]
> 安装 SQL Server Express 可能需要一些时间才能完成。 安装期间，屏幕或任务窗格上不会显示安装进度。 若要监视安装，您应使用 Windows 任务管理器并查找 MSIExec 进程和安装程序文件SQL Server。 这样就可以查看安装状态并确保安装正在进行。 根据此帮助主题范围以外的因素，可能需要 15 分钟或SQL Server安装实例。 
  

