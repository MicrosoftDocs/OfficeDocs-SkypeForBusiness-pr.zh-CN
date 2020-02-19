---
title: Lync Server 2013：中央管理存储复制状态
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Central management store replication status
ms:assetid: f514f88d-986b-4e45-b79b-e04a7616c1fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720926(v=OCS.15)
ms:contentKeyID: 63969663
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb72b44cf53a33b3c0d7a79f6adda8870fe37254
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="central-management-store-replication-status-in-lync-server-2013"></a><span data-ttu-id="09c48-102">Lync Server 2013 中的中央管理存储复制状态</span><span class="sxs-lookup"><span data-stu-id="09c48-102">Central management store replication status in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09c48-103">_**上次修改的主题：** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="09c48-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="09c48-104">当管理员将某种类型的更改更改为 Lync Server 时（例如，当管理员创建新的语音策略或更改通讯簿服务器配置设置）时，会将更改记录在中央管理存储中。</span><span class="sxs-lookup"><span data-stu-id="09c48-104">When an administrator makes a change of some kind to Lync Server (for example, when an administrator creates a new voice policy or changes the Address Book Server configuration settings) that change is recorded in the Central Management store.</span></span> <span data-ttu-id="09c48-105">反过来，必须将更改复制到运行 Lync Server 服务或服务器角色的所有计算机。</span><span class="sxs-lookup"><span data-stu-id="09c48-105">In turn, the change must then be replicated to all the computers that are running Lync Server services or server roles.</span></span>

<span data-ttu-id="09c48-106">若要复制数据，主复制器（在中央管理服务器上运行）将创建更改的配置数据的快照。</span><span class="sxs-lookup"><span data-stu-id="09c48-106">To replicate data, the Master Replicator (running on the Central Management Server) creates a snapshot of the changed configuration data.</span></span> <span data-ttu-id="09c48-107">然后，将此快照的副本发送到运行 Lync Server 服务或服务器角色的每台计算机。</span><span class="sxs-lookup"><span data-stu-id="09c48-107">A copy of this snapshot is then sent to each computer that is running Lync Server services or server roles.</span></span> <span data-ttu-id="09c48-108">在这些计算机上，复制代理接收快照并上载已更改的数据。</span><span class="sxs-lookup"><span data-stu-id="09c48-108">On those computers, a replication agent receives the snapshot and uploads the changed data.</span></span> <span data-ttu-id="09c48-109">然后，代理会将报告最新复制状态的邮件发送到主复制器。</span><span class="sxs-lookup"><span data-stu-id="09c48-109">The agent then sends the Master Replicator a message reporting the latest replication status.</span></span>

<span data-ttu-id="09c48-110">Get-csmanagementstorereplicationstatus cmdlet 使您能够验证组织中的所有（或全部） Lync Server 计算机的复制状态。</span><span class="sxs-lookup"><span data-stu-id="09c48-110">The Get-CsManagementStoreReplicationStatus cmdlet enables you to verify the replication status for any (or all) of the Lync Server computers in your organization.</span></span>

<span data-ttu-id="09c48-111">谁可以运行此 cmdlet？</span><span class="sxs-lookup"><span data-stu-id="09c48-111">Who can run this cmdlet?</span></span> <span data-ttu-id="09c48-112">默认情况下，以下组的成员有权在本地运行 Get-csmanagementstorereplicationstatus cmdlet： RTCUniversalUserAdmins、RTCUniversalServerAdmins。</span><span class="sxs-lookup"><span data-stu-id="09c48-112">By default, members of the following groups are authorized to run the Get-CsManagementStoreReplicationStatus cmdlet locally: RTCUniversalUserAdmins, RTCUniversalServerAdmins.</span></span>

<span data-ttu-id="09c48-113">若要返回此 cmdlet 分配到的所有 RBAC 角色的列表（包括您自己创建的任何自定义 RBAC 角色），请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="09c48-113">To return a list of all RBAC roles this cmdlet was assigned to (including any custom RBAC roles that you have created yourself), run the following command from the Windows PowerShell prompt:</span></span>

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Get-CsManagementStoreReplicationStatus"}

<div>

## <a name="see-also"></a><span data-ttu-id="09c48-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09c48-114">See Also</span></span>


[<span data-ttu-id="09c48-115">Get-csmanagementstorereplicationstatus</span><span class="sxs-lookup"><span data-stu-id="09c48-115">Get-CsManagementStoreReplicationStatus</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsManagementStoreReplicationStatus)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

