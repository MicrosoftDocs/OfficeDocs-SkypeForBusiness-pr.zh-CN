---
title: 下载并安装 Skype for Business Online 连接器模块
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: '下载、安装和使用 Skype for Business Online 连接器以创建连接到 Skype for business Online 的远程 Windows PowerShell 会话。 '
ms.openlocfilehash: 4d794902ce39687c32f584f97b126c98f237c486
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991297"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="12e45-103">下载并安装 Skype for Business Online 连接器模块</span><span class="sxs-lookup"><span data-stu-id="12e45-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="12e45-104">Skype for Business Online 连接器模块包括**CsOnlineSession** cmdlet，可用于创建连接到 Skype For business Online 的远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="12e45-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="12e45-105">此模块仅受64位计算机支持（请参阅[使用 Windows PowerShell 设置适用于 Skype for Business Online 管理的计算机](set-up-your-computer-for-windows-powershell.md)），可从 Microsoft 下载中心下载[https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="12e45-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="12e45-106">下载 SkypeOnlinePowershell 文件，然后完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="12e45-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="12e45-107">双击 " **SkypeOnlinePowershell** " 文件。</span><span class="sxs-lookup"><span data-stu-id="12e45-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="12e45-108">在 Skype for Business Online 的 Windows PowerShell 设置向导中的 " **Microsoft 软件许可条款**" 页面上，选择 "**我接受许可协议中的条款**"，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="12e45-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="12e45-109">如果出现 "**用户帐户控制**" 对话框，请单击 **"是"** 以继续安装。</span><span class="sxs-lookup"><span data-stu-id="12e45-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="12e45-110">在 "**已完成 Skype For Business Online，Windows PowerShell 模块**" 页面上，单击 "**完成**"。</span><span class="sxs-lookup"><span data-stu-id="12e45-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="12e45-111">安装程序会将 Skype for Business Online 连接器模块（以及**CsOnlineSession** cmdlet）复制到你的计算机。</span><span class="sxs-lookup"><span data-stu-id="12e45-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="12e45-112">若要访问该模块，请在 "管理员凭据" 下启动 Windows PowerShell 会话，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="12e45-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="12e45-113">如果你不希望每次启动 Windows PowerShell 时都键入此命令，你可以将该命令添加到你的 Windows PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="12e45-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="12e45-114">若要执行此操作，请在 Windows PowerShell 提示符处键入以下命令，然后按 ENTER：</span><span class="sxs-lookup"><span data-stu-id="12e45-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="12e45-115">出现 "记事本" 时，将以下行添加到配置文件中已存在的命令底部（如果有）：</span><span class="sxs-lookup"><span data-stu-id="12e45-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="12e45-116">保存文件。</span><span class="sxs-lookup"><span data-stu-id="12e45-116">Save the file.</span></span> <span data-ttu-id="12e45-117">下次启动 Windows PowerShell 时，将自动导入 Skype for business Online 连接器模块。</span><span class="sxs-lookup"><span data-stu-id="12e45-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="12e45-118">请注意，你将收到一条错误消息，如果你未在 "管理员凭据" 下运行 Windows PowerShell，将不会加载该模块。</span><span class="sxs-lookup"><span data-stu-id="12e45-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="12e45-119">除了安装 Skype for Business Online 连接器模块之外，SkypeOnlinePowershell 还会安装三个附加组件：1）标识服务客户端运行时库（IDCRL），用于处理对 Skype for business 的客户端身份验证Online2） .NET Framework 4.5;和3） Microsoft Visual c + + 2012 可再发行（x64）程序包（版本11.0.50727）。</span><span class="sxs-lookup"><span data-stu-id="12e45-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="12e45-120">.NET Framework 4.5 提供用于构建和运行 .NET 应用程序（包括 Windows PowerShell）的基础结构。</span><span class="sxs-lookup"><span data-stu-id="12e45-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="12e45-121">Visual c + + 可再发行程序包为未安装 Microsoft Visual Studio 2012 的计算机安装 Visual c + + 运行时组件。</span><span class="sxs-lookup"><span data-stu-id="12e45-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="12e45-122">若要验证您的计算机上当前安装的连接器模块的版本号，请打开 "控制面板"，打开 "**程序和功能**"，然后查看**Skype for Business Online、Windows PowerShell 模块**的版本号。</span><span class="sxs-lookup"><span data-stu-id="12e45-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="12e45-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="12e45-123">Related topics</span></span>
[<span data-ttu-id="12e45-124">使用 Windows PowerShell 为 skype for business online 管理设置计算机</span><span class="sxs-lookup"><span data-stu-id="12e45-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
