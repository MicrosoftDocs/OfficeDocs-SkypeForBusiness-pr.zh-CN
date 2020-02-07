---
title: 检查你的环境是否为 Microsoft Teams 准备好
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dansteve
description: 了解检查你的环境是否为 Microsoft Teams 准备好时要查看的内容。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48af92d4e7a325fdcabd1650b987a12bfb1ddf50
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832862"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>检查你的环境是否为 Microsoft Teams 准备好
===========================================

向云过渡因每个组织而不同，并且当前状态可能会影响 Teams 的运行情况。

强烈建议教育机构在部署 Microsoft 团队之前[部署学校数据同步](https://docs.microsoft.com/schooldatasync/)。 学校数据同步使用你的学校的 SIS 名单数据为 Microsoft 团队和其他应用程序自动创建类和组。

为了获得使用 Teams 的最佳体验，贵组织必须已部署了 Exchange Online 和 SharePoint Online。 你还必须确保你的当前环境已准备好进行团队。  有关帮助，请参阅以下链接：

-   如果贵组织未部署任何 Office 365 工作负荷，请参阅[开始使用 Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)。

-   如果贵组织没有为 Office 365 添加或配置已验证的域，请参阅[验证 Office 365 域](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)。

-   如果贵组织没有将标识同步到 Azure Active Directory，请参阅 [Microsoft Teams 中的标识模式和身份验证](identify-models-authentication.md)。

-   如果贵组织没有 Exchange Online，请参阅[了解 Exchange 与 Microsoft Teams 如何交互](Exchange-Teams-interact.md)。

-   如果贵组织没有 SharePoint Online，请参阅[了解 SharePoint Online 和 OneDrive for Business 与 Microsoft Teams 如何交互](SharePoint-OneDrive-interact.md)。

- 如果您的组织是教育机构，并且您使用学生信息系统（SIS），请在部署 Microsoft 团队之前[部署学校数据同步](https://docs.microsoft.com/schooldatasync/)。

- 如果你的组织具有现有的本地 Skype for business 服务器（或 Lync Server）部署，则必须将 Azure AD Connect 配置为将本地目录与 Office 365 同步。  有关详细信息，请参阅[配置团队和 Skype for business 的 AZURE AD 连接](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect)。