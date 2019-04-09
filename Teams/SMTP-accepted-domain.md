---
title: 在 Exchange Online 中将 Microsoft Teams SMTP 域添加为允许的发件人域
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: 了解如何添加 Microsoft 团队 SMTP 域为不允许的发件人的域在 Exchange Online 将通知发送给团队成员。
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4a1a94bec69b1c7953dea6802d62058b04700bb
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "31516804"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="8cae0-103">在 Exchange Online 中将 Microsoft Teams SMTP 域添加为允许的发件人域</span><span class="sxs-lookup"><span data-stu-id="8cae0-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="8cae0-104">在管理控制台中或通过使用 Outlook 创建 Office 365 组时，使用 Exchange Online 发送向组添加团队成员的通知。</span><span class="sxs-lookup"><span data-stu-id="8cae0-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="8cae0-105">这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。</span><span class="sxs-lookup"><span data-stu-id="8cae0-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![示例 Outlook 电子邮件标题屏幕截图，显示已将用户添加到组。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="8cae0-107">团队也使用 Microsoft Exchange Online 在添加团队成员时向这些成员发送通知。</span><span class="sxs-lookup"><span data-stu-id="8cae0-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="8cae0-108">区别在于域的 SMTP 邮件 FQDN 是为商业/业务租户"@email.teams.microsoft.com"和"@GCC-email.teams.com"的政府租户，无法捕获的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="8cae0-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![示例 Outlook 电子邮件标题屏幕截图，显示已将用户添加到组。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="8cae0-110">对于最佳结果和无缝操作，请考虑添加到"允许发件人域"列表为 Exchange Online 的垃圾邮件配置中的 Microsoft 团队 SMTP 域：</span><span class="sxs-lookup"><span data-stu-id="8cae0-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![Exchange Online 垃圾邮件配置设置的“允许列表”部分屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
