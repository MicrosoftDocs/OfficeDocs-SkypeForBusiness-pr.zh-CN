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
ms.openlocfilehash: c63e9952abab192e7f8f4a71e97a660d2798d3b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-contact-object-management-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange 联系人对象管理

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-25_

您需要为您的跨平台部署中的每个自动助理号码和订户访问号码配置联系人对象。

为了与托管 Exchange UM 集成，ocsumutil 无法用于管理联系人对象，因为它依赖于 Active Directory Exchange UM 设置。 在跨平台部署中，Lync Server 2013 和托管 Exchange UM 安装在单独的林中，它们之间不受信任。 出于安全原因，Lync Server 2013 管理员无法直接访问 Exchange UM Active Directory 设置。 因此，Lync Server 2013 提供了一种不同的模型来管理共享 SIP 地址空间中的联系人对象，该*共享 SIP 地址空间*可同时用于 Lync Server 2013 和托管 Exchange UM 服务。

<div>

## <a name="hosted-contact-object-workflow"></a>托管联系人对象工作流

以下是使用托管的 Exchange 租户管理员管理联系人对象的常规步骤：

1.  Exchange 管理员请求 Exchange UM 订阅者访问和自动助理联系人对象的电话号码。

2.  Lync Server 2013 管理员为每个电话号码创建一个 Contact 对象，并为每个 Contact 对象分配一个托管语音邮件策略。

3.  Lync Server 2013 管理员向 Exchange 管理员提供电话号码。

4.  Exchange 管理员将电话号码分配给合适的 Exchange UM 拨号计划，以便自动助理和订阅者访问。

<div>


> [!NOTE]  
> 无需在联系人对象上配置任何 Lync Server 2013 拨号计划设置，就像本地部署一样。



</div>

</div>

<div>

## <a name="configuring-hosted-contact-objects"></a>配置托管联系人对象

<div>


> [!NOTE]  
> 在 Lync Server 2013 中可以为托管 Exchange UM 启用联系人对象之前，必须部署适用于它们的托管语音邮件策略。 策略可以是全局、网站级或每用户范围，只要它适用于要启用的联系人对象。 有关详细信息，请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。



</div>

若要在跨平台部署中配置托管的自动助理和订阅者访问联系人对象，必须使用以下 cmdlet：

  - **New-CsExUmContact**为托管 UM 创建新的联系人对象。

  - **Set-CsExUmContact**修改托管 Exchange UM 的现有联系人对象。

以下示例创建自动助理联系人对象：

    New-CsExUmContact -SipAddress sip:exumaa1@fabrikam.com -RegistrarPool RedmondPool.litwareinc.com -OU "OU=ExUmContacts,DC=litwareinc,DC=com" -DisplayNumber 2065559876 -AutoAttendant $True

此示例使用 SIP 地址 sip:exumaa1@fabrikam.com 创建新的 Exchange UM 联系人对象。 Lync Server 2013 注册机构服务正在运行的池的名称为 RedmondPool.litwareinc.com。 将存储此信息的 Active Directory 组织单位为 OU = ExUmContacts、DC = litwareinc、DC = com。 联系人对象的电话号码是2065554567。 "可选-自动助理 $True" 参数指定此对象是自动助理联系人对象。 将-自动助理参数设置为 False （默认值）指定订阅者访问联系人对象。

有关新的 CsExUmContact 和 CsExUmContact cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档。

</div>

</div>

<span> </span>

</div>

</div>

</div>

