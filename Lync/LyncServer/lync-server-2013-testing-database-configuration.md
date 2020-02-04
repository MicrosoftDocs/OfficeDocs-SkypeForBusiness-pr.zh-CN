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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="e94a8-102">在 Lync Server 2013 中测试数据库配置</span><span class="sxs-lookup"><span data-stu-id="e94a8-102">Testing database configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e94a8-103">_**主题上次修改时间：** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="e94a8-103">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e94a8-104">验证计划</span><span class="sxs-lookup"><span data-stu-id="e94a8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="e94a8-105">每天</span><span class="sxs-lookup"><span data-stu-id="e94a8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e94a8-106">测试工具</span><span class="sxs-lookup"><span data-stu-id="e94a8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="e94a8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e94a8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e94a8-108">需要权限</span><span class="sxs-lookup"><span data-stu-id="e94a8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="e94a8-109">使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员，并且需要拥有 SQL Server 的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="e94a8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="e94a8-110">使用 Windows PowerShell 的远程实例运行时，必须向用户分配具有运行<strong>CsDatabase</strong> cmdlet 权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="e94a8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="e94a8-111">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e94a8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="e94a8-112">说明</span><span class="sxs-lookup"><span data-stu-id="e94a8-112">Description</span></span>

<span data-ttu-id="e94a8-113">**CsDatabase** cmdlet 验证与一个或多个 Lync Server 2013 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="e94a8-113">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="e94a8-114">运行时， **CsDatabase** cmdlet 会读取 Lync Server 拓扑，尝试连接到相关数据库，然后返回每次尝试成功或失败的报告。</span><span class="sxs-lookup"><span data-stu-id="e94a8-114">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="e94a8-115">如果可以建立连接，则 cmdlet 还会报告返回有关数据库名称、SQL Server 版本信息以及任何已安装镜像数据库位置的信息。</span><span class="sxs-lookup"><span data-stu-id="e94a8-115">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="e94a8-116">运行测试</span><span class="sxs-lookup"><span data-stu-id="e94a8-116">Running the test</span></span>

<span data-ttu-id="e94a8-117">示例1中所示的命令验证中央管理数据库的配置。</span><span class="sxs-lookup"><span data-stu-id="e94a8-117">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="e94a8-118">示例2验证计算机 atl-sql-001.litwareinc.com 上安装的所有 Lync Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="e94a8-118">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="e94a8-119">在示例3中，仅对计算机 atl-sql-001.litwareinc.com 上安装的存档数据库执行验证。</span><span class="sxs-lookup"><span data-stu-id="e94a8-119">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com.</span></span> <span data-ttu-id="e94a8-120">请注意，SqlInstanceName 参数包含于指定存档数据库所在的 SQL Server 实例（Archinst）。</span><span class="sxs-lookup"><span data-stu-id="e94a8-120">Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="e94a8-121">示例4中所示的命令验证本地计算机上安装的数据库。</span><span class="sxs-lookup"><span data-stu-id="e94a8-121">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="e94a8-122">确定成功还是失败</span><span class="sxs-lookup"><span data-stu-id="e94a8-122">Determining success or failure</span></span>

<span data-ttu-id="e94a8-123">如果数据库连接配置正确，您将收到与此类似的输出，其中 "成功" 属性标记为**True**：</span><span class="sxs-lookup"><span data-stu-id="e94a8-123">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="e94a8-124">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e94a8-124">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e94a8-125">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="e94a8-125">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e94a8-126">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e94a8-126">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e94a8-127">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e94a8-127">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e94a8-128">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="e94a8-128">DatabaseName : xds</span></span>

<span data-ttu-id="e94a8-129">数据源</span><span class="sxs-lookup"><span data-stu-id="e94a8-129">DataSource :</span></span>

<span data-ttu-id="e94a8-130">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-130">SQLServerVersion :</span></span>

<span data-ttu-id="e94a8-131">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="e94a8-131">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="e94a8-132">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-132">InstalledVersion :</span></span>

<span data-ttu-id="e94a8-133">成功： True</span><span class="sxs-lookup"><span data-stu-id="e94a8-133">Succeed : True</span></span>

<span data-ttu-id="e94a8-134">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e94a8-134">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e94a8-135">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="e94a8-135">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e94a8-136">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e94a8-136">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e94a8-137">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e94a8-137">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e94a8-138">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="e94a8-138">DatabaseName : lis</span></span>

<span data-ttu-id="e94a8-139">数据源</span><span class="sxs-lookup"><span data-stu-id="e94a8-139">DataSource :</span></span>

<span data-ttu-id="e94a8-140">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-140">SQLServerVersion :</span></span>

<span data-ttu-id="e94a8-141">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="e94a8-141">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="e94a8-142">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-142">InstalledVersion :</span></span>

<span data-ttu-id="e94a8-143">成功： True</span><span class="sxs-lookup"><span data-stu-id="e94a8-143">Succeed : True</span></span>

<span data-ttu-id="e94a8-144">如果数据库配置正确但仍可用，则 "成功" 字段将显示为**False**，并且将提供其他警告和信息：</span><span class="sxs-lookup"><span data-stu-id="e94a8-144">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="e94a8-145">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e94a8-145">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="e94a8-146">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="e94a8-146">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e94a8-147">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e94a8-147">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e94a8-148">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e94a8-148">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e94a8-149">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="e94a8-149">DatabaseName : xds</span></span>

<span data-ttu-id="e94a8-150">数据源</span><span class="sxs-lookup"><span data-stu-id="e94a8-150">DataSource :</span></span>

<span data-ttu-id="e94a8-151">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-151">SQLServerVersion :</span></span>

<span data-ttu-id="e94a8-152">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="e94a8-152">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="e94a8-153">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-153">InstalledVersion :</span></span>

<span data-ttu-id="e94a8-154">成功： False</span><span class="sxs-lookup"><span data-stu-id="e94a8-154">Succeed : False</span></span>

<span data-ttu-id="e94a8-155">SqlServerFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="e94a8-155">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="e94a8-156">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="e94a8-156">SqlInstanceName : rtc</span></span>

<span data-ttu-id="e94a8-157">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="e94a8-157">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="e94a8-158">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="e94a8-158">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="e94a8-159">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="e94a8-159">DatabaseName : lis</span></span>

<span data-ttu-id="e94a8-160">数据源</span><span class="sxs-lookup"><span data-stu-id="e94a8-160">DataSource :</span></span>

<span data-ttu-id="e94a8-161">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-161">SQLServerVersion :</span></span>

<span data-ttu-id="e94a8-162">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="e94a8-162">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="e94a8-163">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="e94a8-163">InstalledVersion :</span></span>

<span data-ttu-id="e94a8-164">成功： False</span><span class="sxs-lookup"><span data-stu-id="e94a8-164">Succeed : False</span></span>

<span data-ttu-id="e94a8-165">警告： CsDatabase 遇到错误。</span><span class="sxs-lookup"><span data-stu-id="e94a8-165">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="e94a8-166">请参阅日志文件获取</span><span class="sxs-lookup"><span data-stu-id="e94a8-166">Consult the log file for a</span></span>

<span data-ttu-id="e94a8-167">详细分析，并确保解决所有错误（2）和警告（0）</span><span class="sxs-lookup"><span data-stu-id="e94a8-167">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="e94a8-168">然后再继续。</span><span class="sxs-lookup"><span data-stu-id="e94a8-168">before continuing.</span></span>

<span data-ttu-id="e94a8-169">警告：可以在以下位置找到详细结果</span><span class="sxs-lookup"><span data-stu-id="e94a8-169">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="e94a8-170">"C：\\用户\\测试\\AppData\\本地\\温度\\2\\测试-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="e94a8-170">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="e94a8-171">04d593cce8e6 "。</span><span class="sxs-lookup"><span data-stu-id="e94a8-171">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="e94a8-172">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="e94a8-172">Reasons why the test might have failed</span></span>

<span data-ttu-id="e94a8-173">下面是**测试 CsDatabase**可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="e94a8-173">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="e94a8-174">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="e94a8-174">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="e94a8-175">如果使用，则必须正确配置可选参数，否则测试将失败。</span><span class="sxs-lookup"><span data-stu-id="e94a8-175">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="e94a8-176">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="e94a8-176">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="e94a8-177">如果数据库配置错误或尚未部署，此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="e94a8-177">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e94a8-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e94a8-178">See Also</span></span>


[<span data-ttu-id="e94a8-179">Get-CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="e94a8-179">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="e94a8-180">CsService</span><span class="sxs-lookup"><span data-stu-id="e94a8-180">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="e94a8-181">Get-CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="e94a8-181">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

