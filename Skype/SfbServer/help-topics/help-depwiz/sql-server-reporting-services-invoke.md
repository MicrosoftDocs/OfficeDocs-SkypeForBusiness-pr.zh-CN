---
title: SQL Server Reporting Services（调用）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSInvoke
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4a4ba8d6-ba43-45b3-b834-372d092561e7
description: 监视服务器的部署报告给 Microsoft SQL Server 2008 R2，或者 Microsoft SQL Server 2012年报表服务，到页上执行命令显示的摘要发出要安装的命令提供所需的信息之后对 SQL Server 报表服务的报告。
ms.openlocfilehash: 54be791fb026d3268ce8b33ea4c82fe5fd1374df
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sql-server-reporting-services-invoke"></a><span data-ttu-id="1767a-103">SQL Server Reporting Services（调用）</span><span class="sxs-lookup"><span data-stu-id="1767a-103">SQL Server Reporting Services (Invoke)</span></span>
 
<span data-ttu-id="1767a-104">监视服务器的部署报告给 Microsoft SQL Server 2008 R2，或者 Microsoft SQL Server 2012年报表服务，到页上执行命令显示的摘要发出要安装的命令提供所需的信息之后对 SQL Server 报表服务的报告。</span><span class="sxs-lookup"><span data-stu-id="1767a-104">After supplying the required information for the deployment of the Monitoring Server reports to the Microsoft SQL Server 2008 R2, or to Microsoft SQL Server 2012 Report Services, the page Execute Commands displays a summary of commands that are issued to install the reports to the SQL Server Reporting Services.</span></span>
  
<span data-ttu-id="1767a-p101">检查命令摘要，注意这些命令中显示的任何错误或警告消息。如果生成了日志文件，请从摘要窗口下的下拉列表中选择日志文件，然后单击“**查看日志**”以显示日志文件。</span><span class="sxs-lookup"><span data-stu-id="1767a-p101">Review the summary of commands and note any error or warning messages displayed from the commands. If a log file is generated, select the log file from the drop-down list under the summary window, and click **View Log** to display the log file.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1767a-107">若要成功部署，并在部署完成后访问报表的报表服务报表，您必须有 TCP/IP 在 Windows 防火墙中打开端口 80 （和 （可选） 用于 SSL，如果您将证书分配给报告服务的 TCP 端口 443）在 SQL Server 上的高级安全性。</span><span class="sxs-lookup"><span data-stu-id="1767a-107">For the Reporting Services reports to deploy successfully, and to access the reports after deployment is complete, you must have TCP/IP port 80 (and optionally, TCP port 443 for SSL, if you assign a certificate to the Reporting Services) open in the Windows Firewall with Advanced Security on the SQL Server.</span></span> <span data-ttu-id="1767a-108">有关详细信息，请参见[配置 Windows 防火墙允许 SQL Server 访问](https://go.microsoft.com/fwlink/p/?linkId=218031)Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1767a-108">For details, see [Configure the Windows Firewall to Allow SQL Server Access](https://go.microsoft.com/fwlink/p/?linkId=218031) for Microsoft SQL Server 2008 R2.</span></span>
  
<span data-ttu-id="1767a-109">复查摘要，然后单击**完成**以完成安装的 SQL Server 报告服务的报告。</span><span class="sxs-lookup"><span data-stu-id="1767a-109">After reviewing the summary, click **Finish** to complete the installation of the reports to the SQL Server Reporting Services.</span></span>
  

