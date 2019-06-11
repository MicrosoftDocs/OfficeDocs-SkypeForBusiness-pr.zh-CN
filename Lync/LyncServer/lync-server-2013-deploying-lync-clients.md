---
title: 'Lync Server 2013: 部署 Lync 客户端'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync clients
ms:assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204827(v=OCS.15)
ms:contentKeyID: 48183925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbbecc50ed88ac9b3237277ba1c991f8c1fcba2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-clients-in-lync-server-2013"></a>在 Lync Server 2013 中部署 Lync 客户端

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-03_

Lync 2013 引入了一种不同的客户端部署方法。 在以前版本的出发期间, Lync 2013 不再拥有自己的安装程序。 而是在 Office 2013 安装程序中随附 Lync。 若要将 Lync 2013 部署到你的用户, 你可以使用 Office 2013 安装方法和自定义工具。

  - **Office 2013 Windows installer**是基于 Windows 安装程序包的安装程序包, 它包含多个 MSI 文件。 一个与语言无关的核心 MSI 包与一个或多个特定语言的包组合在一起构成了完整产品。 在用户计算机上安装 Office 的过程中以及安装之后，安装程序将组合各个包并执行自定义和维护任务。 本部分中的主题介绍了如何使用和自定义 Office 2013 的 Windows 安装程序来部署 Lync 2013。

  - **Office 2013 即点**即用是从 Microsoft office 365 门户将 Office 安装程序文件流式处理到用户的安装程序。 通过使用针对即点即用的 Office 部署工具，管理员可以自定义安装。 由于 Office 2013 的即点即用主要用于 Microsoft Office 365 环境, 本部分中不详细介绍此安装方法。 有关如何使用和自定义即点即用安装的详细信息, 请参阅 Office 2013 资源工具包文档。 管理员还可以将 Office 2013 的即点即用程序和语言源文件下载到本地位置, 这在你需要最大程度地减少网络需求或阻止用户从 Internet 安装软件时很有用, 因为公司安全要求。

本部分中的主题重点介绍如何使用基于 Office 2013 的基于 MSI 的安装程序部署客户端。 您的主参考应是 Office 2013 资源工具包文档, 其中详细介绍了如何准备基础结构、自定义安装和部署 Office 2013。 但是, 你应将 Office 文档与本部分中的主题结合使用, 以指出特定于 Lync 2013 的部署注意事项。

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>Lync 2013 的联机会议加载项 (支持来自 Outlook 消息和协作客户端的会议管理) 将自动与 Lync 2013 一起安装。</P>
> <LI>
> <P>Office 2013 安装程序不会卸载以前版本的 Lync 或 Office Communicator。 Lync 2013 客户端与其他 Lync 或 Office Communicator 客户端并行安装</P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中自定义客户端安装](lync-server-2013-customizing-client-installation.md)

  - [在 Lync Server 2013 中自定义 Lync 行为和用户界面](lync-server-2013-customizing-lync-behavior-and-the-user-interface.md)

  - [在 Lync Server 2013 中自定义联机会议加载项](lync-server-2013-customizing-the-online-meeting-add-in.md)

  - [在 Lync Server 2013 中配置与会页面](lync-server-2013-configuring-the-meeting-join-page.md)

  - [在 Lync Server 2013 中配置支持的客户端版本](lync-server-2013-configuring-supported-client-versions.md)

  - [在 Lync Server 2013 中配置增强的联机状态隐私模式](lync-server-2013-configuring-enhanced-presence-privacy-mode.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

