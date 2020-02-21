---
title: Lync Server 2013：创建或修改公用区域电话联系人对象
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a common area phone Contact object
ms:assetid: eec33ad1-e4f2-49b2-91d6-d5a9d2e1714b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994083(v=OCS.15)
ms:contentKeyID: 51803995
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83d2eb58df1e5c83f23fdb1d31ba73b408d107a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180089"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-common-area-phone-contact-object-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改公用区域电话联系人对象

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-20_

若要为所有公用区域电话创建 Active Directory 域服务联系人对象，请使用**CsCommonAreaPhone** cmdlet。 此 cmdlet 可以创建新的 contact 对象以与公用区域电话一起使用，也可以将现有联系人对象与新的公用区域电话相关联。 若要修改与公用区域电话相关联的 contact 对象的属性，请使用**CsCommonAreaPhone** cmdlet。 **CsCommonAreaPhone**的可选参数使您能够更改项目，例如联系人的 Active Directory 显示名称或与电话关联的行统一资源标识符（URI），并启用和禁用与 Lync Server 一起使用的帐户。 有关所有可用修改的详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone)的 Parameters 部分。 有关**CsCommonAreaPhone**参数的详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone)。

您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行这两个 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>


<div>

## <a name="creating-a-common-area-phone-contact-object"></a>创建公用区域电话联系人对象

  - 若要创建新的公共区域电话联系人对象，请使用**CsCommonAreaPhone** cmdlet。 在创建 contact 对象时，至少必须提供以下信息：
    
      - **LineUri**：分配给公共区域电话的电话号码。 请注意，在指定电话号码时，您必须使用. 164 格式。
    
      - **RegistrarPool**：将承载 contact 对象的注册器池的完全限定域名（FQDN）。
    
      - **OU**：将在其中创建 contact 对象的 Active Directory 容器的可分辨名称。
    
    此外，我们还建议您提供一个 Active Directory 域服务的显示名称。 否则，您将需要使用 GUID 来指定电话标识。 例如：
    
        New-CsCommonAreaPhone -LineUri "tel:+12065551219" -RegistrarPool "atl-cs-001.litwareinc.com" -OU "OU=Phones,dc=litwareinc,dc=com" -DisplayName "Lobby"

</div>

<div>

## <a name="modifying-a-common-area-phone-contact-object"></a>修改公用区域电话联系人对象

  - 若要修改现有公用区域电话的属性，contact 对象使用**CsCommonAreaPhone** cmdlet。 例如，以下命令使用 DisplayName 大厅配置公用区域电话的 SIP 地址：
    
        Set-CsCommonAreaPhone -Identity "Lobby" -SipAddress "sip:lobby@litwareinc.com"

</div>

有关详细信息，请参阅[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/New-CsCommonAreaPhone) Cmdlet 和[CsCommonAreaPhone](https://docs.microsoft.com/powershell/module/skype/Set-CsCommonAreaPhone) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

