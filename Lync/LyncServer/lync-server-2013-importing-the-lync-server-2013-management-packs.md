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
ms.openlocfilehash: 4edc22c1cfc46b032e679a9dc0718113bc6967bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526649"
---
# <a name="importing-the-lync-server-2013-management-packs"></a><span data-ttu-id="63df2-102">导入 Lync Server 2013 管理包</span><span class="sxs-lookup"><span data-stu-id="63df2-102">Importing the Lync Server 2013 management packs</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63df2-103">_**上次修改的主题：** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="63df2-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="63df2-104">您可以通过安装管理包来扩展 System Center Operations Manager 的功能，该软件规定 System Center Operations Manager 可以监视的项目，以及应如何监视这些项目以及应如何触发和报告警报。</span><span class="sxs-lookup"><span data-stu-id="63df2-104">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, and how those items should be monitored and how alerts should be triggered and reported.</span></span> <span data-ttu-id="63df2-105">Lync Server 2013 包括两个 System Center Operations Manager 管理包，它们提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="63df2-105">Lync Server 2013 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

  - <span data-ttu-id="63df2-106">组件和用户管理包 (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) 跟踪在事件日志中记录的、由性能计数器注册的 Lync Server 问题，或记录在 (CDR) 的呼叫详细记录中，或在 QoE (数据库的体验质量) 。</span><span class="sxs-lookup"><span data-stu-id="63df2-106">The Component and User Management Pack (Microsoft.LS.2013.Monitoring.ComponentAndUser.mp) tracks Lync Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDR) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="63df2-107">对于关键问题，可以将 System Center Operations Manager 配置为通过电子邮件、即时消息或短信服务立即通知管理员 (SMS) 消息传递。</span><span class="sxs-lookup"><span data-stu-id="63df2-107">For critical problems, System Center Operations Manager can be configured to immediately notify administrators via email, instant message, or Short Message Service (SMS) messaging.</span></span> <span data-ttu-id="63df2-108">SMS 是用于将短信从一个移动设备发送到另一个移动设备的技术。 ) </span><span class="sxs-lookup"><span data-stu-id="63df2-108">SMS is the technology used to send text messages from one mobile device to another.)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="63df2-109">有关配置 Operations Manager 通知的详细信息，请参阅 TechNet Library 中的配置通知 <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A> 。</span><span class="sxs-lookup"><span data-stu-id="63df2-109">For details about configuring Operations Manager notification, see the Configuring Notification in the TechNet Library at <A href="https://go.microsoft.com/fwlink/p/?linkid=268785">https://go.microsoft.com/fwlink/p/?LinkId=268785</A>.</span></span>

    
    </div>

  - <span data-ttu-id="63df2-110">主动监控管理包 (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) 主动测试关键 Lync Server 组件，例如登录到系统、交换即时消息或呼叫位于公用电话交换网 (PSTN) 的电话。</span><span class="sxs-lookup"><span data-stu-id="63df2-110">The Active Monitoring Management Pack (Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp) proactively tests key Lync Server components such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="63df2-111">这些测试通过使用 Lync Server 综合事务 cmdlet 进行。</span><span class="sxs-lookup"><span data-stu-id="63df2-111">These tests are conducted using the Lync Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="63df2-112">例如，您可使用 **Test-CsIM** cmdlet 在一对测试用户之间模拟即时消息 (IM) 对话。</span><span class="sxs-lookup"><span data-stu-id="63df2-112">For example, you can use the **Test-CsIM** cmdlet to simulate an instant messaging (IM) conversation between a pair of test users.</span></span> <span data-ttu-id="63df2-113">如果此命令模拟消息对话失败，则将生成警报。</span><span class="sxs-lookup"><span data-stu-id="63df2-113">If this simulated messaging conversation fails an alert is generated.</span></span>

<span data-ttu-id="63df2-114">您需要导入管理包。</span><span class="sxs-lookup"><span data-stu-id="63df2-114">You need to import the management packs.</span></span> <span data-ttu-id="63df2-115">如果不导入管理包，则不能使用 Operations Manager 来监视 Lync Server 事件或运行 Lync Server 合成事务。</span><span class="sxs-lookup"><span data-stu-id="63df2-115">If you do not import the management packs, you cannot use Operations Manager to monitor Lync Server events or run Lync Server synthetic transactions.</span></span>

<span data-ttu-id="63df2-116">组件和用户管理包仅用于监视 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="63df2-116">The Component and User Management Pack is only used to monitor Lync Server 2013.</span></span> <span data-ttu-id="63df2-117">如果您在共存方案中，同时安装了 Lync Server 2013 和 Lync Server 2010，则应继续为 Lync Server 2010 计算机使用 Lync Server 2010 管理包。</span><span class="sxs-lookup"><span data-stu-id="63df2-117">If you are in a coexistence scenario, where you have both Lync Server 2013 and Lync Server 2010 installed, you should continue to use the Lync Server 2010 management packs for your Lync Server 2010 computers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="63df2-118">Lync Server 2010 的管理包包括 Lync Server 2010 监视管理包和 Lync Server 2010 组聊天监控管理包。</span><span class="sxs-lookup"><span data-stu-id="63df2-118">Management packs for Lync Server 2010 include the Lync Server 2010 Monitoring Management Pack and the Lync Server 2010 Group Chat Monitoring Management Pack.</span></span>



</div>

<span data-ttu-id="63df2-119">可使用下列任一工具导入管理包：</span><span class="sxs-lookup"><span data-stu-id="63df2-119">You can use one of the following tools to import management packs:</span></span>

  - <span data-ttu-id="63df2-120">**System Center Operations Manager**    使用此方法，可以使用 Operations Manager 为 Lync Server 添加监控。</span><span class="sxs-lookup"><span data-stu-id="63df2-120">**System Center Operations Manager**   With this method, you use the Operations Manager to add monitoring for Lync Server.</span></span>

  - <span data-ttu-id="63df2-121">**Operations Manager 命令行**     管理程序您可以使用 Operations Manager 命令行管理程序直接导入，或解决您在使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题。</span><span class="sxs-lookup"><span data-stu-id="63df2-121">**Operations Manager Shell**   You can use the Operations Manager Shell to import directly or to troubleshoot any issues you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

<div>

## <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="63df2-122">使用 System Center Operations Manager 导入管理包</span><span class="sxs-lookup"><span data-stu-id="63df2-122">Importing the Management Packs by Using System Center Operations Manager</span></span>

1.  <span data-ttu-id="63df2-123">下载文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp。</span><span class="sxs-lookup"><span data-stu-id="63df2-123">Download the files Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2013.Monitoring.ComponentAndUser.mp.</span></span>

2.  <span data-ttu-id="63df2-124">在 System Center Operations Manager 中，单击 " **管理**"。</span><span class="sxs-lookup"><span data-stu-id="63df2-124">In System Center Operations Manager, click **Administration**.</span></span>

3.  <span data-ttu-id="63df2-125">在“管理”\*\*\*\* 窗格中，右键单击“管理包”\*\*\*\*，然后单击“导入管理包”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63df2-125">In the **Administration** pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4.  <span data-ttu-id="63df2-126">在“选择管理包”\*\*\*\* 对话框中，单击“添加”\*\*\*\*，然后单击“从磁盘中添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="63df2-126">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5.  <span data-ttu-id="63df2-127">在 " **联机目录连接** " 对话框中，单击 " **取消** " 以阻止 Operations Manager 联机查看是否存在与 Lync Server 管理包相关的依赖项。</span><span class="sxs-lookup"><span data-stu-id="63df2-127">In the **Online Catalog Connection** dialog box, click **Cancel** to prevent Operations Manager from going online to see if any dependencies exist for the Lync Server management packs.</span></span> <span data-ttu-id="63df2-128">如果使用的是 System Center Operations Manager 2012，请单击 " **否**"。</span><span class="sxs-lookup"><span data-stu-id="63df2-128">If you are using System Center Operations Manager 2012, click **No**.</span></span>

6.  <span data-ttu-id="63df2-p107">在“选择要导入的管理包”\*\*\*\* 对话框中，查找并选择“Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp”\*\*\*\* 和“Microsoft.LS.2013.Monitoring.ComponentAndUser.mp”\*\*\*\*，然后单击“打开”\*\*\*\*。若要在对话框中选择多个文件，请单击第一个文件，按住 Ctrl 键，然后单击第二个文件。</span><span class="sxs-lookup"><span data-stu-id="63df2-p107">In the **Select Management Packs to import** dialog box, locate and select the files **Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp** and **Microsoft.LS.2013.Monitoring.ComponentAndUser.mp** and then click **Open**. To select multiple files in the dialog box, click the first file, hold down the Ctrl key and then click the second file.</span></span>

7.  <span data-ttu-id="63df2-p108">在“选择管理包”\*\*\*\* 对话框中，单击“安装”\*\*\*\*。如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。如果出现此情况，请将文件复制到其他文件夹中，然后重新开始导入和安装过程。</span><span class="sxs-lookup"><span data-stu-id="63df2-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder and then restart the import and installation process.</span></span>

8.  <span data-ttu-id="63df2-p109">在“选择管理包”\*\*\*\* 对话框中，单击“关闭”\*\*\*\*。请注意，导入和安装过程可能需要几分钟时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="63df2-p109">In the **Select Management Packs** dialog box, click **Close**. Note that the import and installation process might require several minutes to complete.</span></span>

</div>

<div>

## <a name="importing-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="63df2-136">使用 Operations Manager 命令行管理程序导入管理包</span><span class="sxs-lookup"><span data-stu-id="63df2-136">Importing Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="63df2-137">通常情况下，使用 Operations Manager 导入管理包更为简单。但是，如果发生错误，并且导入失败，则控制台不总是提供足够的错误报告。</span><span class="sxs-lookup"><span data-stu-id="63df2-137">In general it is easier to import the management packs by using the Operations Manager.However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="63df2-138">通过比较，Operations Manager 命令行管理程序提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="63df2-138">By comparison, the Operations Manager Shell, provides detailed information.</span></span> <span data-ttu-id="63df2-139">如果您使用的是 Operations Manager，并且在导入管理包时遇到问题，请使用 Operations Manager 命令行管理程序导入该程序包。</span><span class="sxs-lookup"><span data-stu-id="63df2-139">If you are using Operations Manager and you run into problems importing a management pack, import the pack by using the Operations Manager Shell .</span></span> <span data-ttu-id="63df2-140">Operations Manager 命令行管理程序提供了详细信息，可帮助您确定导入失败的原因。</span><span class="sxs-lookup"><span data-stu-id="63df2-140">The Operations Manager Shell provides more information that might help you determine why the import failed.</span></span>

<span data-ttu-id="63df2-141">如果您使用的是 System Center Operations Manager 2007 R2，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="63df2-141">If you are using System Center Operations Manager 2007 R2, complete the following procedure:</span></span>

1.  <span data-ttu-id="63df2-142">依次单击 " **开始**"、" **所有程序**"、" **System Center Operations Manager 2007 R2**" 和 " **Operations Manager Shell**"。</span><span class="sxs-lookup"><span data-stu-id="63df2-142">Click **Start**, click **All Programs**, click **System Center Operations Manager 2007 R2**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="63df2-143">在 Operations Manager 命令行管理程序中，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="63df2-143">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp

3.  <span data-ttu-id="63df2-144">导入第一个管理包之后，使用至文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：</span><span class="sxs-lookup"><span data-stu-id="63df2-144">After you import the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        MPImport.exe D:\MP\Microsoft.LS.2013.Monitoring.ComponentAndUser.mp

4.  <span data-ttu-id="63df2-145">关闭 Operations Manager 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="63df2-145">Close the Operations Manager Shell.</span></span>

<span data-ttu-id="63df2-146">如果使用的是 System Center Operations Manager 2012，请改为完成此过程：</span><span class="sxs-lookup"><span data-stu-id="63df2-146">If you are using System Center Operations Manager 2012, complete this procedure instead:</span></span>

1.  <span data-ttu-id="63df2-147">依次单击 " **开始**"、" **所有程序**"、" **Microsoft System Center 2012**"、" **Operations manager**" 和 " **operations manager Shell**"。</span><span class="sxs-lookup"><span data-stu-id="63df2-147">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2.  <span data-ttu-id="63df2-148">在 Operations Manager 命令行管理程序中，使用文件 Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp 的副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="63df2-148">In the Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ActiveMonitoring.mp"

3.  <span data-ttu-id="63df2-149">导入第一个管理包之后，使用至文件 Microsoft.LS.2013.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：</span><span class="sxs-lookup"><span data-stu-id="63df2-149">After you have imported the first management pack, repeat the process using the path to your copy of the file Microsoft.LS.2013.Monitoring.ComponentAndUser.mp:</span></span>
    
        Import-SCOMManagementPack -FullName "D:\MP\ Microsoft.LS.2013.Monitoring.ComponentAndUser.mp"

</div>

</div>

<span> </span>

</div>

</div>

</div>

