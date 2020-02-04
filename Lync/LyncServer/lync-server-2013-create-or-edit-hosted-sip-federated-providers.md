---
title: Lync Server 2013：创建或编辑托管的 SIP 联盟提供程序
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
ms.openlocfilehash: d6c97255ce1dc9fce00d9eca6f358f4c68e1ff8a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-hosted-sip-federated-providers-lync-server-2013"></a>在 Lync Server 2013 中创建或编辑托管的 SIP 联盟提供程序

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-19_

托管提供商即时消息（IM）连接使组织中的用户能够使用 IM 与托管提供商（包括 Microsoft Office 365 和 Lync Online）提供的 IM 服务的用户进行通信。

每个托管提供程序均使用提供程序的边缘服务器完全限定的域名进行配置，默认验证级别**允许用户仅与其 "联系人" 列表中使用此提供程序的人员进行通信**。

使用以下过程创建或编辑托管提供程序：

<div>

## <a name="to-create-or-edit-hosted-providers"></a>创建或编辑托管提供商

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**联盟和外部访问**"，然后单击 " **SIP 联合提供商**"。

4.  如果需要创建新的托管提供商，请单击 "**新建**"，然后单击 "**托管提供商**"。

5.  如果需要从托管提供商列表中编辑条目，请选择托管提供商，单击 "**编辑**"，然后单击 "**显示详细信息**"。

6.  在 "**编辑 SIP 联合提供商**" 页面上，您可以键入或编辑以下设置：
    
      - **启用与此提供商**   的通信选择此设置可启用与此提供商的用户的通信。
    
      - **提供程序名称：**   "必需" 属性键入提供程序的名称，因为它将反映在 SIP 联合提供程序的列表中。
    
      - **Access edge 服务（FQDN）：**   一个必需的属性，键入你要配置的托管提供程序的访问边缘服务的完全限定的域名。 此信息应由托管提供程序提供，并且仅当托管提供程序对托管提供程序的访问边缘服务的 FQDN 进行更改时，才应更改此信息。
    
      - **默认验证级别：**   默认设置，**允许用户与使用此提供商的联系人列表中的人员进行通信**，将对您已接受的联系人和您的联系人列表中的联系人进行通信。
        
        选择 "**允许用户通过此提供商与所有人通信**"，将删除您必须收到并接受的联系人邀请的限制。 此设置不限制可以通过托管提供商的网络与您联系的人员。

7.  配置设置完成后，单击 "**提交**" 以保存，或单击 "**取消**" 放弃更改。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置策略以控制公共用户访问](lync-server-2013-configure-policies-to-control-public-user-access.md)  
[在 Lync Server 2013 中启用或禁用联盟和公共 IM 连接](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

