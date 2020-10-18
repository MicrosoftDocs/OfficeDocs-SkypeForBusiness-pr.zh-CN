---
title: Lync Server 2013：还原监视或存档数据
description: Lync Server 2013：还原监视或存档数据。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 169a5da2d606b97c7cd3f59d6cbae3d4c584e6e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575509"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="303b8-103">在 Lync Server 2013 中还原监视或存档数据</span><span class="sxs-lookup"><span data-stu-id="303b8-103">Restoring monitoring or archiving data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="303b8-104">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="303b8-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="303b8-105">在出现故障后，无需还原监视和存档数据即可使 Lync Server 启动并运行。</span><span class="sxs-lookup"><span data-stu-id="303b8-105">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="303b8-106">但是，如果监视和存档数据对您的组织至关重要，您将需要在重新创建数据库后还原数据。</span><span class="sxs-lookup"><span data-stu-id="303b8-106">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="303b8-107">以下过程介绍如何使用 SQL Server Management Studio 还原存档或监视数据。</span><span class="sxs-lookup"><span data-stu-id="303b8-107">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="303b8-108">从备份文件中还原监控或存档数据</span><span class="sxs-lookup"><span data-stu-id="303b8-108">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="303b8-109">以本地计算机上 Administrators 组的成员或具有同等用户权限的组的成员身份登录到要还原的服务器。</span><span class="sxs-lookup"><span data-stu-id="303b8-109">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="303b8-110">打开 SQL Server Management Studio：依次单击 " **开始**"、" **所有程序**"、" **Microsoft sql Server 2012** " 或 " **microsoft sql server 2008 R2**"，然后单击 " **SQL server management Studio**"。</span><span class="sxs-lookup"><span data-stu-id="303b8-110">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="303b8-111">在“连接到服务器”\*\*\*\* 中，至少提供服务器的名称和身份验证信息，以连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="303b8-111">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="303b8-112">在“对象资源管理器”\*\*\*\* 中，右键单击“数据库”\*\*\*\*，然后单击“还原数据库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-112">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="303b8-113">在“选择页”\*\*\*\* 下，单击“常规”\*\*\*\*，然后在“目标数据库”\*\*\*\* 中选择数据库名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="303b8-113">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="303b8-114">对于存档数据库，请选择 " **LcsLog**"。</span><span class="sxs-lookup"><span data-stu-id="303b8-114">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="303b8-115">对于呼叫详细信息记录 (CDR) 数据库，请选择“LcsCDR”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-115">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="303b8-116">对于用户体验质量 (QoE) 数据库，请选择“QoEMetrics”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-116">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="303b8-117">单击“自设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-117">Click **From device**.</span></span>

7.  <span data-ttu-id="303b8-118">在“选择用于还原的备份集”\*\*\*\* 下，单击备份文件，然后单击“还原”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-118">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="303b8-119">在“选择页”\*\*\*\* 下，单击“选项”\*\*\*\*，确认数据文件路径和日志路径位于正确的文件夹中，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-119">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="303b8-120">确保 (Acl) 的访问控制列表正确</span><span class="sxs-lookup"><span data-stu-id="303b8-120">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="303b8-121">依次展开“数据库”\*\*\*\*、存档数据库或监控数据库、“安全”\*\*\*\*，然后展开“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-121">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="303b8-122">确认域组 RTCComponentUniversalServices 作为用户存在。</span><span class="sxs-lookup"><span data-stu-id="303b8-122">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="303b8-123">如果 " **用户**" 下不存在 RTCComponentUniversalServices，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="303b8-123">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="303b8-124">右键单击“用户”\*\*\*\*，然后单击“新建用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-124">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="303b8-125">在 " **登录名**" 中，键入缺少的组名称 RTCComponentUniversalServices。</span><span class="sxs-lookup"><span data-stu-id="303b8-125">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="303b8-126">在“数据库角色成员身份”\*\*\*\* 中，选择“ServerRole”\*\*\*\* 权限，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="303b8-126">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="303b8-127">无需重新启动存档服务或监控服务。</span><span class="sxs-lookup"><span data-stu-id="303b8-127">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

