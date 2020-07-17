---
title: 解决团队客户端的连接问题
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 解决 Microsoft Teams 客户端的连接问题（主要由防火墙或代理连接导致），并了解如何进行修复。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 116ce1afef08a6f1639ed011b799f9ca43ea57f5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085228"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="a052a-103">使用 Microsoft Teams 客户端解决连接性问题</span><span class="sxs-lookup"><span data-stu-id="a052a-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="a052a-104">已发现的有关 Microsoft Teams 客户端的大多数问题都可追溯到防火墙或代理连接。</span><span class="sxs-lookup"><span data-stu-id="a052a-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="a052a-105">验证是否在防火墙或代理中打开了所需的 URL、IP 地址和端口可最大程度地减少不必要的故障排除。</span><span class="sxs-lookup"><span data-stu-id="a052a-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="a052a-106">有关 Microsoft 团队所需的 Url 和 IPs 的特定信息，请参阅[microsoft 365 和 Office 365 url 和 IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支持文章。</span><span class="sxs-lookup"><span data-stu-id="a052a-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="a052a-107">以下方案需要在防火墙中打开特定 URL 和端口。</span><span class="sxs-lookup"><span data-stu-id="a052a-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="a052a-108">身份验证</span><span class="sxs-lookup"><span data-stu-id="a052a-108">Authentication</span></span>

-   <span data-ttu-id="a052a-109">Microsoft Teams 客户端连接</span><span class="sxs-lookup"><span data-stu-id="a052a-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="a052a-110">协作</span><span class="sxs-lookup"><span data-stu-id="a052a-110">Collaboration</span></span>

-   <span data-ttu-id="a052a-111">媒体</span><span class="sxs-lookup"><span data-stu-id="a052a-111">Media</span></span>

-   <span data-ttu-id="a052a-112">共享服务</span><span class="sxs-lookup"><span data-stu-id="a052a-112">Shared Services</span></span>

-   <span data-ttu-id="a052a-113">第三方集成</span><span class="sxs-lookup"><span data-stu-id="a052a-113">Third Party Integration</span></span>

-   <span data-ttu-id="a052a-114">Skype for Business 互操作性</span><span class="sxs-lookup"><span data-stu-id="a052a-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="a052a-115">Skype for Business 客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="a052a-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="a052a-116">相关主题</span><span class="sxs-lookup"><span data-stu-id="a052a-116">Related topics</span></span>

[<span data-ttu-id="a052a-117">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="a052a-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)