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
ms.openlocfilehash: 4185c02bc85077b0f68ca76d83fd48203e0e5fd9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-core-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="ad5fb-102">在 Lync Server 2013 中备份核心数据和设置</span><span class="sxs-lookup"><span data-stu-id="ad5fb-102">Backing up core data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad5fb-103">_**主题上次修改时间：** 2014-04-23_</span><span class="sxs-lookup"><span data-stu-id="ad5fb-103">_**Topic Last Modified:** 2014-04-23_</span></span>

<span data-ttu-id="ad5fb-104">以下过程使用 Lync Server Management Shell cmdlet 为核心服务的设置和数据创建备份文件。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-104">The following procedures use Lync Server Management Shell cmdlets to create backup files for settings and data for core services.</span></span> <span data-ttu-id="ad5fb-105">有关本部分中使用的工具的详细信息（包括它们所在的位置），请参阅[Lync Server 2013 中的备份和还原要求：工具和权限](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-105">For details about the tools used in this section, including where they are located, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span> <span data-ttu-id="ad5fb-106">有关备份存档和监视数据的详细信息，请参阅[在 Lync Server 2013 中备份存档和监视数据库](lync-server-2013-backing-up-archiving-and-monitoring-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-106">For details about backing up Archiving and Monitoring data, see [Backing up Archiving and Monitoring databases in Lync Server 2013](lync-server-2013-backing-up-archiving-and-monitoring-databases.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad5fb-107">此部分中备份中央管理存储的步骤包括用于存档和监视的设置和配置。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-107">The step in this section to back up the Central Management store includes the settings and configuration for Archiving and Monitoring.</span></span>



</div>

<span data-ttu-id="ad5fb-108">你可以在本地或远程运行本部分所述的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-108">You can run the cmdlets described in this section locally or remotely.</span></span>

<div>

## <a name="to-back-up-core-data-and-settings"></a><span data-ttu-id="ad5fb-109">备份核心数据和设置</span><span class="sxs-lookup"><span data-stu-id="ad5fb-109">To back up core data and settings</span></span>

1.  <span data-ttu-id="ad5fb-110">从 RTCUniversalServerAdmins 组成员的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-110">From a user account that is a member of the RTCUniversalServerAdmins group, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="ad5fb-111">要将创建的备份存储在以下步骤中，请创建一个新的共享文件夹，并将 **$Backup**引用的路径更新为新的共享文件夹。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-111">To store the backups you create in the following steps, create a new shared folder and update the path referenced by **$Backup** to the new shared folder.</span></span>

3.  <span data-ttu-id="ad5fb-112">启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="ad5fb-113">备份中央管理存储配置文件。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-113">Back up the Central Management store configuration file.</span></span> <span data-ttu-id="ad5fb-114">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-114">At the command line, type the following:</span></span>
    
        Export-CsConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="ad5fb-115">例如：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-115">For example:</span></span>
    
        Export-CsConfiguration -FileName "C:\Config.zip"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad5fb-116">此步骤将 Lync 服务器拓扑、策略和配置设置导出到文件。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-116">This step exports your Lync Server topology, policies, and configuration settings to a file.</span></span> <span data-ttu-id="ad5fb-117">备份拓扑数据不需要其他步骤。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-117">No other step is required to backup topology data.</span></span>

    
    </div>

5.  <span data-ttu-id="ad5fb-118">将备份的中央管理存储配置文件复制到 $Backup\\。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-118">Copy the backed-up Central Management store configuration file to $Backup\\.</span></span>

6.  <span data-ttu-id="ad5fb-119">备份位置信息服务数据。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-119">Back up Location Information service data.</span></span> <span data-ttu-id="ad5fb-120">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-120">At the command line, type the following:</span></span>
    
        Export-CsLisConfiguration -FileName <path and file name for backup>
    
    <span data-ttu-id="ad5fb-121">例如：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-121">For example:</span></span>
    
        Export-CsLisConfiguration -FileName "C:\E911Config.zip"

7.  <span data-ttu-id="ad5fb-122">将备份的位置信息服务配置文件复制到 $Backup\\。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-122">Copy the backed-up Location Information service configuration file to $Backup\\.</span></span>

8.  <span data-ttu-id="ad5fb-123">备份前端池和每个标准版服务器的每个后端数据库上的用户数据。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-123">Back up user data on every back-end database of a Front End pool and every Standard Edition server.</span></span> <span data-ttu-id="ad5fb-124">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-124">At the command line, type the following:</span></span>
    
        Export-CsUserData -PoolFQDN <Fqdn> -FileName <String>
    
    <span data-ttu-id="ad5fb-125">例如：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-125">For example:</span></span>
    
        Export-CsUserData -PoolFQDN "atl-cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserData.zip"

9.  <span data-ttu-id="ad5fb-126">将已备份的用户文件复制到\\$Backup。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-126">Copy the backed up user file to $Backup\\.</span></span>

10. <span data-ttu-id="ad5fb-127">在运行响应组应用程序的每个池上，备份响应组配置。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-127">On every pool that runs the Response Group application, back up the Response Group configuration.</span></span> <span data-ttu-id="ad5fb-128">请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-128">Do the following:</span></span>
    
    1.  <span data-ttu-id="ad5fb-129">在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-129">At the command line, type:</span></span>
        
            Export-CsRgsConfiguration -Source "service:ApplicationServer:<pool FQDN>" -FileName <path and file name for backup>
        
        <span data-ttu-id="ad5fb-130">例如：</span><span class="sxs-lookup"><span data-stu-id="ad5fb-130">For example:</span></span>
        
            Export-CsRgsConfiguration -Source ApplicationServer:pool01.contoso.com -FileName C:\RgsConfiguration.zip

11. <span data-ttu-id="ad5fb-131">将已备份的响应组配置文件复制到\\$Backup。</span><span class="sxs-lookup"><span data-stu-id="ad5fb-131">Copy the backed up Response Group configuration file to $Backup\\.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

