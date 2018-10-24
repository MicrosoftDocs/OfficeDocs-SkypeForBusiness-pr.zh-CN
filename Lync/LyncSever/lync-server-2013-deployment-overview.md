---
title: Lync Server 2013：部署概述
TOCTitle: 部署概述
ms:assetid: da67555e-f410-4c37-9996-d511f37da8d1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205305(v=OCS.15)
ms:contentKeyID: 49314432
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 部署概述

 

_**上一次修改主题：** 2013-03-12_

Lync Server 2013  企业版 和 Lync Server 2013  标准版 的主要差异是 标准版 不支持 企业版 的高可用性功能。为实现高可用性，需要将多个 前端服务器部署到一个池中，然后可以进行镜像运行 SQL Server 的服务器。使用 企业版，您可选择并置或定义独立 中介服务器。 监控服务器和 存档服务器可使用独立的运行 SQL Server 的服务器。或者，可以将数据库服务器上运行的 SQL Server 实例用于 前端服务器和池。

运行 Lync Server 2013标准版 的服务器旨在供小型组织和远程位置使用，组织的主要部署在地理位置上删除了这些小型组织和远程位置。配对在一起以便在发生灾难时进行故障转移的两台 Standard Edition Server 服务器最多可支持 5,000 个用户。您无法像操作 企业版 中的前端服务器一样将 Standard Edition 服务器放在池中。此外，标准版 使用的 SQL Server 数据库是运行 SQL Server Express 的并置服务器，用于处理 Standard Edition Server 工作负荷。这并不是说所有角色都必须驻留在 Standard Edition Server上。您可具有独立中介服务器和边缘服务器。由于 Lync Server 2013 的原因，中央管理存储的 SQL Server 数据库必须驻留在与运行 SQL Server 的服务器并置的 Standard Edition Server 上。监控服务器和存档服务器使用含有 SQL Server 数据库的独立服务器。

