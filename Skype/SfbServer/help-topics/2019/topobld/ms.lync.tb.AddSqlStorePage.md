---
title: 添加 SQL 存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
ROBOTS: NOINDEX, NOFOLLOW
description: 若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例）。请指定以下内容。
ms.openlocfilehash: ad0e821f07fb94f48a3484b3a2de1327ee8ef57e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116400"
---
# <a name="add-sql-store"></a><span data-ttu-id="27b4e-103">添加 SQL 存储</span><span class="sxs-lookup"><span data-stu-id="27b4e-103">Add SQL Store</span></span>

<span data-ttu-id="27b4e-104">若要定义新的 SQL Store，这意味着要指定基于 SQL Server 的数据库和 SQL Server 实例（默认实例或命名实例）。请指定以下内容。</span><span class="sxs-lookup"><span data-stu-id="27b4e-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="27b4e-105">指定将承载所 (数据库实例) 的SQL Server FQDN 的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="27b4e-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="27b4e-106">指定将SQL Server数据的实例。</span><span class="sxs-lookup"><span data-stu-id="27b4e-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="27b4e-107">可以指定默认实例，也可以指定命名实例。</span><span class="sxs-lookup"><span data-stu-id="27b4e-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="27b4e-108">应明确理解特定实例中的数据库并置。</span><span class="sxs-lookup"><span data-stu-id="27b4e-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="27b4e-109">有关服务器并置和数据库实例并置的详细信息，请参阅[Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)和[Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)。</span><span class="sxs-lookup"><span data-stu-id="27b4e-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) and [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).</span></span>