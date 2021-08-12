---
title: 共享到Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 了解"共享到Teams"功能，该功能允许用户将电子邮件和电子邮件附件从 Outlook 共享到任何聊天或Teams。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 073f5ecf262d51853aecf14f982af144434791b19be617887f4ac788f11b301c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312500"
---
# <a name="share-to-teams-from-outlook"></a>从Teams共享到Outlook

通过共享Teams共享Outlook (共享Teams) 用户可以将电子邮件（包括附件）从 Outlook 共享到 Teams 中任何聊天或Teams。

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook共享到Teams 

"共享到Teams"功能需要一个加载项用于Outlook。 每当用户登录到 Teams Web 应用或 Teams 客户端时，都会自动安装此加载项。

> [!NOTE]
> 请务必查看[Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) Outlook 中的加载项Exchange Online客户端访问规则[Outlook](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)正常运行。 此外，禁用连接体验可能会阻止Outlook加载项正常工作。 有关详细信息[，请参阅Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)连接体验。  

共享到Teams使用与用户通过电子邮件发送通道时相同的传输机制。 若要共享到聊天，电子邮件 (包括电子邮件附件) 将复制到发件人的OneDrive。 若要共享到频道，电子邮件和附件将复制到"电子邮件"文件夹中SharePoint。 

Outlook 共享到 Teams 的 Outlook 加载项使用要求集 1.7，如[Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)加载项文档详述，其中包括有关 Outlook 加载项的详细信息、Outlook 加载项的环境要求，以及要求集 1.7 支持的特定 Outlook 客户端。

## <a name="enabling-or-disabling-share-to-teams"></a>启用或禁用共享到Teams

Outlook PowerShell cmdlet 选择性地禁用或启用Teams共享到用户的共享加载项。

> [!NOTE]
> 只有在安装加载项后，才能禁用加载项。 若要强制禁用租户中的所有用户，请定期运行脚本。

若要禁用共享用于Outlook的加载项Teams，请运行此处找到的[cmdlet。](/powershell/module/exchange/disable-app?view=exchange-ps) 

若要为共享用于Outlook的加载项Teams，请运行此处[的 cmdlet。](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>浏览器和单一登录

共享到Teams（Outlook 网页版和Outlook客户端）都依赖于浏览器 WebView。 有关[哪些客户端使用Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)的详细信息，请参阅加载项使用的浏览器。 

> [!IMPORTANT]
> 共享Teams需要为用户的浏览器启用第三方 Cookie 和本地存储访问权限。

共享Teams使用单一登录 (SSO) ，这意味着用户在通过"共享到共享"功能使用加载项时不需要提供Teams。 默认情况下，Outlook 网页版 https://outlook.office365.com/owa/extSSO.aspx SSO 支持和 https://outlook.office.com/owa/extSSO.aspx 回复 URL。 对于虚域，管理员需要添加相应的Azure Active Directory URL。