---
title: 升级或更新后端服务器或标准版服务器
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
ms.openlocfilehash: 0526cc7ba6a6abefd066bf07d845ffed3a4107ca
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="50c1e-102">在 Lync Server 2013 中升级或更新后端服务器或标准版服务器</span><span class="sxs-lookup"><span data-stu-id="50c1e-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50c1e-103">_**主题上次修改时间：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="50c1e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="50c1e-104">本主题介绍如何在企业版后端服务器或标准版服务器上安装更新。</span><span class="sxs-lookup"><span data-stu-id="50c1e-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="50c1e-105">如果后端服务器在升级后至少30分钟，则用户可能会进入恢复模式。</span><span class="sxs-lookup"><span data-stu-id="50c1e-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="50c1e-106">升级完成且后端服务器再次与池中的前端服务器连接时，用户将返回到完整功能。</span><span class="sxs-lookup"><span data-stu-id="50c1e-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="50c1e-107">如果升级所用时间少于 30 分钟，则用户不会受到影响。</span><span class="sxs-lookup"><span data-stu-id="50c1e-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="50c1e-108">更新后端服务器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="50c1e-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="50c1e-109">以 CsAdministrator 角色的成员身份登录到要升级的服务器。</span><span class="sxs-lookup"><span data-stu-id="50c1e-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="50c1e-110">下载更新并将其提取到本地硬盘。</span><span class="sxs-lookup"><span data-stu-id="50c1e-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="50c1e-111">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="50c1e-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="50c1e-112">停止 Lync 服务器服务。</span><span class="sxs-lookup"><span data-stu-id="50c1e-112">Stop Lync Server services.</span></span> <span data-ttu-id="50c1e-113">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="50c1e-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="50c1e-114">停止万维网服务。</span><span class="sxs-lookup"><span data-stu-id="50c1e-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="50c1e-115">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="50c1e-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="50c1e-116">关闭所有 Lync Server Management Shell 窗口。</span><span class="sxs-lookup"><span data-stu-id="50c1e-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="50c1e-117">安装该更新。</span><span class="sxs-lookup"><span data-stu-id="50c1e-117">Install the update.</span></span>

8.  <span data-ttu-id="50c1e-118">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="50c1e-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="50c1e-119">再次停止 Lync Server 服务以捕获全局程序集缓存（GAC）-d 程序集。</span><span class="sxs-lookup"><span data-stu-id="50c1e-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="50c1e-120">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="50c1e-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="50c1e-121">重新启动万维网服务。</span><span class="sxs-lookup"><span data-stu-id="50c1e-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="50c1e-122">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="50c1e-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="50c1e-123">通过执行下列操作之一将 LyncServerUpdateInstaller 所做的更改应用到 SQL Server 数据库：</span><span class="sxs-lookup"><span data-stu-id="50c1e-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="50c1e-124">如果这是企业版后端服务器，并且此服务器上没有 collocated 数据库（如 "存档" 或 "监视数据库"），请在命令行中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="50c1e-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="50c1e-125">如果这是企业版后端服务器，并且此服务器上有 collocated 数据库，请在命令行中键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="50c1e-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="50c1e-126">如果这是标准版服务器，请在命令行键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="50c1e-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

