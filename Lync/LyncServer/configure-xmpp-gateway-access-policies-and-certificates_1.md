---
title: 配置 XMPP 网关访问策略和证书
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e8461d8f784df9f945f47ab9fcee66a889caf99
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>配置 XMPP 网关访问策略和证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-15_

XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。XMPP 配置允许 Lync 用户通过以下方式访问 XMPP 域用户：

  - IM 和状态 – 仅限于面对面

  - Lync 客户端中 XMPP 联盟联系人的创建

当您将策略配置为支持可扩展消息传递和状态协议 (XMPP) 联盟伙伴时，这些策略适用于 XMPP 联盟域的用户，但不适用于会话初始协议 (SIP) 即时消息 (IM) 服务提供者（例如，Windows Live）或 SIP 联盟域的用户。您可以针对要允许您的用户添加联系人并与之进行通信的每个 XMPP 联盟域配置 XMPP 联盟伙伴。在制定好这些策略之后，您需要配置 XMPP 网关证书。

<div>


> [!NOTE]  
> 若要开始 XMPP 网关迁移，您需要部署 Lync Server 2013 XMPP 网关，并配置访问策略以为用户启用 Lync Server 2013 XMPP 网关。 在执行这些步骤之前，必须将所有用户移动到 Lync Server 2013 部署。 有关详细信息，请参阅<A href="configure-xmpp-gateway-on-lync-server-2013_1.md">在 Lync Server 2013 上配置 XMPP 网关</A>。



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>配置外部访问策略以启用 Lync Server 2013 XMPP 网关的用户

1.  打开“Lync Server 控制面板”。

2.  在左侧导航栏中，单击“联盟和外部访问”****，然后单击“外部访问策略”****。

3.  单击“新建”****，然后单击“用户策略”****。

4.  输入外部访问用户策略的名称。

5.  提供外部访问用户策略的说明。

6.  选中“启用与联盟用户的通信”****。

7.  选中“启用与 XMPP 联盟用户的通信”****。

8.  单击“提交”**** 保存对站点或用户策略的更改。

</div>

</div>

<span> </span>

</div>

</div>

</div>

