---
title: 共享到Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 了解“共享到Teams”功能，该功能允许用户将电子邮件和电子邮件附件从Outlook共享到Teams中的任何聊天或频道。
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a768424033ff300a079fc0b505d1e9ce32a970e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682023"
---
# <a name="share-to-teams-from-outlook"></a>从Outlook共享到Teams

共享到Teams从Outlook (共享到Teams) 使用户能够共享电子邮件，包括附件，从Outlook到Teams中的任何聊天或频道。

## <a name="outlook-add-in-for-share-to-teams"></a>Outlook“共享”加载项Teams 

“共享到Teams”功能需要一个用于Outlook的加载项。 每当用户登录到 Teams Web 应用或Teams桌面客户端时，都会自动安装此加载项。

> [!NOTE]
> 请务必查看[Exchange Online中Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)和[客户端访问规则中](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)Outlook的加载项，以确保Outlook加载项正常运行。 此外，禁用连接体验可能会阻止Outlook的加载项正常工作。 有关详细信息，请参阅[Office中的连接体验](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c)。  

共享到Teams使用与用户通过电子邮件发送频道相同的传输机制。 若要与聊天共享，电子邮件 (包括电子邮件附件) 将复制到发件人的OneDrive。 若要共享到频道，电子邮件和附件将复制到SharePoint中 **的电子邮件** 文件夹。

share 到Teams Outlook外接程序使用要求集 1.7，如[Outlook外接程序文档](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)中所述，其中包括有关Outlook加载项的详细信息、Outlook外接程序的环境要求，以及要求集 1.7 支持的特定Outlook客户端。

## <a name="enabling-or-disabling-share-to-teams"></a>启用或禁用共享以Teams

可以使用以下 PowerShell cmdlet 选择性地禁用或按用户启用 share 到Teams的Outlook加载项。

> [!NOTE]
> 只有在安装加载项后，才可以禁用外接程序。 如果要对租户中的所有用户强制禁用，请定期运行脚本。

若要禁用 Share 用于Teams的Outlook加载项，请运行[此处找到的 cmdlet](/powershell/module/exchange/disable-app)。

若要为 Share 使用的Outlook启用加载项以Teams，请运行[此处找到的 cmdlet](/powershell/module/exchange/enable-app)。

## <a name="browsers-and-single-sign-on"></a>浏览器和单一登录

在Outlook 网页版和Outlook桌面客户端中，共享到Teams依赖于浏览器 WebView。 有关哪些客户端使用哪些特定浏览器的详细信息，请参阅[Office加载项使用的](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins)浏览器。 

> [!IMPORTANT]
> 共享到Teams需要为用户的浏览器启用第三方 Cookie 和本地存储访问权限。

共享到Teams使用单一登录 (SSO) ，这意味着用户在通过 Share 使用外接程序Teams时不需要提供凭据。 默认情况下，SSO for Outlook 网页版 支持<https://outlook.office365.com/owa/extSSO.aspx>并<https://outlook.office.com/owa/extSSO.aspx>回复 URL。 对于虚荣域，管理员需要添加相应的Azure Active Directory回复 URL。
