---
title: 为混合部署配置自动发现
TOCTitle: 为混合部署配置自动发现
ms:assetid: ca605e62-181c-42ca-80a1-e37e610f8277
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945653(v=OCS.15)
ms:contentKeyID: 52061120
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为混合部署配置自动发现

 

_**上一次修改主题：** 2012-12-12_

混合部署是同时使用 Microsoft Lync Online 云服务和内部部署的配置。在此类型的配置中，自动发现服务必须能够找到用户实际所处的位置。也就是说，自动发现在查找用户帐户和承载用户帐户的服务器所处的位置方面提供帮助，与它是否在内部部署或在 Skype for Business Online 部署中无关。

例如，如果用户的帐户承载在 Skype for Business Online 中的服务器上，查找用户的尝试发生方式如下所示（在进程中称为*可发现性*）：

  - 用户启动对内部部署的连接尝试 **contoso.com**。

  - 会将尝试发送到 lyncdiscover.contoso.com，DNS 名称与自动发现服务相关联。

  - 自动发现指的是假定注册池处于内部部署上的 contoso.com 中，且是对在 Skype for Business Online 中承载用户的实际主服务器的指定信息。然后自动发现会向用户对 **lync.com** 联机自动发现服务发送一个引用。

  - 用户对 lync.com 联机自动发现服务启动一个连接尝试，并能够找到用户的帐户和用户的主服务器。

要使客户端能够发现用户主服务器所在的部署，则必须使用新的统一资源定位器 (URL) 配置自动发现服务。执行下列操作可配置自动发现服务。

## 为混合部署配置自动发现

1.  在本主题 [Lync Server 2013 的自动发现服务要求](lync-server-2013-autodiscover-service-requirements.md) 中，可使用 Get-CsHostingProvider 检索属性 ProxyFQDN 的值。

2.  从 Lync Server 命令行管理程序，键入
    
        Set-CsHostingProvider -Identity [identity] -AutodiscoverUrl https://webdir.online.lync.com/autodiscover/autodisccoverservice.svc/root
    
    其中 \[identity\] 使用共享 SIP 地址空间的域名替换。

## 另请参阅

#### 其他资源

[Get-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsHostingProvider)  
[Set-CsHostingProvider](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsHostingProvider)

