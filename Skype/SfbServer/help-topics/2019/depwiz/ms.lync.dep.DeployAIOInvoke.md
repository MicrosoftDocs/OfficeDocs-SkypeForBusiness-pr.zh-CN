---
title: 准备单个 Standard Edition Server（调用）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 5da0aa73-8bf8-41f3-81e7-94f955cda541
ROBOTS: NOINDEX, NOFOLLOW
description: 在"正在执行命令"页上，可以在任务窗格中SQL Server Express安装和配置用作中央管理存储的任务。 默认情况下，将创建基于 SQL Server数据库（名为 RTC）的实例。 还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。 完成任务后，可从下拉列表中选择日志文件。 日志文件名为“Bootstrap local machine”。 选择此日志文件后，单击“查看日志”。 在日志文件中查看任何错误和警告信息。 准备好继续操作时，单击“完成”。 如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。
ms.openlocfilehash: b218fe92f46fb930dda7ffdc3c52dc986447ad7ef14f1f6ff93c70837e21aa3d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54292140"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>准备单个 Standard Edition Server（调用）
 
在 **"正在执行命令**"页上，可以在任务窗格中SQL Server Express安装和配置用作中央管理存储的任务。 默认情况下，将创建基于 SQL Server数据库（名为 RTC）的实例。 还会创建防火墙规则，以允许对服务器和客户端的入站和出站访问，从而与数据库和实例进行通信。 完成任务后，可从下拉列表中选择日志文件。 日志文件名为“Bootstrap local machine”。 选择此日志文件后，单击“查看日志”。 在日志文件中查看任何错误和警告信息。 准备好继续操作时，单击“完成”。 如果尚未定义拓扑生成器，现在应该使用拓扑生成器定义拓扑。
  
> [!IMPORTANT]
> 安装 SQL Server Express可能需要一些时间才能完成。 安装期间，屏幕或任务窗格上不会显示安装进度。 若要监视安装，您应Windows任务管理器，并查找 MSIExec 进程和安装程序文件SQL Server。 这样就可以查看安装状态并确保安装正在进行。 根据本帮助主题范围以外的因素，安装此实例可能需要 15 分钟或SQL Server才能完成。 
  

