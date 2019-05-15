---
title: 下载并安装 for Business Online Connector 模块 Skype
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: '下载、 安装，然后使用 Business Online Connector 的 Skype 创建连接到 Skype 业务 online 远程 Windows PowerShell 会话。 '
ms.openlocfilehash: a93cf1d3d09910001f25619969b6d504e23ec36f
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036689"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="26359-103">下载并安装 for Business Online Connector 模块 Skype</span><span class="sxs-lookup"><span data-stu-id="26359-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="26359-104">为业务 Online Connector 模块 Skype 包括**新建 CsOnlineSession** cmdlet，使您能够创建连接到 Skype 业务 online 远程 Windows PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="26359-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="26359-105">此模块只能在 （有关详细信息，请参阅[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md) ） 的 64 位计算机的受支持，可以从 Microsoft 下载中心获取下载[https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="26359-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="26359-106">下载 SkypeOnlinePowershell.exe 文件，然后完成以下过程：</span><span class="sxs-lookup"><span data-stu-id="26359-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="26359-107">双击**SkypeOnlinePowershell.exe**文件。</span><span class="sxs-lookup"><span data-stu-id="26359-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="26359-108">业务 online Skype，在 Windows PowerShell 安装向导，在**Microsoft 软件许可条款**页中，选择**我接受许可协议中的条款**，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="26359-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="26359-109">如果出现**用户帐户控制**对话框，请单击**是**以继续安装。</span><span class="sxs-lookup"><span data-stu-id="26359-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="26359-110">在**已完成的业务 Online Windows PowerShell 模块 Skype**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="26359-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="26359-111">安装程序将复制到您的计算机业务 Online Connector 模块 （和**新建 CsOnlineSession** cmdlet） Skype。</span><span class="sxs-lookup"><span data-stu-id="26359-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="26359-112">若要访问的模块和启动 Windows PowerShell 会话下管理员凭据，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="26359-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="26359-113">如果您不希望每次启动 Windows PowerShell，请键入以下命令，您可以将命令添加到 Windows PowerShell 配置文件。</span><span class="sxs-lookup"><span data-stu-id="26359-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="26359-114">为此，在 Windows PowerShell 提示符处键入以下命令，然后按 ENTER:</span><span class="sxs-lookup"><span data-stu-id="26359-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="26359-115">出现记事本时，添加以下行到底部的配置文件 （如果有） 中已有的命令：</span><span class="sxs-lookup"><span data-stu-id="26359-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="26359-116">保存文件。</span><span class="sxs-lookup"><span data-stu-id="26359-116">Save the file.</span></span> <span data-ttu-id="26359-117">下次启动 Windows PowerShell for Business Online Connector 模块 Skype 将自动导入。</span><span class="sxs-lookup"><span data-stu-id="26359-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="26359-118">注意，您将收到一条错误消息，并将不会加载该模块，如果您不管理员凭据运行 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="26359-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="26359-119">除了安装 for Business Online Connector 模块 Skype，SkypeOnlinePowershell.exe 还安装了三个其他组件： 1) 标识服务客户端运行时库 (IDCRL)，用于处理对业务的 Skype 的客户端身份验证联机;2).NET framework 4.5;以及 3） 的 Microsoft Visual c + + 2012年可再发行软件包 (x64) 程序包 （版本 11.0.50727）。</span><span class="sxs-lookup"><span data-stu-id="26359-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="26359-120">.NET framework 4.5 提供用于构建和运行.NET 应用程序，包括 Windows PowerShell 的基础结构。</span><span class="sxs-lookup"><span data-stu-id="26359-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="26359-121">Visual c + + 可再发行软件包安装 Visual c + + 运行时组件没有安装 Microsoft Visual Studio 2012 的计算机。</span><span class="sxs-lookup"><span data-stu-id="26359-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="26359-122">若要验证您的计算机当前安装的连接器模块的版本号，打开控制面板和打开**程序和功能**，然后检查**Windows PowerShell 模块业务 online，Skype**的版本号。</span><span class="sxs-lookup"><span data-stu-id="26359-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="26359-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="26359-123">Related topics</span></span>
[<span data-ttu-id="26359-124">设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype</span><span class="sxs-lookup"><span data-stu-id="26359-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
