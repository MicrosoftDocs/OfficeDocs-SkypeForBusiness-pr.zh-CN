---
title: 添加监控服务器 SQL Server 存储
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 监控服务器需要受支持的 64 位版本SQL Server数据库软件来存储监控数据。 除了要用于新数据库的 SQL Server 实例之外，还可以选择之前定义的 SQL Server 数据库进行监视，或者通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库SQL Server数据库 (，可以是默认实例，也可以是指定的命名) 。
ms.openlocfilehash: bc6dfa021997a77ea4ac7a37ea2c663e245d6762
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397836"
---
# <a name="add-monitoring-server-sql-server-store"></a>添加监控服务器 SQL Server 存储

监控服务器需要受支持的 64 位版本SQL Server数据库软件来存储监控数据。 除了要用于新数据库的 SQL Server 实例之外，还可以选择之前定义的 SQL Server 数据库进行监视，或者通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库SQL Server数据库 (，可以是默认实例，也可以是指定的命名) 。

有关支持SQL Server的详细信息，请参阅可支持性文档中[的数据库软件和群集](/previous-versions/office/lync-server-2013/lync-server-2013-database-software-support)支持。 有关监控数据库（包括监控数据库并置）的详细信息，请参阅可支持性文档中的S supported [Server Location](/previous-versions/office/lync-server-2013/lync-server-2013-supported-server-collocation)、规划文档中的 Planning [for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) 和部署文档中的 [SQL Server Data and Log File Placement](/previous-versions/office/lync-server-2013/lync-server-2013-sql-server-data-and-log-file-placement)。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。 还可以稍后创建数据库（包括在安装过程中）。 >若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmin SQL Server的成员，则必须请求添加到组，直到部署数据库文件。 如果您无法成为 sysadmins 组的成员，您应向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的 Deployment [Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server) for SQL Server。