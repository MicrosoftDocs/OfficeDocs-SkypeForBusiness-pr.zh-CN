---
title: 在 Skype for Business Server 2015 中使用安装程序命令行选项
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: 摘要： 了解有关 Office 安装程序中的 Setup.exe 命令行操作。
ms.openlocfilehash: 0fa4f31750697f0bd0dbe87bbde025cbc7f530bd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="use-setup-command-line-options-in-skype-for-business-server-2015"></a><span data-ttu-id="42523-103">在 Skype for Business Server 2015 中使用安装程序命令行选项</span><span class="sxs-lookup"><span data-stu-id="42523-103">Use Setup command-line options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="42523-104">**摘要：**了解有关 Office 安装程序中的 Setup.exe 命令行操作。</span><span class="sxs-lookup"><span data-stu-id="42523-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="42523-105">Setup.exe 命令行用于 Office 安装中的几个操作。</span><span class="sxs-lookup"><span data-stu-id="42523-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="42523-106">而不是使用安装程序命令行选项，您通常使用 Office 自定义工具和 Config.xml 文件为产品安装和功能自定义。</span><span class="sxs-lookup"><span data-stu-id="42523-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="42523-107">Office Setup.exe 命令行识别下表中介绍的命令行选项。</span><span class="sxs-lookup"><span data-stu-id="42523-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="42523-108">**Office 安装程序命令行选项**</span><span class="sxs-lookup"><span data-stu-id="42523-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="42523-109">**安装程序命令行选项**</span><span class="sxs-lookup"><span data-stu-id="42523-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="42523-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="42523-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="42523-111">/admin</span><span class="sxs-lookup"><span data-stu-id="42523-111">/admin</span></span>  <br/> |<span data-ttu-id="42523-112">运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。</span><span class="sxs-lookup"><span data-stu-id="42523-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="42523-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="42523-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="42523-p102">将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="42523-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="42523-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="42523-116">/config [path]</span></span>  <br/> |<span data-ttu-id="42523-117">指定安装程序在安装过程中使用的 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="42523-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="42523-118">/Config 选项用于指定您为自定义 Skype 对于企业安装，例如 Config.xml 文件：`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="42523-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="42523-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="42523-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="42523-120">用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。</span><span class="sxs-lookup"><span data-stu-id="42523-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="42523-121">例如，您可以使用 / 修改选项添加或删除 Skype 业务功能。</span><span class="sxs-lookup"><span data-stu-id="42523-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="42523-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="42523-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="42523-123">从用户的计算机以修复 Skype 业务运行安装程序。</span><span class="sxs-lookup"><span data-stu-id="42523-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="42523-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="42523-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="42523-125">运行安装程序在用户的计算机上删除 Skype 业务。</span><span class="sxs-lookup"><span data-stu-id="42523-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   
<span data-ttu-id="42523-126">有关使用安装程序命令行选项的详细信息，请参阅[https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515)。</span><span class="sxs-lookup"><span data-stu-id="42523-126">For details about using the setup command-line options, see [https://go.microsoft.com/fwlink/p/?linkid=267515](https://go.microsoft.com/fwlink/p/?linkid=267515).</span></span> 
  

