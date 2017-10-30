---
title: "对 Microsoft Teams 客户端的连接问题进行故障排除 | Microsoft 支持"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "对 Microsoft Teams 客户端的连接问题（主要是由防火墙或代理连接导致的）进行故障排除，以及了解如何解决问题。"
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: fdba24620fca80b12b4e86780b19203436e7c9f4
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2017
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="5feee-103">对 Microsoft Teams 客户端的连接问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="5feee-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="5feee-104">在 Microsoft Teams 客户端上发现的大多数问题都可以追溯到防火墙或代理连接。</span><span class="sxs-lookup"><span data-stu-id="5feee-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="5feee-105">确认是否在你的防火墙或代理中打开了必需的 URL、IP 地址和端口可以最大限度地减少不必要的故障排除</span><span class="sxs-lookup"><span data-stu-id="5feee-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="5feee-106">有关 Microsoft Teams 所需的 URL 和 IP 的特定信息，请参阅 [Office 365 URL 和 IP 地址](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams)支持文章。</span><span class="sxs-lookup"><span data-stu-id="5feee-106">For specific information on URLs and IPs required for Microsoft Teams, please reference the [Office 365 URLs and IP Address](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams) support article.</span></span> <span data-ttu-id="5feee-107">以下应用场景需要在防火墙中打开特定的 URL 和端口。</span><span class="sxs-lookup"><span data-stu-id="5feee-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="5feee-108">身份验证</span><span class="sxs-lookup"><span data-stu-id="5feee-108">Authentication</span></span>

-   <span data-ttu-id="5feee-109">Microsoft Teams 客户端连接</span><span class="sxs-lookup"><span data-stu-id="5feee-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="5feee-110">协作</span><span class="sxs-lookup"><span data-stu-id="5feee-110">collaboration</span></span>

-   <span data-ttu-id="5feee-111">媒体</span><span class="sxs-lookup"><span data-stu-id="5feee-111">Media</span></span>

-   <span data-ttu-id="5feee-112">共享服务</span><span class="sxs-lookup"><span data-stu-id="5feee-112">Shared Services</span></span>

-   <span data-ttu-id="5feee-113">第三方集成</span><span class="sxs-lookup"><span data-stu-id="5feee-113">Third Party Integration</span></span>

-   <span data-ttu-id="5feee-114">Skype for Business 互操作性</span><span class="sxs-lookup"><span data-stu-id="5feee-114">Skype for Business</span></span>

-   <span data-ttu-id="5feee-115">Skype for Business 客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="5feee-115">Skype for Business Client Interoperability</span></span>
