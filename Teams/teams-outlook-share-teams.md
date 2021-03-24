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
# <a name="share-to-teams-from-outlook"></a><span data-ttu-id="e3a73-103">从 Outlook 共享到 Teams</span><span class="sxs-lookup"><span data-stu-id="e3a73-103">Share to Teams from Outlook</span></span>

<span data-ttu-id="e3a73-104">从 Outlook 共享到 Teams (共享到 Teams) 使用户能够将电子邮件（包括附件）从 Outlook 共享到 Teams 中的任意聊天或频道。</span><span class="sxs-lookup"><span data-stu-id="e3a73-104">Share to Teams from Outlook (Share to Teams) enables users to share emails, including attachments, from Outlook to any chat or channel in Teams.</span></span>

## <a name="outlook-add-in-for-share-to-teams"></a><span data-ttu-id="e3a73-105">用于共享到 Teams 的 Outlook 加载项</span><span class="sxs-lookup"><span data-stu-id="e3a73-105">Outlook add-in for Share to Teams</span></span> 

<span data-ttu-id="e3a73-106">"共享到 Teams"功能需要 Outlook 的加载项。</span><span class="sxs-lookup"><span data-stu-id="e3a73-106">The Share to Teams feature requires an add-in for Outlook.</span></span> <span data-ttu-id="e3a73-107">每当用户登录到 Teams Web 应用或 Teams 桌面客户端时，都会自动安装此加载项。</span><span class="sxs-lookup"><span data-stu-id="e3a73-107">This add-in is installed automatically whenever a user logs on to either the Teams Web app or the Teams desktop client.</span></span>

> [!NOTE]
> <span data-ttu-id="e3a73-108">请务必查看 [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) 中的 Outlook 加载项和 [Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) 中的客户端访问规则，以确保 Outlook 加载项正常运行。</span><span class="sxs-lookup"><span data-stu-id="e3a73-108">Be sure to review [Add-ins for Outlook in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook) and [Client Access Rules in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) to make sure your add-ins for Outlook function correctly.</span></span> <span data-ttu-id="e3a73-109">此外，禁用连接体验可能会阻止 Outlook 的加载项正常工作。</span><span class="sxs-lookup"><span data-stu-id="e3a73-109">Also, disabling connected experiences can prevent add-ins for Outlook from working properly.</span></span> <span data-ttu-id="e3a73-110">有关详细信息 [，请参阅 Office 中的](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) 连接体验。</span><span class="sxs-lookup"><span data-stu-id="e3a73-110">See [Connected experiences in Office](https://support.microsoft.com/topic/connected-experiences-in-office-8d2c04f7-6428-4e6e-ac58-5828d4da5b7c) for more information.</span></span>  

<span data-ttu-id="e3a73-111">"共享到 Teams"使用与用户向频道发送电子邮件时相同的传输机制。</span><span class="sxs-lookup"><span data-stu-id="e3a73-111">Share to Teams uses the same transport mechanism as when a user emails a channel.</span></span> <span data-ttu-id="e3a73-112">若要共享到聊天， (电子邮件附件) 将复制到发件人的 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="e3a73-112">For sharing to chats, emails (including email attachments) are copied to the sender’s OneDrive.</span></span> <span data-ttu-id="e3a73-113">若要共享到频道，电子邮件和附件将复制到 SharePoint 中的 **"电子邮件** "文件夹。</span><span class="sxs-lookup"><span data-stu-id="e3a73-113">For sharing to channels, emails and attachments are copied to the **Email messages** folder in SharePoint.</span></span>

<span data-ttu-id="e3a73-114">适用于"共享到 Teams"的 Outlook 加载项使用要求集 1.7，如 [Outlook](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook)加载项文档中详述，其中包括有关 Outlook 加载项的详细信息、Outlook 加载项的环境要求，以及要求集 1.7 支持的特定 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="e3a73-114">The Outlook add-in for Share to Teams uses requirement set 1.7, as detailed in [Outlook add-ins documentation](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/add-ins-for-outlook), which includes details on Outlook add-ins, environment requirements for Outlook add-ins, and the specific Outlook clients that are supported with requirement set 1.7.</span></span>

## <a name="enabling-or-disabling-share-to-teams"></a><span data-ttu-id="e3a73-115">启用或禁用"共享到 Teams"</span><span class="sxs-lookup"><span data-stu-id="e3a73-115">Enabling or disabling Share to Teams</span></span>

<span data-ttu-id="e3a73-116">可以使用以下 PowerShell cmdlet 选择性地按用户禁用或启用"共享到 Teams"的 Outlook 加载项。</span><span class="sxs-lookup"><span data-stu-id="e3a73-116">The Outlook add-in for Share to Teams can be selectively disabled or enabled on a per-user basis using the following PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="e3a73-117">只有在安装加载项后，才能禁用加载项。</span><span class="sxs-lookup"><span data-stu-id="e3a73-117">Disabling the add-in is only possible after the add-in has been installed.</span></span> <span data-ttu-id="e3a73-118">若要强制禁用租户中的所有用户，请定期运行脚本。</span><span class="sxs-lookup"><span data-stu-id="e3a73-118">If you would like to enforce disabling for all users in your tenant, run a script periodically.</span></span>

<span data-ttu-id="e3a73-119">若要禁用"共享到 Teams"使用的 Outlook 加载项，请运行此处[的 cmdlet。](/powershell/module/exchange/disable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="e3a73-119">To disable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/disable-app?view=exchange-ps).</span></span> 

<span data-ttu-id="e3a73-120">若要为"共享到 Teams"使用的 Outlook 启用加载项，请运行此处[找到的 cmdlet。](/powershell/module/exchange/enable-app?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="e3a73-120">To enable the add-in for Outlook used by Share to Teams, run the [cmdlet found here](/powershell/module/exchange/enable-app?view=exchange-ps).</span></span>

## <a name="browsers-and-single-sign-on"></a><span data-ttu-id="e3a73-121">浏览器和单一登录</span><span class="sxs-lookup"><span data-stu-id="e3a73-121">Browsers and Single Sign-on</span></span>

<span data-ttu-id="e3a73-122">在 Outlook 网页版和 Outlook 桌面客户端中，共享到 Teams 依赖于浏览器 WebView。</span><span class="sxs-lookup"><span data-stu-id="e3a73-122">Share to Teams, in both Outlook on the web and Outlook desktop clients, relies on a browser WebView.</span></span> <span data-ttu-id="e3a73-123">有关 [哪些客户端使用哪些特定浏览器](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) 的详细信息，请参阅 Office 加载项使用的浏览器。</span><span class="sxs-lookup"><span data-stu-id="e3a73-123">See [Browsers used by Office Add-ins](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins) for details on which clients use which specific browsers.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e3a73-124">共享到 Teams 需要为用户的浏览器启用第三方 Cookie 和本地存储访问权限。</span><span class="sxs-lookup"><span data-stu-id="e3a73-124">Share to Teams requires both third-party cookies and local storage access to be enabled for users' browsers.</span></span>

<span data-ttu-id="e3a73-125">共享到 Teams 使用单一登录 (SSO) ，这意味着用户在通过共享到 Teams 使用加载项时不需要提供凭据。</span><span class="sxs-lookup"><span data-stu-id="e3a73-125">Share to Teams uses Single Sign-on (SSO), which means users don’t need to provide their credentials when using the add-in via Share to Teams.</span></span> <span data-ttu-id="e3a73-126">默认情况下，SSO for Outlook 网页 https://outlook.office365.com/owa/extSSO.aspx 支持 https://outlook.office.com/owa/extSSO.aspx 并回复 URL。</span><span class="sxs-lookup"><span data-stu-id="e3a73-126">SSO for Outlook on the web supports https://outlook.office365.com/owa/extSSO.aspx and https://outlook.office.com/owa/extSSO.aspx reply URLs by default.</span></span> <span data-ttu-id="e3a73-127">对于虚域，管理员需要添加相应的 Azure Active Directory 回复 URL。</span><span class="sxs-lookup"><span data-stu-id="e3a73-127">For vanity domains, administrators need to add the appropriate Azure Active Directory reply URL.</span></span>