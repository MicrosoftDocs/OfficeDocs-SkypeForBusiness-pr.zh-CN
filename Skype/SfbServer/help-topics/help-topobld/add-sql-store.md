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
description: 若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例），请指定以下内容。
ms.openlocfilehash: 79429b596eef1ed0695aeb24594ea08ce12093be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833302"
---
# <a name="add-sql-store"></a><span data-ttu-id="45a01-103">添加 SQL 存储</span><span class="sxs-lookup"><span data-stu-id="45a01-103">Add SQL Store</span></span>

<span data-ttu-id="45a01-104">若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例），请指定以下内容。</span><span class="sxs-lookup"><span data-stu-id="45a01-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="45a01-105">指定 FQDN (FQDN) 将SQL Server所定义的数据库实例的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="45a01-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="45a01-106">指定将SQL Server数据的实例。</span><span class="sxs-lookup"><span data-stu-id="45a01-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="45a01-107">可以指定默认实例，也可以指定命名实例。</span><span class="sxs-lookup"><span data-stu-id="45a01-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="45a01-108">应明确理解特定实例中的数据库并置。</span><span class="sxs-lookup"><span data-stu-id="45a01-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="45a01-109">有关服务器并置和数据库实例并置的详细信息，请参阅[Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx)和[Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx)。</span><span class="sxs-lookup"><span data-stu-id="45a01-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](https://technet.microsoft.com/library/0516b18d-14c0-4237-9279-0f92e341b1bd.aspx) and [Server Collocation in a Standard Edition Server Deployment](https://technet.microsoft.com/library/0763ffab-4fd6-463a-8e62-d97876b376d3.aspx).</span></span>


