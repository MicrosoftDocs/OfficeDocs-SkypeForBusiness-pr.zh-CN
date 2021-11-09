---
title: 添加前端存档存储
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
description: 存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。 除了要用于新的 SQL Server 数据库 (（可以是默认实例）的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库（可以是默认实例）或指定) 的命名实例。 SQL Server
ms.openlocfilehash: ecf1aad9b21a3501e8f05dfdecbd5b1472846b58
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837834"
---
# <a name="add-front-end-archiving-store"></a>添加前端存档存储

存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。 除了要用于新的 SQL Server 数据库 (（可以是默认实例）的 SQL Server 实例之外，还可以指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库（可以是默认实例）或指定) 的命名实例。 SQL Server

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。 您还可以稍后创建数据库，该数据库包含在安装过程中。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmin SQL Server的成员，则必须请求将您添加到组，直到部署数据库文件。 如果您无法成为 sysadmins 组的成员，您应向 SQL Server 管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。