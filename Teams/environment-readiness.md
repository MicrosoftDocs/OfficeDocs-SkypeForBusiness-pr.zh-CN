---
title: 检查你的环境是否为 Microsoft Teams 准备好
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: 了解检查你的环境是否为 Microsoft Teams 准备好时要查看的内容。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1794b87beb1c6b1f1e499c214cde8d3e0b9b0a34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235402"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>检查你的环境是否为 Microsoft Teams 准备好
===========================================

向云过渡因每个组织而不同，并且当前状态可能会影响 Teams 的运行情况。

部署 Microsoft 团队之前强烈建议[部署学校数据同步](https://docs.microsoft.com/schooldatasync/)到的教育机构。 学校数据同步使用您的学校 SI 名单数据自动创建的 Microsoft 团队和其他应用程序的类和组。

为了获得使用 Teams 的最佳体验，贵组织必须已部署了 Exchange Online 和 SharePoint Online。 您还必须确保您的当前环境已准备好团队。  请参阅以下链接以帮助：

-   如果贵组织未部署任何 Office 365 工作负荷，请参阅[开始使用 Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

-   如果贵组织没有为 Office 365 添加或配置已验证的域，请参阅[验证 Office 365 域](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

-   如果贵组织没有将标识同步到 Azure Active Directory，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。

-   如果贵组织没有 Exchange Online，请参阅[了解 Exchange 与 Microsoft Teams 如何交互](Exchange-Teams-interact.md)。

-   如果贵组织没有 SharePoint Online，请参阅[了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](SharePoint-OneDrive-interact.md)。

- 如果您的组织是教育机构并使用学生信息系统 (SI)，然后再部署 Microsoft 团队[部署学校数据同步](https://docs.microsoft.com/schooldatasync/)。

- 如果贵组织拥有现有的内部部署 Skype 业务服务器 （或 Lync Server） 部署，则必须配置 Azure AD 连接将与 Office 365 同步您的本地目录。  有关详细信息，请参阅[个团队和 Skype for Business 配置 Azure AD 连接](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect)。