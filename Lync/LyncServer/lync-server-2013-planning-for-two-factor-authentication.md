---
title: Lync Server 2013：规划双因素身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中规划双因素身份验证

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2015-04-06_

以下是配置 Microsoft Lync Server 2013 环境以支持双因素身份验证时的部署注意事项列表。

<div>

## <a name="client-support"></a>客户端支持

Lync Server 2013 的 Lync 2013 累积更新：7月2013桌面客户端和所有移动客户端当前支持双重身份验证。

</div>

<div>

## <a name="topology-requirements"></a>拓扑要求

强烈建议客户使用专用 Lync Server 2013 进行双因素身份验证，使用 Lync Server 2013 的累积更新：7月 2013 Edge、导演和用户池。 若要为 Lync 用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下内容：


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>配置类型</th>
<th>服务类型</th>
<th>服务器角色</th>
<th>要禁用的身份验证类型</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web 服务</p></td>
<td><p>Web 服务器</p></td>
<td><p>控制器</p></td>
<td><p>Kerberos、NTLM 和证书</p></td>
</tr>
<tr class="even">
<td><p>Web 服务</p></td>
<td><p>Web 服务器</p></td>
<td><p>前端</p></td>
<td><p>Kerberos、NTLM 和证书</p></td>
</tr>
<tr class="odd">
<td><p>代理</p></td>
<td><p>EdgeServer</p></td>
<td><p>Edge</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
<tr class="even">
<td><p>代理</p></td>
<td><p>注册器</p></td>
<td><p>前端</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
</tbody>
</table>


除非在服务级别禁用这些身份验证类型，否则在你的部署中启用了两个因素身份验证后，Lync 客户端的所有其他版本都将无法成功登录。

</div>

<div>

## <a name="lync-service-discovery"></a>Lync 服务发现

内部和/或外部客户端用于发现 Lync 服务的 DNS 记录应配置为解析为未启用双因素身份验证的 Lync 服务器。 通过此配置，没有为两个因素身份验证启用的 Lync Pool 中的用户输入 PIN 进行身份验证时，不需要使用适用于双因素身份验证的 Lync Pool 中的用户将其 PIN 输入到验证.

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 身份验证

已为 Microsoft Exchange 部署了双因素身份验证的客户可能会发现 Lync 客户端中的某些功能不可用。 这是当前设计的，因为 Lync 客户端不支持依赖于 Exchange 集成的功能的双重身份验证。

</div>

<div>

## <a name="lync-contacts"></a>Lync 联系人

配置为利用 "统一联系人存储" 功能的 Lync 用户将发现，使用双因素身份验证登录后，他们的联系人将不再可用。

你应该使用**CsUcsRollback** cmdlet 从 "统一联系人存储" 中删除现有用户联系人，并将其存储在 Lync Server 2013 中，然后再启用双重身份验证。

</div>

<div>

## <a name="skill-search"></a>技能搜索

在 Lync 环境中配置技能搜索功能的客户将发现，当启用 Lync 的双重身份验证时，此功能不起作用。 这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。

</div>

<div>

## <a name="lync-credentials"></a>Lync 凭据

有许多部署注意事项涉及保存的 Lync 凭据，这可能会影响配置为使用双因素身份验证的用户。

<div>

## <a name="deleting-saved-credentials"></a>删除保存的凭据

桌面客户端用户应使用 Lync 客户端中的 "**删除我的登录信息**" 选项，并从% localappdata\\% Microsoft\\Office\\15.0\\Lync 删除其 SIP 配置文件，然后再尝试使用双因素身份验证进行首次登录。

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 身份验证方法时，将自动使用用户的 Windows 凭据进行身份验证。 在支持 Kerberos 和/或 NTLM 进行身份验证的典型 Lync Server 2013 部署中，用户每次登录时都不应输入其凭据。

如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。

若要阻止额外的凭据提示，请在本地工作站上创建以下注册表项，或使用 Lync 管理模板应用到使用组策略的给定池的所有用户：

HKEY\_LOCAL\_MACHINE\\软件\\策略\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD： DisableNTCredentials

值：0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

当用户首次登录 Lync 时，系统会提示用户保存其密码。 如果选中，此选项允许用户的客户端证书存储在个人证书存储中，而用户的 Windows 凭据存储在本地计算机的凭据管理器中。

当 Lync 配置为支持双因素身份验证时，应禁用**SavePassword**注册表设置。 若要防止用户保存其密码，请在本地工作站上更改以下注册表项，或使用 Lync 管理模板应用到使用组策略的给定池的所有用户：

HKEY\_当前\_用户\\软件\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD： SavePassword

值：0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 令牌重播

AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。

在高度关注安全的环境（例如使用展台时）中，应启用此功能。 有关令牌重播检测的详细信息，请参阅 "安全规划和部署 AD FS 2.0 的最佳做法[http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)"。

</div>

<div>

## <a name="external-user-access"></a>外部用户访问

在这些主题中不涉及配置 AD FS 代理或反向代理以支持来自外部网络的 Lync 双重身份验证。

</div>

</div>

<span> </span>

</div>

</div>

</div>

