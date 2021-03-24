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
description: 向 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 报告服务提供部署监控服务器报告所需的信息后，"执行命令"页将显示为将报告安装到 SQL Server Reporting Services 而发出的命令的摘要。
ms.openlocfilehash: 17824f79ab0d710d4969d736b864912b424abaa9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109658"
---
# <a name="sql-server-reporting-services-invoke"></a>SQL Server Reporting Services（调用）
 
向 Microsoft SQL Server 报告服务提供部署监控服务器报告所需的信息后，"执行命令"页将显示为将报告安装到 SQL Server Reporting Services 而发出的命令的摘要。
  
检查命令摘要，注意这些命令中显示的任何错误或警告消息。如果生成了日志文件，请从摘要窗口下的下拉列表中选择日志文件，然后单击 **“查看日志”** 以显示日志文件。
  
> [!IMPORTANT]
> 若要使 Reporting Services 报告成功部署，且在部署完成后访问报告，必须具有 TCP/IP 端口 80 (并且（可选）TCP 端口 443（对于 SSL）（如果向 SQL Server 上的高级安全 Windows 防火墙中打开的 Reporting Services) 分配证书）。 有关详细信息，请参阅 [Configure the Windows Firewall to Allow SQL Server Access](/sql/sql-server/install/configure-the-windows-firewall-to-allow-sql-server-access) for Microsoft SQL Server 2008 R2。
  
查看摘要后，单击"完成"以完成报告到 SQL Server Reporting Services 的安装。
