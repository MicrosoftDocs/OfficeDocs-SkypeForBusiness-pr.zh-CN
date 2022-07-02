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
description: 了解“共享到 Teams”功能，该功能允许用户将电子邮件和电子邮件附件从 Outlook 共享到 Teams 中的任何聊天或频道。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: db4b3adabecf147f5adf9cadb9891892b5a82e5a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606221"
---
# <a name="share-to-teams-from-outlook"></a>从 Outlook 共享到 Teams

从 Outlook 共享到 Teams (共享到 Teams) 使用户能够共享电子邮件（包括附件）从 Outlook 到 Teams 中的任何聊天或频道。

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook Share to Teams 加载项 

“共享到 Teams”功能需要 Outlook 加载项。 每当用户登录 Teams Web 应用或 Teams 桌面客户端时，都会自动安装此加载项。

> [!NOTE]
> 请务必[查看 Exchange Online 中的 Outlook 加](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)载项和[Exchange Online中的客户端访问规则](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)，以确保 Outlook 加载项正常运行。 此外，禁用连接体验可能会阻止 Outlook 加载项正常工作。 有关详细信息，请参阅 [Office 中的连接体验](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 。  

共享到 Teams 使用与用户通过电子邮件发送频道相同的传输机制。 对于共享聊天，电子邮件 (包括电子邮件附件) 将复制到发件人的 OneDrive。 若要共享到频道，电子邮件和附件将复制到 SharePoint 中 **的电子邮件** 文件夹。

Outlook Add-in for Share to Teams 使用要求集 1.7，如 [Outlook 外接程序文档中](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)所述，其中包括有关 Outlook 外接程序的详细信息、Outlook 外接程序的环境要求，以及要求集 1.7 支持的特定 Outlook 客户端。

## <a name="enabling-or-disabling-share-to-teams"></a>启用或禁用“共享到 Teams”

可以使用以下 PowerShell cmdlet 选择性地禁用或按用户启用 Outlook Share to Teams 加载项。

> [!NOTE]
> 只有在安装加载项后，才可以禁用外接程序。 如果要对租户中的所有用户强制禁用，请定期运行脚本。

若要禁用 Share to Teams 使用的 Outlook 加载项，请运行 [此处找到的 cmdlet](/powershell/module/exchange/disable-app)。

若要启用 Share to Teams 使用的 Outlook 加载项，请运行 [此处找到的 cmdlet](/powershell/module/exchange/enable-app)。

## <a name="browsers-and-single-sign-on"></a>浏览器和单一登录

在 Outlook 网页版 和 Outlook 桌面客户端中共享到 Teams 依赖于浏览器 WebView。 有关使用哪些特定浏览器的客户端的详细信息，请参阅 [Office 加载项使用的](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 浏览器。 

> [!IMPORTANT]
> 共享到 Teams 需要为用户的浏览器启用第三方 Cookie 和本地存储访问权限。

共享到 Teams 使用单一登录 (SSO) ，这意味着用户在通过“共享到 Teams”使用外接程序时无需提供凭据。 默认情况下，SSO for Outlook 网页版 支持<https://outlook.office365.com/owa/extSSO.aspx>并<https://outlook.office.com/owa/extSSO.aspx>回复 URL。 对于虚荣域，管理员需要添加相应的 Azure Active Directory 回复 URL。
