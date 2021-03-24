---
title: 共享到 Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 了解"共享到 Teams"功能，该功能允许用户将电子邮件和电子邮件附件从 Outlook 共享到 Teams 的任何聊天或频道。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: af5c2f6029b0c5314c507de7734abf8c479af709
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098218"
---
# <a name="share-to-teams-from-outlook"></a>从 Outlook 共享到 Teams

从 Outlook 共享到 Teams (共享到 Teams) 使用户能够将电子邮件（包括附件）从 Outlook 共享到 Teams 中的任意聊天或频道。

## <a name="outlook-add-in-for-share-to-teams"></a>用于共享到 Teams 的 Outlook 加载项 

"共享到 Teams"功能需要 Outlook 的加载项。 每当用户登录到 Teams Web 应用或 Teams 桌面客户端时，都会自动安装此加载项。

> [!NOTE]
> 请务必查看 [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 中的 Outlook 加载项和 [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 中的客户端访问规则，以确保 Outlook 加载项正常运行。 此外，禁用连接体验可能会阻止 Outlook 的加载项正常工作。 有关详细信息 [，请参阅 Office 中的](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 连接体验。  

"共享到 Teams"使用与用户向频道发送电子邮件时相同的传输机制。 若要共享到聊天， (电子邮件附件) 将复制到发件人的 OneDrive。 若要共享到频道，电子邮件和附件将复制到 SharePoint 中的 **"电子邮件** "文件夹。

适用于"共享到 Teams"的 Outlook 加载项使用要求集 1.7，如 [Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)加载项文档中详述，其中包括有关 Outlook 加载项的详细信息、Outlook 加载项的环境要求，以及要求集 1.7 支持的特定 Outlook 客户端。

## <a name="enabling-or-disabling-share-to-teams"></a>启用或禁用"共享到 Teams"

可以使用以下 PowerShell cmdlet 选择性地按用户禁用或启用"共享到 Teams"的 Outlook 加载项。

> [!NOTE]
> 只有在安装加载项后，才能禁用加载项。 若要强制禁用租户中的所有用户，请定期运行脚本。

若要禁用"共享到 Teams"使用的 Outlook 加载项，请运行此处[的 cmdlet。](/powershell/module/exchange/disable-app?view=exchange-ps) 

若要为"共享到 Teams"使用的 Outlook 启用加载项，请运行此处[找到的 cmdlet。](/powershell/module/exchange/enable-app?view=exchange-ps)

## <a name="browsers-and-single-sign-on"></a>浏览器和单一登录

在 Outlook 网页版和 Outlook 桌面客户端中，共享到 Teams 依赖于浏览器 WebView。 有关 [哪些客户端使用哪些特定浏览器](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 的详细信息，请参阅 Office 加载项使用的浏览器。 

> [!IMPORTANT]
> 共享到 Teams 需要为用户的浏览器启用第三方 Cookie 和本地存储访问权限。

共享到 Teams 使用单一登录 (SSO) ，这意味着用户在通过共享到 Teams 使用加载项时不需要提供凭据。 默认情况下，SSO for Outlook 网页 https://outlook.office365.com/owa/extSSO.aspx 支持 https://outlook.office.com/owa/extSSO.aspx 并回复 URL。 对于虚域，管理员需要添加相应的 Azure Active Directory 回复 URL。