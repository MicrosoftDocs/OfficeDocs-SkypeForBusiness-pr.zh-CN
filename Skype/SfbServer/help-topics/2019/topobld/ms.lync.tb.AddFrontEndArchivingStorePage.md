---
title: 添加前端存档存储
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: 存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。 除了要用于新的 SQL Server 数据库 (实例（可以是默认实例）或指定指定) 的命名实例之外，还可以选择以前定义的 SQL Server 数据库进行存档，或者通过指定 SQL Server SQL Server 数据库所在的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库。
ms.openlocfilehash: 29a51e437c5249f2bd361579eadde812d5f65e17
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864139"
---
# <a name="add-front-end-archiving-store"></a>添加前端存档存储

存档需要受支持的 64 位版本的 Microsoft SQL Server 数据库软件来存储存档数据。 除了要用于新的 SQL Server 数据库 (实例（可以是默认实例）或指定指定) 的命名实例之外，还可以选择以前定义的 SQL Server 数据库进行存档，或者通过指定 SQL Server SQL Server 数据库所在的服务器的完全限定域名 (FQDN) 来定义新的 SQL Server 数据库。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则可以在发布拓扑时创建监控数据库。 您还可以稍后创建数据库，该数据库包含在安装过程中。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库进行监视，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmin SQL Server的成员，则必须请求将您添加到该组，直到部署数据库文件。 如果无法成为 sysadmins 组的成员，应为数据库管理员SQL Server脚本来配置和部署数据库。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。