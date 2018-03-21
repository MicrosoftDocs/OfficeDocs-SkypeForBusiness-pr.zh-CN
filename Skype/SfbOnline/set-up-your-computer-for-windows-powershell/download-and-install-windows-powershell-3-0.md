---
title: "下载并安装 Windows PowerShell 3.0"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
description: "下载、 安装和使用 Windows PowerShell 3.0 创建远程 PowerShell 会话连接到 Skype 的在线业务。"
ms.openlocfilehash: 28f4db7492c233f5cfa16137d77ed8e0dc4a6572
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="c095e-103">下载并安装 Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="c095e-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="c095e-104">如果您使用的 Windows 8.1、 Windows 8、 Windows Server 2012 R2 或 Windows Server 2012，您应该已经 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-104">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0.</span></span> <span data-ttu-id="c095e-105">这是因为此应用程序是使用这些操作系统预装。</span><span class="sxs-lookup"><span data-stu-id="c095e-105">That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="c095e-106">如果您运行的 Windows 7 或 Windows Server 2008 R2，您可能也在运行 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-106">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0.</span></span> <span data-ttu-id="c095e-107">但是，也可能是您可能会运行版本 2.0 相反 — — 这些操作系统附带的原装的版本。</span><span class="sxs-lookup"><span data-stu-id="c095e-107">However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems.</span></span> <span data-ttu-id="c095e-108">要确定正在使用哪个版本的 Microsoft PowerShelll，请执行下列操作在 Windows 7 计算机或 Windows Server 2008 R2 计算机上：</span><span class="sxs-lookup"><span data-stu-id="c095e-108">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="c095e-109">单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**，，然后都单击**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="c095e-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="c095e-110">在 PowerShell 控制台中，键入以下命令，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="c095e-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="c095e-111">然后会在控制台窗口中显示类似于以下的信息：</span><span class="sxs-lookup"><span data-stu-id="c095e-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="c095e-112">返回的版本号为 3.0，如果您正在运行 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-112">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="c095e-113">如果返回的版本号不是 3.0，您将需要安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-113">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="c095e-114">您可以从[Microsoft 下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=34595)下载 Windows 管理框架 3.0，其中包括 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-114">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="c095e-115">已验证安装了 Windows PowerShell 3.0 后，必须确保 PowerShell 确认已为运行远程脚本配置。</span><span class="sxs-lookup"><span data-stu-id="c095e-115">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="c095e-116">要做到这一点，请以管理员身份启动 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c095e-116">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="c095e-117">在 Windows 7，Windows Server 2008 R2、 Windows Server 2012 或 Windows Server 2012 R2 上执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c095e-117">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="c095e-118">单击**开始**，单击**所有程序**，都单击**附件**，都单击**Windows PowerShell**、 **Windows PowerShell**，用鼠标右键单击，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="c095e-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="c095e-119">如果出现**用户帐户控制**对话框，请单击**是**以确认您想要在管理员凭据下运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c095e-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="c095e-120">如果您运行的 Windows 8，而是完成此过程：</span><span class="sxs-lookup"><span data-stu-id="c095e-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="c095e-121">访问的魅力栏，单击**搜索**框中，然后用鼠标右键单击**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="c095e-121">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="c095e-122">您可以快速访问 （触摸屏或非触摸屏） 的任何 Windows 8 计算机上的魅力栏下 Windows 键，然后按 c。</span><span class="sxs-lookup"><span data-stu-id="c095e-122">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="c095e-123">在屏幕底部工具栏中，单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="c095e-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="c095e-124">如果出现**用户帐户控制**对话框，请单击**是**以确认您想要在管理员凭据下运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c095e-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="c095e-125">PowerShell 运行后，您必须更改执行策略以允许远程脚本的运行。</span><span class="sxs-lookup"><span data-stu-id="c095e-125">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="c095e-126">在 PowerShell 控制台中，键入以下命令，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="c095e-126">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
<span data-ttu-id="c095e-127">要验证已正确配置执行策略，PowerShell 提示符处键入以下内容，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="c095e-127">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="c095e-128">如果您得到以下值，然后一切都已正确配置：</span><span class="sxs-lookup"><span data-stu-id="c095e-128">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="c095e-129">如果您当前未运行的 Windows PowerShell 3.0，您还需要下载并安装从 Microsoft 下载中心获取 Windows 管理框架 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-129">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="c095e-130">这是一个安装包，包括 Windows PowerShell 3.0 和 Windows 远程管理 (WinRM) 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-130">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="c095e-131">如果运行 Windows 7，而且尚未更新到 Windows PowerShell 3.0，则可能需要此安装程序包。</span><span class="sxs-lookup"><span data-stu-id="c095e-131">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="c095e-132">如果您运行的 Windows Server 2012、 Windows Server 2012 R2、 Windows 8 或 Windows 8.1，应该不需要安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-132">If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="c095e-133">这些操作系统时预安装 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="c095e-133">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="c095e-134">在安装 Windows 管理框架 3.0： 之前</span><span class="sxs-lookup"><span data-stu-id="c095e-134">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="c095e-135">请确保您已下载的安装软件包的正确版本。</span><span class="sxs-lookup"><span data-stu-id="c095e-135">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="c095e-136">如果您运行的 64 位版本的 Windows 7，下载的文件 Windows6.1-KB2506143-x64.msu。</span><span class="sxs-lookup"><span data-stu-id="c095e-136">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="c095e-137">如果您运行的 32 位版本的 Windows 7，下载的文件 Windows6.1-KB2506143-x86.msu。</span><span class="sxs-lookup"><span data-stu-id="c095e-137">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="c095e-138">如果您在您的计算机上运行 Windows 7，请确保您已安装了 Windows 7 Service Pack 1。</span><span class="sxs-lookup"><span data-stu-id="c095e-138">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="c095e-139">如果您不确定哪个版本的 Windows 正在运行，或者您不能确定如果已经安装了 Windows 7 Service Pack 1，单击**开始**，右键单击**计算机**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c095e-139">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="c095e-140">在系统对话框还会报告此信息。</span><span class="sxs-lookup"><span data-stu-id="c095e-140">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="c095e-141">要安装 Windows 管理框架 3.0，请完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="c095e-141">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="c095e-142">双击。MSU 安装文件 （ **Windows6.1-KB2506143-x64.msu**或**Windows6.1-KB2506143-x86.msu**）。</span><span class="sxs-lookup"><span data-stu-id="c095e-142">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="c095e-143">在下载并安装更新向导中，在**阅读这些许可条款 (第 1 个 1)**页上，单击**我接受**。</span><span class="sxs-lookup"><span data-stu-id="c095e-143">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="c095e-144">安装完成后，请单击**立即重新启动**以重新启动您的计算机。</span><span class="sxs-lookup"><span data-stu-id="c095e-144">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="c095e-145">重新启动计算机后，请验证 Windows PowerShell 可以启动和应用程序，可以在管理凭据下运行。</span><span class="sxs-lookup"><span data-stu-id="c095e-145">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="c095e-146">若要此操作：</span><span class="sxs-lookup"><span data-stu-id="c095e-146">To do this:</span></span>
  
1. <span data-ttu-id="c095e-147">单击**开始**单击**所有程序**，都单击**附件**、 **Windows PowerShell**用鼠标右键单击**Windows PowerShell**和，然后都单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="c095e-147">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="c095e-148">如果出现对话框，用户帐户控制，请单击**是**以确认您要在管理员凭据下运行 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c095e-148">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="c095e-149">当 PowerShell 控制台出现时，然后应验证 WinRM 服务正在运行并已正确配置。</span><span class="sxs-lookup"><span data-stu-id="c095e-149">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="c095e-150">若要验证该服务正在运行，PowerShell 提示符处键入以下命令，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="c095e-150">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="c095e-151">然后，WinRM 服务有关的信息将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="c095e-151">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="c095e-152">如果服务状态不等于"正在运行"，通过键入以下命令，然后按 enter 键启动 WinRM 服务：</span><span class="sxs-lookup"><span data-stu-id="c095e-152">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="c095e-153">在服务启动后，运行以下命令来确保 WinRM 使用基本身份验证：</span><span class="sxs-lookup"><span data-stu-id="c095e-153">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="c095e-154">类似于以下的信息将显示在屏幕上：</span><span class="sxs-lookup"><span data-stu-id="c095e-154">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="c095e-155">如果基本的身份验证已设置为 true，然后您就可以使用 PowerShell 将连接到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="c095e-155">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="c095e-156">相关主题</span><span class="sxs-lookup"><span data-stu-id="c095e-156">Related topics</span></span>
[<span data-ttu-id="c095e-157">为 Windows PowerShell 设置计算机</span><span class="sxs-lookup"><span data-stu-id="c095e-157">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

## <a name="feedback"></a><span data-ttu-id="c095e-158">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="c095e-158">Feedback?</span></span>
<span data-ttu-id="c095e-159">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="c095e-159">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>