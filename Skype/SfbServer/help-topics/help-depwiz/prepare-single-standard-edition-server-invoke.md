---
title: 准备单个 Standard Edition Server（调用）
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
description: 在"正在执行命令"页上，可以在任务窗格中SQL Server Express安装和配置充当中央管理存储的任务。 默认情况下，将创建基于 SQL Server 数据库（名为 RTC）的实例。 还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。 完成任务后，可从下拉列表中选择日志文件。 日志文件名为“Bootstrap local machine”。 选择此日志文件后，单击“查看日志”。 在日志文件中查看任何错误和警告信息。 准备好继续操作时，单击“完成”。 如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。
ms.openlocfilehash: fbb66e6e79b25fed8db266f727fb33a0d68bce1c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62410265"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>准备单个 Standard Edition Server（调用）
 
在 **"正在执行命令**"页上，可以在任务窗格中SQL Server Express安装和配置用作中央管理存储的任务。 默认情况下，将创建基于 SQL Server 数据库（名为 RTC）的实例。 还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。 完成任务后，可从下拉列表中选择日志文件。 日志文件名为“Bootstrap local machine”。 选择此日志文件后，单击“查看日志”。 在日志文件中查看任何错误和警告信息。 准备好继续操作时，单击“完成”。 如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。
  
> [!IMPORTANT]
> 安装 SQL Server Express可能需要一些时间才能完成。 安装期间，屏幕或任务窗格上不会显示安装进度。 若要监视安装，您应Windows任务管理器，并查找 MSIExec 进程和安装程序文件SQL Server。 这样就可以查看安装状态并确保安装正在进行。 根据此帮助主题范围以外的因素，可能需要 15 分钟或更完整的时间才能完成安装SQL Server实例。 
  

