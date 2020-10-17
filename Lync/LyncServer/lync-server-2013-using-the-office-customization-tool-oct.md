---
title: 'Lync Server 2013：使用 Office 自定义工具 (OCT) '
description: Lync Server 2013：使用 Office 自定义工具 (OCT) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 602502ba4579ed6c640eee909d4c6b056ce247d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547328"
---
# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a><span data-ttu-id="fd0ac-103">在 Lync Server 2013 中使用 Office 自定义工具 (OCT) </span><span class="sxs-lookup"><span data-stu-id="fd0ac-103">Using the Office Customization Tool (OCT) in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd0ac-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="fd0ac-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="fd0ac-105">Office 自定义工具 (OCT) 是安装程序的一部分，也是完成许多自定义操作的推荐工具。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-105">The Office Customization Tool (OCT) is part of the Setup program and is the recommended tool for many customizations.</span></span> <span data-ttu-id="fd0ac-106">使用 OCT 可以自定义 Office 并将您的自定义设置保存在安装程序自定义 .msp 文件中。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-106">By using the OCT, you customize Office and save your customizations in a Setup customization .msp file.</span></span> <span data-ttu-id="fd0ac-107">可将该文件放在网络安装点上的 Updates 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-107">You place the file in the Updates folder on the network installation point.</span></span> <span data-ttu-id="fd0ac-108">在安装 Office 时，安装程序会在 Updates 文件夹中查找安装程序自定义文件，并应用自定义设置。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-108">When you install Office, Setup looks for a Setup customization file in the Updates folder and applies the customizations.</span></span> <span data-ttu-id="fd0ac-109">Updates 文件夹仅可用于在 Office 2013 的初始安装过程中部署软件更新。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-109">The Updates folder can be used only to deploy software updates during an initial installation of Office 2013.</span></span>

<span data-ttu-id="fd0ac-110">OCT 是安装程序的一部分且包括在产品的批量许可版本中。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-110">The OCT is part of setup and it is included in volume license versions of the product.</span></span> <span data-ttu-id="fd0ac-111">通过 `setup.exe /admin` 从包含 Office 2013 源文件的网络安装点的根目录中的命令行键入，可以运行 OCT。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-111">You run the OCT by typing `setup.exe /admin` at the command line from the root of the network installation point that contains the Office 2013 source files.</span></span> <span data-ttu-id="fd0ac-112">例如，可使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="fd0ac-112">For example, use the following:</span></span>

`\\server\share\Office15\setup.exe /admin`

<span data-ttu-id="fd0ac-113">管理员可使用 OCT 创建安装程序自定义 .msp 文件。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-113">Administrators use the OCT to create a setup customization .msp file.</span></span> <span data-ttu-id="fd0ac-114">就像在 Microsoft Office 2010 年10月中一样，管理员可以自定义以下方面：</span><span class="sxs-lookup"><span data-stu-id="fd0ac-114">As in the Microsoft Office 2010 OCT, administrators can customize the following areas:</span></span>

  - <span data-ttu-id="fd0ac-115">**设置** 用于指定客户端的默认安装位置和默认单位名称、其他网络安装源、产品密钥、最终用户许可协议、显示级别、Office 的早期版本、要删除的自定义程序、安装过程中要运行的自定义程序、安全设置和安装程序属性。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-115">**Setup** Used to specify default installation location on the client and default organization name, additional network installation sources, product key, end-user license agreement, display level, earlier versions of Office to remove, custom programs to run during installation, security settings, and Setup properties.</span></span>

  - <span data-ttu-id="fd0ac-116">**功能** 用于配置用户设置并自定义 Office 功能的安装方式。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-116">**Features** Used to configure user settings and to customize how Office features are installed.</span></span> <span data-ttu-id="fd0ac-117">管理员可以使用 OCT 为用户指定 Office 应用程序设置的初始默认值。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-117">Administrators can use the OCT to specify initial default values of Office application settings for users.</span></span> <span data-ttu-id="fd0ac-118">用户可以在安装后修改大多数设置。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-118">Users can modify most of the settings after the installation.</span></span>

  - <span data-ttu-id="fd0ac-119">**其他内容** 用于添加或删除文件、添加或删除注册表项，以及配置快捷方式。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-119">**Additional content** Used to add or remove files, add or remove registry entries, and configure shortcuts.</span></span>

  - <span data-ttu-id="fd0ac-120">**Outlook** 用于自定义用户的默认 Outlook 配置文件、指定 Exchange 设置、添加帐户、删除帐户和导出设置，以及指定发送和 \\ 接收组。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-120">**Outlook** Used to customize a user's default Outlook profile, specify Exchange settings, add accounts, remove accounts and export settings, and specify Send\\Receive groups.</span></span>

<span data-ttu-id="fd0ac-121">有关 OCT 的信息，请参阅 <https://go.microsoft.com/fwlink/p/?linkid=267516> 。</span><span class="sxs-lookup"><span data-stu-id="fd0ac-121">For information about the OCT, see <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

