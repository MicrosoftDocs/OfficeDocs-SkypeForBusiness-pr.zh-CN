---
title: 升级或更新后端服务器或 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193075"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="42a52-102">在 Lync Server 2013 中升级或更新后端服务器或 Standard Edition 服务器</span><span class="sxs-lookup"><span data-stu-id="42a52-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42a52-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="42a52-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="42a52-104">本主题介绍如何在企业版后端服务器或 Standard Edition server 上安装更新。</span><span class="sxs-lookup"><span data-stu-id="42a52-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="42a52-p101">如果在您升级后端服务器时它至少要停机 30 分钟，则用户可能会进入恢复能力模式。升级完成，且后端服务器又与池中的前端服务器连接后，用户会返回到全部功能。如果升级所用时间少于 30 分钟，将不会对用户造成影响。</span><span class="sxs-lookup"><span data-stu-id="42a52-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="42a52-108">更新后端服务器或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="42a52-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="42a52-109">以 CsAdministrator 角色的成员身份登录到要升级的服务器。</span><span class="sxs-lookup"><span data-stu-id="42a52-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="42a52-110">下载更新并将其提取到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="42a52-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="42a52-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42a52-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="42a52-p102">停止 Lync Server 服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="42a52-p102">Stop Lync Server services. At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="42a52-p103">停止万维网服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="42a52-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="42a52-116">关闭所有 Lync Server 命令行管理程序窗口。</span><span class="sxs-lookup"><span data-stu-id="42a52-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="42a52-117">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="42a52-117">Install the update.</span></span>

8.  <span data-ttu-id="42a52-118">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42a52-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="42a52-p104">再次停止 Lync Server 服务以缓存全局程序集缓存 (GAC) –d 程序集。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="42a52-p104">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies. At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="42a52-p105">重新启动万维网服务。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="42a52-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="42a52-123">通过执行以下操作之一将 LyncServerUpdateInstaller.exe 进行的更改应用于 SQL Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="42a52-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="42a52-124">如果这是企业版后端服务器，并且此服务器上没有并置数据库（如存档或监控数据库），则在命令行中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="42a52-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="42a52-125">如果这是企业版后端服务器，并且此服务器上有并置数据库，请在命令行中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="42a52-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="42a52-126">如果这是标准版服务器，请在命令行中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="42a52-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

