---
title: 在 Exchange Online 中将 Microsoft Teams SMTP 域添加为允许的发件人域
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
ms.openlocfilehash: a3455c56ab3d51b83d2d5bc27d41824b6fe16ae9
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834762"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a>在 Exchange Online 中将 Microsoft Teams SMTP 域添加为允许的发件人域 
=============================================================================

在管理控制台中或通过使用 Outlook 创建 Office 365 组时，使用 Exchange Online 发送向组添加团队成员的通知。 这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

团队也使用 Microsoft Exchange Online 在添加团队成员时向这些成员发送通知。 不同于 SMTP 邮件的域 FQDN 是 @email "teams.microsoft.com" （对于商业/商业租户），"@GCC-email.teams.com" 适用于政府租户，并且可能被垃圾邮件筛选器捕获。

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

为获得最佳效果和无缝操作，请考虑将 Microsoft 团队 SMTP 域添加到 Exchange Online 垃圾邮件配置中的 "允许的发件人域" 列表：

![垃圾邮件配置设置的 "允许列表" 部分的屏幕截图](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
