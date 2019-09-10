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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: 下载、安装并使用 Windows PowerShell 5.1 创建连接到 Skype for Business Online 的远程 PowerShell 会话。
ms.openlocfilehash: 5afca0ef1fd5d7437c3974de1424a664c99ab1a1
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701549"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="507d2-103">下载并安装 Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="507d2-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="507d2-104">如果使用的是 Windows 10 周年更新或 Windows Server 2016，则应已拥有 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="507d2-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="507d2-105">这是因为此应用程序随这些操作系统预安装。</span><span class="sxs-lookup"><span data-stu-id="507d2-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="507d2-106">要确定你使用的是什么版本的 Microsoft PowerShelll，请在 Windows 7 或 Windows Server 2008 R2 或 Windows Server 2012 计算机上执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="507d2-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="507d2-107">依次单击“**开始**”、“**所有程序**”、“**附件**”和“**Windows PowerShell**”，然后单击“**Windows PowerShell**”。</span><span class="sxs-lookup"><span data-stu-id="507d2-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="507d2-108">在 PowerShell 控制台中，键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="507d2-108">In the console window, type the following command and press ENTER.</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="507d2-109">控制台窗口中随后应显示以下类似信息：</span><span class="sxs-lookup"><span data-stu-id="507d2-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="507d2-110">如果返回的版本号为 5.1，表明正在运行 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="507d2-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="507d2-111">如果返回的版本号不是 5.1，则需要安装 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="507d2-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="507d2-112">可从 [Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=54616)下载 Windows Management Framework 5.1（其中包括 Windows PowerShell 5.1）。</span><span class="sxs-lookup"><span data-stu-id="507d2-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="507d2-113">验证已安装 Windows PowerShell 5.1 后，必须确保 PowerShell 已配置为可以运行远程脚本。</span><span class="sxs-lookup"><span data-stu-id="507d2-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="507d2-114">为此，以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="507d2-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="507d2-115">在 Windows 7、Windows Server 2008 R2、Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="507d2-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="507d2-116">单击“**启动**”，依次单击“**所有程序**”、“**附件**”、“**Windows PowerShell**”，然后右键单击“**Windows PowerShell**”，单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="507d2-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="507d2-117">如果显示“**用户帐户控制**”对话框，单击“**是**”确定要通过管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="507d2-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="507d2-118">如果运行的是 Windows 8，请完成此过程：</span><span class="sxs-lookup"><span data-stu-id="507d2-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="507d2-119">访问超级按钮栏，单击“**搜索**”，然后右键单击“**Windows PowerShell**”。</span><span class="sxs-lookup"><span data-stu-id="507d2-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="507d2-120">可以通过按住 Windows 键并按 C 来在任何 Windows 8 计算机（触摸屏或非触摸屏）上快速访问超级按钮栏。</span><span class="sxs-lookup"><span data-stu-id="507d2-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="507d2-121">在屏幕底部的工具栏中，单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="507d2-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="507d2-122">如果显示“**用户帐户控制**”对话框，单击“**是**”确定要通过管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="507d2-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="507d2-123">在 PowerShell 运行后，必须更改执行策略以允许运行远程脚本。</span><span class="sxs-lookup"><span data-stu-id="507d2-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="507d2-124">在 PowerShell 控制台中，键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="507d2-124">In the console window, type the following command and press ENTER.</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="507d2-125">运行上述命令后，可能会收到以下错误消息：> *Set-ExecutionPolicy：对注册表项“HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell”的访问被拒绝。*</span><span class="sxs-lookup"><span data-stu-id="507d2-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="507d2-126">如果未在管理员凭据下运行 PowerShell，则通常会出现此错误消息。</span><span class="sxs-lookup"><span data-stu-id="507d2-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="507d2-127">关闭 PowerShell 会话，并以管理员身份启动新会话。</span><span class="sxs-lookup"><span data-stu-id="507d2-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="507d2-128">要验证是否已正确配置执行策略，请在 PowerShell 提示符处键入以下内容，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="507d2-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="507d2-129">如果获得以下值，则所有内容已正确配置：</span><span class="sxs-lookup"><span data-stu-id="507d2-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="507d2-130">如果当前未运行 Windows PowerShell 5.1，则还需要从 Microsoft 下载中心下载并安装 Windows Management Framework 5.1。</span><span class="sxs-lookup"><span data-stu-id="507d2-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="507d2-131">这是一个安装程序包，包含 Windows PowerShell 5.1 和 Windows 远程管理 (WinRM) 3.0。</span><span class="sxs-lookup"><span data-stu-id="507d2-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="507d2-132">例如，如果运行的是 Windows 7 SP1，并且尚未更新到 Windows PowerShell 5.1，则可能需要此安装程序包。</span><span class="sxs-lookup"><span data-stu-id="507d2-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="507d2-133">如果运行的是 Windows Server 2016 或 Windows 10 周年更新，则无需安装 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="507d2-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="507d2-134">这些操作系统上预装了 Windows PowerShell 5.1。</span><span class="sxs-lookup"><span data-stu-id="507d2-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="507d2-135">在安装 Windows Management Framework 5.1 之前：</span><span class="sxs-lookup"><span data-stu-id="507d2-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="507d2-136">确保已下载安装程序包的正确版本。</span><span class="sxs-lookup"><span data-stu-id="507d2-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="507d2-137">如果运行的是 64 位版本的 Windows 7 SP1，请下载文件 Win7AndW2K8R2-KB3191566-x64.ZIP。</span><span class="sxs-lookup"><span data-stu-id="507d2-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="507d2-138">如果运行的是 32 位版本的 Windows 7，请下载文件 Win7-KB3191566-x86.ZIP。</span><span class="sxs-lookup"><span data-stu-id="507d2-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="507d2-139">如果计算机正在运行 Windows 7，请确保已安装 Windows 7 Service Pack 1。</span><span class="sxs-lookup"><span data-stu-id="507d2-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="507d2-140">如果不确定正在运行的 Windows 版本，或者不确定是否已安装 Windows 7 Service Pack 1，请单击“**开始**”，右键单击“**计算机**”，然后单击“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="507d2-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="507d2-141">“系统”对话框中将报告此信息。</span><span class="sxs-lookup"><span data-stu-id="507d2-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="507d2-142">要安装 Windows Management Framework 5.1，请完成[安装和配置 WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure) 中的程序。</span><span class="sxs-lookup"><span data-stu-id="507d2-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="507d2-143">计算机重新启动后，验证 Windows PowerShell 是否可以启动以及应用程序是否可在管理凭据下运行。</span><span class="sxs-lookup"><span data-stu-id="507d2-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="507d2-144">要执行此操作：</span><span class="sxs-lookup"><span data-stu-id="507d2-144">To do this run:</span></span>
  
1. <span data-ttu-id="507d2-145">单击“**启动**”，依次单击“**所有程序**”、“**附件**”、“**Windows PowerShell**”，然后右键单击“**Windows PowerShell**”，单击“**以管理员身份运行**”。</span><span class="sxs-lookup"><span data-stu-id="507d2-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="507d2-146">如果显示“用户帐户控制”对话框，单击“**是**”确定要通过管理员凭据运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="507d2-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="507d2-147">当 PowerShell 控制台出现时，应该验证 WinRM 服务是否正在运行并且已正确配置。</span><span class="sxs-lookup"><span data-stu-id="507d2-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="507d2-148">要验证服务是否正在运行，请在 PowerShell 提示符处键入以下命令，然后按 Enter：</span><span class="sxs-lookup"><span data-stu-id="507d2-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="507d2-149">屏幕上将显示有关 WinRM 服务的信息：</span><span class="sxs-lookup"><span data-stu-id="507d2-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="507d2-150">如果服务状态不是“正在运行”，请通过键入以下命令并按 Enter 来启动 WinRM 服务：</span><span class="sxs-lookup"><span data-stu-id="507d2-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="507d2-151">服务启动后，请运行以下命令以确保 WinRM 使用基本身份验证：</span><span class="sxs-lookup"><span data-stu-id="507d2-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="507d2-152">屏幕上将显示以下类似信息：</span><span class="sxs-lookup"><span data-stu-id="507d2-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="507d2-153">如果基本身份验证设置为 true，则可以开始使用 PowerShell 连接 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="507d2-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="507d2-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="507d2-154">Related topics</span></span>
[<span data-ttu-id="507d2-155">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="507d2-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
