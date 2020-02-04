---
title: 添加监控服务器 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddMonitoringServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d873a2ad-9d3a-4ef6-9f25-ccdd3716218c
description: 监视服务器需要支持的 SQL Server 数据库软件的64位版本才能存储监视数据。 你可以选择用于监视的以前定义的 SQL Server 数据库，或者通过指定 sql Server 数据库将驻留的服务器的完全限定的域名（FQDN）来定义新的 SQL Server 数据库，以及 SQL 实例要用于新 SQL Server 数据库的服务器（可以是默认实例或你指定的命名实例）。
ms.openlocfilehash: 8c74462e0623c34fbbbf4c3f67d1a0adf0f3c922
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698177"
---
# <a name="add-monitoring-server-sql-server-store"></a>添加监控服务器 SQL Server 存储

监视服务器需要支持的 SQL Server 数据库软件的64位版本才能存储监视数据。 你可以选择用于监视的以前定义的 SQL Server 数据库，或者通过指定 sql Server 数据库将驻留的服务器的完全限定的域名（FQDN）来定义新的 SQL Server 数据库，以及 SQL 实例要用于新 SQL Server 数据库的服务器（可以是默认实例或你指定的命名实例）。

有关 SQL Server 支持的详细信息，请参阅支持文档中的[数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 有关监视数据库（包括监视数据库的 collocation）的详细信息，请参阅支持文档中的[支持的服务器位置](https://technet.microsoft.com/library/3be990a1-5485-4b83-b73f-947ac97821f9.aspx)、规划文档中的[监视](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)、 [SQL Server 数据和日志文件](https://technet.microsoft.com/library/67aa525b-8aa3-474f-827e-8e1d4697f30f.aspx)在部署文档中的位置。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权利和权限，则可以在发布拓扑时创建监视数据库。 你还可以稍后创建数据库，包括安装过程的一部分。 > 若要在基于 SQL Server 的监视服务器上安装和部署数据库，您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。 如果您不是 SQL Server sysadmin 组的成员，则必须请求将其添加到组中，直到部署数据库文件。 如果你不能成为 sysadmin 组的成员，你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些步骤所需的用户权限和权限的详细信息，请参阅部署文档中的[SQL Server 部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


