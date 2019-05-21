---
title: 将设置命令行选项与 Skype for Business 客户端配合使用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
description: '摘要: 了解 Office 安装程序中的 setup.exe 命令行操作。'
ms.openlocfilehash: 2eee24f9ae79ed2f73e23c68883f2552902fb672
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306480"
---
# <a name="use-setup-command-line-options-with-skype-for-business-clients"></a><span data-ttu-id="62376-103">将设置命令行选项与 Skype for Business 客户端配合使用</span><span class="sxs-lookup"><span data-stu-id="62376-103">Use Setup command-line options with Skype for Business clients</span></span>
 
<span data-ttu-id="62376-104">**摘要:** 了解 Office 安装程序中的 setup.exe 命令行操作。</span><span class="sxs-lookup"><span data-stu-id="62376-104">**Summary:** Learn about Setup.exe command line operations in Office setup.</span></span>
  
<span data-ttu-id="62376-105">Setup.exe 命令行用于 Office 安装中的几个操作。</span><span class="sxs-lookup"><span data-stu-id="62376-105">The Setup.exe command line is used for very few operations in Office setup.</span></span> <span data-ttu-id="62376-106">通常使用 Office 自定义工具和 Config.xml 文件进行产品设置和功能自定义, 而不是使用设置命令行选项。</span><span class="sxs-lookup"><span data-stu-id="62376-106">Instead of using the Setup command-line options, you'll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>
  
<span data-ttu-id="62376-107">Office Setup.exe 命令行识别下表中介绍的命令行选项。</span><span class="sxs-lookup"><span data-stu-id="62376-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>
  
<span data-ttu-id="62376-108">**Office 安装程序命令行选项**</span><span class="sxs-lookup"><span data-stu-id="62376-108">**Office Setup Command-Line Options**</span></span>

|<span data-ttu-id="62376-109">**安装程序命令行选项**</span><span class="sxs-lookup"><span data-stu-id="62376-109">**Setup Command-Line Option**</span></span>|<span data-ttu-id="62376-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="62376-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="62376-111">/admin</span><span class="sxs-lookup"><span data-stu-id="62376-111">/admin</span></span>  <br/> |<span data-ttu-id="62376-112">运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。</span><span class="sxs-lookup"><span data-stu-id="62376-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span>  <br/> |
|<span data-ttu-id="62376-113">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="62376-113">/adminfile [path]</span></span>  <br/> |<span data-ttu-id="62376-p102">将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="62376-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span>  <br/> |
|<span data-ttu-id="62376-116">/config [path]</span><span class="sxs-lookup"><span data-stu-id="62376-116">/config [path]</span></span>  <br/> |<span data-ttu-id="62376-117">指定安装程序在安装过程中使用的 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="62376-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="62376-118">使用/config 选项指定为 Skype for Business 安装自定义的 Config.xml 文件, 例如:`/config \\server\share\Skype15\Skype.WW\Config.xml`</span><span class="sxs-lookup"><span data-stu-id="62376-118">Use the /config option to specify the Config.xml file you customized for Skype for Business installations, for example:  `/config \\server\share\Skype15\Skype.WW\Config.xml`</span></span> <br/> |
|<span data-ttu-id="62376-119">/modify Skype</span><span class="sxs-lookup"><span data-stu-id="62376-119">/modify Skype</span></span>  <br/> |<span data-ttu-id="62376-120">用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。</span><span class="sxs-lookup"><span data-stu-id="62376-120">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="62376-121">例如, 您可以使用/modify 选项添加或删除 Skype for Business 功能。</span><span class="sxs-lookup"><span data-stu-id="62376-121">For example, you can use the /modify option to add or remove Skype for Business features.</span></span>  <br/> |
|<span data-ttu-id="62376-122">/repair Skype</span><span class="sxs-lookup"><span data-stu-id="62376-122">/repair Skype</span></span>  <br/> |<span data-ttu-id="62376-123">从用户的计算机运行安装程序以修复 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="62376-123">Runs Setup from the user's computer to repair Skype for Business.</span></span>  <br/> |
|<span data-ttu-id="62376-124">/uninstall Skype</span><span class="sxs-lookup"><span data-stu-id="62376-124">/uninstall Skype</span></span>  <br/> |<span data-ttu-id="62376-125">运行安装程序以从用户的计算机中删除 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="62376-125">Runs Setup to remove Skype for Business from the user's computer.</span></span>  <br/> |
   


