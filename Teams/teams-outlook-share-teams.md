---
title: 共享到 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 了解“共享到 Teams”功能，该功能允许用户将 Outlook 中的电子邮件和电子邮件附件共享到 Teams 中的任何聊天或频道。
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f8334f8dbdbebce17dea4a8a4ebc8ebf798b79
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198484"
---
# <a name="share-to-teams-from-outlook"></a>从 Outlook 共享到 Teams

从 Outlook 共享到 Teams (共享到 Teams) 使用户能够将电子邮件（包括附件）从 Outlook 共享到 Teams 中的任何聊天或频道。

## <a name="outlook-add-in-for-share-to-teams"></a>用于共享到 Teams 的 Outlook 加载项 

“共享到 Teams”功能需要 Outlook 的加载项。 每当用户登录到 Teams Web 应用或 Teams 桌面客户端时，都会自动安装此加载项。

> [!NOTE]
> 请务必[查看 Exchange Online 中的 Outlook 加载项](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)和 [Exchange Online 中的客户端访问规则](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)，以确保 Outlook 加载项正常运行。 此外，禁用连接体验可能会阻止 Outlook 加载项正常工作。 有关详细信息 [，请参阅 Office 中的连接体验](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 。 加载项不支持共享邮箱。 

“共享到 Teams”使用与用户通过电子邮件发送频道时相同的传输机制。 对于共享聊天，电子邮件 (包括电子邮件附件) 将复制到发件人的 OneDrive。 若要共享到频道，电子邮件和附件将复制到 SharePoint 中的 **“Email邮件**”文件夹。

Share to Teams 的 Outlook 外接程序使用要求集 1.7，如 [Outlook 外接程序文档](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)中所述，其中包括有关 Outlook 加载项的详细信息、Outlook 外接程序的环境要求以及要求集 1.7 支持的特定 Outlook 客户端。

## <a name="enabling-or-disabling-share-to-teams"></a>启用或禁用“共享到 Teams”

可以使用以下 PowerShell cmdlet 在每个用户的基础上选择性地禁用或启用用于共享到 Teams 的 Outlook 加载项。

> [!NOTE]
> 只有在安装加载项后，才能禁用加载项。 如果要对租户中的所有用户强制禁用，请定期运行脚本。

若要禁用 Share to Teams 使用的 Outlook 加载项，请运行 [此处找到的 cmdlet](/powershell/module/exchange/disable-app)。

若要启用 Share to Teams 使用的 Outlook 加载项，请运行 [此处找到的 cmdlet](/powershell/module/exchange/enable-app)。

## <a name="browsers-and-single-sign-on"></a>浏览器和单一登录

在 Outlook 网页版 和 Outlook 桌面客户端中共享到 Teams 依赖于浏览器 WebView。 有关哪些客户端使用哪些特定浏览器的详细信息 [，请参阅 Office 外接程序使用的](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 浏览器。 

> [!IMPORTANT]
> 共享到 Teams 需要为用户的浏览器启用第三方 Cookie 和本地存储访问权限。

“共享到 Teams”使用单一登录 (SSO) ，这意味着用户在通过“共享到 Teams”使用加载项时无需提供其凭据。 默认情况下，sso for Outlook 网页版 支持<https://outlook.office365.com/owa/extSSO.aspx>和<https://outlook.office.com/owa/extSSO.aspx>回复 URL。 对于虚域，管理员需要添加相应的 Azure Active Directory 回复 URL。
