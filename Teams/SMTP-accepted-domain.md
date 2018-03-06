---
title: "在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anprakas
description: "了解如何在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域以向团队成员发送通知。"
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f671d64b2928c3b5a81d38993143d9755ce42ba
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a><span data-ttu-id="dfb0d-103">在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域</span><span class="sxs-lookup"><span data-stu-id="dfb0d-103">Add the Microsoft Teams SMTP domain as an accepted domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="dfb0d-104">在管理控制台中或通过使用 Outlook 创建 Office 365 组时，使用 Exchange Online 发送向组添加团队成员的通知。</span><span class="sxs-lookup"><span data-stu-id="dfb0d-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="dfb0d-105">这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。</span><span class="sxs-lookup"><span data-stu-id="dfb0d-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![示例 Outlook 电子邮件标题屏幕截图，显示已将用户添加到组。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="dfb0d-107">团队也使用 Microsoft Exchange Online 在添加团队成员时向这些成员发送通知。</span><span class="sxs-lookup"><span data-stu-id="dfb0d-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="dfb0d-108">SMTP 邮件的域 FQDN 的区别是“@email.teams.microsoft.com”，垃圾邮件筛选可能会捕获它。</span><span class="sxs-lookup"><span data-stu-id="dfb0d-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” and could be caught by spam filtering.</span></span> <span data-ttu-id="dfb0d-109">如下图所示，Outlook 将此邮件视为来自外部发件人，这受标准安全功能（例如阻止图片和某些内容）的约束。</span><span class="sxs-lookup"><span data-stu-id="dfb0d-109">As you can see from the image below, Outlook considers this message as an external sender which is subject to standard security features such as blocking images and certain content.</span></span>

![示例 Outlook 电子邮件标题屏幕截图，显示已将用户添加到组。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="dfb0d-111">为了获得最佳效果以及实现无缝操作，请考虑在 Exchange Online 垃圾邮件配置中将 Microsoft Teams SMTP 域添加到你的“接受的域”列表：</span><span class="sxs-lookup"><span data-stu-id="dfb0d-111">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “accepted domains” list in your Exchange Online spam configuration:</span></span>

![Exchange Online 垃圾邮件配置设置的“允许列表”部分屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
