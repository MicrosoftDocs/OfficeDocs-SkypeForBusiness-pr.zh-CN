---
title: Lync Server 2013：为反向代理设置证书
TOCTitle: 为反向代理设置证书
ms:assetid: c03a08ec-a67b-4f11-b0d7-6677461beaaa
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412938(v=OCS.15)
ms:contentKeyID: 49314136
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为反向代理设置证书

 

_**上一次修改主题：** 2012-09-08_

每台反向代理服务器都需要一个 Web 服务器证书，以供侦听服务使用。该 Web 服务器证书必须是由公共证书颁发机构 (CA) 颁发的。

有关证书的这一要求以及其他要求的详细信息，请参阅[Lync Server 2013 中外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

## 为反向代理设置 Web 服务证书

  - 您应该已经设置了反向代理，包括设置 Web 服务证书。如果在开始部署边缘服务器之前尚未设置反向代理，请按照 [为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)中的步骤创建请求并安装 Web 服务证书，然后创建各个 Web 发布规则，并将规则配置为使用证书。

