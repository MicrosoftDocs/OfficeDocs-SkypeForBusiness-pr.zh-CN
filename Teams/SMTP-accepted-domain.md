---
title: "在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "了解如何在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域以向团队成员发送通知。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: c33cba163d3395be7214caf5df4e87eaa164e020
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="add-the-microsoft-teams-smtp-domain-as-an-accepted-domain-in-exchange-online"></a>在 Exchange Online 中将 Microsoft Teams SMTP 域添加为接受的域 
=============================================================================

在管理控制台中或通过使用 Outlook 创建 Office 365 组时，使用 Exchange Online 发送向组添加团队成员的通知。 这些邮件是从你的租户生成的，因为其代表你的默认域 SMTP FQDN。

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image1.jpg)

团队也使用 Microsoft Exchange Online 在添加团队成员时向这些成员发送通知。 SMTP 邮件的域 FQDN 的区别是“@email.teams.microsoft.com”，垃圾邮件筛选可能会捕获它。 如下图所示，Outlook 将此邮件视为来自外部发件人，这受标准安全功能（例如阻止图片和某些内容）的约束。

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image2.jpg)

为了获得最佳效果以及实现无缝操作，请考虑在 Exchange Online 垃圾邮件配置中将 Microsoft Teams SMTP 域添加到你的“接受的域”列表：

![](media/Add_the_Microsoft_Teams_SMTP_domain_as_an_accepted_domain_in_Exchange_Online_image3.png)
