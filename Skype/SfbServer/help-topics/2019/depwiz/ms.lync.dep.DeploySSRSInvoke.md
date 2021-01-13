---
title: SQL Server Reporting Services（调用）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
ROBOTS: NOINDEX, NOFOLLOW
description: 向 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 报告服务提供部署监控服务器报告所需的信息后，"执行命令"页将显示为将报告安装到 SQL Server Reporting Services 而发出的命令摘要。
ms.openlocfilehash: 560bda7437103db9ca322176c8cf98340a611f05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808782"
---
# <a name="sql-server-reporting-services-invoke"></a>SQL Server Reporting Services（调用）
 
向 Microsoft SQL Server 报告服务提供部署监控服务器报告所需的信息后，"执行命令"页将显示为将报告安装到 SQL Server Reporting Services 而发出的命令摘要。
  
检查命令摘要，注意这些命令中显示的任何错误或警告消息。如果生成了日志文件，请从摘要窗口下的下拉列表中选择日志文件，然后单击 **“查看日志”** 以显示日志文件。
  
> [!IMPORTANT]
> 若要使 Reporting Services 报告成功部署，且在部署完成后访问报告，您必须具有 TCP/IP 端口 80 (，并且（可选）TCP 端口 443 用于 SSL（如果将证书分配给 Reporting Services) ，则 SQL Server 上的 Windows 防火墙中打开了该证书。 有关详细信息，请参阅 [配置 Windows 防火墙](https://go.microsoft.com/fwlink/p/?linkId=218031) 以允许 SQL Server 2008 R2 Microsoft SQL Server访问。
  
查看摘要后，单击"完成"以完成报告到 SQL Server Reporting Services 的安装。
  

