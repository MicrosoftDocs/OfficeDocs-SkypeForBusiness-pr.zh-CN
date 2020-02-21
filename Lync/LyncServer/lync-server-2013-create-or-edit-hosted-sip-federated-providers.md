---
title: Lync Server 2013：创建或编辑托管的 SIP 联合提供程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit hosted SIP federated providers
ms:assetid: 0dd6dcb6-a88d-46b8-9c96-b35967309bcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552445(v=OCS.15)
ms:contentKeyID: 48679556
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937dfe2a63f755a7366fbb1b82c5593c466ac544
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>创建或编辑托管的 SIP 联合提供商 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

托管提供程序即时消息（IM）连接使组织中的用户能够使用 IM 与托管提供商（包括 Microsoft Office 365 和 Lync Online）提供的 IM 服务的用户进行通信。

使用提供程序的边缘服务器的完全限定域名以及默认验证级别**仅允许用户与其联系人列表上使用此提供程序的人员进行通信**来配置每个托管提供程序。

使用以下过程创建或编辑托管提供程序：

<div>

## <a name="to-create-or-edit-hosted-providers"></a>创建或编辑托管提供程序

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“联盟和外部访问”****，然后单击“SIP 联盟提供程序”****。

4.  如果您需要创建一个新的托管提供程序，请单击“新建”****，然后单击“托管提供程序”****。

5.  如果您需要编辑托管提供程序列表上的一个条目，请选择一个托管提供程序，单击“编辑”****，然后单击“显示详细信息”****。

6.  在“编辑 SIP 联盟提供程序”**** 页面上，您可以键入或编辑下列设置：
    
      - **启用与此提供程序**   的通信选择此设置将启用与此提供商的用户的通信。
    
      - **提供程序名称：**   必需属性，键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。
    
      - **访问边缘服务（FQDN）：**   "必需" 属性，键入要配置的托管提供程序的访问边缘服务的完全限定域名。 此信息应由托管提供程序提供，并且仅当托管提供程序对托管提供程序的访问边缘服务的 FQDN 进行更改时，才应更改此信息。
    
      - **默认验证级别：**   默认设置是，**允许用户与其 "联系人" 列表中使用此提供程序的人员进行通信**，将通信限制为您已接受且在联系人列表中的联系人。
        
        选择“允许用户与所有使用此提供程序的人员通信”**** 可取消您必须收到并接受联系人邀请的限制。此设置不限制可从托管提供程序的网络与您联系的人。

7.  当您配置完设置后，单击“提交”**** 进行保存，或单击“取消”**** 放弃所做的更改。

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

