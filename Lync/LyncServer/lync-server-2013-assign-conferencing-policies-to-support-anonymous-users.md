---
title: Lync Server 2013：分配会议策略以支持匿名用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign conferencing policies to support anonymous users
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab1c3da15bd72bb03233ca05d86e355eebbb233
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-conferencing-policies-to-support-anonymous-users-in-lync-server-2013"></a>在 Lync Server 2013 中分配会议策略以支持匿名用户

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

默认情况下，将阻止所有用户邀请匿名用户参与会议。 你可以通过配置会议策略来控制哪些人可以邀请匿名用户，并将该会议策略应用于特定用户。 有关如何配置会议策略以支持匿名用户的详细信息，请参阅[在 Lync server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)以及[管理对 lync server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。

使用此部分中的过程将已创建的会议策略应用于一个或多个用户或用户组。

<div>


> [!NOTE]  
> 除了配置和应用策略以允许用户邀请匿名用户之外，还必须为你的组织启用匿名用户支持。 有关详细信息，请参阅<A href="lync-server-2013-configure-policies-to-control-public-user-access.md">在 Lync Server 2013 中配置控制公共用户访问的策略</A>。



</div>

<div>

## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>配置匿名参与会议的用户策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**会议**"，然后执行下列操作之一：
    
    1.  若要创建新的用户策略，请单击 "**新建**"，然后单击 "**用户策略**"。 在 "**名称**" 字段中创建一个唯一名称，用于指示用户策略所涉及的内容（例如， **EnableAnonymous**适用于启用与匿名用户的通信的用户策略）。
    
    2.  若要配置现有用户策略，请单击表中列出的相应策略，单击 "**编辑**"，然后单击 "**显示详细信息**"。

4.  在 "**会议策略**" 对话框中，选中 "**允许参与者邀请匿名用户**" 复选框。

5.  单击“**提交**”。

6.  在左侧导航栏中，单击 "**用户**"，搜索要配置的用户帐户。

7.  在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。

8.  在 "在**会议策略**中**编辑 Lync 服务器用户**" 下，选择包含要应用于此用户的匿名用户访问配置的用户策略。
    
    <div>
    

    > [!NOTE]  
    > " <STRONG> &lt;自动&gt; </STRONG>设置" 应用默认服务器安装设置，并由服务器自动应用。

    
    </div>

若要使用户能够邀请匿名用户加入会议，还必须在组织中启用匿名用户支持。 有关详细信息，请参阅在部署文档或操作文档中，[配置控制在 Lync Server 2013 中控制公共用户访问的策略](lync-server-2013-configure-policies-to-control-public-user-access.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

