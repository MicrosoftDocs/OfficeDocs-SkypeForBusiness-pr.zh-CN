---
title: 'Lync Server 2013: 正在准备还原 Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="38553-102">准备还原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38553-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38553-103">_**主题上次修改时间:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="38553-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="38553-104">在出现故障后开始还原服务器和数据库之前, 需要确定以下事项:</span><span class="sxs-lookup"><span data-stu-id="38553-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="38553-105">需要还原哪些内容。</span><span class="sxs-lookup"><span data-stu-id="38553-105">What needs to be restored.</span></span>

  - <span data-ttu-id="38553-106">您需要恢复的硬件、软件、数据和工具。</span><span class="sxs-lookup"><span data-stu-id="38553-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="38553-107">确定要还原的内容</span><span class="sxs-lookup"><span data-stu-id="38553-107">Determining What to Restore</span></span>

<span data-ttu-id="38553-108">本主题介绍如何还原在服务器、池或中央管理存储级别发生的 Lync 服务器中断。</span><span class="sxs-lookup"><span data-stu-id="38553-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="38553-109">如果中央管理存储失败, 则 Lync Server 部署将继续正常运行, 但不能更改任何配置。</span><span class="sxs-lookup"><span data-stu-id="38553-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="38553-110">如果后端服务器或标准版服务器出现故障, 用户池将停止运行。</span><span class="sxs-lookup"><span data-stu-id="38553-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="38553-111">如果任何其他服务器出现故障, 则故障的大小取决于服务器运行的服务器角色以及服务器托管一个还是多个数据库。</span><span class="sxs-lookup"><span data-stu-id="38553-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="38553-112">还原内容</span><span class="sxs-lookup"><span data-stu-id="38553-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="38553-113">如果此操作失败</span><span class="sxs-lookup"><span data-stu-id="38553-113">If this failed</span></span></th>
<th><span data-ttu-id="38553-114">请参阅以下部分:</span><span class="sxs-lookup"><span data-stu-id="38553-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="38553-115">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="38553-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="38553-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">在 Lync Server 2013 中还原标准版服务器</a></span><span class="sxs-lookup"><span data-stu-id="38553-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38553-117">中央管理存储</span><span class="sxs-lookup"><span data-stu-id="38553-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="38553-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">在 Lync Server 2013 中还原托管中央管理存储的服务器</a></span><span class="sxs-lookup"><span data-stu-id="38553-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38553-119">企业版后端</span><span class="sxs-lookup"><span data-stu-id="38553-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="38553-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync Server 2013 中还原企业版后端服务器</a></span><span class="sxs-lookup"><span data-stu-id="38553-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38553-121">企业版镜像后端主服务器</span><span class="sxs-lookup"><span data-stu-id="38553-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="38553-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">在 Lync Server 2013 中还原镜像的企业版后端服务器-主要</a></span><span class="sxs-lookup"><span data-stu-id="38553-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38553-123">企业版镜像后端辅助服务器</span><span class="sxs-lookup"><span data-stu-id="38553-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="38553-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013 中还原镜像的企业版后端服务器-镜像</a></span><span class="sxs-lookup"><span data-stu-id="38553-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38553-125">任何运行服务器角色的企业版服务器, 如前端服务器、边缘服务器、控制器、中介服务器、或持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="38553-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="38553-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync Server 2013 中还原企业版成员服务器</a></span><span class="sxs-lookup"><span data-stu-id="38553-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38553-127">整个 Lync 服务器池</span><span class="sxs-lookup"><span data-stu-id="38553-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="38553-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">在 Lync Server 2013 中还原 Lync 服务器池</a></span><span class="sxs-lookup"><span data-stu-id="38553-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38553-129">企业版文件存储</span><span class="sxs-lookup"><span data-stu-id="38553-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="38553-130"><a href="lync-server-2013-restoring-a-file-store.md">在 Lync Server 2013 中还原文件存储</a></span><span class="sxs-lookup"><span data-stu-id="38553-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="38553-131">独立监视数据库或存档数据库</span><span class="sxs-lookup"><span data-stu-id="38553-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="38553-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">在 Lync Server 2013 中还原监视或存档数据</a></span><span class="sxs-lookup"><span data-stu-id="38553-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="38553-133">独立的持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="38553-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="38553-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">在 Lync Server 2013 中还原永久聊天数据</a></span><span class="sxs-lookup"><span data-stu-id="38553-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="38553-135">收集硬件、软件和工具</span><span class="sxs-lookup"><span data-stu-id="38553-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="38553-136">还原服务器时, 需要从新的或全新的计算机开始。</span><span class="sxs-lookup"><span data-stu-id="38553-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="38553-137">此外, 你必须具有以下可用硬件和软件:</span><span class="sxs-lookup"><span data-stu-id="38553-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="38553-138">具有与失败的服务器相同的完全限定的域名 (FQDN) 的全新服务器或新服务器。</span><span class="sxs-lookup"><span data-stu-id="38553-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="38553-139">在安装操作系统时, 请确保不要删除 Active Directory 域服务中的计算机帐户, 并验证是否保留帐户的组权限。</span><span class="sxs-lookup"><span data-stu-id="38553-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="38553-140">操作系统的安装软件。</span><span class="sxs-lookup"><span data-stu-id="38553-140">Installation software for the operating system.</span></span> <span data-ttu-id="38553-141">若要安装操作系统, 请使用服务器部署过程和由你的组织建立的配置。</span><span class="sxs-lookup"><span data-stu-id="38553-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="38553-142">还原服务时, 应具备这些过程和配置要求。</span><span class="sxs-lookup"><span data-stu-id="38553-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="38553-143">SQL Server 2012 或 SQL Server 2008 R2 的安装软件。</span><span class="sxs-lookup"><span data-stu-id="38553-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="38553-144">若要安装数据库服务器, 请使用相应版本的 SQL Server 和由你的组织建立的数据库服务器部署过程和配置。</span><span class="sxs-lookup"><span data-stu-id="38553-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="38553-145">还原服务时, 应具备这些过程和配置要求。</span><span class="sxs-lookup"><span data-stu-id="38553-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38553-146">在安装本地配置存储时, Lync Server 部署向导会在每个标准版服务器和任何其他 Lync Server 服务器上自动安装 SQL Server 2012 Express, 除非已预安装 SQL Server 2012 或 SQL Server 2008 R2服务器。</span><span class="sxs-lookup"><span data-stu-id="38553-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="38553-147">用于拍摄系统映像的软件。</span><span class="sxs-lookup"><span data-stu-id="38553-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="38553-148">我们建议你在安装操作系统和 SQL Server 之后以及开始还原之前获取系统的映像副本, 以便你可以将此映像用作回退点, 以防还原过程中出现错误。</span><span class="sxs-lookup"><span data-stu-id="38553-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="38553-149">Lync Server 2013 安装软件。</span><span class="sxs-lookup"><span data-stu-id="38553-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="38553-150">Lync Server 部署向导位于 Lync Server 安装文件夹或位于\\安装\\amd64\\setup.exe 的媒体中。</span><span class="sxs-lookup"><span data-stu-id="38553-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="38553-151">在还原期间, 你可以使用以下工具:</span><span class="sxs-lookup"><span data-stu-id="38553-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="38553-152">Lync Server Management Shell cmdlet</span><span class="sxs-lookup"><span data-stu-id="38553-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="38553-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="38553-153">Import-CsUserData</span></span>

  - <span data-ttu-id="38553-154">用于还原 Windows 文件夹的工具</span><span class="sxs-lookup"><span data-stu-id="38553-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="38553-155">拓扑生成器</span><span class="sxs-lookup"><span data-stu-id="38553-155">Topology Builder</span></span>

  - <span data-ttu-id="38553-156">SQL Server 数据库实用工具, 例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="38553-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="38553-157">准备还原服务器</span><span class="sxs-lookup"><span data-stu-id="38553-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="38553-158">在还原服务器之前, 必须执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="38553-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="38553-159">安装操作系统。</span><span class="sxs-lookup"><span data-stu-id="38553-159">Install the operating system.</span></span>

2.  <span data-ttu-id="38553-160">如果服务器是后端服务器, 请安装 SQL Server 2012 或 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="38553-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="38553-161">还原或重新注册证书。</span><span class="sxs-lookup"><span data-stu-id="38553-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="38553-162">有关证书的详细信息, 请参阅[Lync Server 2013: data 中的 "备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)" 中的 "其他备份要求"。</span><span class="sxs-lookup"><span data-stu-id="38553-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="38553-163">在启动还原之前获取系统的映像, 以用作回滚点, 以防还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="38553-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="38553-164">在本主题的过程中介绍的 Lync Server 部署向导和 cmdlet 以及相关主题, 设置所有所需的访问控制列表 (Acl)。</span><span class="sxs-lookup"><span data-stu-id="38553-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="38553-165">验证在开始还原之前, 验证你要还原的组件是否可用所需的硬件和软件。</span><span class="sxs-lookup"><span data-stu-id="38553-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="38553-166">安装操作系统和 SQL Server 后, 可以远程运行以下还原过程中的大部分步骤。</span><span class="sxs-lookup"><span data-stu-id="38553-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="38553-167">这些过程中将注明异常。</span><span class="sxs-lookup"><span data-stu-id="38553-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="38553-168">你还应了解你的组织的备份和还原计划以及上次备份中的信息 (如本文档中的工作表中的信息) (有关详细信息, 请参阅[Lync Server 2013 的备份和还原工作表](lync-server-2013-backup-and-restoration-worksheets.md))。开始还原之前可用。</span><span class="sxs-lookup"><span data-stu-id="38553-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

