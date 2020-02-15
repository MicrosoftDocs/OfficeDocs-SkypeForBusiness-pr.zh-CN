---
title: Lync Server 2013：测试数据库配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45781238f7fb8aa461e050f2e8f0cbf04e45a950
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="a2024-102">在 Lync Server 2013 中测试数据库配置</span><span class="sxs-lookup"><span data-stu-id="a2024-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a2024-103">_**上次修改的主题：** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="a2024-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a2024-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="a2024-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="a2024-105">每天</span><span class="sxs-lookup"><span data-stu-id="a2024-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a2024-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="a2024-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="a2024-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2024-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a2024-108">所需的权限</span><span class="sxs-lookup"><span data-stu-id="a2024-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="a2024-109">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员，并且需要具有对 SQL Server 的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="a2024-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="a2024-110">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行<strong>CsDatabase</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="a2024-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="a2024-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="a2024-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="a2024-112">说明</span><span class="sxs-lookup"><span data-stu-id="a2024-112">Description</span></span>

<span data-ttu-id="a2024-113">**CsDatabase** cmdlet 验证与一个或多个 Lync Server 2013 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="a2024-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="a2024-114">在运行时， **CsDatabase** cmdlet 会读取 Lync Server 拓扑，尝试连接到相关数据库，然后报告每次尝试成功或失败。</span><span class="sxs-lookup"><span data-stu-id="a2024-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="a2024-115">如果可以建立连接，该 cmdlet 还将返回数据库名称、SQL Server 版本以及所有已安装的镜像数据库的位置等信息。</span><span class="sxs-lookup"><span data-stu-id="a2024-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="a2024-116">运行测试</span><span class="sxs-lookup"><span data-stu-id="a2024-116">Running the test</span></span>

<span data-ttu-id="a2024-117">示例 1 中显示的命令验证中央管理数据库的配置。</span><span class="sxs-lookup"><span data-stu-id="a2024-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="a2024-118">示例2验证安装在计算机 atl-sql-001.litwareinc.com 上的所有 Lync Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="a2024-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="a2024-p103">在示例 3 中，仅对安装在计算机 atl-sql-001.litwareinc.com 上的存档数据库执行验证。请注意，包括了 SqlInstanceName 参数以指定存档数据库所在的 SQL Server 实例 (Archinst)。</span><span class="sxs-lookup"><span data-stu-id="a2024-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="a2024-121">示例 4 中显示的命令用于验证本地计算机上安装的数据库。</span><span class="sxs-lookup"><span data-stu-id="a2024-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="a2024-122">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="a2024-122">Determining success or failure</span></span>

<span data-ttu-id="a2024-123">如果数据库连接配置正确，您将收到与以下内容类似的输出，其中 "成功" 属性被标记为**True**：</span><span class="sxs-lookup"><span data-stu-id="a2024-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="a2024-124">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2024-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a2024-125">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a2024-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a2024-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a2024-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a2024-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a2024-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a2024-128">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="a2024-128">DatabaseName : xds</span></span>

<span data-ttu-id="a2024-129">DataSource</span><span class="sxs-lookup"><span data-stu-id="a2024-129">DataSource :</span></span>

<span data-ttu-id="a2024-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-130">SQLServerVersion :</span></span>

<span data-ttu-id="a2024-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="a2024-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="a2024-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-132">InstalledVersion :</span></span>

<span data-ttu-id="a2024-133">成功： True</span><span class="sxs-lookup"><span data-stu-id="a2024-133">Succeed : True</span></span>

<span data-ttu-id="a2024-134">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2024-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a2024-135">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a2024-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a2024-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a2024-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a2024-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a2024-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a2024-138">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="a2024-138">DatabaseName : lis</span></span>

<span data-ttu-id="a2024-139">DataSource</span><span class="sxs-lookup"><span data-stu-id="a2024-139">DataSource :</span></span>

<span data-ttu-id="a2024-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-140">SQLServerVersion :</span></span>

<span data-ttu-id="a2024-141">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="a2024-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="a2024-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-142">InstalledVersion :</span></span>

<span data-ttu-id="a2024-143">成功： True</span><span class="sxs-lookup"><span data-stu-id="a2024-143">Succeed : True</span></span>

<span data-ttu-id="a2024-144">如果数据库配置正确但仍可用，则 "成功" 字段将显示为**False**，并将提供其他警告和信息：</span><span class="sxs-lookup"><span data-stu-id="a2024-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="a2024-145">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2024-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="a2024-146">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a2024-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a2024-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a2024-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a2024-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a2024-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a2024-149">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="a2024-149">DatabaseName : xds</span></span>

<span data-ttu-id="a2024-150">DataSource</span><span class="sxs-lookup"><span data-stu-id="a2024-150">DataSource :</span></span>

<span data-ttu-id="a2024-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-151">SQLServerVersion :</span></span>

<span data-ttu-id="a2024-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="a2024-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="a2024-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-153">InstalledVersion :</span></span>

<span data-ttu-id="a2024-154">成功： False</span><span class="sxs-lookup"><span data-stu-id="a2024-154">Succeed : False</span></span>

<span data-ttu-id="a2024-155">SqlServerFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="a2024-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="a2024-156">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="a2024-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="a2024-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="a2024-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="a2024-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="a2024-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="a2024-159">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="a2024-159">DatabaseName : lis</span></span>

<span data-ttu-id="a2024-160">DataSource</span><span class="sxs-lookup"><span data-stu-id="a2024-160">DataSource :</span></span>

<span data-ttu-id="a2024-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-161">SQLServerVersion :</span></span>

<span data-ttu-id="a2024-162">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="a2024-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="a2024-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="a2024-163">InstalledVersion :</span></span>

<span data-ttu-id="a2024-164">成功： False</span><span class="sxs-lookup"><span data-stu-id="a2024-164">Succeed : False</span></span>

<span data-ttu-id="a2024-165">警告： CsDatabase 遇到错误。</span><span class="sxs-lookup"><span data-stu-id="a2024-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="a2024-166">请参阅日志文件获取</span><span class="sxs-lookup"><span data-stu-id="a2024-166">Consult the log file for a</span></span>

<span data-ttu-id="a2024-167">详细分析，并确保解决所有错误（2）和警告（0）</span><span class="sxs-lookup"><span data-stu-id="a2024-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="a2024-168">，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="a2024-168">before continuing.</span></span>

<span data-ttu-id="a2024-169">警告：详细结果可在以下位置找到：</span><span class="sxs-lookup"><span data-stu-id="a2024-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="a2024-170">"C：\\用户\\测试\\AppData\\本地\\临时\\2\\测试-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="a2024-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="a2024-171">04d593cce8e6 "。</span><span class="sxs-lookup"><span data-stu-id="a2024-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="a2024-172">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="a2024-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="a2024-173">以下是**测试 CsDatabase**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="a2024-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="a2024-174">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="a2024-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="a2024-175">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="a2024-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="a2024-176">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="a2024-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="a2024-177">如果数据库配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="a2024-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a2024-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2024-178">See Also</span></span>


[<span data-ttu-id="a2024-179">CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="a2024-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="a2024-180">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="a2024-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="a2024-181">CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="a2024-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

