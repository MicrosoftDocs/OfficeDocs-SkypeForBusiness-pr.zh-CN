---
title: 'Lync Server 2013：IPv6 的迁移和共存注意事项   '
TOCTitle: IPv6 的迁移和共存注意事项
ms:assetid: 8c769c4f-c8a9-4cbf-9080-beee3be9848a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205068(v=OCS.15)
ms:contentKeyID: 49313530
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 IPv6 的迁移和共存注意事项

 

_**上一次修改主题：** 2012-06-14_

Lync Server 2010 或 Office Communications Server 上不支持 IP 版本 6 (IPv6)。若要试用，您可测试 Lync Server 2010 和 Lync Server 2013 双协议栈共存。建议在为任何池启用 IPv6（双协议栈网络）之前，将给定中央站点的所有池升级到 Lync Server 2013。如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。

迁移和共存期间支持下列方案：

  - Lync Server 2013、 Lync Server 2010 和 Office Communications Server 2007 R2 池处于 IPv4 模式，与双协议栈模式下的 Lync Server 2013 共存。

  - 如果存储仅 IPv6 池，则 Lync Server 2013 池将处于仅 IPv6 模式。

