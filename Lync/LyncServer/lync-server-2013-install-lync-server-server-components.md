---
title: Lync Server 2013：安装 Lync Server 服务器组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 895047715bfa632970adbabb20311d8c68182499
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>安装适用于 Lync Server 2013 的服务器组件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-05-05_

在执行以下步骤之前, 请确保你使用既是本地管理员又是 Active Directory 中 RTCUniversalReadOnlyAdmins 组成员的域用户帐户登录到服务器。

Lync Server 部署向导用于为每个 Lync 服务器角色安装所需的组件和激活服务器。 本文将引导你完成在 Lync 基础结构中部署标准版服务器或前端服务器的步骤。

<div>

## <a name="to-install-lync-server-components"></a>安装 Lync Server 组件

1.  如果 Lync Server 部署向导未在运行, 请在要安装 Lync 的服务器上启动它。

2.  单击 "**安装或更新 Lync Server 系统**"。

3.  在部署向导中, 确认**步骤 1: 安装本地配置存储**带有绿色复选标记, 这意味着该服务器已成功安装应用商店的本地副本。 如果未选中, 则需要在服务器上安装本地配置存储。 按照在[Lync Server 2013 中安装本地配置存储中](lync-server-2013-install-the-local-configuration-store.md)的步骤操作, 然后回到此处。

4.  准备好在服务器上安装 Lync Server 2013 组件时, 请单击**步骤 2: 设置或删除 Lync Server 组件**旁边的 "**运行**"。

5.  在 "**设置 Lync Server 组件**" 页面上, 单击 "**下一步**" 以设置在已发布拓扑中定义的组件。

6.  "**执行命令**" 页面将在设置发生时显示命令和安装信息的摘要。 完成后，可以使用列表选择要查看的日志，然后单击“**查看日志**”。

7.  在 Lync Server 2013 组件设置完成后, 如果需要, 您已查看日志, 请单击 "**完成**" 以在安装中完成此步骤。
    
    <div>
    

    > [!NOTE]  
    > 如果系统提示您重新启动服务器 (如果需要安装 Windows 桌面体验, 可能会发生这种情况), 因此一定要这样做。 当计算机恢复正常运行时, 你需要再次执行这些步骤, 从上面列出的步骤3开始 (基本上在 "部署向导" 中再次运行步骤 2)。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

