---
title: Lync Server 2013：托管 Exchange 联系人对象管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange Contact object management
ms:assetid: eead9d76-bc4f-4c1c-9779-683cb7a88410
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412978(v=OCS.15)
ms:contentKeyID: 48185748
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ede940e1126660aaae89fe6552f050632f841b8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange 联系人对象管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-25_

您需要为交叉部署中的每个自动助理号码和订阅者访问号码配置联系人对象。

为了与托管 Exchange UM 集成，ocsumutil.exe 不能用于管理联系人对象，因为它取决于 Active Directory Exchange UM 设置。 在跨界部署中，Lync Server 2013 和托管 Exchange UM 安装在单独的林中，它们之间没有任何信任关系。 出于安全考虑，Lync Server 2013 管理员不能直接访问 Exchange UM Active Directory 设置。 因此，Lync Server 2013 提供了一个不同的模型，用于在 Lync Server 2013 和托管 Exchange UM 服务可访问的*共享 SIP 地址空间*中管理联系人对象。

<div>

## <a name="hosted-contact-object-workflow"></a>托管的联系人对象工作流

以下是托管的 Exchange 租户管理员用于管理联系人对象的常规步骤：

1.  Exchange 管理员为 Exchange UM 订阅者访问和自动助理联系人对象请求电话号码。

2.  Lync Server 2013 管理员为每个电话号码创建一个 Contact 对象，并向每个 Contact 对象分配一个托管语音邮件策略。

3.  Lync Server 2013 管理员向 Exchange 管理员提供电话号码。

4.  Exchange 管理员将电话号码分配给自动助理和订阅者访问的相应 Exchange UM 拨号计划。

<div>


> [!NOTE]  
> 无论在本地部署中，都不需要在联系人对象上配置任何 Lync Server 2013 拨号计划设置。



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>配置托管的联系人对象

<div>


> [!NOTE]  
> 在 Lync Server 2013 中可以为托管 Exchange UM 启用联系人对象之前，必须部署适用于这些对象的托管语音邮件策略。 策略可以是全局策略、站点级别策略或每用户策略，只要策略适用于要启用的联系人对象。 有关详细信息，请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

要在交叉部署中配置托管的自动助理和订阅者访问联系人对象，必须使用以下 cmdlet：

  - **New-CsExUmContact** 为托管的 UM 创建新的联系人对象。

  - **Set-CsExUmContact** 为托管 Exchange UM 修改现有的联系人对象。

以下示例创建一个自动助理联系人对象：

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

此示例创建一个 SIP 地址为 sip:exumaa1@fabrikam.com 的新 Exchange UM 联系人对象。 运行 Lync Server 2013 注册器服务的池的名称为 RedmondPool.litwareinc.com。 将用于存储此信息的 Active Directory 组织单位为 OU=ExUmContacts,DC=litwareinc,DC=com。 联系人对象的电话号码为 2065554567。 可选参数 -AutoAttendant $True 指定此对象为自动助理联系人对象。 将 -AutoAttendant 参数设置为 False（默认值）可指定订阅者访问联系人对象。

有关 CsExUmContact 和 CsExUmContact cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。

</div>

</div>

<span> </span>

</div>

</div>

</div>

