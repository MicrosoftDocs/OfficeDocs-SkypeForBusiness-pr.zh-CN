---
title: 下载并安装 Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: 下载和安装，然后使用 Windows PowerShell 3.0 创建连接到 Skype 业务 online 的远程 PowerShell 会话。
ms.openlocfilehash: 9c2b0f02d9da7e44cdb5585314c13a6bafbe58c6
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568319"
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="3d916-103">下载并安装 Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="3d916-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="3d916-104">如果您使用的 Windows 8.1、 Windows 8、 Windows Server 2012 R2 或 Windows Server 2012，则您应该已经 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="3d916-104">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0.</span></span> <span data-ttu-id="3d916-105">这是因为此应用程序方面与这些操作系统预安装。</span><span class="sxs-lookup"><span data-stu-id="3d916-105">That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="3d916-106">如果您运行的 Windows 7 或 Windows Server 2008 R2，您可能还运行 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="3d916-106">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0.</span></span> <span data-ttu-id="3d916-107">但是，也可能是，您可能会运行 2.0 版改为 — 最初附带这些操作系统的版本。</span><span class="sxs-lookup"><span data-stu-id="3d916-107">However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems.</span></span> <span data-ttu-id="3d916-108">若要确定使用哪个版本的 Microsoft PowerShelll，执行下列操作在 Windows 7 或 Windows Server 2008 R2 的计算机上：</span><span class="sxs-lookup"><span data-stu-id="3d916-108">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="3d916-109">单击**开始**，单击**所有程序**、 都**附件**、 都**Windows PowerShell**，，然后都单击**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="3d916-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="3d916-110">在 PowerShell 控制台中，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="3d916-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="3d916-111">然后应控制台窗口中显示类似于以下的信息：</span><span class="sxs-lookup"><span data-stu-id="3d916-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    3.0
    </pre>

    <span data-ttu-id="3d916-112">如果返回的版本号是 3.0，您正在运行 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="3d916-112">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="3d916-113">如果返回的版本号不是 3.0，您需要安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="3d916-113">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="3d916-114">您可以从[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=34595)下载 Windows Management Framework 3.0，其中包括 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="3d916-114">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="3d916-115">验证了安装了 Windows PowerShell 3.0 后，您必须确保 PowerShell 确认已配置的运行远程脚本。</span><span class="sxs-lookup"><span data-stu-id="3d916-115">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="3d916-116">为此，请以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3d916-116">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="3d916-117">在 Windows 7、 Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3d916-117">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="3d916-118">单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**、 **Windows PowerShell**中，右键单击，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="3d916-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="3d916-119">如果出现**用户帐户控制**对话框，请单击**是**以确认您想要管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3d916-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="3d916-120">如果您运行的 Windows 8，而是完成此过程：</span><span class="sxs-lookup"><span data-stu-id="3d916-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="3d916-121">访问超级按钮栏，单击**搜索**，然后右键单击**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="3d916-121">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="3d916-122">您可以快速访问的超级按钮栏 （触摸屏或非触摸屏） 的任何 Windows 8 计算机上，通过按下 Windows 键和 c。</span><span class="sxs-lookup"><span data-stu-id="3d916-122">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="3d916-123">在屏幕底部工具栏中，单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="3d916-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="3d916-124">如果出现**用户帐户控制**对话框，请单击**是**以确认您想要管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3d916-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="3d916-125">运行 PowerShell 后，您必须更改执行策略，以允许脚本远程运行。</span><span class="sxs-lookup"><span data-stu-id="3d916-125">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="3d916-126">在 PowerShell 控制台中，键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="3d916-126">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="3d916-127">运行上述命令时，您可能会收到以下错误消息： > *Set-executionpolicy： 向注册表项的访问 HKEY_LOCAL_MACHINE\\软件\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell 被拒绝。*</span><span class="sxs-lookup"><span data-stu-id="3d916-127">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="3d916-128">如果您不管理员凭据运行 PowerShell，通常会出现此错误消息。</span><span class="sxs-lookup"><span data-stu-id="3d916-128">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="3d916-129">关闭会话的 PowerShell 中，并以管理员身份启动新的会话。</span><span class="sxs-lookup"><span data-stu-id="3d916-129">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="3d916-130">若要验证已正确配置执行策略，在 PowerShell 提示符处键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="3d916-130">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="3d916-131">如果您获得以下值，然后所有已正确配置：</span><span class="sxs-lookup"><span data-stu-id="3d916-131">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="3d916-132">如果您当前未运行 Windows PowerShell 3.0，您还需要下载并安装 Windows Management Framework 3.0 从 Microsoft 下载中心。</span><span class="sxs-lookup"><span data-stu-id="3d916-132">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="3d916-133">这是一个安装包，包括 Windows PowerShell 3.0 和 Windows 远程管理 (WinRM) 3.0。</span><span class="sxs-lookup"><span data-stu-id="3d916-133">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="3d916-134">如果运行 Windows 7 和尚未更新到 Windows PowerShell 3.0，可能需要此安装软件包。</span><span class="sxs-lookup"><span data-stu-id="3d916-134">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="3d916-135">如果您运行的 Windows Server 2012、 Windows Server 2012 R2、 Windows 8 或 Windows 8.1，应该有无需安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="3d916-135">If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="3d916-136">Windows PowerShell 3.0 这些操作系统的亮起预安装。</span><span class="sxs-lookup"><span data-stu-id="3d916-136">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="3d916-137">安装 Windows Management Framework 3.0： 之前</span><span class="sxs-lookup"><span data-stu-id="3d916-137">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="3d916-138">请确保您已下载安装程序包的正确版本。</span><span class="sxs-lookup"><span data-stu-id="3d916-138">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="3d916-139">如果您运行的 64 位版本的 Windows 7，下载 Windows6.1-KB2506143-x64.msu 的文件。</span><span class="sxs-lookup"><span data-stu-id="3d916-139">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="3d916-140">如果您运行的 32 位版本的 Windows 7，下载 Windows6.1-KB2506143-x86.msu 的文件。</span><span class="sxs-lookup"><span data-stu-id="3d916-140">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="3d916-141">如果在您的计算机上运行 Windows 7，请确保您已安装 Windows 7 Service Pack 1。</span><span class="sxs-lookup"><span data-stu-id="3d916-141">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="3d916-142">如果您不确定哪个版本的 Windows 运行的，或者您不确定如果已安装 Windows 7 Service Pack 1，单击**开始**，右键单击**计算机**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3d916-142">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="3d916-143">在系统对话框中，将报告此信息。</span><span class="sxs-lookup"><span data-stu-id="3d916-143">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="3d916-144">若要安装 Windows Management Framework 3.0，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="3d916-144">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="3d916-145">双击。MSU 安装文件 （ **Windows6.1-KB2506143-x64.msu**或**Windows6.1-KB2506143-x86.msu**）。</span><span class="sxs-lookup"><span data-stu-id="3d916-145">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="3d916-146">下载并安装更新向导，在**阅读 (第 1 个 1) 这些许可条款**页上，单击**我接受**。</span><span class="sxs-lookup"><span data-stu-id="3d916-146">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="3d916-147">安装完成后，单击**立即重新启动**以重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="3d916-147">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="3d916-148">已重新启动计算机后，验证，可以启动 Windows PowerShell，可以在管理凭据下运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d916-148">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="3d916-149">若要此操作：</span><span class="sxs-lookup"><span data-stu-id="3d916-149">To do this:</span></span>
  
1. <span data-ttu-id="3d916-150">单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**，右键单击**Windows PowerShell** ，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="3d916-150">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="3d916-151">如果用户帐户控制显示对话框，请单击**是**以验证您想要管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3d916-151">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="3d916-152">PowerShell 控制台显示时，则应验证 WinRM 服务正在运行并已正确配置。</span><span class="sxs-lookup"><span data-stu-id="3d916-152">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="3d916-153">若要确认服务正在运行，在 PowerShell 提示符处键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="3d916-153">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="3d916-154">然后，有关 WinRM 服务的信息将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="3d916-154">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="3d916-155">如果该服务状态不等于"运行"，通过键入以下命令并按 ENTER 启动 WinRM 服务：</span><span class="sxs-lookup"><span data-stu-id="3d916-155">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="3d916-156">服务已启动后，运行以下命令以确保 WinRM 使用基本身份验证：</span><span class="sxs-lookup"><span data-stu-id="3d916-156">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="3d916-157">类似于以下的信息将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="3d916-157">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="3d916-158">如果基本身份验证已设置为 true，然后便可以使用 PowerShell 连接到 Skype 业务 online。</span><span class="sxs-lookup"><span data-stu-id="3d916-158">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="3d916-159">相关主题</span><span class="sxs-lookup"><span data-stu-id="3d916-159">Related topics</span></span>
[<span data-ttu-id="3d916-160">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="3d916-160">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 