---
title: 准备一个标准版服务器 （调用）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在执行命令页，可以在任务窗格中查看安装 SQL Server Express 和配置作为中央管理存储的任务。 默认情况下，创建的名为 RTC 的基于 SQL Server 的数据库实例。 此外可以创建防火墙规则以允许入站和出站访问服务器和客户端与数据库和实例进行通信。 在任务完成后，您可以从下拉列表中选择日志文件。 启动本地计算机命名为日志文件。 选择日志文件之后, 单击查看日志。 检查所有错误和警告的日志文件。 当准备好继续时，单击完成。 如果您有不这样做，现在应该定义拓扑结构与拓扑生成器。
ms.openlocfilehash: d900c383d0f434176ff18b3f310c41042df75b2e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="prepare-single-standard-edition-server-invoke"></a>准备一个标准版服务器 （调用）
 
在**执行命令**页中，可以在任务窗格中查看安装 SQL Server Express 和配置作为中央管理存储的任务。 默认情况下，创建的名为 RTC 的基于 SQL Server 的数据库实例。 此外可以创建防火墙规则以允许入站和出站访问服务器和客户端与数据库和实例进行通信。 在任务完成后，您可以从下拉列表中选择日志文件。 **启动本地计算机**命名为日志文件。 选择日志文件之后, 单击**查看日志**。 检查所有错误和警告的日志文件。 当准备好继续时，单击**完成。** 如果您有不这样做，现在应该定义拓扑结构与拓扑生成器。
  
> [!IMPORTANT]
> SQL Server Express 安装可能需要一些时间才能完成。 安装期间，没有任何进度屏幕或任务窗格上的可见。 要监视安装，应使用 Windows 任务管理器并查找 SQL Server MSIExec 进程和安装程序文件。 以这种方式，您可以查看安装状态并确保安装正在进行。 根据此帮助主题的范围之外的因素，它可以需要长达 15 分钟或更多安装 SQL Server 的实例来完成。 
  

