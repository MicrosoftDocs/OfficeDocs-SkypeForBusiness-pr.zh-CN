---
title: 添加 SQL 存储
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
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例）。请指定以下内容。
ms.openlocfilehash: dfc1c891e3f64df0b8ba96f9f917ec502c272cb50ea87c022977bfc6c7c116b7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307333"
---
# <a name="add-sql-store"></a>添加 SQL 存储

若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例）。请指定以下内容。

指定将承载所 (数据库实例) 的SQL Server FQDN 的完全限定域名。

指定将SQL Server数据的实例。 可以指定默认实例，也可以指定命名实例。

应明确理解特定实例中的数据库并置。有关服务器并置和数据库实例并置的详细信息，请参阅[Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)和[Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)。