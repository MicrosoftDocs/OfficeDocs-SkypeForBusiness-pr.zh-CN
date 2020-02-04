---
title: SQL Server Reporting Services（调用）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
ROBOTS: NOINDEX, NOFOLLOW
description: 在为将监视服务器报告部署到 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012 报表服务提供所需的信息后，"执行页面" 命令将显示为安装该程序所发出命令的摘要报告到 SQL Server Reporting Services。
ms.openlocfilehash: 970b570c2fba75cf1afe4f4a217e809eb62a7411
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691667"
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="08896-103">SQL Server Reporting Services（调用）</span><span class="sxs-lookup"><span data-stu-id="08896-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="08896-104">在为将监视服务器的部署报告部署到 Microsoft SQL Server 报表服务提供所需信息之后，"执行页面" 命令将显示为将报告安装到 SQL Server 报告而发出的命令的摘要服务.</span><span class="sxs-lookup"><span data-stu-id="08896-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="08896-p101">检查命令摘要，注意这些命令中显示的任何错误或警告消息。如果生成了日志文件，请从摘要窗口下的下拉列表中选择日志文件，然后单击“**查看日志**”以显示日志文件。</span><span class="sxs-lookup"><span data-stu-id="08896-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="08896-107">为了使 Reporting Services 报表能够成功部署，并且在部署完成后访问报告，你必须具有 TCP/IP 端口80（如果你将证书分配到 Reporting Services，则还必须使用 TCP 端口443）在 SQL Server 上使用高级安全性的 Windows 防火墙中打开。</span><span class="sxs-lookup"><span data-stu-id="08896-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="08896-108">有关详细信息，请参阅[将 Windows 防火墙配置为允许](https://go.microsoft.com/fwlink/p/?linkId=218031)Microsoft sql Server 2008 R2 的 SQL server Access。</span><span class="sxs-lookup"><span data-stu-id="08896-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="08896-109">查看摘要后，单击 "**完成**" 以完成报表到 SQL Server Reporting Services 的安装。</span><span class="sxs-lookup"><span data-stu-id="08896-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

