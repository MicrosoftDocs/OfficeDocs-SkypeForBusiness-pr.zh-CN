---
title: Lync Server 2013：备份核心数据和设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up core data and settings
ms:assetid: 278bc95a-7b8d-4e01-a872-a844830459de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202170(v=OCS.15)
ms:contentKeyID: 51541452
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4523dcaaee5931e6bf4df9dd79c09ec92636ec31
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="0a0c7-102">在 Lync Server 2013 中备份核心数据和设置</span><span class="sxs-lookup"><span data-stu-id="0a0c7-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a0c7-103">_**上次修改的主题：** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="0a0c7-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="0a0c7-104">以下过程使用 Lync Server 命令行管理程序 cmdlet 为核心服务的设置和数据创建备份文件。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="0a0c7-105">有关此部分中使用的工具（包括它们位于何处）的详细信息，请参阅[Lync Server 2013 中的备份和还原要求：工具和权限](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="0a0c7-106">有关备份存档和监视数据的详细信息，请参阅[在 Lync Server 2013 中备份存档和监控数据库](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a0c7-107">本部分中对中央管理存储进行备份的步骤包括用于存档和监视的设置和配置。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="0a0c7-108">您可以在本地运行本节所述的 cmdlet，也可以远程运行它们。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="0a0c7-109">备份核心数据和设置</span><span class="sxs-lookup"><span data-stu-id="0a0c7-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="0a0c7-110">通过 RTCUniversalServerAdmins 组成员的用户帐户，登录内部部署中的任意计算机。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a0c7-111">若要采用以下步骤存储创建的备份，请创建新的共享文件夹，并将 **$Backup** 引用的路径更新到该新共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="0a0c7-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="0a0c7-113">备份中央管理存储配置文件。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="0a0c7-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="0a0c7-115">例如：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a0c7-116">此步骤将 Lync Server 拓扑、策略和配置设置导出到文件中。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="0a0c7-117">无需使用其他步骤来备份拓扑数据。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="0a0c7-118">将备份的中央管理存储配置文件复制到 $Backup\\。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="0a0c7-p104">备份位置信息服务数据。在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-p104">Back up Location Information service data. At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="0a0c7-121">例如：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="0a0c7-122">将备份的位置信息服务配置文件复制到 $Backup\\。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="0a0c7-123">备份前端池和每个 Standard Edition 服务器的每个后端数据库上的用户数据。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="0a0c7-124">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="0a0c7-125">例如：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="0a0c7-126">将已备份的用户文件复制到\\$Backup。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="0a0c7-127">在运行响应组应用程序的每个池中，备份响应组配置。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="0a0c7-128">请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="0a0c7-129">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="0a0c7-130">例如：</span><span class="sxs-lookup"><span data-stu-id="0a0c7-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="0a0c7-131">将已备份的响应组配置文件复制到\\$Backup。</span><span class="sxs-lookup"><span data-stu-id="0a0c7-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

