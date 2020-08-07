---
title: 在 Exchange Online 中将团队 SMTP 域作为允许的发件人域添加
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 33605a8250c9cd2bdcec90ade7b3fcea536f8977
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582049"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="2cd20-103">在 Exchange Online 中将 Microsoft Teams SMTP 域添加为允许的发件人域</span><span class="sxs-lookup"><span data-stu-id="2cd20-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="2cd20-104">无论是在管理员控制台还是使用 Outlook 创建 Microsoft 365 组，Exchange Online 都用于发送添加到组的团队成员的通知。</span><span class="sxs-lookup"><span data-stu-id="2cd20-104">Whether you create a Microsoft 365 group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a group.</span></span> <span data-ttu-id="2cd20-105">这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。</span><span class="sxs-lookup"><span data-stu-id="2cd20-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="2cd20-107">团队使用 Microsoft Exchange Online，并在添加通知后向团队成员发送通知。</span><span class="sxs-lookup"><span data-stu-id="2cd20-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they've been added.</span></span> <span data-ttu-id="2cd20-108">不同于 SMTP 邮件的域 FQDN 是 @email "teams.microsoft.com" （对于商业/商业租户），"@GCC-email.teams.microsoft.com" 适用于政府租户，并且可能被垃圾邮件筛选器捕获。</span><span class="sxs-lookup"><span data-stu-id="2cd20-108">The difference being the domain FQDN of the SMTP message is "@email.teams.microsoft.com" for Commercial/Business tenants and "@GCC-email.teams.microsoft.com" for Government tenants and could be caught by spam filtering.</span></span>

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="2cd20-110">为获得最佳效果和无缝操作，请考虑将 Microsoft 团队 SMTP 域添加到 Exchange Online 垃圾邮件配置中的 "允许的发件人域" 列表：</span><span class="sxs-lookup"><span data-stu-id="2cd20-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your "allowed sender domains" list in your Exchange Online spam configuration:</span></span>

![垃圾邮件配置设置的 "允许列表" 部分的屏幕截图](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
