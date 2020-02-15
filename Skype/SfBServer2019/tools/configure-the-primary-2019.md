---
title: 配置主管理服务器
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 摘要：配置您的主管理服务器、安装 System Center Operations Manager 和导入 Skype for business Server 2019 的管理包。
ms.openlocfilehash: ccc522da216b98e6f18ea381a74aff19fc5cc24d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006047"
---
# <a name="configure-the-primary-management-server"></a><span data-ttu-id="8ccfc-103">配置主管理服务器</span><span class="sxs-lookup"><span data-stu-id="8ccfc-103">Configure the Primary Management Server</span></span>

<span data-ttu-id="8ccfc-104">**摘要：** 配置您的主管理服务器，安装 System Center Operations Manager，并导入 Skype for business Server 2019 的管理包。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-104">**Summary:** Configure your primary management server, install System Center Operations Manager, and import management packs for Skype for Business Server 2019.</span></span>

<span data-ttu-id="8ccfc-105">若要充分利用 Skype for Business Server 2019 中包含的新运行状况监视功能，必须先指定一台计算机作为主管理服务器。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-105">To take full advantage of the new health monitoring capabilities included in Skype for Business Server 2019, you must first designate a computer to act as your primary management server.</span></span> <span data-ttu-id="8ccfc-106">然后，必须在该计算机上安装 System Center Operations Manager 2012 SP1 或 R2 或 System Center Operations Manager 2007 R2。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-106">You must then install System Center Operations Manager 2012 SP1 or R2 or System Center Operations Manager 2007 R2 on that computer.</span></span> <span data-ttu-id="8ccfc-107">此外，必须先安装受支持的 SQL Server 版本，才能充当 Operations Manager 后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-107">In addition, you must first install a supported version of SQL Server to function as your Operations Manager back-end database.</span></span>

<span data-ttu-id="8ccfc-108">安装 System Center Operations Manager 时，将需要安装该产品的所有组件，包括：</span><span class="sxs-lookup"><span data-stu-id="8ccfc-108">When you install System Center Operations Manager, you will need to install all the components of that product, including:</span></span>

- <span data-ttu-id="8ccfc-109">操作数据库</span><span class="sxs-lookup"><span data-stu-id="8ccfc-109">Operational database</span></span>

- <span data-ttu-id="8ccfc-110">服务器</span><span class="sxs-lookup"><span data-stu-id="8ccfc-110">Server</span></span>

- <span data-ttu-id="8ccfc-111">控制台</span><span class="sxs-lookup"><span data-stu-id="8ccfc-111">Console</span></span>

- <span data-ttu-id="8ccfc-112">Windows PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="8ccfc-112">Windows PowerShell cmdlets</span></span>

- <span data-ttu-id="8ccfc-113">Web 控制台</span><span class="sxs-lookup"><span data-stu-id="8ccfc-113">Web console</span></span>

- <span data-ttu-id="8ccfc-114">Reporting</span><span class="sxs-lookup"><span data-stu-id="8ccfc-114">Reporting</span></span>

- <span data-ttu-id="8ccfc-115">数据仓库</span><span class="sxs-lookup"><span data-stu-id="8ccfc-115">Data warehouse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8ccfc-116">安装 System Center Operations Manager 2012 前，需要安装 "[Microsoft Report Viewer 2010 可再发行组件包](https://www.microsoft.com/download/details.aspx?id=6442)"。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-116">The "[Microsoft Report Viewer 2010 Redistributable Package](https://www.microsoft.com/download/details.aspx?id=6442)" needs to be installed before you install System Center Operations Manager 2012.</span></span>

<span data-ttu-id="8ccfc-117">有关这些产品及其安装的详细信息，请参阅以下链接：</span><span class="sxs-lookup"><span data-stu-id="8ccfc-117">For details about these products and their installation, see the following links:</span></span>

- [<span data-ttu-id="8ccfc-118">System Center Operations Manager 2012</span><span class="sxs-lookup"><span data-stu-id="8ccfc-118">System Center Operations Manager 2012</span></span>](https://go.microsoft.com/fwlink/p/?linkid=257527)

- [<span data-ttu-id="8ccfc-119">System Center Operations Manager 2007</span><span class="sxs-lookup"><span data-stu-id="8ccfc-119">System Center Operations Manager 2007</span></span>](https://technet.microsoft.com/library/bb735860.aspx)

<span data-ttu-id="8ccfc-120">请注意，每个 Skype for Business Server 部署只能有一个根管理服务器。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-120">Keep in mind that you can have only one Root Management Server per Skype for Business Server deployment.</span></span>

## <a name="importing-the-skype-for-business-server-2019-management-packs"></a><span data-ttu-id="8ccfc-121">导入 Skype for Business Server 2019 管理包</span><span class="sxs-lookup"><span data-stu-id="8ccfc-121">Importing the Skype for Business Server 2019 Management Packs</span></span>

<span data-ttu-id="8ccfc-122">您可以通过安装管理包来扩展 System Center Operations Manager 的功能—该软件规定 System Center Operations Manager 可以监视的项目、这些项目的监视方式以及应如何触发警报以及如何触发警报以及报表.</span><span class="sxs-lookup"><span data-stu-id="8ccfc-122">You can extend the capabilities of System Center Operations Manager by installing management packs—software that dictates which items System Center Operations Manager can monitor, how those items should be monitored, and how alerts should be triggered and reported.</span></span> <span data-ttu-id="8ccfc-123">Skype for Business Server 2019 包括两个 System Center Operations Manager 管理包，它们提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="8ccfc-123">Skype for Business Server 2019 includes two System Center Operations Manager management packs that provide the following capabilities:</span></span>

- <span data-ttu-id="8ccfc-124">**组件和用户管理包**（Microsoft.LS.2019.Monitoring.ComponentAndUser.mp）跟踪在事件日志中记录的、由性能计数器注册的 Skype For business Server 问题，或记录在呼叫详细信息记录（cdr）或体验质量（QoE）数据库中的问题。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-124">**The Component and User Management Pack** (Microsoft.LS.2019.Monitoring.ComponentAndUser.mp) tracks Skype for Business Server issues recorded in event logs, registered by performance counters, or logged in the call detail records (CDRs) or the Quality of Experience (QoE) databases.</span></span> <span data-ttu-id="8ccfc-125">对于关键问题，可以将 System Center Operations Manager 配置为立即通过电子邮件、即时消息或 SMS 消息通知管理员。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-125">For critical issues, System Center Operations Manager can be configured to immediately notify administrators through email, instant message, or SMS messaging.</span></span> <span data-ttu-id="8ccfc-126">（SMS 或短信服务）是用于将短信从一个移动设备发送到另一个移动设备的技术。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-126">(SMS, or Short Message Service, is the technology used to send text messages from one mobile device to another.)</span></span>

    > [!NOTE]
    >  <span data-ttu-id="8ccfc-127">有关配置 Operations Manager 通知的详细信息，请参阅[配置通知](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409)。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-127">For details about configuring Operations Manager notification, see [Configuring Notification](https://go.microsoft.com/fwlink/p/?LinkID=268785&amp;amp;clcid=0x409).</span></span>

- <span data-ttu-id="8ccfc-128">**主动监控管理包**（Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp）主动测试密钥 Skype For business Server 组件，例如登录到系统、交换即时消息或呼叫位于公用电话交换网（PSTN）的电话。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-128">**The Active Monitoring Management Pack** (Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp) proactively tests key Skype for Business Server components, such as signing into to the system, exchanging instant messages, or making calls to a phone located on the public switched telephone network (PSTN).</span></span> <span data-ttu-id="8ccfc-129">这些测试通过使用 Skype for Business Server 综合事务 cmdlet 进行。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-129">These tests are conducted by using the Skype for Business Server synthetic transaction cmdlets.</span></span> <span data-ttu-id="8ccfc-130">例如，**Test-CsIM** cmdlet 可用来模拟一对测试用户之间的即时消息对话。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-130">For example, the **Test-CsIM** cmdlet is used to simulate an instant messaging conversation between a pair of test users.</span></span> <span data-ttu-id="8ccfc-131">如果此模拟对话失败，则会生成警报。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-131">If this simulated conversation fails, an alert is generated.</span></span>

<span data-ttu-id="8ccfc-132">导入管理包是一个至关重要的步骤。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-132">Importing the management packs is a crucial step.</span></span> <span data-ttu-id="8ccfc-133">如果未导入管理包，你将无法使用 Operations Manager 来监视 Skype for business Server 事件或运行 Skype for Business Server 合成事务。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-133">If the management packs are not imported, you will not be able to use Operations Manager to monitor Skype for Business Server events or run Skype for Business Server synthetic transactions.</span></span>

<span data-ttu-id="8ccfc-134">组件和用户管理包用于仅监视 Skype for Business Server 2019。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-134">The Component and User Management Pack is used to monitor only Skype for Business Server 2019.</span></span> <span data-ttu-id="8ccfc-135">如果您处于同时安装 Skype for business Server 2019 和 Skype for business Server 2015 的共存方案中，应继续为 Skype for business Server 2015 计算机使用 Skype for Business Server 2015 管理包。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-135">If you are in a coexistence scenario where both Skype for Business Server 2019 and Skype for Business Server 2015 are installed, you should continue to use the Skype for Business Server 2015 management packs for your Skype for Business Server 2015 computers.</span></span>

> [!NOTE]
> <span data-ttu-id="8ccfc-136">适用于 Skype for business Server 2019 的管理包包括 Skype for Business Server 2019 组件和用户管理包，以及 Skype for Business Server 2019 主动监控管理包。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-136">Management packs for Skype for Business Server 2019 include the Skype for Business Server 2019 Component and User Management Pack and the Skype for Business Server 2019 Active Monitoring Management Pack.</span></span>

<span data-ttu-id="8ccfc-137">可使用下列任一工具导入管理包：</span><span class="sxs-lookup"><span data-stu-id="8ccfc-137">You can use one of the following tools to import management packs:</span></span>

- <span data-ttu-id="8ccfc-138">**System Center Operations Manager**使用此方法，可以使用 Operations Manager 为 Skype for business Server 添加监控。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-138">**System Center Operations Manager** With this method, you use the Operations Manager to add monitoring for Skype for Business Server.</span></span>

- <span data-ttu-id="8ccfc-139">**Operations Manager 命令行管理**程序您可以使用 Operations Manager 命令行管理程序直接导入，或解决在使用 System Center Operations Manager 控制台导入管理包时遇到的任何问题。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-139">**Operations Manager Shell** You can use the Operations Manager Shell to import directly, or to troubleshoot any issues that you encounter when you import management packs by using the System Center Operations Manager console.</span></span>

### <a name="importing-the-management-packs-by-using-system-center-operations-manager"></a><span data-ttu-id="8ccfc-140">使用 System Center Operations Manager 导入管理包</span><span class="sxs-lookup"><span data-stu-id="8ccfc-140">Importing the Management Packs by Using System Center Operations Manager</span></span>

1. <span data-ttu-id="8ccfc-141">从 Microsoft Web 下载中下载 SkypeForBusiness2019ManagementPacks，并安装 msi。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-141">Download the SkypeForBusiness2019ManagementPacks.msi from the Microsoft Web downloads, and install the msi.</span></span>

2. <span data-ttu-id="8ccfc-142">在 System Center Operations Manager 中，单击 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-142">In System Center Operations Manager, click **Administration**.</span></span>

3. <span data-ttu-id="8ccfc-143">在 "管理" 窗格中，右键单击 "**管理包**"，然后单击 "**导入管理包**"。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-143">In the Administration pane, right-click **Management Packs**, and then click **Import Management Packs**.</span></span>

4. <span data-ttu-id="8ccfc-144">在“选择管理包”\*\*\*\* 对话框中，单击“添加”\*\*\*\*，然后单击“从磁盘中添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-144">In the **Select Management Packs** dialog box, click **Add**, and then click **Add from disk**.</span></span>

5. <span data-ttu-id="8ccfc-145">在 "**联机目录连接**" 对话框中，单击 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-145">In the **Online Catalog Connection** dialog box, click **No**.</span></span>

6. <span data-ttu-id="8ccfc-146">在 "**选择要导入的管理包**" 对话框中，找到并选择文件 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 和 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp，然后单击 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-146">In the **Select Management Packs to import** dialog box, locate and select the files Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp and Microsoft.LS.2019.Monitoring.ComponentAndUser.mp, and then click **Open**.</span></span> <span data-ttu-id="8ccfc-147">若要在对话框中选择多个文件，请单击第一个文件，然后在按住 Ctrl 键的同时单击后续文件。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-147">To select multiple files in the dialog box, click the first file, and then hold down the Ctrl key and click the subsequent files.</span></span>

7. <span data-ttu-id="8ccfc-148">在“选择管理包”\*\*\*\* 对话框中，单击“安装”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-148">In the **Select Management Packs** dialog box, click **Install**.</span></span> <span data-ttu-id="8ccfc-149">如果您收到错误消息并且安装失败，则通常意味着管理包文件位于受 Windows 用户帐户控制保护的文件夹中。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-149">If you get an error message and installation fails, that typically means that the management pack files are in a folder protected by the Windows User Account Control.</span></span> <span data-ttu-id="8ccfc-150">如果出现这种情况，请将文件复制到其他文件夹，然后重新启动导入和安装过程。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-150">If this occurs, copy the files to a different folder, and then restart the import and installation process.</span></span>

8. <span data-ttu-id="8ccfc-151">在“选择管理包”\*\*\*\* 对话框中，单击“关闭”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-151">In the **Select Management Packs** dialog box, click **Close**.</span></span> <span data-ttu-id="8ccfc-152">导入和安装过程可能需要几分钟的时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-152">The import and installation process might require several minutes to complete.</span></span>

## <a name="importing-the-management-packs-by-using-the-operations-manager-shell"></a><span data-ttu-id="8ccfc-153">使用 Operations Manager 命令行管理程序导入管理包</span><span class="sxs-lookup"><span data-stu-id="8ccfc-153">Importing the Management Packs by Using the Operations Manager Shell</span></span>

<span data-ttu-id="8ccfc-154">通常情况下，使用 Operations Manager 控制台导入管理包更为简单。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-154">In general, it is easier to import the management packs by using the Operations Manager console.</span></span> <span data-ttu-id="8ccfc-155">但是，如果发生错误，并且导入失败，则控制台不总是提供足够的错误报告。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-155">However, if an error occurs and the import fails, the console does not always provide adequate error reports.</span></span> <span data-ttu-id="8ccfc-156">通过比较，Operations Manager 命令行管理程序提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-156">By comparison, the Operations Manager Shell provides detailed information.</span></span> <span data-ttu-id="8ccfc-157">如果您使用的是 Operations Manager，并且在导入管理包时遇到问题，请使用 Operations Manager 命令行管理程序导入该程序包。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-157">If you are using Operations Manager and you encounter issues when importing a management pack, import the pack by using the Operations Manager Shell.</span></span> <span data-ttu-id="8ccfc-158">Operations Manager 命令行管理程序提供的信息可帮助您确定导入失败的原因。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-158">The information provided by Operations Manager Shell can help you determine why the import failed.</span></span>

1. <span data-ttu-id="8ccfc-159">依次单击 "**开始**"、"**所有程序**"、" **Microsoft System Center 2012**"、" **Operations manager**" 和 " **operations manager Shell**"。</span><span class="sxs-lookup"><span data-stu-id="8ccfc-159">Click **Start**, click **All Programs**, click **Microsoft System Center 2012**, click **Operations Manager**, and then click **Operations Manager Shell**.</span></span>

2. <span data-ttu-id="8ccfc-160">在 Operations Manager 命令行管理程序中，使用文件 Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp 的副本的实际路径在命令提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="8ccfc-160">In Operations Manager Shell, type the following command at the command prompt, using the actual path to your copy of the file Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp, and then press ENTER:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ActiveMonitoring.mp"
   ```

3. <span data-ttu-id="8ccfc-161">导入第一个管理包后，请使用文件 Microsoft.LS.2019.Monitoring.ComponentAndUser.mp 的副本的路径重复此过程：</span><span class="sxs-lookup"><span data-stu-id="8ccfc-161">After you have imported the first management pack, repeat the process, using the path to your copy of the file Microsoft.LS.2019.Monitoring.ComponentAndUser.mp:</span></span>

   ```PowerShell
   Import-SCOMManagementPack -FullName "D:\MP\Microsoft.LS.2019.Monitoring.ComponentAndUser.mp"
   ```
