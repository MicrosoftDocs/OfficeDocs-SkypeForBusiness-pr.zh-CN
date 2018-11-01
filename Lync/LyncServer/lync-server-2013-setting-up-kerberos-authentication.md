---
title: Lync Server 2013：设置 Kerberos 身份验证
TOCTitle: 设置 Kerberos 身份验证
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398976(v=OCS.15)
ms:contentKeyID: 49314483
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中设置 Kerberos 身份验证

 

_**上一次修改主题：** 2013-02-21_

Lync Server 2013 支持对 Web 服务进行 NTLM 和 Kerberos 身份验证。 Office Communications Server 2007 和 Office Communications Server 2007 R2 使用默认的 RTCComponentService 和 RTCService 作为运行 Web 服务应用程序池的用户帐户，以便允许服务主体名称 (SPN) 分配给用户帐户并充当身份验证主体。 Lync Server 使用 NetworkService 来运行 Web 服务，且不能将 SPN 分配给 NetworkService。

为了解决 Active Directory 对象未保留 SPN 的问题，Lync Server 控制面板 可以使用计算机帐户对象来实现此目的。计算机帐户对象可以保留 SPN，且不受密码过期影响，使用以前版本中的用户帐户时存在受密码过期影响的问题。

使用 Windows PowerShell cmdlet 将计算机对象配置为提供 Kerberos 身份验证。

## 本部分内容

  - [在 Lync Server 2013 中启用 Kerberos 身份验证的先决条件](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [在 Lync Server 2013 中创建 Kerberos 身份验证帐户](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [在 Lync Server 2013 中将 Kerberos 身份验证帐户分配给站点](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [在 Lync Server 2013 中设置 Kerberos 身份验证帐户密码](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [在 Lync Server 2013 中向其他站点添加 Kerberos 身份验证](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [在 Lync Server 2013 中将 Kerberos 身份验证从站点中删除](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [在 Lync Server 2013 中测试和报告 Kerberos 身份验证的状态和分配](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

