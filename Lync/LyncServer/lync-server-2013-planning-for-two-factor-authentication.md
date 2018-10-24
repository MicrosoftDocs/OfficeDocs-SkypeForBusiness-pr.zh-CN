---
title: 规划双重身份验证
TOCTitle: 规划双重身份验证
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn308562(v=OCS.15)
ms:contentKeyID: 56271121
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 规划双重身份验证

 

_**上一次修改主题：** 2016-12-08_

下面列出了配置 Microsoft Lync Server 2013 环境以支持双重身份验证时的部署注意事项。

## 客户端支持

具有 2013 年 7 月 Lync Server 2013 累积更新的 Lync 2013 桌面客户端是当前唯一支持双重身份验证的 Lync 客户端。

## 拓扑要求

强烈鼓励客户使用具有 2013 年 7 月 Lync Server 2013 累积更新的专用 Lync Server 2013（边缘、控制器和用户池）部署双重身份验证。要为 Lync 用户启用被动身份验证，必须为其他角色和服务禁用其他身份验证方法，包括以下各项：


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
<td><p>边缘服务器</p></td>
<td><p>边缘</p></td>
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


除非在服务级别禁用这些身份验证类型，否则一旦在您的部署中启用双重身份验证，所有其他版本的 Lync 客户端将无法成功登录。

## Lync 服务发现

应配置内部和/或外部客户端用于发现 Lync 服务的 DNS 记录，以解析为未启用双重身份验证的 Lync 服务器。使用此配置时，Lync 池中未启用双重身份验证的用户无需输入 PIN 进行身份验证，而 Lync 池中启用了双重身份验证的用户需要输入其 PIN 进行身份验证。

## Exchange 身份验证

为 Microsoft Exchange 部署了双重身份验证的客户可能会发现 Lync 客户端中的某些功能不可用。当前设计就是如此，因为 Lync 客户端对于依赖于 Exchange 集成的功能不支持双重身份验证。

## Lync 联系人

配置为利用统一联系人存储功能的 Lync 用户将会发现，在使用双重身份验证登录之后其联系人不再可用。

在启用双重身份验证之前，您应该使用 **Invoke-CsUcsRollback** cmdlet 从统一联系人存储中删除现有用户联系人，并将他们存储在 Lync Server 2013 中。

## 技能搜索

在其 Lync 环境中配置了技能搜索功能的客户将会发现，当为 Lync 启用双重身份验证时，此功能无法正常工作。这是设计使然，因为 Microsoft SharePoint 当前不支持双重身份验证。

## Lync 凭据

有许多涉及保存的 Lync 凭据的部署注意事项，它们可能会影响配置为使用双重身份验证的用户。

## 删除保存的凭据

在第一次尝试使用双重身份验证登录之前，用户应使用 Lync 客户端中的“删除我的登录信息”选项，并从 %localappdata%\\Microsoft\\Office\\15.0\\Lync 中删除其 SIP 配置文件文件夹。

## DisableNTCredentials

使用 Kerberos 或 NTLM 身份验证方法时，将自动使用用户的 Windows 凭据进行身份验证。在启用 Kerberos 和/或 NTLM 进行身份验证的典型 Lync Server 2013 部署中，用户每次登录时不必输入其凭据。

如果在提示用户输入其 PIN 之前无意中提示用户输入凭据，则可能通过组策略在客户端计算机上无意中配置了 **DisableNTCredentials** 注册表项。

为防止另外提示输入凭据，请在本地工作站上创建以下注册表项或者使用 Lync 管理模板通过组策略应用于给定池的所有用户：

HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD：DisableNTCredentials

值：0x0

## SavePassword

当用户首次登录 Lync 时，系统将提示用户保存其密码。如果选中，此选项允许用户的客户端证书存储在个人证书存储中，而用户的 Windows 凭据存储在本地计算机的凭据管理器中。

当 Lync 配置为支持双重身份验证时，应禁用 **SavePassword** 注册表设置。为防止用户保存其密码，请在本地工作站上更改以下注册表项或者使用 Lync 管理模板通过组策略应用于给定池的所有用户：

HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD：SavePassword

值：0x0

## AD FS 2.0 令牌重播

AD FS 2.0 提供了一项功能称为“令牌重播检测”，借助该功能，可以检测并丢弃多个使用相同令牌的令牌请求。启用此功能时，令牌重播检测可确保从不多次使用相同令牌，从而保护 WS 联合被动配置文件和 SAML WebSSO 配置文件中身份验证请求的完整性。

在高度关注安全的环境（例如使用展台时）中，应启用此功能。有关令牌重播检测的详细信息，请参阅“AD FS 2.0 安全规划和部署的最佳做法”，网址为 [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)。

## 外部用户访问

这些主题不涵盖配置 ADFS 代理或反向代理以从外部网络支持 Lync 双重身份验证。

