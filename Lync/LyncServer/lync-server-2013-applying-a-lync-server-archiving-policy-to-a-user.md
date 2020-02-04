---
title: Lync Server 2013：将 Lync Server 存档策略应用于用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7b82fd0d42aa6a34533f6b5005e15edd2aa5cbd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a>将 Lync 服务器存档策略应用于 Lync Server 2013 中的用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-10_

创建 Lync 服务器用户策略后，必须将其应用于在 Lync Server 2013 上托管的特定用户或用户组，然后它才能生效。 有关为特定用户创建用户策略的详细信息，请参阅部署文档中的[在 Lync Server 2013 中创建和配置用于存档的用户策略](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)。

有关存档策略的工作原理的详细信息（包括全局、网站和用户策略的层次结构），请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]  
> 为了配置和使用存档，您必须首先部署存档。 有关详细信息，请参阅部署文档中的<A href="lync-server-2013-deploying-archiving.md">Lync Server 2013</A>中的 "部署存档"。<BR>如果为你的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管于 Exchange 2013 的用户启用存档，并将其邮箱置于原地保留。 有关详细信息，请参阅在部署文档中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时在 Lync Server 2013 中设置存档策略</A>。<BR>在启用存档之前，应在存档配置中指定所有适当的选项。 有关详细信息，请参阅部署文档中<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中的 "配置存档选项</A>"。



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a>将 Lync 服务器存档策略应用于用户

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。 有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

5.  在 "在**存档策略**中**编辑 Lync 服务器用户**" 下，选择要应用的存档用户策略。
    
    <div>
    

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置。 服务器将自动应用这些设置。

    
    </div>

6.  单击“**提交**”。

</div>

</div>

<span> </span>

</div>

</div>

</div>

