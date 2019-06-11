---
title: 'Lync Server 2013: 使用设置命令行选项'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845414"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="1bd3d-102">使用 Lync Server 2013 中的设置命令行选项</span><span class="sxs-lookup"><span data-stu-id="1bd3d-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bd3d-103">_**主题上次修改时间:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="1bd3d-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="1bd3d-p101">Setup.exe 命令行用于 Office 安装中的几个操作。您通常将使用 Office 自定义工具和 Config.xml 文件（而非安装程序命令行选项）来进行产品安装和功能自定义。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="1bd3d-106">Office Setup.exe 命令行识别下表中介绍的命令行选项。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="1bd3d-107">Office 安装程序命令行选项</span><span class="sxs-lookup"><span data-stu-id="1bd3d-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1bd3d-108">安装程序命令行选项</span><span class="sxs-lookup"><span data-stu-id="1bd3d-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="1bd3d-109">描述</span><span class="sxs-lookup"><span data-stu-id="1bd3d-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1bd3d-110">/admin</span><span class="sxs-lookup"><span data-stu-id="1bd3d-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="1bd3d-111">运行 Office 自定义工具以创建安装程序自定义文件（.msp 文件）。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bd3d-112">/adminfile [path]</span><span class="sxs-lookup"><span data-stu-id="1bd3d-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="1bd3d-p102">将指定的安装程序自定义文件应用于安装。您可以指定特定的自定义文件（.msp 文件）的路径或指定存储自定义文件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bd3d-115">/config [path]</span><span class="sxs-lookup"><span data-stu-id="1bd3d-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="1bd3d-116">指定安装程序在安装过程中使用的 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="1bd3d-117">使用/config 选项指定为 Lync 2013 安装自定义的 Config.xml 文件, 例如:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="1bd3d-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bd3d-118">/modify Lync</span><span class="sxs-lookup"><span data-stu-id="1bd3d-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="1bd3d-119">用于修改后的 Config.xml 文件可在维护模式下运行安装程序并对现有 Office 安装进行更改。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="1bd3d-120">例如, 你可以使用/modify 选项添加或删除 Lync 功能。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1bd3d-121">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="1bd3d-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="1bd3d-122">从用户计算机运行安装程序以修复 Lync。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1bd3d-123">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="1bd3d-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="1bd3d-124">运行安装程序以从用户的计算机中删除 Lync。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1bd3d-125">有关使用设置命令行选项的详细信息, 请参阅<http://go.microsoft.com/fwlink/p/?linkid=267515>。</span><span class="sxs-lookup"><span data-stu-id="1bd3d-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

