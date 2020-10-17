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
ms.openlocfilehash: 1932164cd1236257bbb81d1503b0310c8c55526e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513449"
---
# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>在 Lync Server 2013 中规划双因素身份验证

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-04-06_

以下是配置 Microsoft Lync Server 2013 环境以支持双重身份验证时的部署注意事项列表。

<div>

## <a name="client-support"></a>客户端支持

Lync Server 2013 的 Lync 2013 累积更新：7月2013桌面客户端和所有移动客户端当前支持双重身份验证。

</div>

<div>

## <a name="topology-requirements"></a>拓扑要求

强烈建议客户使用专用 Lync Server 2013 和 Lync Server 2013 的累积更新来部署双重身份验证：7月 2013 Edge、Director 和用户池。 若要为 Lync 用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：


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
<td><p>Web</p></td>
<td><p>控制器</p></td>
<td><p>Kerberos、NTLM 和证书</p></td>
</tr>
<tr class="even">
<td><p>Web 服务</p></td>
<td><p>Web</p></td>
<td><p>前端</p></td>
<td><p>Kerberos、NTLM 和证书</p></td>
</tr>
<tr class="odd">
<td><p>代理</p></td>
<td><p>EdgeServer</p></td>
<td><p>Microsoft Edge</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
<tr class="even">
<td><p>代理</p></td>
<td><p>注册</p></td>
<td><p>前端</p></td>
<td><p>Kerberos 和 NTLM</p></td>
</tr>
</tbody>
</table>


除非在服务级别禁用这些身份验证类型，否则在您的部署中启用双重身份验证后，Lync 客户端的所有其他版本都将无法成功登录。

</div>

<div>

## <a name="lync-service-discovery"></a>Lync 服务发现

应将内部和/或外部客户端使用的 DNS 记录配置为解析为未启用双重身份验证的 Lync server。 使用此配置时，未启用双重身份验证的 Lync 池中的用户不需要输入 PIN 即可进行身份验证，而启用了双重身份验证的 Lync 池中的用户将需要输入其 PIN 以进行身份验证。

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 身份验证

已为 Microsoft Exchange 部署双重身份验证的客户可能会发现 Lync 客户端中的某些功能不可用。 这是当前设计的，因为 Lync 客户端不支持依赖 Exchange 集成的功能的双重身份验证。

</div>

<div>

## <a name="lync-contacts"></a>Lync 联系人

配置为利用统一联系人存储功能的 Lync 用户将会发现，在使用双重身份验证登录后，他们的联系人将不再可用。

应使用 **invoke-csucsrollback** Cmdlet 从统一的联系人存储库中删除现有用户联系人，并将其存储在 Lync Server 2013 中，然后再启用双重身份验证。

</div>

<div>

## <a name="skill-search"></a>技能搜索

在 Lync 环境中配置技能搜索功能的客户将会发现启用了双因素身份验证的 Lync 后，此功能不起作用。 这是由设计决定的，因为 Microsoft SharePoint 目前不支持双重身份验证。

</div>

<div>

## <a name="lync-credentials"></a>Lync 凭据

有许多部署注意事项涉及保存的 Lync 凭据，这可能会影响配置为使用双重身份验证的用户。

<div>

## <a name="deleting-saved-credentials"></a>删除保存的凭据

桌面客户端用户应使用 Lync 客户端中的 " **删除我的登录信息** " 选项，并从% localappdata% Microsoft Office 15.0 Lync 中删除其 SIP 配置文件文件夹， \\ \\ \\ \\ 然后再尝试使用双重身份验证进行首次签名。

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

使用 Kerberos 或 NTLM 身份验证方法时，将自动使用用户的 Windows 凭据进行身份验证。 在为身份验证启用了 Kerberos 和/或 NTLM 的典型 Lync Server 2013 部署中，用户在每次登录时都不应输入其凭据。

如果在提示用户输入 PIN 之前，无意中提示用户输入凭据，则可能会在客户端计算机上无意中配置 **DisableNTCredentials** 注册表项，这可能是通过组策略。

若要阻止额外的凭据提示，请在本地工作站上创建以下注册表项，或使用 Lync 管理模板应用到使用组策略的给定池的所有用户：

HKEY \_ 本地 \_ 机器 \\ 软件 \\ 策略 \\ Microsoft \\ Office \\ 15.0 \\ Lync

REG \_ DWORD： DisableNTCredentials

值：0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

当用户第一次登录 Lync 时，系统会提示用户保存其密码。 如果选中此选项，则允许将用户的客户端证书存储在个人证书存储中，并允许将用户的 Windows 凭据存储在本地计算机的凭据管理器中。

将 Lync 配置为支持双重身份验证时，应禁用 **SavePassword** 注册表设置。 若要防止用户保存其密码，请更改本地工作站上的以下注册表项，或使用 Lync 管理模板将组策略应用于给定池的所有用户：

HKEY \_ 当前 \_ 用户 \\ 软件 \\ Microsoft \\ Office \\ 15.0 \\ Lync

REG \_ DWORD： SavePassword

值：0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 令牌重播

AD FS 2.0 提供一种称为令牌重播检测的功能，可检测到使用相同令牌的多个令牌请求，然后将其丢弃。 启用此功能后，令牌重播检测通过确保不会多次使用同一令牌来保护 WS-Federation 被动配置文件和 SAML WebSSO 配置文件中的身份验证请求的完整性。

如果安全性是非常重要的问题（例如使用展台时），应启用此功能。 有关令牌重播检测的详细信息，请参阅在上安全规划和部署 AD FS 2.0 的最佳实践 [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215) 。

</div>

<div>

## <a name="external-user-access"></a>外部用户访问

这些主题不涉及将 AD FS 代理或反向代理配置为支持来自外部网络的 Lync 双重身份验证。

</div>

</div>

<span> </span>

</div>

</div>

</div>

