---
title: Lync Server 2013：安装 Lync Server server 组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9237ed0b60e14383f69ff1e7ef0b0927afe49c98
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498699"
---
# <a name="install-server-components-for-lync-server-2013"></a>安装 Lync Server 2013 的服务器组件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-05-05_

在执行以下步骤之前，请确保您使用具有本地管理员的域用户帐户和 Active Directory 中的 RTCUniversalReadOnlyAdmins 组的成员登录到服务器。

Lync Server 部署向导用于为每个 Lync server 角色安装所需的组件并激活服务器。 本文将引导您完成在 Lync 基础结构中部署 Standard Edition server 或前端服务器的步骤。

<div>

## <a name="to-install-lync-server-components"></a>安装 Lync Server 组件

1.  如果未运行 Lync Server 部署向导，请在要安装 Lync 的服务器上启动它。

2.  单击 " **安装或更新 Lync Server 系统**"。

3.  在部署向导中，确认 " **步骤1：安装本地配置存储区** " 带有绿色的复选标记，这表示此服务器已成功安装存储的本地副本。 如果未选中此项，则需要在服务器上安装本地配置存储。 按照在 [Lync Server 2013 中安装本地配置存储中](lync-server-2013-install-the-local-configuration-store.md) 的步骤操作，然后回到此处。

4.  当您准备好在服务器上安装 Lync Server 2013 组件时，请单击 "**步骤2：安装或删除 Lync Server 组件**" 旁边的 "**运行**"。

5.  在 "安装 **Lync Server 组件** " 页上，单击 " **下一步** " 设置在已发布拓扑中定义的组件。

6.  " **正在执行命令** " 页将在设置发生时显示命令和安装信息的摘要。 完成后，可以使用列表选择要查看的日志，然后单击 " **查看日志**"。

7.  在安装了 Lync Server 2013 组件并根据需要查看日志后，请单击 " **完成** " 以完成安装中的此步骤。
    
    <div>
    

    > [!NOTE]  
    > 如果系统提示您重新启动服务器 (如果需要安装 Windows 桌面体验) ，则可能会发生这种情况。 当计算机重新启动并运行时，您需要再次执行这些步骤，从上面列出的第三步开始 (基本上在 "部署向导" 中再次运行步骤 2) 。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

