---
title: 添加前端存档存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndArchivingStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: ce1723eb-7c93-424a-a622-9c888bf6d3bc
ROBOTS: NOINDEX, NOFOLLOW
description: 存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。 除了要用于新的 SQL Server 数据库 () （可以是默认实例）的 SQL Server 实例之外，还可以指定要驻留 SQL Server 数据库的服务器的完全限定域名 (FQDN) ，也可以指定新的 SQL Server 数据库 (（可以是默认实例）或指定命名实例，从而定义新的 SQL Server 数据库。 SQL Server
ms.openlocfilehash: a2709a2701e64c201eeb14789ddabf815afdbf69
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587642"
---
# <a name="add-front-end-archiving-store"></a>添加前端存档存储

存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。 除了要用于新的 SQL Server 数据库 () （可以是默认实例）的 SQL Server 实例之外，还可以指定要驻留 SQL Server 数据库的服务器的完全限定域名 (FQDN) ，也可以指定新的 SQL Server 数据库 (（可以是默认实例）或指定命名实例，从而定义新的 SQL Server 数据库。 SQL Server

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。 您还可以稍后创建数据库，该数据库包含在安装过程中。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是要安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmin SQL Server的成员，则必须请求将您添加到该组，直到部署数据库文件。 如果您不能成为 sysadmins 组的成员，您应向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。