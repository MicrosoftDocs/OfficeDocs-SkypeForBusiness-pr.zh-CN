---
title: SQL Server Reporting Services（调用）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: 向 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 报告服务提供部署监控服务器报告所需的信息后，"执行命令"页将显示为将报告安装到 SQL Server Reporting Services 而发出的命令摘要。
ms.openlocfilehash: eac8b7884859c0b5b14218471054533eedb6d481
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829532"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="e585f-103">SQL Server Reporting Services（调用）</span><span class="sxs-lookup"><span data-stu-id="e585f-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="e585f-104">向 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 报告服务提供部署监控服务器报告所需的信息后，"执行命令"页将显示为将报告安装到 SQL Server Reporting Services 而发出的命令摘要。</span><span class="sxs-lookup"><span data-stu-id="e585f-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="e585f-p101">检查命令摘要，注意这些命令中显示的任何错误或警告消息。如果生成了日志文件，请从摘要窗口下的下拉列表中选择日志文件，然后单击 **“查看日志”** 以显示日志文件。</span><span class="sxs-lookup"><span data-stu-id="e585f-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e585f-107">若要使 Reporting Services 报告成功部署，且在部署完成后访问报告，您必须具有 TCP/IP 端口 80 (，并且（可选）TCP 端口 443 用于 SSL（如果将证书分配给 Reporting Services) ，则 SQL Server 上的 Windows 防火墙中打开了该证书。</span><span class="sxs-lookup"><span data-stu-id="e585f-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="e585f-108">有关详细信息，请参阅 [配置 Windows 防火墙](https://go.microsoft.com/fwlink/p/?linkId=218031) 以允许 SQL Server 2008 R2 Microsoft SQL Server访问。</span><span class="sxs-lookup"><span data-stu-id="e585f-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="e585f-109">查看摘要后，单击"完成"以完成报告到 SQL Server Reporting Services 的安装。</span><span class="sxs-lookup"><span data-stu-id="e585f-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

