---
title: Lync Server 2013：自定义客户端安装
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing client installation
ms:assetid: 5c1a85f1-5ebb-48fb-acb7-3bf46decbf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204934(v=OCS.15)
ms:contentKeyID: 48184254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 755a53b6afc089093f5efbfd2a90699e12e66b8f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516689"
---
# <a name="customizing-client-installation-in-lync-server-2013"></a><span data-ttu-id="2743a-102">在 Lync Server 2013 中自定义客户端安装</span><span class="sxs-lookup"><span data-stu-id="2743a-102">Customizing client installation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2743a-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="2743a-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="2743a-104">企业管理员可以使用本节中讨论的方法来自定义基于 Office 2013 Windows Installer 的 ( .msi) 安装。</span><span class="sxs-lookup"><span data-stu-id="2743a-104">Enterprise administrators can customize the Office 2013 Windows Installer-based (.msi) installation by using the methods discussed in this section.</span></span> <span data-ttu-id="2743a-105">由于没有一个工具提供所有自定义选项，因此您可能会在 Lync 2013 部署中结合使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="2743a-105">Because no single tool provides all customization options, you’ll likely use a combination of these methods in your Lync 2013 deployment.</span></span> <span data-ttu-id="2743a-106">您至少可以使用以下章节中所述的工具：</span><span class="sxs-lookup"><span data-stu-id="2743a-106">At a minimum, you might use the tools described in the following sections:</span></span>

  - <span data-ttu-id="2743a-107">[在 Lync Server 2013 中使用 Office 自定义工具 (OCT) ](lync-server-2013-using-the-office-customization-tool-oct.md) 自定义 lync 和其他 Office 程序的安装选项和功能。</span><span class="sxs-lookup"><span data-stu-id="2743a-107">[Using the Office Customization Tool (OCT) in Lync Server 2013](lync-server-2013-using-the-office-customization-tool-oct.md) to customize setup options and features for Lync and other Office programs.</span></span>

  - <span data-ttu-id="2743a-108">[使用 Config.xml 在 Lync Server 2013 中执行安装任务](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) ，以指定网络安装点的路径并执行无提示安装。</span><span class="sxs-lookup"><span data-stu-id="2743a-108">[Using Config.xml to perform installation tasks in Lync Server 2013](lync-server-2013-using-config-xml-to-perform-installation-tasks.md) to specify the path of the network installation point and perform silent installation.</span></span>

  - <span data-ttu-id="2743a-109">[使用 Lync Server 2013 中的安装程序命令行选项](lync-server-2013-using-setup-command-line-options.md) 指定要在安装过程中使用的 Config.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="2743a-109">[Using Setup command-line options in Lync Server 2013](lync-server-2013-using-setup-command-line-options.md) to specify the Config.xml file to use during installation.</span></span>

  - <span data-ttu-id="2743a-110">使用组策略对象编辑器 MMC 管理单元在[Lync Server 2013 中配置客户端引导策略](lync-server-2013-configuring-client-bootstrapping-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2743a-110">[Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) by using the Group Policy Object Editor MMC snap-in.</span></span>

<span data-ttu-id="2743a-p102">在部署 Office 产品套件时，可能存在要配置的其他选项。本节中的主题概述了这些自定义工具并讨论了特定于 Lync 的注意事项。包含的是指向每个工具的详细 Office 帮助的链接。</span><span class="sxs-lookup"><span data-stu-id="2743a-p102">There will probably be other options you’ll want to configure as you deploy the Office suite of products. The topics in this section give an overview of these customization tools and discuss Lync-specific considerations. Included are links to detailed Office help for each tool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

