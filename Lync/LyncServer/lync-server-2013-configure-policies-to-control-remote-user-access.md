---
title: Lync Server 2013：配置策略以控制远程用户访问
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f1687a26e5bf464191b742d046bc28e8c8a329a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>在 Lync Server 2013 中配置策略以控制远程用户访问

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

您可以配置一个或多个外部用户访问策略以控制远程用户是否可以与内部 Lync Server 用户进行协作。 若要控制远程用户访问，可以在全局、站点和用户级别配置策略。 站点策略将覆盖全局策略，而用户策略将覆盖站点策略和全局策略。 有关您可以配置的策略类型的详细信息，请参阅[管理对 Lync Server 2013 的联盟和外部访问](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)。 在一个策略级别应用的 Lync Server 策略设置可以覆盖在另一个策略级别应用的设置。 Lync Server 策略优先级为：用户策略（最具影响力）替代网站策略，然后网站策略将覆盖全局策略（最不影响）。 这意味着，策略设置越接近策略所影响的对象，它对对象的影响越大。

<div>


> [!NOTE]  
> 即使没有为组织启用远程用户访问，也可以配置策略来控制远程用户访问。 但是，只有为组织启用远程用户访问后，配置的策略才会生效。 有关启用远程用户访问的详细信息，请参阅<A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接</A>。 此外，如果您指定了用于控制远程用户访问的用户策略，则该策略仅适用于启用了 Lync Server 并配置为使用该策略的用户。 有关指定可从远程位置登录 Lync Server 的用户的详细信息，请参阅<A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">在 Lync server 2013 中向启用 lync 的用户分配外部用户访问策略</A>。



</div>

按照以下过程配置要用于控制远程用户访问的每个外部访问策略。

<div>


> [!NOTE]  
> 此过程描述如何配置策略以便仅启用与远程用户的通信，但配置为支持远程用户访问的每个策略也可以配置联盟用户访问和公共用户访问。 有关配置策略以支持联合用户的详细信息，请参阅<A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">在 Lync Server 2013 中配置用于控制联合用户访问的策略</A>。 有关配置策略以支持公用用户的详细信息，请参阅<A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">在 Lync Server 2013 中创建或编辑公用 SIP 联合提供程序</A>。



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>配置外部访问策略以支持远程用户访问

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“外部用户访问”****，然后单击“外部访问策略”****。

4.  在“外部访问策略”**** 页上，执行下列操作之一：
    
      - 要将全局策略配置为支持远程用户访问，请单击该全局策略，再单击“编辑”****，然后单击“显示详细信息”****。
    
      - 要创建新的站点策略，请单击“新建”****，然后单击“站点策略”****。在“选择站点”**** 中，单击列表中相应的站点，然后单击“确定”****。
    
      - 要创建新的用户策略，请单击“新建”****，然后单击“用户策略”****。在“新建外部访问策略”**** 的“名称”**** 字段中，创建一个唯一的名称以指示用户策略的作用范围（例如，**EnableRemoteUsers** 代表启用远程用户通信的用户策略）。
    
      - 要更改现有的策略，请单击表中列出的相应策略，再单击“编辑”****，然后单击“显示详细信息”****。

5.  （可选）如果要添加或编辑说明，请在“说明”**** 中为策略指定相应的信息。

6.  执行下列操作之一：
    
      - 要为策略启用远程用户访问，请选中“启用与远程用户的通信”**** 复选框。
    
      - 要为策略禁用远程用户访问，请清除“启用与远程用户的通信”**** 复选框。

7.  单击“提交”****。

要启用远程用户访问，还必须在组织中启用对远程用户访问的支持。 有关详细信息，请参阅部署文档或操作文档中的[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)。

如果这是一个用户策略，则还必须将此策略应用于希望其可以进行远程连接的用户。 有关详细信息，请参阅部署文档或操作文档中的在[Lync Server 2013 中将外部用户访问策略分配给启用 lync 的用户](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

