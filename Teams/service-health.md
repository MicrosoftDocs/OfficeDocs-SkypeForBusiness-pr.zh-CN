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
<a name="verify-service-health-for-microsoft-teams"></a>验证 Microsoft Teams 的服务运行状况
===========================================

Microsoft 团队的服务运行状况显示在 Microsoft 365 管理中心。 在对问题进行故障排除之前，建议验证 Teams 服务是否正常运行。 转到<a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">团队服务运行状况</a>控制台以查看服务运行状况。

此外，请记住，Microsoft 团队是基于其他 Microsoft 365 或 Office 365 服务构建的，因此在查看服务运行状况时，请记住还要检查 Exchange、SharePoint 和 OneDrive for business 的状态。 这些其他服务的服务运行状况问题并不自动表示 Teams 受到影响（例如，Exchange 中的通讯簿下载不可用），但你应该查看针对这些受影响服务的建议，以确定是否影响 Microsoft Teams。

![“服务运行状况”页面屏幕截图。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![此屏幕截图显示 Microsoft Teams 服务运行正常。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a>相关主题

[Teams 疑难解答](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)