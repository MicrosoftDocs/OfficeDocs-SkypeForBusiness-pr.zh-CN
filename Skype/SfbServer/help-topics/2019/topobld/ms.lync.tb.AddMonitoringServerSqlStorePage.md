---
title: 添加监控服务器 SQL Server 存储
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
ROBOTS: NOINDEX, NOFOLLOW
description: 监控服务器需要支持的 64 位版本的 SQL Server 数据库软件存储监视数据。 您可以选择先前定义的 SQL Server 数据库，用于监控，或通过指定在其的 SQL Server 数据库将位于，除了 SQL 实例的服务器的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 的服务器。
ms.openlocfilehash: f0efdf2662567f786a035d30236d11c14ccc8efe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890702"
---
# <a name="add-monitoring-server-sql-server-store"></a>添加监控服务器 SQL Server 存储

监控服务器需要支持的 64 位版本的 SQL Server 数据库软件存储监视数据。 您可以选择先前定义的 SQL Server 数据库，用于监控，或通过指定在其的 SQL Server 数据库将位于，除了 SQL 实例的服务器的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 的服务器。

有关 SQL Server 的详细信息支持，请参阅可支持性文档中的[数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 详细信息监视数据库，包括并置的监控数据库，请参阅[支持的服务器位置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)可支持性文档中的规划文档和[SQL Server 数据的[Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)中和日志文件放置](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)部署文档中。

> [!NOTE]
> 如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建的监控数据库时发布拓扑。 您还可以创建数据库更高版本，包括安装过程的一部分。 安装和部署监控的基于 SQL Server 的服务器上的数据库的 > 您必须安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 SQL Server sysadmin 组的成员，您必须请求添加到组中，直到部署数据库文件。 如果您不能进行 sysadmins 组的成员，应将 SQL Server 数据库管理员提供了脚本，以配置和部署数据库。 有关用户权限和完成这些过程所需的权限的详细信息，请参阅部署文档中的[SQL Server 的部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


