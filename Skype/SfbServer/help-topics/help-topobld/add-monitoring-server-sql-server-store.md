---
title: 添加监控服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 监控服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储监控数据。 除了要用于新 SQL Server SQL Server 数据库 (（可以是默认实例）或指定指定) 实例的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，
ms.openlocfilehash: 53e8a95b179c3e15f52b694710248b5155ef8d07
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828692"
---
# <a name="add-monitoring-server-sql-server-store"></a>添加监控服务器 SQL Server 存储

监控服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储监控数据。 除了要用于新 SQL Server SQL Server 数据库 (（可以是默认实例）或指定指定) 实例的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库，

有关支持SQL Server，请参阅可支持性文档中的数据库 [软件和群集](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx) 支持。 有关监控数据库的详细信息，包括监控数据库并置，请参阅可支持性文档中的 Supported [Server Location、](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)规划[](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)文档中的"规划监控"和部署文档中的[SQL Server Data and Log File Placement。](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。 还可以稍后创建数据库（包括在安装过程中）。 >若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是要安装数据库文件的基于 SQL Server 服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmin SQL Server的成员，则必须请求添加到组，直到部署数据库文件。 如果您不能成为 sysadmins 组的成员，您应该向您的 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中SQL Server部署权限。 [](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)


