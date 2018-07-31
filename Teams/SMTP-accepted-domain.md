---
title: 添加 Microsoft 团队 SMTP 域为不允许的发件人的域在 Exchange Online
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
description: 了解如何添加 Microsoft 团队 SMTP 域为不允许的发件人的域在 Exchange Online 将通知发送给团队成员。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d69e2890589169da126f237562d32a89d378edb
ms.sourcegitcommit: 046cc4a880f3b6b5f912278483cf28fa25619b6e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/31/2018
ms.locfileid: "21597572"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="ed6ac-103">添加 Microsoft 团队 SMTP 域为不允许的发件人的域在 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ed6ac-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="ed6ac-104">在管理控制台中或通过使用 Outlook 创建 Office 365 组时，使用 Exchange Online 发送向组添加团队成员的通知。</span><span class="sxs-lookup"><span data-stu-id="ed6ac-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="ed6ac-105">这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。</span><span class="sxs-lookup"><span data-stu-id="ed6ac-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![示例 Outlook 电子邮件标题屏幕截图，显示已将用户添加到组。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="ed6ac-107">团队也使用 Microsoft Exchange Online 在添加团队成员时向这些成员发送通知。</span><span class="sxs-lookup"><span data-stu-id="ed6ac-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="ed6ac-108">SMTP 邮件的域 FQDN 的区别是“@email.teams.microsoft.com”，垃圾邮件筛选可能会捕获它。</span><span class="sxs-lookup"><span data-stu-id="ed6ac-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering.</span></span>

![示例 Outlook 电子邮件标题屏幕截图，显示已将用户添加到组。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="ed6ac-110">对于最佳结果和无缝操作，请考虑添加到"允许发件人域"列表为 Exchange Online 的垃圾邮件配置中的 Microsoft 团队 SMTP 域：</span><span class="sxs-lookup"><span data-stu-id="ed6ac-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Exchange Online 垃圾邮件配置设置的“允许列表”部分屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
