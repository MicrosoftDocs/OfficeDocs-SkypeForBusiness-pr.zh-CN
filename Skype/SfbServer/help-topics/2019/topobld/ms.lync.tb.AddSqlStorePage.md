---
title: 添加 SQL 存储
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例）。请指定以下内容。
ms.openlocfilehash: fee7fcd3a7d18f9bf6f3c8fe91c3c971c9cdcba0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769330"
---
# <a name="add-sql-store"></a>添加 SQL 存储

若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例）。请指定以下内容。

指定将承载所 (数据库实例) 的SQL Server FQDN 的完全限定域名。

指定将SQL Server数据的实例。 可以指定默认实例，也可以指定命名实例。

应明确理解特定实例中的数据库并置。有关服务器并置和数据库实例并置的详细信息，请参阅[Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)和[Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)。