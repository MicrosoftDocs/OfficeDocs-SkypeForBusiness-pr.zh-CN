---
title: Lync Server 2013：还原监视或存档数据
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
ms.openlocfilehash: 9e908792e8a2563094b11bcce73d4ac6ce6c7121
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511419"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="a93b4-102">在 Lync Server 2013 中还原监视或存档数据</span><span class="sxs-lookup"><span data-stu-id="a93b4-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a93b4-103">_**上次修改的主题：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="a93b4-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="a93b4-104">在出现故障后，无需还原监视和存档数据即可使 Lync Server 启动并运行。</span><span class="sxs-lookup"><span data-stu-id="a93b4-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="a93b4-105">但是，如果监视和存档数据对您的组织至关重要，您将需要在重新创建数据库后还原数据。</span><span class="sxs-lookup"><span data-stu-id="a93b4-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="a93b4-106">以下过程介绍如何使用 SQL Server Management Studio 还原存档或监视数据。</span><span class="sxs-lookup"><span data-stu-id="a93b4-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="a93b4-107">从备份文件中还原监控或存档数据</span><span class="sxs-lookup"><span data-stu-id="a93b4-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="a93b4-108">以本地计算机上 Administrators 组的成员或具有同等用户权限的组的成员身份登录到要还原的服务器。</span><span class="sxs-lookup"><span data-stu-id="a93b4-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="a93b4-109">打开 SQL Server Management Studio：依次单击 " **开始**"、" **所有程序**"、" **Microsoft sql Server 2012** " 或 " **microsoft sql server 2008 R2**"，然后单击 " **SQL server management Studio**"。</span><span class="sxs-lookup"><span data-stu-id="a93b4-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="a93b4-110">在“连接到服务器”\*\*\*\* 中，至少提供服务器的名称和身份验证信息，以连接到 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="a93b4-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="a93b4-111">在“对象资源管理器”\*\*\*\* 中，右键单击“数据库”\*\*\*\*，然后单击“还原数据库”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="a93b4-112">在“选择页”\*\*\*\* 下，单击“常规”\*\*\*\*，然后在“目标数据库”\*\*\*\* 中选择数据库名称，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a93b4-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="a93b4-113">对于存档数据库，请选择 " **LcsLog**"。</span><span class="sxs-lookup"><span data-stu-id="a93b4-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="a93b4-114">对于呼叫详细信息记录 (CDR) 数据库，请选择“LcsCDR”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="a93b4-115">对于用户体验质量 (QoE) 数据库，请选择“QoEMetrics”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="a93b4-116">单击“自设备”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-116">Click **From device**.</span></span>

7.  <span data-ttu-id="a93b4-117">在“选择用于还原的备份集”\*\*\*\* 下，单击备份文件，然后单击“还原”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="a93b4-118">在“选择页”\*\*\*\* 下，单击“选项”\*\*\*\*，确认数据文件路径和日志路径位于正确的文件夹中，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="a93b4-119">确保 (Acl) 的访问控制列表正确</span><span class="sxs-lookup"><span data-stu-id="a93b4-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="a93b4-120">依次展开“数据库”\*\*\*\*、存档数据库或监控数据库、“安全”\*\*\*\*，然后展开“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="a93b4-121">确认域组 RTCComponentUniversalServices 作为用户存在。</span><span class="sxs-lookup"><span data-stu-id="a93b4-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="a93b4-122">如果 " **用户**" 下不存在 RTCComponentUniversalServices，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a93b4-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="a93b4-123">右键单击“用户”\*\*\*\*，然后单击“新建用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="a93b4-124">在 " **登录名**" 中，键入缺少的组名称 RTCComponentUniversalServices。</span><span class="sxs-lookup"><span data-stu-id="a93b4-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="a93b4-125">在“数据库角色成员身份”\*\*\*\* 中，选择“ServerRole”\*\*\*\* 权限，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a93b4-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a93b4-126">无需重新启动存档服务或监控服务。</span><span class="sxs-lookup"><span data-stu-id="a93b4-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

