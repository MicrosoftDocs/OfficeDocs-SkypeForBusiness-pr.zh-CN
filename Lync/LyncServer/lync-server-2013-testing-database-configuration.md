---
title: Lync Server 2013：测试数据库配置
description: Lync Server 2013：测试数据库配置。
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
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560678"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a><span data-ttu-id="d4c0b-103">在 Lync Server 2013 中测试数据库配置</span><span class="sxs-lookup"><span data-stu-id="d4c0b-103">Testing database configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4c0b-104">_**上次修改的主题：** 2016-07-07_</span><span class="sxs-lookup"><span data-stu-id="d4c0b-104">_**Topic Last Modified:** 2016-07-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d4c0b-105">验证计划</span><span class="sxs-lookup"><span data-stu-id="d4c0b-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="d4c0b-106">每天</span><span class="sxs-lookup"><span data-stu-id="d4c0b-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d4c0b-107">测试工具</span><span class="sxs-lookup"><span data-stu-id="d4c0b-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="d4c0b-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d4c0b-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d4c0b-109">所需的权限</span><span class="sxs-lookup"><span data-stu-id="d4c0b-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="d4c0b-110">在使用 Lync Server 命令行管理程序本地运行时，用户必须是 RTCUniversalServerAdmins 安全组的成员，并且需要具有对 SQL Server 的管理员权限。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group, and need to have Administrator privileges on the SQL server.</span></span></p>
<p><span data-ttu-id="d4c0b-111">使用 Windows PowerShell 的远程实例运行时，必须为用户分配具有运行 <strong>CsDatabase</strong> cmdlet 的权限的 RBAC 角色。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsDatabase</strong> cmdlet.</span></span> <span data-ttu-id="d4c0b-112">若要查看可使用此 cmdlet 的所有 RBAC 角色的列表，请从 Windows PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d4c0b-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="d4c0b-113">说明</span><span class="sxs-lookup"><span data-stu-id="d4c0b-113">Description</span></span>

<span data-ttu-id="d4c0b-114">**CsDatabase** cmdlet 验证与一个或多个 Lync Server 2013 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-114">The **Test-CsDatabase** cmdlet verifies connectivity to one or more Lync Server 2013 databases.</span></span> <span data-ttu-id="d4c0b-115">在运行时， **CsDatabase** cmdlet 会读取 Lync Server 拓扑，尝试连接到相关数据库，然后报告每次尝试成功或失败。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-115">When run, the **Test-CsDatabase** cmdlet reads the Lync Server topology, attempts to connect to relevant databases, and then reports back the success or failure of each try.</span></span> <span data-ttu-id="d4c0b-116">如果可以建立连接，该 cmdlet 还将返回数据库名称、SQL Server 版本以及所有已安装的镜像数据库的位置等信息。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-116">If a connection can be made, the cmdlet will also report back such information as the database name, SQL Server version information, and the location of any installed mirror databases.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="d4c0b-117">运行测试</span><span class="sxs-lookup"><span data-stu-id="d4c0b-117">Running the test</span></span>

<span data-ttu-id="d4c0b-118">示例 1 中显示的命令验证中央管理数据库的配置。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-118">The command shown in Example 1 verifies the configuration of the Central Management database.</span></span>

    Test-CsDatabase -CentralManagementDatabase

<span data-ttu-id="d4c0b-119">示例2验证安装在计算机 atl-sql-001.litwareinc.com 上的所有 Lync Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-119">Example 2 verifies all the Lync Server databases installed on the computer atl-sql-001.litwareinc.com.</span></span>

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

<span data-ttu-id="d4c0b-p103">在示例 3 中，仅对安装在计算机 atl-sql-001.litwareinc.com 上的存档数据库执行验证。请注意，包括了 SqlInstanceName 参数以指定存档数据库所在的 SQL Server 实例 (Archinst)。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-p103">In Example 3, verification is performed only for the Archiving database installed on the computer atl-sql-001.litwareinc.com. Note that the SqlInstanceName parameter is included to specify the SQL Server instance (Archinst) where the Archiving database is located.</span></span>

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

<span data-ttu-id="d4c0b-122">示例 4 中显示的命令用于验证本地计算机上安装的数据库。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-122">The command shown in Example 4 verifies the databases installed on the local computer.</span></span>

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="d4c0b-123">确定成功或失败</span><span class="sxs-lookup"><span data-stu-id="d4c0b-123">Determining success or failure</span></span>

<span data-ttu-id="d4c0b-124">如果数据库连接配置正确，您将收到与以下内容类似的输出，其中 "成功" 属性被标记为 **True**：</span><span class="sxs-lookup"><span data-stu-id="d4c0b-124">If database connectivity is configured correctly, you'll receive output similar to this, with the Succeed property marked as **True**:</span></span>

<span data-ttu-id="d4c0b-125">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4c0b-125">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="d4c0b-126">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="d4c0b-126">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4c0b-127">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-127">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4c0b-128">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-128">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4c0b-129">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="d4c0b-129">DatabaseName : xds</span></span>

<span data-ttu-id="d4c0b-130">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4c0b-130">DataSource :</span></span>

<span data-ttu-id="d4c0b-131">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-131">SQLServerVersion :</span></span>

<span data-ttu-id="d4c0b-132">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="d4c0b-132">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="d4c0b-133">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-133">InstalledVersion :</span></span>

<span data-ttu-id="d4c0b-134">成功： True</span><span class="sxs-lookup"><span data-stu-id="d4c0b-134">Succeed : True</span></span>

<span data-ttu-id="d4c0b-135">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4c0b-135">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="d4c0b-136">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="d4c0b-136">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4c0b-137">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-137">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4c0b-138">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-138">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4c0b-139">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="d4c0b-139">DatabaseName : lis</span></span>

<span data-ttu-id="d4c0b-140">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4c0b-140">DataSource :</span></span>

<span data-ttu-id="d4c0b-141">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-141">SQLServerVersion :</span></span>

<span data-ttu-id="d4c0b-142">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="d4c0b-142">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="d4c0b-143">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-143">InstalledVersion :</span></span>

<span data-ttu-id="d4c0b-144">成功： True</span><span class="sxs-lookup"><span data-stu-id="d4c0b-144">Succeed : True</span></span>

<span data-ttu-id="d4c0b-145">如果数据库配置正确但仍可用，则 "成功" 字段将显示为 **False**，并将提供其他警告和信息：</span><span class="sxs-lookup"><span data-stu-id="d4c0b-145">If the database is configured correctly but still available, the Succeed field will be shown as **False**, and additional warnings and information will be provided:</span></span>

<span data-ttu-id="d4c0b-146">SqlServerFqdn： atl-sql-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4c0b-146">SqlServerFqdn : atl-sql-001.litwareinc.com</span></span>

<span data-ttu-id="d4c0b-147">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="d4c0b-147">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4c0b-148">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-148">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4c0b-149">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-149">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4c0b-150">DatabaseName： xds</span><span class="sxs-lookup"><span data-stu-id="d4c0b-150">DatabaseName : xds</span></span>

<span data-ttu-id="d4c0b-151">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4c0b-151">DataSource :</span></span>

<span data-ttu-id="d4c0b-152">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-152">SQLServerVersion :</span></span>

<span data-ttu-id="d4c0b-153">ExpectedVersion : 10.13.2</span><span class="sxs-lookup"><span data-stu-id="d4c0b-153">ExpectedVersion : 10.13.2</span></span>

<span data-ttu-id="d4c0b-154">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-154">InstalledVersion :</span></span>

<span data-ttu-id="d4c0b-155">成功： False</span><span class="sxs-lookup"><span data-stu-id="d4c0b-155">Succeed : False</span></span>

<span data-ttu-id="d4c0b-156">SqlServerFqdn： atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="d4c0b-156">SqlServerFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="d4c0b-157">SqlInstanceName： rtc</span><span class="sxs-lookup"><span data-stu-id="d4c0b-157">SqlInstanceName : rtc</span></span>

<span data-ttu-id="d4c0b-158">MirrorSqlServerFqdn :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-158">MirrorSqlServerFqdn :</span></span>

<span data-ttu-id="d4c0b-159">MirrorSqlInstanceName :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-159">MirrorSqlInstanceName :</span></span>

<span data-ttu-id="d4c0b-160">DatabaseName： .lis</span><span class="sxs-lookup"><span data-stu-id="d4c0b-160">DatabaseName : lis</span></span>

<span data-ttu-id="d4c0b-161">DataSource</span><span class="sxs-lookup"><span data-stu-id="d4c0b-161">DataSource :</span></span>

<span data-ttu-id="d4c0b-162">SQLServerVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-162">SQLServerVersion :</span></span>

<span data-ttu-id="d4c0b-163">ExpectedVersion : 3.1.1</span><span class="sxs-lookup"><span data-stu-id="d4c0b-163">ExpectedVersion : 3.1.1</span></span>

<span data-ttu-id="d4c0b-164">InstalledVersion :</span><span class="sxs-lookup"><span data-stu-id="d4c0b-164">InstalledVersion :</span></span>

<span data-ttu-id="d4c0b-165">成功： False</span><span class="sxs-lookup"><span data-stu-id="d4c0b-165">Succeed : False</span></span>

<span data-ttu-id="d4c0b-166">警告： Test-CsDatabase 遇到错误。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-166">WARNING: Test-CsDatabase encountered errors.</span></span> <span data-ttu-id="d4c0b-167">请参阅日志文件获取</span><span class="sxs-lookup"><span data-stu-id="d4c0b-167">Consult the log file for a</span></span>

<span data-ttu-id="d4c0b-168">详细分析，并确保解决 (2) 的所有错误和警告 (0) </span><span class="sxs-lookup"><span data-stu-id="d4c0b-168">detailed analysis, and to make sure that all errors (2) and warnings (0) are addressed</span></span>

<span data-ttu-id="d4c0b-169">，然后再继续。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-169">before continuing.</span></span>

<span data-ttu-id="d4c0b-170">警告：详细结果可在以下位置找到：</span><span class="sxs-lookup"><span data-stu-id="d4c0b-170">WARNING: Detailed results can be found at</span></span>

<span data-ttu-id="d4c0b-171">"C： \\ 用户 \\ 测试 \\ AppData \\ 本地 \\ 临时 \\ 2 \\ 测试-CsDatabase-b18d488a-8044-4679-bbf2-</span><span class="sxs-lookup"><span data-stu-id="d4c0b-171">"C:\\Users\\Testing\\AppData\\Local\\Temp\\2\\Test-CsDatabase-b18d488a-8044-4679-bbf2-</span></span>

<span data-ttu-id="d4c0b-172">04d593cce8e6.html "。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-172">04d593cce8e6.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="d4c0b-173">测试可能失败的原因</span><span class="sxs-lookup"><span data-stu-id="d4c0b-173">Reasons why the test might have failed</span></span>

<span data-ttu-id="d4c0b-174">以下是 **测试 CsDatabase** 可能失败的一些常见原因：</span><span class="sxs-lookup"><span data-stu-id="d4c0b-174">Here are some common reasons why **Test-CsDatabase** might fail:</span></span>

  - <span data-ttu-id="d4c0b-175">提供的参数值不正确。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-175">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="d4c0b-176">如果使用，则必须正确配置可选参数或测试将失败。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-176">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="d4c0b-177">重新运行不带可选参数的命令，并查看是否成功。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-177">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="d4c0b-178">如果数据库配置错误或尚未部署，则此命令将失败。</span><span class="sxs-lookup"><span data-stu-id="d4c0b-178">This command will fail if the database is misconfigured or not yet deployed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4c0b-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4c0b-179">See Also</span></span>


[<span data-ttu-id="d4c0b-180">CsDatabaseMirrorState</span><span class="sxs-lookup"><span data-stu-id="d4c0b-180">Get-CsDatabaseMirrorState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[<span data-ttu-id="d4c0b-181">Get-csservice</span><span class="sxs-lookup"><span data-stu-id="d4c0b-181">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="d4c0b-182">CsUserDatabaseState</span><span class="sxs-lookup"><span data-stu-id="d4c0b-182">Get-CsUserDatabaseState</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

