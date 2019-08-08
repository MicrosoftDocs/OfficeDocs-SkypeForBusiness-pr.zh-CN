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
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: anprakas
search.appverid: MET150
description: 了解如何将 Microsoft 团队 SMTP 域添加为 Exchange Online 中允许的发件人域, 以向团队成员发送通知。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dc4b72e973bf6763b817c9bc4f133961cd000f7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245758"
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-allowed-sender-domain-in-exchange-online"></a><span data-ttu-id="79710-103">在 Exchange Online 中将 Microsoft Teams SMTP 域添加为允许的发件人域</span><span class="sxs-lookup"><span data-stu-id="79710-103">Add the Microsoft Teams SMTP domain as an allowed sender domain in Exchange Online</span></span> 
=============================================================================

<span data-ttu-id="79710-104">在管理控制台中或通过使用 Outlook 创建 Office 365 组时，使用 Exchange Online 发送向组添加团队成员的通知。</span><span class="sxs-lookup"><span data-stu-id="79710-104">Whether you create an Office 365 Group in the admin console or by using Outlook, Exchange Online is used to send notifications of a team member being added to a Group.</span></span> <span data-ttu-id="79710-105">这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。</span><span class="sxs-lookup"><span data-stu-id="79710-105">These messages are generated from your tenant as they represent your default domain SMTP FQDN.</span></span>

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

<span data-ttu-id="79710-107">团队也使用 Microsoft Exchange Online 在添加团队成员时向这些成员发送通知。</span><span class="sxs-lookup"><span data-stu-id="79710-107">Teams uses Microsoft Exchange Online as well to send notifications to team members when they’ve been added.</span></span> <span data-ttu-id="79710-108">不同于 SMTP 邮件的域 FQDN 是 @email "teams.microsoft.com" (对于商业/商业租户), "@GCC-email.teams.com" 适用于政府租户, 并且可能被垃圾邮件筛选器捕获。</span><span class="sxs-lookup"><span data-stu-id="79710-108">The difference being the domain FQDN of the SMTP message is “@email.teams.microsoft.com” for Commercial/Business tenants and "@GCC-email.teams.com" for Government tenants and could be caught by spam filtering.</span></span>

![显示添加到组中的用户的邮件头的屏幕截图。](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

<span data-ttu-id="79710-110">为获得最佳效果和无缝操作, 请考虑将 Microsoft 团队 SMTP 域添加到 Exchange Online 垃圾邮件配置中的 "允许的发件人域" 列表:</span><span class="sxs-lookup"><span data-stu-id="79710-110">For best result and seamless operation, consider adding the Microsoft Teams SMTP domain to your “allowed sender domains” list in your Exchange Online spam configuration:</span></span>

![垃圾邮件配置设置的 "允许列表" 部分的屏幕截图](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
