---
title: Lync Server 2013：配置策略以控制远程用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e542f2a2d836cce507863347384135f97db445
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837346"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置策略以控制远程用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

配置一个或多个外部用户访问策略, 以控制远程用户是否可以与内部 Lync Server 用户进行协作。 若要控制远程用户访问, 可以在全局、网站和用户级别配置策略。 网站策略替代全局策略, 而用户策略替代网站和全局策略。 有关可以配置的策略类型的详细信息, 请参阅[管理 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在其他策略级别应用的设置。 Lync 服务器策略优先级为: 用户策略 (最受影响) 覆盖网站策略, 然后网站策略覆盖全局策略 (最不影响)。 这意味着，策略设置与策略所影响的对象距离越近，它对该对象的影响力越大。

<div>


> [!NOTE]  
> 你可以配置策略来控制远程用户访问, 即使你没有为你的组织启用远程用户访问。 但是, 仅当你的组织启用了远程用户访问时, 你配置的策略才有效。 有关启用远程用户访问的详细信息, 请参阅<A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</A>。 此外, 如果你指定用于控制远程用户访问的用户策略, 该策略将仅应用于为 Lync Server 启用且配置为使用该策略的用户。 有关从远程位置指定可登录 Lync Server 的用户的详细信息, 请参阅<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">在 Lync server 2013 中将外部用户访问策略分配给启用 lync 的用户</A>。



</div>

使用以下过程配置要用于控制远程用户访问的每个外部访问策略。

<div>


> [!NOTE]  
> 此过程介绍如何配置策略以启用与远程用户的通信, 但配置为支持远程用户访问的每个策略也可以配置联合用户访问和公共用户访问。 有关配置支持联盟用户的策略的详细信息, 请参阅<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联盟用户访问的策略</A>。 有关配置策略以支持公共用户的详细信息, 请参阅<A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公共 SIP 联合提供商</A>。



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>将外部访问策略配置为支持远程用户访问

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**外部用户访问**", 然后单击 "**外部访问策略**"。

4.  在 "**外部访问策略**" 页面上, 执行下列操作之一:
    
      - 若要将全局策略配置为支持远程用户访问, 请单击全局策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。
    
      - 若要创建新的网站策略, 请单击 "**新建**", 然后单击 "**网站策略**"。 在 "**选择网站**" 中, 从列表中单击相应的网站, 然后单击 **"确定"**。
    
      - 若要创建新的用户策略, 请单击 "**新建**", 然后单击 "**用户策略**"。 在 "**新的外部访问策略**" 中, 在 "**名称**" 字段中创建一个唯一名称, 用于指示用户策略所涉及的内容 (例如, **EnableRemoteUsers**为远程用户启用通信的用户策略)。
    
      - 若要更改现有策略, 请单击表中列出的相应策略, 单击 "**编辑**", 然后单击 "**显示详细信息**"。

5.  可选如果要添加或编辑说明, 请在 "**说明**" 中指定策略的信息。

6.  请执行下列操作之一：
    
      - 若要启用该策略的远程用户访问权限, 请选中 "**启用与远程用户的通信**" 复选框。
    
      - 若要禁用该策略的远程用户访问权限, 请清除 "**启用与远程用户的通信**" 复选框。

7.  单击“**提交**”。

若要启用远程用户访问, 还必须启用对组织中的远程用户访问的支持。 有关详细信息, 请参阅在部署文档或操作文档中[启用或禁用 Lync Server 2013 中的联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是用户策略, 你还必须将策略应用于你希望能够远程连接的用户。 有关详细信息, 请参阅在部署文档或操作文档中[将外部用户访问策略分配给 Lync Server 2013 中启用 Lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

