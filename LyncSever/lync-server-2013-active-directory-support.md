---
title: Lync Server 2013 Active Directory 支持
TOCTitle: Active Directory 支持
ms:assetid: 28ed9ac4-586d-4803-ad45-99c4fa793f54
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425756(v=OCS.15)
ms:contentKeyID: 49312319
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Active Directory 支持

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 支持的 Active Directory 域服务 本地拓扑如下所示：

  - 具有单个域的单林

  - 具有单个树和多个域的单林

  - 具有多个树和互不连接的命名空间的单林

  - 中央林拓扑中的多林

  - 资源林拓扑中的多林

> [!NOTE]  
> Lync Server 2013 不支持单标签域。例如，支持具有名为 <strong>contoso.local</strong> 的根域的林，但不支持名为 <strong>local</strong> 的单标签根域。有关详细信息，请参阅 Microsoft 知识库文章 300684“关于如何为使用单标签 DNS 名称的域配置 Windows 的信息”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=143752">http://go.microsoft.com/fwlink/p/?linkId=143752</a>。



> [!NOTE]  
> Lync Server 2013 不支持重命名域。如果需要重命名部署有 Lync Server 的域，则需要先卸载 Lync Server，然后重命名域，最后重新安装 Lync Server。



有关本地部署支持的拓扑和相关要求的详细信息，请参阅规划文档中的 [Lync Server 2013 中的 Active Directory 域服务要求、支持和拓扑](lync-server-2013-active-directory-domain-services-requirements-support-and-topologies.md)。

