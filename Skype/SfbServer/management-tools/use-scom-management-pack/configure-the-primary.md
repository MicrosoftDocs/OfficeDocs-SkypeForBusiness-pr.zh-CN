---
title: 配置主管理服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 摘要：为 Skype for Business Server 2015 配置主管理服务器、安装 System Center Operations Manager 和导入管理包。
ms.openlocfilehash: ace25e1b4971c561dc1544290b04f481f36c9676
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111638"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="9d858-103">配置主管理服务器</span><span class="sxs-lookup"><span data-stu-id="9d858-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="9d858-104">**摘要：** 为 Skype for Business Server 2015 配置主管理服务器、安装 System Center Operations Manager 和导入管理包。</span><span class="sxs-lookup"><span data-stu-id="9d858-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2015.</span></span>

<span data-ttu-id="9d858-105">若要充分利用 Skype for Business Server 2015 中包含的新运行状况监视功能，必须先指定一台计算机作为主管理服务器。</span><span class="sxs-lookup"><span data-stu-id="9d858-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2015, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="9d858-106">然后必须在该计算机上安装 System Center Operations Manager 2012 SP1 或 R2 或 System Center Operations Manager 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="9d858-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="9d858-107">此外，您必须先安装受支持的 SQL Server，以用作 Operations Manager 后端数据库。</span><span class="sxs-lookup"><span data-stu-id="9d858-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="9d858-108">安装 System Center Operations Manager 时，将需要安装该产品的所有组件，包括：</span><span class="sxs-lookup"><span data-stu-id="9d858-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="9d858-109">操作数据库</span><span class="sxs-lookup"><span data-stu-id="9d858-109">Operational database</span></span>

- <span data-ttu-id="9d858-110">服务器</span><span class="sxs-lookup"><span data-stu-id="9d858-110">Server</span></span>

- <span data-ttu-id="9d858-111">控制台</span><span class="sxs-lookup"><span data-stu-id="9d858-111">Console</span></span>

- <span data-ttu-id="9d858-112">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="9d858-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="9d858-113">Web 控制台</span><span class="sxs-lookup"><span data-stu-id="9d858-113">Web console</span></span>

- <span data-ttu-id="9d858-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="9d858-114">Reporting</span></span>

- <span data-ttu-id="9d858-115">数据仓库</span><span class="sxs-lookup"><span data-stu-id="9d858-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d858-116">在安装 System Center Operations[Manager 2012 之前，需要安装"Microsoft Report Viewer 2010](https://www.microsoft.com/download/details.aspx?id=6442)可再发行软件包"。</span><span class="sxs-lookup"><span data-stu-id="9d858-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="9d858-117">有关这些产品及其安装的详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="9d858-117">For details about these products and their installation, see the following links:</span></span>

- <span data-ttu-id="9d858-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span><span class="sxs-lookup"><span data-stu-id="9d858-118">[System Center Operations Manager 2012](/previous-versions/system-center/system-center-2012-R2/hh205987(v=sc.12))</span></span>

- [<span data-ttu-id="9d858-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="9d858-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="9d858-120">请记住，每个 Skype for Business Server 部署只能有一个根管理服务器。</span><span class="sxs-lookup"><span data-stu-id="9d858-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2015-management-packs"></a><span data-ttu-id="9d858-121">导入 Skype for Business Server 2015 管理包</span><span class="sxs-lookup"><span data-stu-id="9d858-121">Importing the Skype for Business Server 2015 Management Packs</span></span>

<span data-ttu-id="9d858-122">可以通过安装管理包（指示 System Center Operations Manager 可以监视的项目、应监视这些项目如何以及触发和报告警报方式的软件）来扩展 System Center Operations Manager 的功能。</span><span class="sxs-lookup"><span data-stu-id="9d858-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="9d858-123">Skype for Business Server 2015 包括两个 System Center Operations Manager 管理包，它们提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="9d858-123">Skype for Business Server 2015 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="9d858-124">组件 **和** 用户管理包 (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) 跟踪事件日志中记录的 Skype for Business Server 问题、由性能计数器注册的问题，或记录在呼叫详细信息记录 (CDR) 或用户体验质量 (QoE) 数据库中的问题。</span><span class="sxs-lookup"><span data-stu-id="9d858-124">**The Component and User Management Pack** (Microsoft.LS.2015.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="9d858-125">对于关键问题，可以将 System Center Operations Manager 配置为立即通过电子邮件、即时消息或短信通知管理员。</span><span class="sxs-lookup"><span data-stu-id="9d858-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="9d858-126"> (短信服务是一种用于将短信从一个移动设备发送到另一个移动设备的技术。) </span><span class="sxs-lookup"><span data-stu-id="9d858-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="9d858-127">有关配置 Operations Manager 通知的详细信息，请参阅 [配置通知](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10))。</span><span class="sxs-lookup"><span data-stu-id="9d858-127">For details about configuring Operations Manager notification, see [Configuring Notification](/previous-versions/system-center/operations-manager-2007-r2/dd440890(v=technet.10)).</span></span>

- <span data-ttu-id="9d858-128">**Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) 主动测试关键的 Skype for Business Server 组件，例如登录系统、交换即时消息或呼叫位于公用电话交换网 (PSTN) 上的电话。</span><span class="sxs-lookup"><span data-stu-id="9d858-128">**The Active Monitoring Management Pack** (Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="9d858-129">这些测试使用 Skype for Business Server 综合事务 cmdlet 执行。</span><span class="sxs-lookup"><span data-stu-id="9d858-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="9d858-130">例如，**Test-CsIM** cmdlet 可用来模拟一对测试用户之间的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="9d858-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="9d858-131">如果此模拟对话失败，将生成警报。</span><span class="sxs-lookup"><span data-stu-id="9d858-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="9d858-132">导入管理包是一个关键步骤。</span><span class="sxs-lookup"><span data-stu-id="9d858-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="9d858-133">如果未导入管理包，你将不能使用 Operations Manager 监视 Skype for Business Server 事件或运行 Skype for Business Server 综合事务。</span><span class="sxs-lookup"><span data-stu-id="9d858-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="9d858-134">组件和用户管理包仅用于监视 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="9d858-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2015.</span></span> <span data-ttu-id="9d858-135">如果同时安装了 Skype for Business Server 2015 和 Lync Server 2013 的共存方案，您应该继续使用 Lync Server 2013 计算机的 Lync Server 2013 管理包。</span><span class="sxs-lookup"><span data-stu-id="9d858-135">If you are in a coexistence scenario where both Skype for Business Server 2015 and Lync Server 2013 are installed, you should continue to use the Lync Server 2013 management packs for your Lync Server 2013 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="9d858-136">Skype for Business Server 2015 的管理包包括 Skype for Business Server 2015 组件和用户管理包以及 Skype for Business Server 2015 Active Monitoring Management Pack。</span><span class="sxs-lookup"><span data-stu-id="9d858-136">Management packs for Skype for Business Server 2015 include the Skype for Business Server 2015 Component and User Management Pack and the Skype for Business Server 2015 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="9d858-137">可使用下列任一工具导入管理包：</span><span class="sxs-lookup"><span data-stu-id="9d858-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="9d858-138">**System Center Operations Manager** 使用此方法，可使用 Operations Manager 为 Skype for Business Server 添加监视。</span><span class="sxs-lookup"><span data-stu-id="9d858-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="9d858-139">**Operations Manager Shell** 可以使用 Operations Manager Shell 直接导入，或使用 System Center Operations Manager 控制台对导入管理包时遇到的任何问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="9d858-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="9d858-140">使用 System Center Operations Manager 导入管理包</span><span class="sxs-lookup"><span data-stu-id="9d858-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="9d858-141">从 microsoft SkypeForBusiness2015ManagementPacks.msi下载下载文件，然后安装 msi。</span><span class="sxs-lookup"><span data-stu-id="9d858-141">Download the SkypeForBusiness2015ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="9d858-142">在 System Center Operations Manager 中，单击"管理 **"。**</span><span class="sxs-lookup"><span data-stu-id="9d858-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="9d858-143">在"管理"窗格中，右键单击"**管理包"，** 然后单击"**导入管理包"。**</span><span class="sxs-lookup"><span data-stu-id="9d858-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="9d858-144">在“选择管理包”对话框中，单击“添加”，然后单击“从磁盘中添加”。</span><span class="sxs-lookup"><span data-stu-id="9d858-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="9d858-145">在"**联机目录连接"** 对话框中，单击"否 **"。**</span><span class="sxs-lookup"><span data-stu-id="9d858-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="9d858-146">在 **"选择要导入的管理** 包"对话框中，找到并选择 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp Microsoft.LS.2015.Monitoring.ComponentAndUser.mp 文件，然后单击"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="9d858-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2015.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="9d858-147">若要在对话框中选择多个文件，请单击第一个文件，然后按住 Ctrl 键，然后单击后续文件。</span><span class="sxs-lookup"><span data-stu-id="9d858-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="9d858-148">在“选择管理包”对话框中，单击“安装”。</span><span class="sxs-lookup"><span data-stu-id="9d858-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="9d858-149">如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="9d858-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="9d858-150">如果发生这种情况，将文件复制到其他文件夹，然后重新启动导入和安装过程。</span><span class="sxs-lookup"><span data-stu-id="9d858-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="9d858-151">在“选择管理包”对话框中，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="9d858-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="9d858-152">导入和安装过程可能需要几分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="9d858-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="9d858-153">使用 Operations Manager Shell 导入管理包</span><span class="sxs-lookup"><span data-stu-id="9d858-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="9d858-154">通常，使用 Operations Manager 控制台导入管理包会更容易。</span><span class="sxs-lookup"><span data-stu-id="9d858-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="9d858-155">但是，如果发生错误并且导入失败，则控制台不会始终提供足够的错误报告。</span><span class="sxs-lookup"><span data-stu-id="9d858-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="9d858-156">相比之下，Operations Manager Shell 提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="9d858-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="9d858-157">如果使用的是 Operations Manager，并且导入管理包时遇到问题，则使用 Operations Manager Shell 导入该包。</span><span class="sxs-lookup"><span data-stu-id="9d858-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="9d858-158">Operations Manager Shell 提供的信息可以帮助您确定导入失败的原因。</span><span class="sxs-lookup"><span data-stu-id="9d858-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="9d858-159">单击 **"开始**"，单击"**所有** 程序"，Microsoft System Center 2012，单击 **"Operations Manager"，** 然后单击 **"Operations Manager Shell"。** </span><span class="sxs-lookup"><span data-stu-id="9d858-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="9d858-160">在 Operations Manager 命令行管理程序 中，在命令提示符下键入以下命令，使用文件副本的实际路径 Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="9d858-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="9d858-161">导入第一个管理包后，使用文件副本的路径重复此过程 Microsoft.LS.2015.Monitoring.ComponentAndUser.mp：</span><span class="sxs-lookup"><span data-stu-id="9d858-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2015.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2015.Monitoring.ComponentAndUser.mp"
   ```