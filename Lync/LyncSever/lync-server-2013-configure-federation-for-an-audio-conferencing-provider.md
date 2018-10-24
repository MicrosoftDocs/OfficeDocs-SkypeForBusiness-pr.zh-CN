---
title: Lync Server 2013：为音频会议提供商配置联盟
TOCTitle: 为音频会议提供商配置联盟
ms:assetid: 08dedcce-0d3f-45da-8282-cf2634a41665
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn510996(v=OCS.15)
ms:contentKeyID: 59955436
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为音频会议提供商配置联盟

 

_**上一次修改主题：** 2014-07-24_

如果希望在混合部署（本地 Lync Server 及 Lync Online）中使用音频会议提供商 (ACP)，您需要在本地 Lync 部署和 ACP 合作伙伴（作为允许的合作伙伴服务器）之间配置联盟。您可以通过向本地部署的联盟域列表添加 ACP 合作伙伴域和边缘服务器（可称为访问代理）来配置联盟。然后，ACP 合作伙伴需要将您的本地边缘服务器池的 FQDN 添加到允许的联盟域列表。联系您的 ACP 提供商以了解详细信息。ACP 合作伙伴需要将您的本地边缘服务器池的 FQDN 添加到允许的联盟域列表。

  - **将 ACP 域和边缘服务器添加为允许的联盟域**
    
    要将 ACP 域添加为允许的合作伙伴服务器（允许的联盟域），请按照 [在 Lync Server 2013 中配置对允许的外部域的支持](lync-server-2013-configure-support-for-allowed-external-domains.md)中的步骤执行操作。对于边缘服务器，请添加 ACP 合作伙伴的边缘服务器的 FQDN。 您可能需要联系 ACP 合作伙伴，获得其边缘服务器的 FQDN，ACP 也可能称之为访问代理。

  - **向 ACP 合作伙伴提供您的边缘服务器池的 FQDN**
    
    ACP 合作伙伴需要将您的边缘服务器池的 FQDN 添加到允许的联盟域列表，以便配置联盟，将您的本地域添加为允许的合作伙伴服务器。

