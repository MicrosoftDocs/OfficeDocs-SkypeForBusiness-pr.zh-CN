---
title: 添加存档 SQL Server 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddArchivingServerSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 26e0a748-e31d-4c66-b225-b37e0a45408f
ROBOTS: NOINDEX, NOFOLLOW
description: 存档服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储存档数据。 可以选择以前定义的 SQL Server 数据库进行存档，或者通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) ，以及要用于新的 SQL Server 数据库 (（可以是默认实例或指定) 的命名实例）的 SQL Server 实例来定义新的 SQL Server 数据库。
ms.openlocfilehash: ff6cec0d083e4597dec7ae61df08b16ff8feab7f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100208"
---
# <a name="add-archiving-server-sql-server-store"></a>添加存档 SQL Server 存储

存档服务器需要受支持的 64 位版本的 SQL Server 数据库软件来存储存档数据。 可以选择以前定义的 SQL Server 数据库进行存档，或者通过指定 SQL Server 数据库将驻留的服务器的完全限定域名 (FQDN) ，以及要用于新的 SQL Server 数据库 (（可以是默认实例或指定) 的命名实例）的 SQL Server 实例来定义新的 SQL Server 数据库。

> [!NOTE]
> 如果用于发布拓扑的帐户具有相应的用户权限，则您可以在发布拓扑时创建存档数据库 (LcsLog)。也可以稍后在安装过程中或其他操作过程中创建数据库。

> [!NOTE]
> 若要在基于 SQL Server 的服务器上安装和部署数据库进行存档，您必须是安装数据库文件的基于 SQL Server 的服务器的 SQL Server sysadmins 组的成员。 如果您不是 sysadmins SQL Server的成员，则必须请求添加到组，直到部署数据库文件。 如果您无法成为 sysadmins 组的成员，您应向 SQL Server 数据库管理员提供用于配置和部署数据库的脚本。 有关完成这些过程所需的用户权限的详细信息，请参阅部署文档中的[Deployment Permissions for SQL Server](/previous-versions/office/lync-server-2013/lync-server-2013-deployment-permissions-for-sql-server)。