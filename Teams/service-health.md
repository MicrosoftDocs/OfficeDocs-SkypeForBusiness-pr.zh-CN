---
title: 验证 Microsoft Teams 的服务运行状况
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 最佳做法是验证团队服务是否正常工作以及其他 Microsoft 365 或 Office 365 组件（如 Exchange、SharePoint 和 OneDrive for business）。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c30a4da2a37f75540c2b81a1f0d37e2c1e348339
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085518"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="d9d83-103">验证 Microsoft Teams 的服务运行状况</span><span class="sxs-lookup"><span data-stu-id="d9d83-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="d9d83-104">Microsoft 团队的服务运行状况显示在 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="d9d83-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="d9d83-105">在对问题进行故障排除之前，建议验证 Teams 服务是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="d9d83-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="d9d83-106">转到<a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">团队服务运行状况</a>控制台以查看服务运行状况。</span><span class="sxs-lookup"><span data-stu-id="d9d83-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="d9d83-107">此外，请记住，Microsoft 团队是基于其他 Microsoft 365 或 Office 365 服务构建的，因此在查看服务运行状况时，请记住还要检查 Exchange、SharePoint 和 OneDrive for business 的状态。</span><span class="sxs-lookup"><span data-stu-id="d9d83-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="d9d83-108">这些其他服务的服务运行状况问题并不自动表示 Teams 受到影响（例如，Exchange 中的通讯簿下载不可用），但你应该查看针对这些受影响服务的建议，以确定是否影响 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="d9d83-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![“服务运行状况”页面屏幕截图。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![此屏幕截图显示 Microsoft Teams 服务运行正常。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a><span data-ttu-id="d9d83-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="d9d83-111">Related topics</span></span>

[<span data-ttu-id="d9d83-112">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="d9d83-112">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)