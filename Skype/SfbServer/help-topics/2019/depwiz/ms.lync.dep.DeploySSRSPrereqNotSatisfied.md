---
title: SQL Server Reporting Services（不满足先决条件）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: 如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。
ms.openlocfilehash: 599be0110d83a061443d6cc2d0cf112e194155f2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705317"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="5e276-104">SQL Server Reporting Services（不满足先决条件）</span><span class="sxs-lookup"><span data-stu-id="5e276-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="5e276-p102">如果未在基础结构中部署监控服务器，则会看到此页。这表示尚未满足部署监控服务器报告的最低要求。</span><span class="sxs-lookup"><span data-stu-id="5e276-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="5e276-107">若要解决此问题，请确保你已将监视服务器加入到域中，该服务器已在拓扑生成器中定义，并且拓扑已发布。</span><span class="sxs-lookup"><span data-stu-id="5e276-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="5e276-108">SQL server Reporting Services 还必须在 SQL Server 上可用，并作为功能安装到 SQL Server 上的监视服务器数据库中。</span><span class="sxs-lookup"><span data-stu-id="5e276-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="5e276-109">有关详细信息，请参阅[在 Skype For Business 服务器中安装监视报告](../../../deploy/deploy-monitoring/install-monitoring-reports.md)和[部署监视](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5e276-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


