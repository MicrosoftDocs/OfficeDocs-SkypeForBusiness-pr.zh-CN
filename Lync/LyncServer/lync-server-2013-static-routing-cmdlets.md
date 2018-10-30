---
title: 静态路由 Cmdlet
TOCTitle: 静态路由 Cmdlet
ms:assetid: 71d5e0cd-8412-4383-818a-95b851a4da4b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg416492(v=OCS.15)
ms:contentKeyID: 49313222
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 静态路由 Cmdlet

 

_**上一次修改主题：** 2016-12-08_

通过静态路由，管理员可以预先确定 SIP 消息采用的网络路由。当服务器接收消息时，该服务器将检查消息地址，并将其转发到管理员预先配置的下一个跃点服务器。如果配置正确，静态路由将有助于确保及时、准确地传送消息，并在服务器上消耗最少的开销。

## 静态路由 Cmdlet

除非另有 Microsoft 支持人员指导，否则应使用 [New-CsStaticRoute](new-csstaticroute.md) cmdlet 创建为 Microsoft Lync Server 2013 配置的静态路由。创建路由之后，即可使用 CsStaticRoutingConfiguration cmdlet 将该路由添加到静态路由集合。

**静态路由**

  -   
    [Get-CsSipResponseCodeTranslationRule](get-cssipresponsecodetranslationrule.md)

  -   
    [New-CsSipResponseCodeTranslationRule](new-cssipresponsecodetranslationrule.md)

  -   
    [Remove-CsSipResponseCodeTranslationRule](remove-cssipresponsecodetranslationrule.md)

  -   
    [Set-CsSipResponseCodeTranslationRule](set-cssipresponsecodetranslationrule.md)

  -   
    [New-CsStaticRoute](new-csstaticroute.md)

  -   
    [Get-CsStaticRoutingConfiguration](get-csstaticroutingconfiguration.md)

  -   
    [New-CsStaticRoutingConfiguration](new-csstaticroutingconfiguration.md)

  -   
    [Remove-CsStaticRoutingConfiguration](remove-csstaticroutingconfiguration.md)

  -   
    [Set-CsStaticRoutingConfiguration](set-csstaticroutingconfiguration.md)

  -   
    [New-CsSipProxyCustom](new-cssipproxycustom.md)

  -   
    [New-CsSipProxyRealm](new-cssipproxyrealm.md)

  -   
    [New-CsSipProxyTCP](new-cssipproxytcp.md)

  -   
    [New-CsSipProxyTLS](new-cssipproxytls.md)

  -   
    [New-CsSipProxyTransport](new-cssipproxytransport.md)

  -   
    [New-CsSipProxyUseDefault](new-cssipproxyusedefault.md)

  -   
    [New-CsSipProxyUseDefaultCert](new-cssipproxyusedefaultcert.md)

  -   
    [New-CsIssuedCertId](new-csissuedcertid.md)

## 另请参阅

#### 其他资源

[Lync Server PowerShell 博客](http://go.microsoft.com/fwlink/?linkid=203150%26clcid=0x804)

