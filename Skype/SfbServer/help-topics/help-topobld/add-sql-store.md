---
title: 添加 SQL 存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 若要定义新的 SQL 存储，这意味着您要指定基于 SQL Server 的数据库和 SQL Server 实例（无论是默认实例还是命名实例），请指定以下项。
ms.openlocfilehash: 261cc9ca3b0f792c9ab6566ba24f1d4d7236937a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217123"
---
# <a name="add-sql-store"></a>添加 SQL 存储

若要定义新的 SQL 存储，这意味着您要指定基于 SQL Server 的数据库和 SQL Server 实例（无论是默认实例还是命名实例），请指定以下项。

指定将托管您正在定义的数据库实例的 SQL Server (FQDN) 的完全限定的域名称。

指定将承载数据的 SQL Server 实例。 可以指定默认实例，也可以指定命名实例。

应明确理解特定实例中的数据库并置。 有关服务器并置和数据库实例并置的详细信息，请参阅[Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx)和[Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)。


