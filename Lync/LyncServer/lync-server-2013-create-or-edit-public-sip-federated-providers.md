---
title: Lync Server 2013：创建或编辑公共 SIP 联合提供程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit public SIP federated providers
ms:assetid: 5321598c-1ab1-40e3-b739-4b2e6d0a3a3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398349(v=OCS.15)
ms:contentKeyID: 48184167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8a8da9937e31f0544dd93b1994745dc3a9eb10b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-public-sip-federated-providers-in-lync-server-2013"></a>在 Lync Server 2013 中创建或编辑公共 SIP 联合提供程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

公共即时消息（IM）连接使组织中的用户能够使用 IM 与公共 IM 服务提供商提供的 IM 服务的用户通信，包括 Windows Live Messenger、Yahoo\!和 AOL。

Lync Server 2013 具有适用于北美在线、Windows Live 和 Yahoo 的公共提供程序配置\! 即时消息的公共提供程序配置。 每个公共提供程序均使用提供程序的边缘服务器完全限定域名和默认验证级别“仅允许用户与其联系人列表中使用此提供程序的人员进行通信”**** 进行配置。

作为默认设置，将不启用任何公共提供程序。 您应先完成许可协议和设置工作，然后再启用公共提供程序。 您可以先启用提供程序，然后再完成许可和设置工作。 在完成首要工作之前，用户将无法与这些提供程序的联系人进行通信。 有关授权和预配公共提供商的详细信息，请参阅[在 Lync Server 2013 中配置控制公用用户访问的策略](lync-server-2013-configure-policies-to-control-public-user-access.md)。

使用以下过程可创建或编辑公共提供程序：

<div>

## <a name="to-create-or-edit-public-providers"></a>创建或编辑公共提供程序

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“联盟和外部访问”****，然后单击“SIP 联盟提供程序”****。

4.  如果您需要创建新的公共提供程序，请单击“新建”****，然后单击“公共提供程序”****。

5.  如果您需要编辑公共提供程序列表中的条目，请选择一个公共提供程序，单击“编辑”****，然后单击“显示详细信息”****。

6.  在“编辑 SIP 联盟提供程序”**** 页上，可以键入或编辑以下设置：
    
      - **启用与此提供程序**   的通信选择此设置将启用与此提供商的用户的 IM。
    
      - **提供程序名称：**   必需属性，键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。
    
      - **访问边缘服务（FQDN）：**   "必需" 属性，键入要配置的提供程序的访问边缘服务的完全限定域名。 此信息作为默认项目提供，仅当公用提供程序对公共提供商的访问边缘服务的 FQDN 进行更改时，才应更改此信息。
    
      - **默认验证级别：**   默认设置是，**允许用户与其 "联系人" 列表中使用此提供程序的人员进行通信**，将通信限制为您已接受且在联系人列表中的联系人。
        
        选择“允许用户与使用此提供程序的每个人通信”**** 将去除您必须接收和接受联系人邀请的限制。此设置不会对可从公共提供程序网络与您联系的人员进行限制。

7.  配置完这些设置后，请单击“提交”**** 以进行保存，或单击“取消”**** 以放弃更改。

</div>

<div>

## <a name="see-also"></a>另请参阅


[配置策略以控制 Lync Server 2013 中的公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

