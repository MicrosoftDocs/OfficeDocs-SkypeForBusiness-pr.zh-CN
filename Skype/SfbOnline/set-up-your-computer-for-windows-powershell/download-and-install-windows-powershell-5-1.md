---
title: 下载并安装 Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: 下载和安装，然后使用 Windows PowerShell 5.1 创建连接到 Skype 业务 online 的远程 PowerShell 会话。
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926693"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="97e0b-103">下载并安装 Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="97e0b-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="97e0b-104">如果您使用的 Windows 10 周年日 Update 或 Windows Server 2016，您应该已经 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="97e0b-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="97e0b-105">这是因为此应用程序方面与这些操作系统预安装。</span><span class="sxs-lookup"><span data-stu-id="97e0b-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="97e0b-106">若要确定使用哪个版本的 Microsoft PowerShelll，执行下列操作 Windows 7 或 Windows Server 2008 R2 或 Windows Server 2012 计算机上：</span><span class="sxs-lookup"><span data-stu-id="97e0b-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="97e0b-107">单击**开始**，单击**所有程序**、 都**附件**、 都**Windows PowerShell**，，然后都单击**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="97e0b-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="97e0b-108">在 PowerShell 控制台中，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="97e0b-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="97e0b-109">然后应控制台窗口中显示类似于以下的信息：</span><span class="sxs-lookup"><span data-stu-id="97e0b-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="97e0b-110">如果返回的版本号，5.1 您正在运行 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="97e0b-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="97e0b-111">如果返回的版本号不 5.1，您将需要安装 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="97e0b-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="97e0b-112">您可以从[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=54616)下载 Windows Management Framework 5.1，其中包括 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="97e0b-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="97e0b-113">验证了安装了 Windows PowerShell 5.1 后，您必须确保 PowerShell 确认已配置的运行远程脚本。</span><span class="sxs-lookup"><span data-stu-id="97e0b-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="97e0b-114">为此，请以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97e0b-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="97e0b-115">在 Windows 7、 Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="97e0b-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="97e0b-116">单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**、 **Windows PowerShell**中，右键单击，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="97e0b-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="97e0b-117">如果出现**用户帐户控制**对话框，请单击**是**以确认您想要管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97e0b-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="97e0b-118">如果您运行的 Windows 8，而是完成此过程：</span><span class="sxs-lookup"><span data-stu-id="97e0b-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="97e0b-119">访问超级按钮栏，单击**搜索**，然后右键单击**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="97e0b-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="97e0b-120">您可以快速访问的超级按钮栏 （触摸屏或非触摸屏） 的任何 Windows 8 计算机上，通过按下 Windows 键和 c。</span><span class="sxs-lookup"><span data-stu-id="97e0b-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="97e0b-121">在屏幕底部工具栏中，单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="97e0b-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="97e0b-122">如果出现**用户帐户控制**对话框，请单击**是**以确认您想要管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97e0b-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="97e0b-123">运行 PowerShell 后，您必须更改执行策略，以允许脚本远程运行。</span><span class="sxs-lookup"><span data-stu-id="97e0b-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="97e0b-124">在 PowerShell 控制台中，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="97e0b-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="97e0b-125">运行上述命令时，您可能会收到以下错误消息： > *Set-executionpolicy： 向注册表项的访问 HKEY_LOCAL_MACHINE\\软件\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell 被拒绝。*</span><span class="sxs-lookup"><span data-stu-id="97e0b-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="97e0b-126">如果您不管理员凭据运行 PowerShell，通常会出现此错误消息。</span><span class="sxs-lookup"><span data-stu-id="97e0b-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="97e0b-127">关闭会话的 PowerShell 中，并以管理员身份启动新的会话。</span><span class="sxs-lookup"><span data-stu-id="97e0b-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="97e0b-128">若要验证已正确配置执行策略，在 PowerShell 提示符处键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="97e0b-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="97e0b-129">如果您获得以下值，然后所有已正确配置：</span><span class="sxs-lookup"><span data-stu-id="97e0b-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="97e0b-130">如果您当前未运行 Windows PowerShell 5.1，您还需要下载并安装 Windows Management Framework 5.1 从 Microsoft 下载中心。</span><span class="sxs-lookup"><span data-stu-id="97e0b-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="97e0b-131">这是一个安装包，包括 Windows PowerShell 5.1 和 Windows 远程管理 (WinRM) 3.0。</span><span class="sxs-lookup"><span data-stu-id="97e0b-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="97e0b-132">如果您，例如，在运行 Windows 7 SP1 和尚未更新到 Windows PowerShell 5.1，则可能需要此安装软件包。</span><span class="sxs-lookup"><span data-stu-id="97e0b-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="97e0b-133">如果您运行的 Windows Server 2016 或 Windows 10 周年日更新，应该有无需安装 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="97e0b-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="97e0b-134">Windows PowerShell 5.1 这些操作系统的亮起预安装。</span><span class="sxs-lookup"><span data-stu-id="97e0b-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="97e0b-135">安装 Windows Management Framework 5.1： 之前</span><span class="sxs-lookup"><span data-stu-id="97e0b-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="97e0b-136">请确保您已下载安装程序包的正确版本。</span><span class="sxs-lookup"><span data-stu-id="97e0b-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="97e0b-137">如果您运行的 64 位版本的 Windows 7 SP1，下载文件 Win7AndW2K8R2-KB3191566 x64.ZIP。</span><span class="sxs-lookup"><span data-stu-id="97e0b-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="97e0b-138">如果您运行的 32 位版本的 Windows 7，下载文件 Win7-KB3191566 x86.ZIP。</span><span class="sxs-lookup"><span data-stu-id="97e0b-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="97e0b-139">如果在您的计算机上运行 Windows 7，请确保您已安装 Windows 7 Service Pack 1。</span><span class="sxs-lookup"><span data-stu-id="97e0b-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="97e0b-140">如果您不确定哪个版本的 Windows 运行的，或者您不确定如果已安装 Windows 7 Service Pack 1，单击**开始**，右键单击**计算机**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="97e0b-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="97e0b-141">在系统对话框中，将报告此信息。</span><span class="sxs-lookup"><span data-stu-id="97e0b-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="97e0b-142">若要安装 Windows Management Framework 5.1，完成[安装和配置 WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)中的过程</span><span class="sxs-lookup"><span data-stu-id="97e0b-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span></span>
  
<span data-ttu-id="97e0b-143">已重新启动计算机后，验证，可以启动 Windows PowerShell，可以在管理凭据下运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="97e0b-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="97e0b-144">若要此操作：</span><span class="sxs-lookup"><span data-stu-id="97e0b-144">To do this:</span></span>
  
1. <span data-ttu-id="97e0b-145">单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**，右键单击**Windows PowerShell** ，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="97e0b-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="97e0b-146">如果用户帐户控制显示对话框，请单击**是**以验证您想要管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97e0b-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="97e0b-147">PowerShell 控制台显示时，则应验证 WinRM 服务正在运行并已正确配置。</span><span class="sxs-lookup"><span data-stu-id="97e0b-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="97e0b-148">若要确认服务正在运行，在 PowerShell 提示符处键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="97e0b-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="97e0b-149">然后，有关 WinRM 服务的信息将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="97e0b-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="97e0b-150">如果该服务状态不等于"运行"，通过键入以下命令并按 ENTER 启动 WinRM 服务：</span><span class="sxs-lookup"><span data-stu-id="97e0b-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="97e0b-151">服务已启动后，运行以下命令以确保 WinRM 使用基本身份验证：</span><span class="sxs-lookup"><span data-stu-id="97e0b-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="97e0b-152">类似于以下的信息将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="97e0b-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="97e0b-153">如果基本身份验证已设置为 true，然后便可以使用 PowerShell 连接到 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="97e0b-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="97e0b-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="97e0b-154">Related topics</span></span>
[<span data-ttu-id="97e0b-155">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="97e0b-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
