---
title: 添加前端 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: 标准版服务器部署会自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，所有选项均已预填充，并且不能对默认配置进行更改。
ms.openlocfilehash: b2f3aef2b48981368a74d536254da55ae5e0495d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685135"
---
# <a name="add-front-end-sql-server-store"></a>添加前端 SQL Server 存储

标准版服务器部署会自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，所有选项均已预填充，并且不能对默认配置进行更改。

企业版服务器部署的前端池需要后端数据库的 SQL Server 数据库软件支持的64位版本。 你可以选择要用于后端数据库的以前定义的 SQL Server 数据库，或者通过指定 SQL Server 数据库所在服务器的完全限定的域名（FQDN），以及 SQL S 的实例来定义新的 SQL Server 数据库。要用于新 SQL Server 数据库的 erver （可以是默认实例或你指定的命名实例）。 你还可以选择在 SQL Server 存储上启用镜像，并为自动故障转移指定镜像见证。

有关 SQL Server 支持的详细信息，请参阅支持文档中的[数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 有关为后端数据库设置 SQL Server 的详细信息，请参阅部署文档中的 "[为 Lync server 2010 配置 Sql server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) "。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限和权限，则可以在发布拓扑时创建后端数据库（实时通信（RTC））。 你还可以稍后创建数据库，包括安装过程的一部分。

> [!NOTE]
> 若要在基于 SQL Server 的企业版部署服务器上安装和部署数据库，您必须是要在其中安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmin 组的成员。 如果您不是 SQL Server sysadmin 组的成员，则必须请求将其添加到组中，直到部署数据库文件。 如果你不能成为 sysadmin 组的成员，你应该向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些步骤所需的用户权限和权限的详细信息，请参阅[SQL Server 部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


