---
title: 验证 Microsoft Teams 的服务运行状况
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
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
description: 最佳做法是验证 Teams 服务是否正常，其他 Microsoft 365 或 Office 365 组件（例如 Exchange、SharePoint 和 OneDrive for Business）。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7aebfec6aedd018580ddece9d3d7dac4e30ca731b91decf5d74bc0acf9c3e91
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316688"
---
# <a name="verify-service-health-for-microsoft-teams"></a>验证 Microsoft Teams 的服务运行状况

服务运行状况Microsoft Teams显示在服务Microsoft 365 管理中心。 在对问题进行故障排除之前，建议验证 Teams 服务是否正常运行。 转到Teams<a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">运行状况</a>控制台查看服务运行状况。

此外，请记住，Microsoft Teams基于其他 Microsoft 365 或 Office 365 服务构建，因此在查看服务运行状况时，请记住还要检查 Exchange、SharePoint 和 OneDrive for Business 的状态。 这些其他服务的服务运行状况问题不会自动意味着 Teams 受到影响 (例如，Exchange 中的通讯簿下载不可用) ，但应查看有关这些受影响服务的公告，以确定对 Microsoft Teams 是否有影响。

![“服务运行状况”页面屏幕截图。](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![此屏幕截图显示 Microsoft Teams 服务运行正常。](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a>相关主题

[Teams 疑难解答](/MicrosoftTeams/troubleshoot/teams)
