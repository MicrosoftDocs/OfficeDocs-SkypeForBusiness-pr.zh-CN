---
title: Lync Server 2013 持久聊天资源工具包工具
description: Lync Server 2013 持久聊天资源工具包工具。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 Persistent Chat Resource Kit Tools
ms:assetid: 7a34d2ba-eb25-4e22-92d1-b9baf81b102c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945599(v=OCS.15)
ms:contentKeyID: 51541423
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 336e81c97da73da47eee654161a7d8d8956f9edb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542348"
---
# <a name="lync-server-2013-persistent-chat-resource-kit-tools"></a><span data-ttu-id="c7470-103">Lync Server 2013 持久聊天资源工具包工具</span><span class="sxs-lookup"><span data-stu-id="c7470-103">Lync Server 2013 Persistent Chat Resource Kit Tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7470-104">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c7470-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="c7470-105">Lync Server 2013 持久聊天资源工具包工具有助于为部署和管理 Lync Server 2013 持久聊天服务器的 IT 管理员更轻松地执行日常任务。</span><span class="sxs-lookup"><span data-stu-id="c7470-105">The Lync Server 2013 Persistent Chat Resource Kit tools help to make routine tasks easier for IT administrators who deploy and manage Lync Server 2013 Persistent Chat Server.</span></span> <span data-ttu-id="c7470-106">除了安装说明之外，本主题还介绍了每个工具的用途及其用法示例。</span><span class="sxs-lookup"><span data-stu-id="c7470-106">In addition to installation instructions, this topic describes the purpose of each tool, and examples of its use.</span></span>

<div>

## <a name="installation-of-the-resource-kit-tools"></a><span data-ttu-id="c7470-107">资源工具包工具的安装</span><span class="sxs-lookup"><span data-stu-id="c7470-107">Installation of the Resource Kit Tools</span></span>

<span data-ttu-id="c7470-108">若要安装 Lync Server 2013、资源工具包工具，请下载 **PersistentChatReskit.msi**。</span><span class="sxs-lookup"><span data-stu-id="c7470-108">To install the Lync Server 2013, Resource Kit Tools, download **PersistentChatReskit.msi**.</span></span> <span data-ttu-id="c7470-109">运行 **PersistentChatReskit.msi** 以执行简单安装。</span><span class="sxs-lookup"><span data-stu-id="c7470-109">Run **PersistentChatReskit.msi** to do a simple installation.</span></span> <span data-ttu-id="c7470-110">.Msi 在以下路径中安装所有工具： \\ **Program Files \\ Microsoft Lync Server 2013 \\ Persistent Chat server 资源工具包**。</span><span class="sxs-lookup"><span data-stu-id="c7470-110">The .msi installs all the tools in the following path: \\**Program Files\\ Microsoft Lync Server 2013\\Persistent Chat Server Resource Kit**.</span></span> <span data-ttu-id="c7470-111">包含自包含可执行文件的工具位于此文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c7470-111">Tools that are self-contained executables are in this folder.</span></span> <span data-ttu-id="c7470-112">还包含文件的工具位于自己的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c7470-112">Tools that also have files are in their own subfolders.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7470-113">安装 Lync Server 2013 （资源工具包工具）后，必须安装<STRONG>PsExec.exe</STRONG>并将<STRONG>PsExec.exe</STRONG>复制到以下路径： \\ <STRONG>Program Files \ Microsoft Lync Server 2013 \ Persistent Chat server Resource Kit\ChatStressTool</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="c7470-113">After installing the Lync Server 2013, Resource Kit Tools, you must install <STRONG>PsExec.exe</STRONG> and copy <STRONG>PsExec.exe</STRONG> to the following path: \\<STRONG>Program Files\ Microsoft Lync Server 2013\Persistent Chat Server Resource Kit\ChatStressTool</STRONG>.</span></span> <span data-ttu-id="c7470-114">如果不复制 <STRONG>PsExec.exe</STRONG>，持久聊天工具将引发错误异常，且不能正常运行。</span><span class="sxs-lookup"><span data-stu-id="c7470-114">If you do not copy <STRONG>PsExec.exe</STRONG>, the Persistent Chat Stress Tool will throw an error exception, and not perform correctly.</span></span> <span data-ttu-id="c7470-115">在运行该工具之前，请确保满足此先决条件要求。</span><span class="sxs-lookup"><span data-stu-id="c7470-115">Make sure that you meet this prerequisite requirement prior to running the tool.</span></span> <span data-ttu-id="c7470-116">有关安装 <STRONG>PsExec.exe</STRONG>的详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A> 。</span><span class="sxs-lookup"><span data-stu-id="c7470-116">For details about installing <STRONG>PsExec.exe</STRONG>, see <A href="https://go.microsoft.com/fwlink/p/?linkid=282246">https://go.microsoft.com/fwlink/p/?LinkId=282246</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-environments"></a><span data-ttu-id="c7470-117">支持的环境</span><span class="sxs-lookup"><span data-stu-id="c7470-117">Supported Environments</span></span>

<span data-ttu-id="c7470-118">为了获得最佳性能，Lync Server 2013，资源工具包工具应安装在相同的环境中，并且具有与 Lync Server 2013 所需的相同规范。</span><span class="sxs-lookup"><span data-stu-id="c7470-118">For optimal performance, the Lync Server 2013, Resource Kit Tools should be installed in the same environment and with the same specifications that are required for Lync Server 2013.</span></span>

</div>

<div>

## <a name="resource-kit-tools-overview"></a><span data-ttu-id="c7470-119">资源工具包工具概述</span><span class="sxs-lookup"><span data-stu-id="c7470-119">Resource Kit Tools Overview</span></span>

<span data-ttu-id="c7470-120">以下是 Lync Server 2013 持久聊天资源工具包中提供的工具。</span><span class="sxs-lookup"><span data-stu-id="c7470-120">Here are the tools that are provided in the Lync Server 2013 Persistent Chat Resource Kit.</span></span> <span data-ttu-id="c7470-121">下一节提供了每个工具的说明，包括要求和示例用法。</span><span class="sxs-lookup"><span data-stu-id="c7470-121">The following section provides a description of each tool, including requirements and example usage.</span></span>

  - <span data-ttu-id="c7470-122">AffCheck</span><span class="sxs-lookup"><span data-stu-id="c7470-122">AffCheck</span></span>

  - <span data-ttu-id="c7470-123">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="c7470-123">ChatMonitoringSummary</span></span>

  - <span data-ttu-id="c7470-124">ChatStress 工具</span><span class="sxs-lookup"><span data-stu-id="c7470-124">ChatStress Tool</span></span>

  - <span data-ttu-id="c7470-125">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="c7470-125">ChatUpgradeVerifier</span></span>

  - <span data-ttu-id="c7470-126">ChatUsageReport</span><span class="sxs-lookup"><span data-stu-id="c7470-126">ChatUsageReport</span></span>

  - <span data-ttu-id="c7470-127">ScheduleADSyncforPrincipal</span><span class="sxs-lookup"><span data-stu-id="c7470-127">ScheduleADSyncforPrincipal</span></span>

</div>

<div>

## <a name="affcheck"></a><span data-ttu-id="c7470-128">AffCheck</span><span class="sxs-lookup"><span data-stu-id="c7470-128">AffCheck</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c7470-129">说明</span><span class="sxs-lookup"><span data-stu-id="c7470-129">Description</span></span>

<span data-ttu-id="c7470-130">AffCheck 工具确认持久聊天后端数据库用户和组附属记录与 Active Directory 域服务的记录相匹配。</span><span class="sxs-lookup"><span data-stu-id="c7470-130">The AffCheck tool confirms that the Persistent Chat back-end database user and group affiliation records match that of Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c7470-131">要求</span><span class="sxs-lookup"><span data-stu-id="c7470-131">Requirements</span></span>

<span data-ttu-id="c7470-132">该工具随加入域的计算机上的 PersistentChatResKit 安装程序一起安装。</span><span class="sxs-lookup"><span data-stu-id="c7470-132">The tool is installed with the PersistentChatResKit installer on a domain joined machine.</span></span>

<span data-ttu-id="c7470-133">运行该工具所使用的用户帐户必须具有对持久聊天后端数据库和 Active Directory 域服务的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="c7470-133">The user account under which the tool is run must have Read access to the Persistent Chat back-end database and Active Directory Domain Services.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c7470-134">用法</span><span class="sxs-lookup"><span data-stu-id="c7470-134">Usage</span></span>

<span data-ttu-id="c7470-135">根据配置文件中的说明配置 AffCheck.exe.config 文件，并运行不带命令行参数的 AffCheck 工具。</span><span class="sxs-lookup"><span data-stu-id="c7470-135">Configure the AffCheck.exe.config file according to the instructions in the config file and run the AffCheck tool without command-line parameters.</span></span> <span data-ttu-id="c7470-136">以下是默认 AffCheck.exe.config 的内容。</span><span class="sxs-lookup"><span data-stu-id="c7470-136">Following are the contents of the default AffCheck.exe.config.</span></span>

<span data-ttu-id="c7470-137">**AffCheck.exe.config：**</span><span class="sxs-lookup"><span data-stu-id="c7470-137">**AffCheck.exe.config:**</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <appSettings>
        <!--Domain Controller IP Address-->
        <add key="LDAP" value="LDAP://0.0.0.0/"/>
        
        <!-- Domain DN  This is case sensitive, it must match exactly-->
        <add key="DomainComponent" value ="DC=DOMAIN,DC=COM"/>
        
        <!--Domain Administrator Login and Password-->
        <add key="DomainLogin" value="DOMAIN\Administrator"/>
        <add key="DomainPassword" value ="password"/>
        
        <!-- Connection string to Group Chat Database-->
        <add key="ConnectionString" value="data source=SQL_SERVER\INSTANCE;initial catalog=DATABASE_NAME;integrated security=SSPI"/>
        
        <!--Check group affiliations-->
        <add key="CheckGroups" value="true"/>
        
        <!--Check user affilations-->
        <add key="CheckUsers" value="true"/>
        
        <!--List all affiliations if there is a mismatch between database and active directory-->
        <add key="ListAffiliations" value="true"/>
    
        <!--If you need to offset the results of the number of affilations in AD(can be negative to add to AD parent count)-->
        <add key="Offset" value ="0"/>
    
        <!--If you need to ignore certain parents, provide a semi colon delimitted list.-->
        <add key="Ignore" value ="DC=uatest,DC=test,DC=contoso,DC=com;DC=test,DC=contoso,DC=com"/>
      </appSettings>
    </configuration>
  ```
</div>

</div>

<div>

## <a name="chatmonitoringsummary"></a><span data-ttu-id="c7470-138">ChatMonitoringSummary</span><span class="sxs-lookup"><span data-stu-id="c7470-138">ChatMonitoringSummary</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c7470-139">说明</span><span class="sxs-lookup"><span data-stu-id="c7470-139">Description</span></span>

<span data-ttu-id="c7470-140">PersistentChatMonitoringSummary 工具将持久聊天监视信息从监控数据库移动到指定的 CSV 日志文件中。</span><span class="sxs-lookup"><span data-stu-id="c7470-140">The PersistentChatMonitoringSummary tool moves Persistent Chat monitoring information from the monitoring database into a specified CSV log file.</span></span>

<span data-ttu-id="c7470-141">CSV 文件将包含按会话总数、成功会话、意外故障、预期失败次数以及诊断 ID、失败次数和失败说明细分意外故障的连续聊天会话的细目。</span><span class="sxs-lookup"><span data-stu-id="c7470-141">The CSV file will contain a breakdown of Persistent Chat sessions by number of total sessions, successful sessions, unexpected failures, expected failures, and a breakdown of the unexpected failures by diagnostic ID, number of failures, and failure description.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c7470-142">要求</span><span class="sxs-lookup"><span data-stu-id="c7470-142">Requirements</span></span>

<span data-ttu-id="c7470-143">在有权访问监控数据库的加入域的计算机上安装持久聊天资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="c7470-143">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Monitoring database.</span></span>

<span data-ttu-id="c7470-144">运行该工具所使用的用户帐户必须具有对监控数据库的读取权限。</span><span class="sxs-lookup"><span data-stu-id="c7470-144">The user account under which the tool runs must have Read access to the Monitoring database.</span></span>

<span data-ttu-id="c7470-145">PersistentChatMonitoringSummary.exe.config 的文件中，必须包含一个 \<connectionStrings\> 定义监控数据库的连接字符串的节。</span><span class="sxs-lookup"><span data-stu-id="c7470-145">The file, PersistentChatMonitoringSummary.exe.config, must contain a \<connectionStrings\> section that defines the connection string to the Monitoring database.</span></span> <span data-ttu-id="c7470-146">它还必须包含将为其收集监控数据的 PersistentChatEndpointUri 的键，以及将生成的 CSV 文件的位置的文件路径。</span><span class="sxs-lookup"><span data-stu-id="c7470-146">It must also contain a key for the PersistentChatEndpointUri that the monitoring data will be gathered for, and a file path to a location for the CSV file that will be generated.</span></span> <span data-ttu-id="c7470-147">有关示例，请参阅已安装的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c7470-147">Refer to the installed config file for examples.</span></span> <span data-ttu-id="c7470-148">文件必须与工具位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="c7470-148">The file must be located in the same directory as the tool.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c7470-149">用法</span><span class="sxs-lookup"><span data-stu-id="c7470-149">Usage</span></span>

```Batch
    PersistentChatMonitoringSummary [-StartDateTime <date>] [-EndDateTime <date>]
```

<span data-ttu-id="c7470-150">这些参数定义数据的选择：</span><span class="sxs-lookup"><span data-stu-id="c7470-150">These parameters define the selection of data:</span></span>

<span data-ttu-id="c7470-151">**StartDateTime：** （可选）指定选择期的开始日期。</span><span class="sxs-lookup"><span data-stu-id="c7470-151">**StartDateTime:** Optionally specifies the start date of the selection period.</span></span> <span data-ttu-id="c7470-152">默认值： 1/1/1753 12:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="c7470-152">Default: 1/1/1753 12:00:00 AM</span></span>

<span data-ttu-id="c7470-153">**EndDateTime：** （可选）指定选择期的结束日期。</span><span class="sxs-lookup"><span data-stu-id="c7470-153">**EndDateTime:** Optionally specifies the last date of the selection period.</span></span> <span data-ttu-id="c7470-154">默认值： Now</span><span class="sxs-lookup"><span data-stu-id="c7470-154">Default: Now</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="c7470-155">示例</span><span class="sxs-lookup"><span data-stu-id="c7470-155">Example</span></span>

```Batch
    C:\Users\Administrator.VDOMAIN>Desktop\PersistentChatMonitoringSummary.exe
    Reading database connection information, Persistent Chat endpoint uri, and csv output path information from the application config file...
    Connecting to Monitoring database with connection string specified in the application config file...
    Gathering Persistent Chat Session Summary information between "1/1/1753 12:00:00 AM" and "11/19/2012 10:11:25 AM" for Persistent Chat Endpoint Uri "persistentChatEndpointUri@domain.com"...
    Press enter to continue or hit ctr-c if these settings are incorrect...
    
    The summary information about Persistent Chat sessions from the Monitoring database has been output to C:\PersistentChatMonitoring_dd4ace24-4c8a-4a3d-8fd4-591bdfacf47b.csv
    Press enter to exit...
```

</div>

</div>

<div>

## <a name="persistent-chat-stress-tool"></a><span data-ttu-id="c7470-156">持久聊天应力工具</span><span class="sxs-lookup"><span data-stu-id="c7470-156">Persistent Chat Stress Tool</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c7470-157">说明</span><span class="sxs-lookup"><span data-stu-id="c7470-157">Description</span></span>

<span data-ttu-id="c7470-158">持久聊天压力工具提供了一种简单的方法来模拟持久聊天的使用情况，以测试实际性能，包括各种用户模型以更好地适合预期的使用方案。</span><span class="sxs-lookup"><span data-stu-id="c7470-158">The Persistent Chat Stress tool provides an easy way to simulate usage of Persistent Chat to test real-world performance, including varied user models to better fit your expected usage scenarios.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c7470-159">要求</span><span class="sxs-lookup"><span data-stu-id="c7470-159">Requirements</span></span>

<span data-ttu-id="c7470-160">将持久聊天资源工具包工具安装到可访问持久聊天后端数据库的加入域的计算机上。</span><span class="sxs-lookup"><span data-stu-id="c7470-160">Install the Persistent Chat Resource Kit tools onto a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="c7470-161">除了此 *控制器* 计算机之外，还需要多个 *加载程序* 计算机。</span><span class="sxs-lookup"><span data-stu-id="c7470-161">In addition to this *controller* machine, you will need several *loader* machines.</span></span> <span data-ttu-id="c7470-162">对于用户模型中的每个10K 用户，加载项计算机上至少需要4GB 的可用 RAM。</span><span class="sxs-lookup"><span data-stu-id="c7470-162">For every 10K users in your user model, you will need at least 4GB of free RAM on a loader machine.</span></span> <span data-ttu-id="c7470-163">例如，运行80K 用户将需要在所有加载程序计算机上分配 32 GB RAM。</span><span class="sxs-lookup"><span data-stu-id="c7470-163">For example, a run with 80K users will require about 32GB of RAM spread across all loader machines.</span></span> <span data-ttu-id="c7470-164">建议您至少具有三个加载程序计算机，而不考虑预期的负载。</span><span class="sxs-lookup"><span data-stu-id="c7470-164">We recommend that you have at least three loader machines, regardless of expected load.</span></span>

<span data-ttu-id="c7470-165">加载程序计算机必须安装 .NET 4.5 Framework 以及安装的 Visual c + + 2012 可再发行组件。</span><span class="sxs-lookup"><span data-stu-id="c7470-165">Loader machines must have the .NET 4.5 Framework as well as the Visual C++ 2012 Redistributable installed.</span></span>

</div>

<div>

## <a name="configuration"></a><span data-ttu-id="c7470-166">配置</span><span class="sxs-lookup"><span data-stu-id="c7470-166">Configuration</span></span>

<span data-ttu-id="c7470-167">将 ChatStressTool 文件复制到可从所有加载程序计算机访问的共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="c7470-167">Copy ChatStressTool files into a shared folder accessible from all loader machines.</span></span>

<span data-ttu-id="c7470-168">创建在压力运行中使用的用户和频道：</span><span class="sxs-lookup"><span data-stu-id="c7470-168">Create users and channels for use in the stress run:</span></span>

  - <span data-ttu-id="c7470-169">为您的用户模型调用创建任意多个用户，为 Lync 启用它们，并将其持久聊天策略设置为 "启用"。</span><span class="sxs-lookup"><span data-stu-id="c7470-169">Create as many users as your user model calls for, enable them for Lync, and set their Persistent Chat policy to Enabled.</span></span>

  - <span data-ttu-id="c7470-170">为您的压力通道创建一个类别，然后根据该类别的需要创建任意多个会议室。</span><span class="sxs-lookup"><span data-stu-id="c7470-170">Create a category for your stress channels, and then create as many rooms as are needed under that category.</span></span> <span data-ttu-id="c7470-171">类别应将所有压力用户放在其 **允许** 列表中 (通过添加其 OU) 的方式，并且压力会议室应具有 **开放**的隐私设置。</span><span class="sxs-lookup"><span data-stu-id="c7470-171">The category should have all stress users in its **Allowed** list (by way of adding their OU), and stress rooms should have a privacy setting of **Open**.</span></span>

  - <span data-ttu-id="c7470-172">我们建议创建额外的压力房间。</span><span class="sxs-lookup"><span data-stu-id="c7470-172">We recommend creating extra stress rooms.</span></span> <span data-ttu-id="c7470-173">您可以使用以下 Windows PowerShell 命令行界面命令创建50000聊天室：</span><span class="sxs-lookup"><span data-stu-id="c7470-173">You can create 50,000 rooms with the following Windows PowerShell command-line interface command:</span></span>
    ```Powershell
        for ($i = 0; $i -le 50000; $i++) { New-CsPersistentChatRoom -Category <parent category> -Name "StressChan_$i" -Privacy Open }
    ```    

<span data-ttu-id="c7470-174">编辑配置文件以适用于您的拓扑：</span><span class="sxs-lookup"><span data-stu-id="c7470-174">Edit the configuration files to fit your topology:</span></span>

<span data-ttu-id="c7470-175">在 **LoaderProcess.exe.config**中，将 "controller.contoso.com" 更改为控制器计算机的完全限定的域名 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="c7470-175">In **LoaderProcess.exe.config**, change “controller.contoso.com” to the controller machine’s fully qualified domain name (FQDN).</span></span>

<span data-ttu-id="c7470-176">在 **StressLauncher.exe.config 中：**</span><span class="sxs-lookup"><span data-stu-id="c7470-176">In **StressLauncher.exe.config:**</span></span>

1.  <span data-ttu-id="c7470-177">将 "LoaderBinary" 设置值更改为共享文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="c7470-177">Change the “LoaderBinary” setting value to the shared folder’s path.</span></span>

2.  <span data-ttu-id="c7470-178">将 "AdminUser"/"AdminPassword" 更改为具有对加载程序计算机的管理员访问权限的凭据。</span><span class="sxs-lookup"><span data-stu-id="c7470-178">Change “AdminUser”/”AdminPassword” to credentials that have admin access to loader machines.</span></span>

3.  <span data-ttu-id="c7470-179">将 "ChannelCategory" 更改为在其下创建了压力通道的类别的名称。</span><span class="sxs-lookup"><span data-stu-id="c7470-179">Change “ChannelCategory” to the name of the category that stress channels have been created under.</span></span>

4.  <span data-ttu-id="c7470-180">将 "UserNamePattern" 和 "UserPasswordPattern" 更改为与你的压力用户凭据相匹配的模板。</span><span class="sxs-lookup"><span data-stu-id="c7470-180">Change “UserNamePattern” and “UserPasswordPattern” to a template that matches your stress user credentials.</span></span> <span data-ttu-id="c7470-181">{0} 将替换为用户的索引号。</span><span class="sxs-lookup"><span data-stu-id="c7470-181">{0} is replaced with the user’s index number.</span></span>

5.  <span data-ttu-id="c7470-182">将 "域" 更改为测试拓扑的 SIP 域。</span><span class="sxs-lookup"><span data-stu-id="c7470-182">Change “Domain” to the SIP domain of your test topology.</span></span>

6.  <span data-ttu-id="c7470-183">将 "ConnectionString" 更改为持久聊天后端数据库的连接字符串。</span><span class="sxs-lookup"><span data-stu-id="c7470-183">Change “ConnectionString” to a connection string for your Persistent Chat back-end database.</span></span>

7.  <span data-ttu-id="c7470-184">将 "UserIndexStart" 更改为第一个压力用户的索引。</span><span class="sxs-lookup"><span data-stu-id="c7470-184">Change “UserIndexStart” to the index of the first stress user.</span></span>

8.  <span data-ttu-id="c7470-185">将 "LyncFQDN" 更改为前端池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c7470-185">Change “LyncFQDN” to the FQDN of your Front End pool.</span></span>

9.  <span data-ttu-id="c7470-186">修改 "计算机" 列表，以包含所有加载程序计算机的计算机名称。</span><span class="sxs-lookup"><span data-stu-id="c7470-186">Modify the “Machines” list to include machine names for all of your loader machines.</span></span>

10. <span data-ttu-id="c7470-187">更改服务终结 (点的 baseAddress 默认值为 "controller.contoso.com" ) 到控制器计算机的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c7470-187">Change the baseAddress of the service endpoint (default is “controller.contoso.com”) to the FQDN of your controller machine.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c7470-188">用法</span><span class="sxs-lookup"><span data-stu-id="c7470-188">Usage</span></span>

<span data-ttu-id="c7470-189">配置完成后，在控制器计算机上打开 StressLauncher.exe。</span><span class="sxs-lookup"><span data-stu-id="c7470-189">After configuration is complete, open StressLauncher.exe on the controller machine.</span></span> <span data-ttu-id="c7470-190">您可以以任何用户的形式启动 StressLauncher。</span><span class="sxs-lookup"><span data-stu-id="c7470-190">You can launch StressLauncher as any user.</span></span> <span data-ttu-id="c7470-191">必须在配置文件中指定用于在加载程序计算机上启动加载程序进程的凭据。</span><span class="sxs-lookup"><span data-stu-id="c7470-191">The credentials under which the loader processes start on the loader machines must be specified in the config file.</span></span> <span data-ttu-id="c7470-192">此外，还必须为连接字符串提供对持久聊天后端数据库的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="c7470-192">You also must give a connection string that has Read access to the Persistent Chat back-end database.</span></span> <span data-ttu-id="c7470-193">如果此连接字符串使用集成的 Windows 身份验证，则必须以具有此访问权限的用户身份启动 StressLauncher。</span><span class="sxs-lookup"><span data-stu-id="c7470-193">If this connection string uses integrated Windows authentication, you must launch StressLauncher as a user that has this access.</span></span>

<span data-ttu-id="c7470-194">根据需要更改用户模型设置。</span><span class="sxs-lookup"><span data-stu-id="c7470-194">Alter the user model settings as needed.</span></span> <span data-ttu-id="c7470-195">单击 " **开始加载** " 以启动运行。</span><span class="sxs-lookup"><span data-stu-id="c7470-195">Click **Start Load** to initiate a run.</span></span> <span data-ttu-id="c7470-196">一分钟后，用户将开始登录，进度栏将开始填充。</span><span class="sxs-lookup"><span data-stu-id="c7470-196">After a minute or so, users will start being signed in, and the progress bar will begin to fill.</span></span> <span data-ttu-id="c7470-197">在这种情况下，您可能可以运行控制器计算机并采用性能度量。</span><span class="sxs-lookup"><span data-stu-id="c7470-197">At this point, you may can the controller machine working and take performance measurements.</span></span>

</div>

</div>

<div>

## <a name="chatupgradeverifier"></a><span data-ttu-id="c7470-198">ChatUpgradeVerifier</span><span class="sxs-lookup"><span data-stu-id="c7470-198">ChatUpgradeVerifier</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c7470-199">说明</span><span class="sxs-lookup"><span data-stu-id="c7470-199">Description</span></span>

<span data-ttu-id="c7470-200">ChatUpgradeVerifier 是一种持久的聊天特定数据库比较工具。</span><span class="sxs-lookup"><span data-stu-id="c7470-200">ChatUpgradeVerifier is a Persistent Chat specific database comparison tool.</span></span> <span data-ttu-id="c7470-201">该工具将组聊天 2007 R2 或组聊天2010数据库 (2007/2010Db) 与持久聊天2013数据库 (2013Db) 进行比较。</span><span class="sxs-lookup"><span data-stu-id="c7470-201">The tool compares either the Group Chat 2007 R2 or Group Chat 2010 Database (2007/2010Db) to the Persistent Chat 2013 Database (2013Db).</span></span>

<span data-ttu-id="c7470-202">该工具将逐个检查、每个类别、持久聊天室和外接程序在 2007/2010Db 中进行检查，以查看它是否出现在2013Db 中。</span><span class="sxs-lookup"><span data-stu-id="c7470-202">The tool will check, one by one, each category, Persistent Chat room, and add-in in 2007/2010Db to see if it appears in the 2013Db.</span></span> <span data-ttu-id="c7470-203">比较包括检查类别、聊天室或外接中的所有设置、类别中的任何主体以及类别或聊天室上的角色中的任何主体。</span><span class="sxs-lookup"><span data-stu-id="c7470-203">The comparison includes checking all settings on the category, chat room, or add-in, any principals in scope on the category, and any principal in a role on either the category or the chat room.</span></span> <span data-ttu-id="c7470-204">如果类别或聊天室未在2013Db 中正确显示，则这些差异将输出到冲突文件中。</span><span class="sxs-lookup"><span data-stu-id="c7470-204">If a category or a chat room does not appear correctly in the 2013Db, the differences will be output to a conflicts file.</span></span> <span data-ttu-id="c7470-205">如果在升级后进行了升级，则会更改 2007/2010Db，然后运行此工具时，冲突文件的输出将会有所不同。</span><span class="sxs-lookup"><span data-stu-id="c7470-205">If, after the upgrade has occurred, the 2007/2010Db is changed and then this tool is run, there will be a differences output to the conflicts file.</span></span> <span data-ttu-id="c7470-206">请注意，此应用程序仅为数据库比较工具，不会验证升级过程。</span><span class="sxs-lookup"><span data-stu-id="c7470-206">Note that this application is a database comparison tool only and does not validate the upgrade process.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c7470-207">要求</span><span class="sxs-lookup"><span data-stu-id="c7470-207">Requirements</span></span>

<span data-ttu-id="c7470-208">在已加入域的计算机上安装持久聊天资源工具包工具，该计算机可访问持久聊天) 的旧版本和当前版本的现有聊天后端数据库 (。</span><span class="sxs-lookup"><span data-stu-id="c7470-208">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end databases (previous and current versions for Persistent Chat).</span></span>

<span data-ttu-id="c7470-209">运行该工具所使用的用户帐户必须具有对持久聊天数据库的读取权限。</span><span class="sxs-lookup"><span data-stu-id="c7470-209">The user account under which the tool runs must have Read access to the Persistent Chat databases.</span></span>

<span data-ttu-id="c7470-210">ChatUpgradeVerifier.exe.config 文件必须包含 GroupChat2007R2Db 参数或 GroupChat2010Db 参数，并将连接字符串指向相应的 Group Chat 数据库 (Groupchat 2007R2 或 2010) 。</span><span class="sxs-lookup"><span data-stu-id="c7470-210">The ChatUpgradeVerifier.exe.config file must contain either the GroupChat2007R2Db parameter or the GroupChat2010Db parameter, with a connection string to the appropriate Group Chat database (either Groupchat 2007R2 or 2010).</span></span> <span data-ttu-id="c7470-211">它还必须包含 PersistentChat2013Db 参数，并将连接字符串连接到持久聊天2013数据库。</span><span class="sxs-lookup"><span data-stu-id="c7470-211">It must also contain a PersistentChat2013Db parameter, with a connection string to the Persistent Chat 2013 database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c7470-212">用法</span><span class="sxs-lookup"><span data-stu-id="c7470-212">Usage</span></span>

<span data-ttu-id="c7470-213">运行不带任何参数的 **ChatUpgradeVerifier** 。</span><span class="sxs-lookup"><span data-stu-id="c7470-213">Run **ChatUpgradeVerifier** without any parameters.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="c7470-214">示例</span><span class="sxs-lookup"><span data-stu-id="c7470-214">Example</span></span>

<span data-ttu-id="c7470-215">![正在运行 ChatUpgradeVerifier.exe。](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "正在运行 ChatUpgradeVerifier.exe。")</span><span class="sxs-lookup"><span data-stu-id="c7470-215">![Running ChatUpgradeVerifier.exe.](images/JJ945599.4c273bc3-7926-47c7-ade7-34522721ebf9(OCS.15).jpg "Running ChatUpgradeVerifier.exe.")</span></span>

</div>

</div>

<div>

## <a name="persistent-chat-usage-report"></a><span data-ttu-id="c7470-216">持久聊天使用情况报告</span><span class="sxs-lookup"><span data-stu-id="c7470-216">Persistent Chat Usage Report</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c7470-217">说明</span><span class="sxs-lookup"><span data-stu-id="c7470-217">Description</span></span>

<span data-ttu-id="c7470-218">ChatUsageReport 工具生成持久聊天服务使用情况的 HTML 报告。</span><span class="sxs-lookup"><span data-stu-id="c7470-218">The ChatUsageReport tool generates an HTML report of Persistent Chat service usage.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c7470-219">要求</span><span class="sxs-lookup"><span data-stu-id="c7470-219">Requirements</span></span>

<span data-ttu-id="c7470-220">在有权访问持久聊天后端数据库的加入域的计算机上安装持久聊天资源工具包工具。</span><span class="sxs-lookup"><span data-stu-id="c7470-220">Install the Persistent Chat Resource Kit tools on a domain-joined machine that has access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="c7470-221">运行该工具所使用的用户帐户必须具有对持久聊天后端数据库的读取访问权限。</span><span class="sxs-lookup"><span data-stu-id="c7470-221">The user account under which the tool is run must have Read access to the Persistent Chat back-end database.</span></span>

<span data-ttu-id="c7470-222">ChatUsageReport.exe.config 的文件中，必须包含 \<connectionStrings\> 定义持久聊天后端数据库的连接字符串的节。</span><span class="sxs-lookup"><span data-stu-id="c7470-222">The file, ChatUsageReport.exe.config, must contain a \<connectionStrings\> section defining the connection string to the Persistent Chat back-end database.</span></span> <span data-ttu-id="c7470-223">默认配置文件的内容包含在此处，供您参考。</span><span class="sxs-lookup"><span data-stu-id="c7470-223">The contents of the default config file are included here, for your reference.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c7470-224">用法</span><span class="sxs-lookup"><span data-stu-id="c7470-224">Usage</span></span>

```Powershell
    ChatUsageReport [-StartDate {date}] [-EndDate {date}] [-TopActiveUsers {n}] [-TopActiveRooms {n}] [-LeastActiveRooms {n}] [-RoomsInactiveSince {Date}] [-OutputFolder {path}]
```
<span data-ttu-id="c7470-225">这些参数定义数据的选择：</span><span class="sxs-lookup"><span data-stu-id="c7470-225">These parameters define the selection of data:</span></span>

<span data-ttu-id="c7470-226">**起始日期：** （可选）指定选择期的 UTC 开始日期。</span><span class="sxs-lookup"><span data-stu-id="c7470-226">**StartDate:** Optionally specifies the UTC start date of the selection period.</span></span> <span data-ttu-id="c7470-227">默认：最早日期</span><span class="sxs-lookup"><span data-stu-id="c7470-227">Default: Earliest Date</span></span>

<span data-ttu-id="c7470-228">**结束日期：** （可选）指定选择期的 UTC 结束日期。</span><span class="sxs-lookup"><span data-stu-id="c7470-228">**EndDate:** Optionally specifies the UTC end date of the selection period.</span></span> <span data-ttu-id="c7470-229">默认值： Now</span><span class="sxs-lookup"><span data-stu-id="c7470-229">Default: Now</span></span>

<span data-ttu-id="c7470-230">这些参数定义了显示数据的方式和方式：</span><span class="sxs-lookup"><span data-stu-id="c7470-230">These parameters define how and what data is displayed:</span></span>

<span data-ttu-id="c7470-231">**TopActiveUsers：** 如果指定此值，则报告将包含 n 个最活跃的用户，这取决于用户在所选时段内已在聊天室中发布的邮件数。</span><span class="sxs-lookup"><span data-stu-id="c7470-231">**TopActiveUsers:** If this is specified, the report will include the n most active users in terms of the number of messages the user has posted in the chat room for the selected period.</span></span> <span data-ttu-id="c7470-232">默认值：10</span><span class="sxs-lookup"><span data-stu-id="c7470-232">Default: 10</span></span>

<span data-ttu-id="c7470-233">**TopActiveRooms：** 如果指定此值，则报告将包含 n 个最活跃的聊天室，这取决于所选时段的会议室中投递的邮件数。</span><span class="sxs-lookup"><span data-stu-id="c7470-233">**TopActiveRooms:** If this is specified, the report will include the n most active chat rooms in terms of the number of messages posted in the room for the selected period.</span></span> <span data-ttu-id="c7470-234">默认值：10</span><span class="sxs-lookup"><span data-stu-id="c7470-234">Default: 10</span></span>

<span data-ttu-id="c7470-235">**LeastActiveRooms：** 如果指定此值，则报告将包含 n 个最小活动聊天室，条件是在所选时段的聊天室中发布的邮件数。</span><span class="sxs-lookup"><span data-stu-id="c7470-235">**LeastActiveRooms:** If this is specified, the report will include the n least active chat rooms in terms of the number of messages posted in the chat room for the selected period.</span></span> <span data-ttu-id="c7470-236">聊天室将至少发布一封邮件。</span><span class="sxs-lookup"><span data-stu-id="c7470-236">Rooms will have at least one message posted.</span></span> <span data-ttu-id="c7470-237">默认值：10</span><span class="sxs-lookup"><span data-stu-id="c7470-237">Default: 10</span></span>

<span data-ttu-id="c7470-238">**RoomsInactiveSince：** 如果指定此类型，报告将包含自指定日期后处于非活动状态的聊天室的列表。</span><span class="sxs-lookup"><span data-stu-id="c7470-238">**RoomsInactiveSince:** If this is specified, the report will include a list of chat rooms that have been inactive since the specified date.</span></span> <span data-ttu-id="c7470-239">默认值：整个时间</span><span class="sxs-lookup"><span data-stu-id="c7470-239">Default: Entire Time</span></span>

<span data-ttu-id="c7470-240">**OutputFolder：** 将在其中放置 ChatUsageReport.html 和 graph 图像的文件夹。</span><span class="sxs-lookup"><span data-stu-id="c7470-240">**OutputFolder:** The folder where the ChatUsageReport.html and the graph images will be placed.</span></span> <span data-ttu-id="c7470-241">这必须在配置文件或命令行中进行定义。</span><span class="sxs-lookup"><span data-stu-id="c7470-241">This must be defined in the config file or on the command line.</span></span>

<span data-ttu-id="c7470-242">此外，还可以在与工具位于同一目录中的 ChatUsageReport.exe.config 文件中指定所有命令行参数值。</span><span class="sxs-lookup"><span data-stu-id="c7470-242">All of the command line parameter values can also be specified in the ChatUsageReport.exe.config file that is located in the same directory as the tool.</span></span> <span data-ttu-id="c7470-243">如果在配置文件和命令行中指定了任何值，则命令行值将替代 config 文件值。</span><span class="sxs-lookup"><span data-stu-id="c7470-243">If any value is specified in both the config file and the command line, the command line value will override the config file value.</span></span>

</div>

<div>

## <a name="output"></a><span data-ttu-id="c7470-244">Output</span><span class="sxs-lookup"><span data-stu-id="c7470-244">Output</span></span>

<span data-ttu-id="c7470-245">报告将始终包含以下输出：</span><span class="sxs-lookup"><span data-stu-id="c7470-245">The report will always include the following output:</span></span>

  - <span data-ttu-id="c7470-246">前 n 个最活跃聊天室（按所选时间段的邮件投递数表示）。</span><span class="sxs-lookup"><span data-stu-id="c7470-246">Top n most active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="c7470-247">按所选时间段的邮件投递次数排名前 n 个的最活跃的用户。</span><span class="sxs-lookup"><span data-stu-id="c7470-247">Top n most active users by number of message posts for selected period.</span></span>

  - <span data-ttu-id="c7470-248">前 n 个最小活动聊天室（按选定时间段内的邮件投递数表示）。</span><span class="sxs-lookup"><span data-stu-id="c7470-248">Top n least active chat rooms by number of message posts for selected period.</span></span>

  - <span data-ttu-id="c7470-249">在数据库的整个生命周期中或自指定的日期起处于非活动状态的聊天室。</span><span class="sxs-lookup"><span data-stu-id="c7470-249">Chat rooms that are inactive for the entire life of the database, or since the specified date.</span></span>

  - <span data-ttu-id="c7470-250">选定时间段内的每日邮件投递趋势。</span><span class="sxs-lookup"><span data-stu-id="c7470-250">Daily message post trend for selected period.</span></span>

  - <span data-ttu-id="c7470-251">选定时段的每周邮件投递趋势。</span><span class="sxs-lookup"><span data-stu-id="c7470-251">Weekly message post trend for selected period.</span></span>

  - <span data-ttu-id="c7470-252">选定时段的每月邮件投递趋势。</span><span class="sxs-lookup"><span data-stu-id="c7470-252">Monthly message post trend for selected period.</span></span>

  - <span data-ttu-id="c7470-253">选定时间段内的邮件投递总数。</span><span class="sxs-lookup"><span data-stu-id="c7470-253">Total message posts for selected period.</span></span>

  - <span data-ttu-id="c7470-254">已启用的会议室总数。</span><span class="sxs-lookup"><span data-stu-id="c7470-254">Total number of enabled rooms.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="c7470-255">示例</span><span class="sxs-lookup"><span data-stu-id="c7470-255">Example</span></span>

<span data-ttu-id="c7470-256">下面的示例将生成2001年的使用率报告，并将报告放置在 ChatUsageReport.exe.config 中指定的 OutputFolder 中。</span><span class="sxs-lookup"><span data-stu-id="c7470-256">The following example generates a usage report for the entire year 2001 and places the report in the OutputFolder specified in the ChatUsageReport.exe.config.</span></span>

```Powershell
    ChatUsageReport -RoomsInactiveSince 06-20-2010
```
<span data-ttu-id="c7470-257">ChatUsageReport.exe.config：</span><span class="sxs-lookup"><span data-stu-id="c7470-257">ChatUsageReport.exe.config:</span></span>

```XML
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
      <connectionStrings>
        <!-- The PersistentChat connection string must be defined in this file. -->
        <add name="PersistentChat" connectionString="Data Source=contoso.com\RTC;Initial Catalog=mgc;Integrated Security=SSPI"/>
      </connectionStrings>
      <appSettings>
        <!-- The OutputFolder must be defined here or on the command line. -->
        <add key="OutputFolder" value="."/>
        <!-- The values below are the same as the application defaults. -->
        <add key="StartDate" value="01/01/0001"/>
        <add key="EndDate" value="12/31/9999"/>
        <add key="TopActiveUsers" value="10"/>
        <add key="TopActiveRooms" value="10"/>
        <add key="LeastActiveRooms" value="10"/>
        <add key="RoomsInactiveSince" value="01/01/0001"/>
      </appSettings>
    </configuration></configuration>
```
</div>

</div>

<div>

## <a name="scheduleadsyncforprincipal"></a><span data-ttu-id="c7470-258">ScheduleADSyncForPrincipal</span><span class="sxs-lookup"><span data-stu-id="c7470-258">ScheduleADSyncForPrincipal</span></span>

<div>

## <a name="description"></a><span data-ttu-id="c7470-259">说明</span><span class="sxs-lookup"><span data-stu-id="c7470-259">Description</span></span>

<span data-ttu-id="c7470-260">ScheduleADSyncForPrincipal 是 Microsoft SQL Server 2012 脚本，它必须在连接到持久聊天后端数据库时直接从 SQL Server Management Studio 中运行。</span><span class="sxs-lookup"><span data-stu-id="c7470-260">ScheduleADSyncForPrincipal is a Microsoft SQL Server 2012 script that must be run directly from within SQL Server Management Studio when connected to the Persistent Chat back-end database.</span></span> <span data-ttu-id="c7470-261">通过此脚本，您可以强制持久聊天将用户的记录与 Active Directory 域服务的记录同步，而不是等待计划的同步时间。</span><span class="sxs-lookup"><span data-stu-id="c7470-261">This script enables you to force Persistent Chat to synchronize its records of a user with those of Active Directory Domain Services, rather than waiting for the scheduled synchronization time.</span></span>

</div>

<div>

## <a name="requirements"></a><span data-ttu-id="c7470-262">要求</span><span class="sxs-lookup"><span data-stu-id="c7470-262">Requirements</span></span>

<span data-ttu-id="c7470-263">运行脚本所使用的用户帐户必须具有对持久聊天后端数据库的所有者访问权限。</span><span class="sxs-lookup"><span data-stu-id="c7470-263">The user account under which the script is run must have owner access to the Persistent Chat back-end database.</span></span>

</div>

<div>

## <a name="usage"></a><span data-ttu-id="c7470-264">用法</span><span class="sxs-lookup"><span data-stu-id="c7470-264">Usage</span></span>

<span data-ttu-id="c7470-265">以下是默认脚本的内容：</span><span class="sxs-lookup"><span data-stu-id="c7470-265">Following are the contents of the default script:</span></span>

```Powershell
    /*
    This script will schedule a principal for a forced AD synchronization cycle
    
    If you're using Sql Server Management Studio, pressing Ctrl+Shift+M will 
    allow you to specify values for the template parameter.
    */
    
        insert into
          tblPrincipalMeta
          (
           prinID
          ,prinAffiliationsDirty
          ,prinAttributesDirty
          ,prinDeleted
          )
          select
            prinID
           ,1
           ,1
           ,0
          from
            tblPrincipal
          where
            prinID not in (select prinID from tblPrincipalMeta) and
            prinID = <PrinID,int,0>
     
        update
          tblPrincipalMeta
        set
          prinAffiliationsDirty = 1
         ,prinAttributesDirty = 1
         ,tryCount = 0
         ,nextTry = null
        where
         prinID = <PrinID,int,0>
```

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

