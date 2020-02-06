---
title: 准备单个 Standard Edition Server（调用）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 "执行命令" 页面上，安装 SQL Server Express 和配置以充当中央管理存储的任务可以在任务窗格中查看。 默认情况下，将创建名为 "RTC" 的基于 SQL Server 的数据库实例。 还会创建防火墙规则，以允许服务器和客户端与数据库和实例通信的入站和出站访问。 任务完成后，您可以从下拉列表中选择日志文件。 日志文件被命名为 "引导本地计算机"。 选择日志文件后，单击 "查看日志"。 查看日志文件，查看是否有任何错误和警告。 准备好继续时，单击 "完成"。 现在，你应该使用拓扑生成器定义拓扑（如果尚未执行此操作）。
ms.openlocfilehash: 0a1b8245df8e50ba4da73c98e9dcb865446a0ecc
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796963"
---
# <a name="prepare-single-standard-edition-server-invoke"></a>准备单个 Standard Edition Server（调用）
 
在 "**执行命令**" 页面上，安装 SQL Server Express 和配置以充当中央管理存储的任务可以在任务窗格中查看。 默认情况下，将创建名为 "RTC" 的基于 SQL Server 的数据库实例。 还会创建防火墙规则，以允许服务器和客户端与数据库和实例通信的入站和出站访问。 任务完成后，您可以从下拉列表中选择日志文件。 日志文件被命名为 "**引导本地计算机**"。 选择日志文件后，单击 "**查看日志**"。 查看日志文件，查看是否有任何错误和警告。 准备好继续时，单击 "**完成"。** 现在，你应该使用拓扑生成器定义拓扑（如果尚未执行此操作）。
  
> [!IMPORTANT]
> SQL Server Express 安装可能需要一些时间才能完成。 在安装期间，屏幕或任务窗格上不显示进度。 若要监视安装，应使用 Windows 任务管理器，查找 MSIExec 进程和 SQL Server 的安装文件。 通过这种方式，您可以查看安装的状态，并确保安装正在继续。 根据本帮助主题范围之外的因素，安装 SQL Server 实例最多可能需要15分钟的时间才能完成。 
  

