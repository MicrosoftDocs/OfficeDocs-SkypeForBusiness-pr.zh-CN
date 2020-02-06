---
title: 配置主管理服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7e21cce-1dd2-489a-a2eb-f632799f7523
description: 摘要：配置你的主管理服务器、安装 System Center Operations Manager 以及导入 Skype for business Server 2015 的管理包。
ms.openlocfilehash: 0492a86062577d5118860faae8beca50f9f7bed2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816121"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="afd82-103">配置主管理服务器</span><span class="sxs-lookup"><span data-stu-id="afd82-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="afd82-104">**摘要：** 配置你的主管理服务器、安装 System Center Operations Manager 以及导入 Skype for business Server 2015 的管理包。</span><span class="sxs-lookup"><span data-stu-id="afd82-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="afd82-105">若要充分利用 Skype for Business Server 2015 中包含的新运行状况监视功能，必须首先指定一个计算机作为你的主管理服务器。</span><span class="sxs-lookup"><span data-stu-id="afd82-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="afd82-106">然后，必须在该计算机上安装 System Center Operations Manager 2012 SP1 或 System Center Operations Manager 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="afd82-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="afd82-107">此外，必须首先安装支持的 SQL Server 版本，才能充当 Operations Manager 后端数据库。</span><span class="sxs-lookup"><span data-stu-id="afd82-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="afd82-108">安装 System Center Operations Manager 时，你将需要安装该产品的所有组件，包括：</span><span class="sxs-lookup"><span data-stu-id="afd82-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="afd82-109">操作数据库</span><span class="sxs-lookup"><span data-stu-id="afd82-109">Operational database</span></span>

- <span data-ttu-id="afd82-110">服务器</span><span class="sxs-lookup"><span data-stu-id="afd82-110">Server</span></span>

- <span data-ttu-id="afd82-111">控制台</span><span class="sxs-lookup"><span data-stu-id="afd82-111">Console</span></span>

- <span data-ttu-id="afd82-112">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="afd82-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="afd82-113">Web 控制台</span><span class="sxs-lookup"><span data-stu-id="afd82-113">Web console</span></span>

- <span data-ttu-id="afd82-114">报告</span><span class="sxs-lookup"><span data-stu-id="afd82-114">Reporting</span></span>

- <span data-ttu-id="afd82-115">数据仓库</span><span class="sxs-lookup"><span data-stu-id="afd82-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afd82-116">必须先安装 "[Microsoft Report Viewer 2010 可再发行组件包](https://www.microsoft.com/en-us/download/details.aspx?id=6442)"，然后才能安装 System Center Operations Manager 2012。</span><span class="sxs-lookup"><span data-stu-id="afd82-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/en-us/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="afd82-117">有关这些产品及其安装方法的详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="afd82-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="afd82-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="afd82-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="afd82-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="afd82-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/en-us/library/bb735860.aspx)

<span data-ttu-id="afd82-120">请记住，每个 Skype for business 服务器部署只能有一个根管理服务器。</span><span class="sxs-lookup"><span data-stu-id="afd82-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="afd82-121">导入 Skype for Business Server 2015 管理包</span><span class="sxs-lookup"><span data-stu-id="afd82-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="afd82-122">你可以通过安装管理包来扩展 System Center Operations Manager 的功能-该软件规定 System Center Operations Manager 可以监视哪些项目、应如何监视这些项目以及应如何触发警报以及据.</span><span class="sxs-lookup"><span data-stu-id="afd82-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="afd82-123">Skype for Business 服务器2015包括两个 System Center Operations Manager 管理包，它们提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="afd82-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="afd82-124">**组件和用户管理包**（Microsoft.LS.2015.Monitoring.ComponentAndUser.mp）跟踪事件日志中记录的 Skype For business 服务器问题（由性能计数器注册），或记录在通话详细记录（CDRs）或体验质量（QoE）数据库中。</span><span class="sxs-lookup"><span data-stu-id="afd82-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="afd82-125">对于严重问题，System Center Operations Manager 可以配置为通过电子邮件、即时消息或 SMS 消息立即通知管理员。</span><span class="sxs-lookup"><span data-stu-id="afd82-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="afd82-126">（SMS，即短消息服务，是一种用来将文本消息从一个移动设备发送到另一个移动设备的技术）。</span><span class="sxs-lookup"><span data-stu-id="afd82-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="afd82-127">有关配置 Operations Manager 通知的详细信息，请参阅[配置通知](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="afd82-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="afd82-128">**活动监视管理包**（Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp）主动测试关键的 Skype For business 服务器组件，例如登录到系统、交换即时消息或拨打公共交换电话网络（PSTN）上的电话。</span><span class="sxs-lookup"><span data-stu-id="afd82-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="afd82-129">这些测试是使用 Skype for Business Server 综合事务 cmdlet 来执行的。</span><span class="sxs-lookup"><span data-stu-id="afd82-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="afd82-130">例如，**Test-CsIM** cmdlet 用来模拟一对测试用户之间的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="afd82-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="afd82-131">如果这种模拟的对话失败，就会生成警报。</span><span class="sxs-lookup"><span data-stu-id="afd82-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="afd82-p105">导入管理包是关键的一步。如果未导入管理包，就不能使用 Operations Manager 来监视 Skype for Business Server 事件，也不能运行 Skype for Business Server 综合事务。</span><span class="sxs-lookup"><span data-stu-id="afd82-p105">Importing the management packs is a crucial step. If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="afd82-p106">组件和用户管理包仅用于监视 Skype for Business Server 2015。如果是在共存情况下，也就是同时安装了 Skype for Business Server 2015 和 Lync Server 2013，那么 Lync Server 2013 计算机应继续使用 Lync Server 2013 管理包。</span><span class="sxs-lookup"><span data-stu-id="afd82-p106">The Component and User Management Pack is used to monitor only Skype for Business Server 2015. If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="afd82-136">Skype for Business Server 2015 的管理包中包含 Business Server 2015 组件和用户管理包，以及 Skype for Business Server 2015 主动监控管理包。</span><span class="sxs-lookup"><span data-stu-id="afd82-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="afd82-137">可使用下列任一工具导入管理包：</span><span class="sxs-lookup"><span data-stu-id="afd82-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="afd82-138">**System Center Operations Manager**使用此方法，你可以使用 Operations Manager 添加针对 Skype for Business 服务器的监视。</span><span class="sxs-lookup"><span data-stu-id="afd82-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="afd82-139">**Operations Manager Shell**你可以使用 Operations Manager 外壳直接导入，或解决在使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题。</span><span class="sxs-lookup"><span data-stu-id="afd82-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="afd82-140">使用 System Center Operations Manager 导入管理包</span><span class="sxs-lookup"><span data-stu-id="afd82-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="afd82-141">从 Microsoft Web 下载网站下载 SkypeForBusiness2015ManagementPacks.msi，然后安装该 msi。</span><span class="sxs-lookup"><span data-stu-id="afd82-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="afd82-142">在 System Center Operations Manager 中，单击 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="afd82-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="afd82-143">在 "管理" 窗格中，右键单击 "**管理包**"，然后单击 "**导入管理包**"。</span><span class="sxs-lookup"><span data-stu-id="afd82-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="afd82-144">在“选择管理包”\*\*\*\* 对话框中，单击“添加”\*\*\*\*，然后单击“从磁盘中添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afd82-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="afd82-145">在“联机目录连接”\*\*\*\* 对话框中，单击“否”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afd82-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="afd82-p107">在“选择要导入的管理包”\*\*\*\* 对话框中，查找并选择文件“Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp”和“Microsoft.LS.2015.Monitoring.ComponentAndUser.mp”，然后单击“打开”\*\*\*\*。若要在对话框中选择多个文件，请单击第一个文件，按住 Ctrl 键，然后单击后续文件。</span><span class="sxs-lookup"><span data-stu-id="afd82-p107">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**. To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="afd82-p108">在“选择管理包”\*\*\*\* 对话框中，单击“安装”\*\*\*\*。如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。如果出现此情况，请将文件复制到其他文件夹中，然后重新开始导入和安装过程。</span><span class="sxs-lookup"><span data-stu-id="afd82-p108">In the **Select Management Packs** dialog box, click **Install**. If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control. If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="afd82-p109">在“选择管理包”\*\*\*\* 对话框中，单击“关闭”\*\*\*\*。导入和安装过程可能需要几分钟时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="afd82-p109">In the **Select Management Packs** dialog box, click **Close**. The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="afd82-153">使用 Operations Manager Shell 导入管理包</span><span class="sxs-lookup"><span data-stu-id="afd82-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="afd82-p110">一般来说，使用 Operations Manager 控制台导入管理包要更容易。但是，如果发生错误并且导入失败，则控制台不会总是提供足够的错误报告。相比之下，Operations Manager Shell 提供了详细信息。如果您使用的是 Operations Manager 并且导入管理包时遇到问题，请使用 Operations Manager Shell 导入包。Operations Manager Shell 提供了可帮助您确定导入失败原因的信息。</span><span class="sxs-lookup"><span data-stu-id="afd82-p110">In general, it is easier to import the management packs by using the Operations Manager console. However, if an error occurs and the import fails, the console does not always provide adequate error reports. By comparison, the Operations Manager Shell provides detailed information. If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell. The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="afd82-159">依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft System Center 2012”\*\*\*\*、“Operations Manager”\*\*\*\* 和“Operations Manager Shell”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afd82-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="afd82-160">在 Operations Manager Shell 中，在命令提示符处键入以下命令，使用文件 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp 的副本的实际路径，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="afd82-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="afd82-161">导入第一个管理包之后，使用至文件 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：</span><span class="sxs-lookup"><span data-stu-id="afd82-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```
