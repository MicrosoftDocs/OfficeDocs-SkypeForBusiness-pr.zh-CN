---
title: 'Lync Server 2013: 自定义客户端安装'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd099f5d57174eb02733abd70bb99a91679a1328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830748"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="ea8c9-102">在 Lync Server 2013 中自定义客户端安装</span><span class="sxs-lookup"><span data-stu-id="ea8c9-102">Customizing client installation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea8c9-103">_**主题上次修改时间:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="ea8c9-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="ea8c9-104">企业管理员可以使用本部分中讨论的方法自定义基于 Office 2013 的基于 Windows 安装程序 (.msi) 安装。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="ea8c9-105">由于没有单个工具提供所有自定义选项, 因此你可能会在 Lync 2013 部署中结合使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="ea8c9-106">至少, 你可以使用以下部分中所述的工具:</span><span class="sxs-lookup"><span data-stu-id="ea8c9-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="ea8c9-107">[使用 Lync Server 2013 中的 Office 自定义工具 (OCT)](lync-server-2013-using-the-office-customization-tool-oct.md)自定义 lync 和其他 Office 程序的设置选项和功能。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="ea8c9-108">[使用 config.xml 在 Lync Server 2013 中执行安装任务](lync-server-2013-using-config-xml-to-perform-installation-tasks.md), 以指定网络安装点的路径并执行静默安装。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="ea8c9-109">[使用 Lync Server 2013 中的设置命令行选项](lync-server-2013-using-setup-command-line-options.md)指定要在安装期间使用的 config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="ea8c9-110">使用组策略对象编辑器 MMC 管理单元在[Lync Server 2013 中配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="ea8c9-111">在部署 Office 产品套件时，可能存在要配置的其他选项。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-111">There will probably be other options you’ll want to configure as you deploy the Office suite of products.</span></span> <span data-ttu-id="ea8c9-112">本部分中的主题概括介绍了这些自定义工具并讨论了特定于 Lync 的注意事项。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-112">The topics in this section give an overview of these customization tools and discuss Lync-specific considerations.</span></span> <span data-ttu-id="ea8c9-113">包含的是指向每个工具的详细 Office 帮助的链接。</span><span class="sxs-lookup"><span data-stu-id="ea8c9-113">Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

