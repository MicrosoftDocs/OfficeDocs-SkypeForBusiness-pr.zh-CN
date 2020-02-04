---
title: Lync Server 2013：导入 Lync Server 2013 管理包
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Importing the Lync Server 2013 management packs
ms:assetid: 846287e1-660f-453f-bdba-b2137b5f0ea1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205052(v=OCS.15)
ms:contentKeyID: 48184690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cc97cad4069c286f66707c34a9a1af7e87e97da
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763826"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="02515-102">导入 Lync Server 2013 管理包</span><span class="sxs-lookup"><span data-stu-id="02515-102">Importing the Lync Server 2013 management packs</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02515-103">_**主题上次修改时间：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="02515-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="02515-104">你可以通过安装管理包来扩展 System Center Operations Manager 的功能，即决定 System Center Operations Manager 可以监视哪些项目以及应如何监视这些项目以及应如何触发警报的软件以及据.</span><span class="sxs-lookup"><span data-stu-id="02515-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="02515-105">Lync Server 2013 包括两个 System Center Operations Manager 管理包，它们提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="02515-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="02515-106">组件和用户管理包（Microsoft.LS.2013.Monitoring.ComponentAndUser.mp）跟踪事件日志中记录的 Lync Server 问题（由性能计数器注册），或记录在呼叫详细记录（CDR）或体验质量（QoE）中。数据库.</span><span class="sxs-lookup"><span data-stu-id="02515-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="02515-107">对于严重问题，System Center Operations Manager 可以配置为通过电子邮件、即时消息或短消息服务（SMS）消息通知立即通知管理员。</span><span class="sxs-lookup"><span data-stu-id="02515-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="02515-108">SMS 是用于将文本消息从一个移动设备发送到另一个移动设备的技术。</span><span class="sxs-lookup"><span data-stu-id="02515-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="02515-109">有关配置 Operations Manager 通知的详细信息，请参阅 TechNet 库中的配置通知<A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>。</span><span class="sxs-lookup"><span data-stu-id="02515-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="http://go.microsoft.com/fwlink/p/?linkid=268785">http://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="02515-110">活动监视管理包（Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp）主动测试关键 Lync 服务器组件，如登录到系统、交换即时消息或拨打公共交换上的电话电话网络（PSTN）。</span><span class="sxs-lookup"><span data-stu-id="02515-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="02515-111">这些测试通过 Lync Server 合成事务 cmdlet 进行。</span><span class="sxs-lookup"><span data-stu-id="02515-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="02515-112">例如，你可以使用**CsIM** cmdlet 来模拟一对测试用户之间的即时消息（IM）对话。</span><span class="sxs-lookup"><span data-stu-id="02515-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="02515-113">如果此模拟消息对话失败，则会生成一个警报。</span><span class="sxs-lookup"><span data-stu-id="02515-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="02515-114">您需要导入管理包。</span><span class="sxs-lookup"><span data-stu-id="02515-114">You need to import the management packs.</span></span> <span data-ttu-id="02515-115">如果不导入管理包，则无法使用 Operations Manager 监视 Lync 服务器事件或运行 Lync Server 合成事务。</span><span class="sxs-lookup"><span data-stu-id="02515-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="02515-116">组件和用户管理包仅用于监视 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="02515-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="02515-117">如果你在共存方案中，同时安装了 Lync Server 2013 和 Lync Server 2010，则应继续为 Lync Server 2010 计算机使用 Lync Server 2010 管理包。</span><span class="sxs-lookup"><span data-stu-id="02515-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="02515-118">Lync Server 2010 的管理包包括 Lync Server 2010 监视管理包和 Lync Server 2010 组聊天监视管理包。</span><span class="sxs-lookup"><span data-stu-id="02515-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="02515-119">可使用下列任一工具导入管理包：</span><span class="sxs-lookup"><span data-stu-id="02515-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="02515-120">**System Center Operations Manager**   使用此方法，你可以使用 Operations Manager 添加 Lync Server 的监视。</span><span class="sxs-lookup"><span data-stu-id="02515-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="02515-121">**Operations manager 外壳**   程序你可以使用 operations manager 外壳程序直接导入，或通过使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="02515-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="02515-122">使用 System Center Operations Manager 导入管理包</span><span class="sxs-lookup"><span data-stu-id="02515-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="02515-123">下载文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。</span><span class="sxs-lookup"><span data-stu-id="02515-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="02515-124">在 System Center Operations Manager 中，单击 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="02515-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="02515-125">在 "**管理**" 窗格中，右键单击 "**管理包**"，然后单击 "**导入管理包**"。</span><span class="sxs-lookup"><span data-stu-id="02515-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="02515-126">在“选择管理包”\*\*\*\* 对话框中，单击“添加”\*\*\*\*，然后单击“从磁盘中添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02515-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="02515-127">在 "**联机目录连接**" 对话框中，单击 "**取消**" 以防止 Operations Manager 联机以查看 Lync Server 管理包是否存在任何依赖关系。</span><span class="sxs-lookup"><span data-stu-id="02515-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="02515-128">如果您使用的是 System Center Operations Manager 2012，请单击 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="02515-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="02515-129">在 "**选择要导入的管理包**" 对话框中，找到并选择 "文件**Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** " 和 " **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** "，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="02515-129">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**.</span></span> <span data-ttu-id="02515-130">若要选择对话框中的多个文件，请单击第一个文件，按住 Ctrl 键，然后单击第二个文件。</span><span class="sxs-lookup"><span data-stu-id="02515-130">To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="02515-131">在“选择管理包”\*\*\*\* 对话框中，单击“安装”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02515-131">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="02515-132">如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="02515-132">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="02515-133">如果出现这种情况，请将文件复制到其他文件夹，然后重新启动导入和安装过程。</span><span class="sxs-lookup"><span data-stu-id="02515-133">If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="02515-134">在“选择管理包”\*\*\*\* 对话框中，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02515-134">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="02515-135">请注意，导入和安装过程可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="02515-135">Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="02515-136">使用 Operations Manager 外壳程序导入管理包</span><span class="sxs-lookup"><span data-stu-id="02515-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="02515-137">一般情况下，使用 Operations Manager 更容易导入管理包。但是，如果出现错误，并且导入失败，则控制台不会始终提供足够的错误报告。</span><span class="sxs-lookup"><span data-stu-id="02515-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="02515-138">通过比较，Operations Manager Shell 提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="02515-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="02515-139">如果你使用的是 Operations Manager，并且在导入管理包时遇到问题，请使用 Operations Manager 外壳程序导入该程序包。</span><span class="sxs-lookup"><span data-stu-id="02515-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="02515-140">Operations Manager Shell 提供详细信息，可帮助你确定导入失败的原因。</span><span class="sxs-lookup"><span data-stu-id="02515-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="02515-141">如果您使用的是 System Center Operations Manager 2007 R2，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="02515-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="02515-142">依次单击 "**开始**"、"**所有程序**"、" **System Center Operations Manager 2007 R2**"，然后单击 " **Operations Manager 外壳**程序"。</span><span class="sxs-lookup"><span data-stu-id="02515-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="02515-143">在 Operations Manager Shell 中，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="02515-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="02515-144">导入第一个管理包后，使用文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 副本的路径重复该过程：</span><span class="sxs-lookup"><span data-stu-id="02515-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="02515-145">关闭 Operations Manager 外壳程序。</span><span class="sxs-lookup"><span data-stu-id="02515-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="02515-146">如果您使用的是 System Center Operations Manager 2012，请改为完成此过程：</span><span class="sxs-lookup"><span data-stu-id="02515-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="02515-147">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft System Center 2012”\*\*\*\*、“Operations Manager”\*\*\*\* 和“Operations Manager Shell”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="02515-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="02515-148">在 Operations Manager Shell 中，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="02515-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="02515-149">导入第一个管理包后，请使用文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复该过程：</span><span class="sxs-lookup"><span data-stu-id="02515-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

