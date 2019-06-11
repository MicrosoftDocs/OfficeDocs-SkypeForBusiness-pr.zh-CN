---
title: Lync Server 2013：SQL Server 的系统要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: System requirements for SQL Server
ms:assetid: 9c235085-cbfa-4e9e-9cec-3f5749039a6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205112(v=OCS.15)
ms:contentKeyID: 48184904
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8e8bb923fd10d505eb9e1b02b0b0ee31612d40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-requirements-for-sql-server-in-lync-server-2013"></a><span data-ttu-id="8d8b2-102">Lync Server 2013 中 SQL Server 的系统要求</span><span class="sxs-lookup"><span data-stu-id="8d8b2-102">System requirements for SQL Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d8b2-103">_**主题上次修改时间:** 2013-10-25_</span><span class="sxs-lookup"><span data-stu-id="8d8b2-103">_**Topic Last Modified:** 2013-10-25_</span></span>

<span data-ttu-id="8d8b2-104">在部署企业版服务器之前, 请在满足硬件要求的专用计算机上安装 Microsoft SQL Server 2008 R2 或 Microsoft SQL Server 2012。</span><span class="sxs-lookup"><span data-stu-id="8d8b2-104">Before you deploy Enterprise Edition server, install Microsoft SQL Server 2008 R2 or Microsoft SQL Server 2012 on a dedicated computer that meets the hardware requirements.</span></span> <span data-ttu-id="8d8b2-105">有关硬件要求的详细信息, 请参阅支持文档中的[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="8d8b2-105">For details about hardware requirements, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) in the Supportability documentation.</span></span> <span data-ttu-id="8d8b2-106">有关软件要求的详细信息, 请参阅支持文档中[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="8d8b2-106">For details about software requirements, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="8d8b2-107">有关部署所需权限的信息, 请参阅[Lync server 2013 中的 SQL Server 部署权限](lync-server-2013-deployment-permissions-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8d8b2-107">For information about the permissions necessary for deployment, see [Deployment permissions for SQL Server in Lync Server 2013](lync-server-2013-deployment-permissions-for-sql-server.md).</span></span>

<span data-ttu-id="8d8b2-108">在创建前端池之前, 还必须通过使用 SQL Server 配置管理器定义服务器的端口并在 Windows 防火墙中打开端口, 将 Windows 防火墙配置为允许 Lync Server 2013 通过特定端口访问 SQL Server高级安全。</span><span class="sxs-lookup"><span data-stu-id="8d8b2-108">Before you create the Front End pool, you must also configure Windows Firewall to allow Lync Server 2013 access to SQL Server over specific ports by defining ports for the server using SQL Server Configuration Manager and opening ports in Windows Firewall with Advanced Security.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

