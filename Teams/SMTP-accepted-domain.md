---
title: 在 Exchange Online 中将团队 SMTP 域作为允许的发件人域添加
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
f1.keywords:
- NOCSH
description: 了解如何将 Microsoft 团队 SMTP 域添加为 Exchange Online 中允许的发件人域，以向团队成员发送通知。
appliesto:
- Microsoft Teams
ms.openlocfilehash: b0efec3be7bbd9cf14ee7d0f1ca826ca76996795
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637741"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>在 Exchange Online 中将 Microsoft Teams SMTP 域添加为允许的发件人域 
=============================================================================

无论是在管理员控制台还是使用 Outlook 创建 Microsoft 365 组，Exchange Online 都用于发送添加到组的团队成员的通知。 这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

团队使用 Microsoft Exchange Online，并在添加通知后向团队成员发送通知。 不同于 SMTP 邮件的域 FQDN 是 @email "teams.microsoft.com" （对于商业/商业租户），"@GCC-email.teams.com" 适用于政府租户，并且可能被垃圾邮件筛选器捕获。

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

为获得最佳效果和无缝操作，请考虑将 Microsoft 团队 SMTP 域添加到 Exchange Online 垃圾邮件配置中的 "允许的发件人域" 列表：

![垃圾邮件配置设置的 "允许列表" 部分的屏幕截图](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
