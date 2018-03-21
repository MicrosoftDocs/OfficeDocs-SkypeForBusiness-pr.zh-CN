---
title: "下载并安装 Skype 业务在线连接器模块"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
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
description: "下载、 安装和使用 Skype 业务在线连接器创建远程 Windows PowerShell 会话连接到 Skype 的在线业务。 "
ms.openlocfilehash: 4b4f611cae3ca46629de42b122ef4e9238402c98
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="d857f-103">下载并安装 Skype 业务在线连接器模块</span><span class="sxs-lookup"><span data-stu-id="d857f-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="d857f-104">Skype 业务在线连接器模块包括**新建 CsOnlineSession** cmdlet，它使您能够创建远程 Windows PowerShell 会话连接到 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="d857f-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="d857f-105">本模块中，这支持仅在 （有关详细信息，请参阅[设置计算机上的 Skype 使用 Windows PowerShell 的在线业务管理](set-up-your-computer-for-windows-powershell.md)） 的 64 位计算机上，可从[https:// 在 Microsoft 下载中心下载www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="d857f-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="d857f-106">下载 SkypeOnlinePowershell.exe 文件，然后完成下面的过程：</span><span class="sxs-lookup"><span data-stu-id="d857f-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="d857f-107">双击**SkypeOnlinePowershell.exe**文件。</span><span class="sxs-lookup"><span data-stu-id="d857f-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="d857f-108">在 Skype 的在线业务，Windows PowerShell 安装向导中的，在**Microsoft 软件许可条款**页中，选择**我接受许可协议中的条款**，然后单击**安装**。</span><span class="sxs-lookup"><span data-stu-id="d857f-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="d857f-109">如果出现**用户帐户控制**对话框，请单击**是**以继续安装。</span><span class="sxs-lookup"><span data-stu-id="d857f-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="d857f-110">在**已完成的业务联机，Windows PowerShell 模块 Skype**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="d857f-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="d857f-111">安装程序复制到您的计算机业务在线连接器模块 （以及**新建 CsOnlineSession** cmdlet） Skype。</span><span class="sxs-lookup"><span data-stu-id="d857f-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="d857f-112">若要访问的模块，启动 Windows PowerShell 会话管理员凭据，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d857f-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="d857f-113">如果您不希望每次启动 Windows PowerShell 键入以下命令，可以对 Windows PowerShell 配置文件中添加命令。</span><span class="sxs-lookup"><span data-stu-id="d857f-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="d857f-114">要做到这一点，在 Windows PowerShell 提示符下键入以下命令，然后按 enter 键：</span><span class="sxs-lookup"><span data-stu-id="d857f-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="d857f-115">记事本出现时，到底端的配置文件 （如果有的话） 中已有的命令中添加以下行：</span><span class="sxs-lookup"><span data-stu-id="d857f-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="d857f-116">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="d857f-116">Save the file.</span></span> <span data-ttu-id="d857f-117">下次启动 Windows PowerShell Skype 业务在线连接器模块将自动导入。</span><span class="sxs-lookup"><span data-stu-id="d857f-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="d857f-118">注意，您将收到错误消息，并且将不会加载该模块，如果不在管理员凭据下运行 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d857f-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="d857f-119">除了安装 Skype 业务在线连接器模块，SkypeOnlinePowershell.exe 还安装了三个其他组件： 1) 标识服务客户端运行时库 (IDCRL)，用来处理业务的 Skype 的客户端身份验证联机;2).net 4.5。以及 3） Microsoft Visual C++ 2012年可再发行组件 (x64) 软件包 （11.0.50727 版）。</span><span class="sxs-lookup"><span data-stu-id="d857f-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="d857f-120">.NET framework 4.5 提供了用于构建和运行.NET 应用程序，包括 Windows PowerShell 的基础结构。</span><span class="sxs-lookup"><span data-stu-id="d857f-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="d857f-121">Visual C++ 可再发行组件包安装计算机没有安装 Microsoft Visual Studio 2012 Visual C++ 运行时的组件。</span><span class="sxs-lookup"><span data-stu-id="d857f-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="d857f-122">要验证当前安装在计算机的连接器模块的版本号，请打开控制面板，打开**程序和功能**，然后检查**Skype 业务在线，Windows PowerShell 模块**的版本号。</span><span class="sxs-lookup"><span data-stu-id="d857f-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d857f-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="d857f-123">Related topics</span></span>
[<span data-ttu-id="d857f-124">设置计算机上的 Skype 业务在线管理使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d857f-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

## <a name="feedback"></a><span data-ttu-id="d857f-125">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="d857f-125">Feedback?</span></span>
<span data-ttu-id="d857f-126">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="d857f-126">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>