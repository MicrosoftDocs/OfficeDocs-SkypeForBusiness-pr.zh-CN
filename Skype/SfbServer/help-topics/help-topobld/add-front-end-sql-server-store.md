---
title: 添加前端 SQL Server 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dace9561-3eb4-4647-83cb-56c246919ae1
description: 部署 Standard Edition server 自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，所有选项都预先都填充，并且您无法更改为默认配置。
ms.openlocfilehash: 4c55f70cae6957acac28854c226b3699e860eea3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33903787"
---
# <a name="add-front-end-sql-server-store"></a>添加前端 SQL Server 存储

部署 Standard Edition server 自动安装所需的 Microsoft SQL Server Express 数据库软件和 SQL Server 数据库。 因此，所有选项都预先都填充，并且您无法更改为默认配置。

Enterprise Edition 服务器部署中的前端池的后端数据库需要的 SQL Server 数据库软件的支持的 64 位版本。 您可以选择先前定义的 SQL Server 数据库，用于后端数据库，或通过指定在其上驻留，SQL Server 数据库的服务器和 SQL S 实例的完全限定的域名 (FQDN) 来定义新的 SQL Server 数据库您想要用于新的 SQL Server 数据库 （这可以是默认的实例或您指定的命名的实例） 的服务器。 您还可以选择启用镜像 SQL Server 存储，并指定镜像见证的自动故障转移。

有关 SQL Server 的详细信息支持，请参阅可支持性文档中的[数据库软件和群集支持](https://technet.microsoft.com/library/e05d0032-bbea-4e61-987d-d07b1c045fd5.aspx)。 有关为后端数据库的 SQL Server 设置的详细信息，请参阅部署文档中的[Lync Server 2010 配置 SQL Server](https://technet.microsoft.com/library/375e5cc4-e436-46dc-9b02-5063f35cdcc1.aspx) 。

> [!NOTE]
> 如果用于发布拓扑的帐户具有适当的用户权限和权限，您可以创建后端数据库 （实时通信 (RTC)） 发布您的拓扑时。 您还可以创建数据库更高版本，包括安装过程的一部分。

> [!NOTE]
> 若要安装和部署 Enterprise Edition 部署中的基于 SQL Server 的服务器上的数据库，您必须安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 SQL Server sysadmins 组的成员，您必须请求添加到组中，直到部署数据库文件。 如果您不能进行 sysadmins 组的成员，应将 SQL Server 数据库管理员提供了脚本，以配置和部署数据库。 有关用户权限和完成这些过程所需的权限的详细信息，请参阅[SQL Server 的部署权限](https://technet.microsoft.com/library/56ea0c02-bcf5-4d45-aa13-570531c29074.aspx)。


