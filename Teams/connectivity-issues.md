---
title: 使用 Microsoft Teams 客户端解决连接性问题
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: 解决连接问题使用的 Microsoft 团队的客户端，主要由防火墙或代理连接，并了解如何解决此问题。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 70255ccbd1c0547c44bb30dee78ffa14d1586705
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568421"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="4e6f7-103">使用 Microsoft Teams 客户端解决连接性问题</span><span class="sxs-lookup"><span data-stu-id="4e6f7-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="4e6f7-104">使用 Microsoft 团队客户端发现的大多数问题可以追溯到防火墙或代理的连接。</span><span class="sxs-lookup"><span data-stu-id="4e6f7-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="4e6f7-105">验证此必需的 Url、 IP 地址和防火墙中打开端口或代理将减少不必要的故障排除。</span><span class="sxs-lookup"><span data-stu-id="4e6f7-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="4e6f7-106">有关 Url 和 Ip 的 Microsoft 团队所需的特定信息，请参阅[Office 365 Url 和 IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支持文章。</span><span class="sxs-lookup"><span data-stu-id="4e6f7-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="4e6f7-107">以下方案需要特定的 Url，在防火墙中打开端口。</span><span class="sxs-lookup"><span data-stu-id="4e6f7-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="4e6f7-108">身份验证</span><span class="sxs-lookup"><span data-stu-id="4e6f7-108">Authentication</span></span>

-   <span data-ttu-id="4e6f7-109">Microsoft 团队客户端连接</span><span class="sxs-lookup"><span data-stu-id="4e6f7-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="4e6f7-110">协作</span><span class="sxs-lookup"><span data-stu-id="4e6f7-110">Collaboration</span></span>

-   <span data-ttu-id="4e6f7-111">媒体</span><span class="sxs-lookup"><span data-stu-id="4e6f7-111">Media</span></span>

-   <span data-ttu-id="4e6f7-112">共享的服务</span><span class="sxs-lookup"><span data-stu-id="4e6f7-112">Shared Services</span></span>

-   <span data-ttu-id="4e6f7-113">第三方集成</span><span class="sxs-lookup"><span data-stu-id="4e6f7-113">Third Party Integration</span></span>

-   <span data-ttu-id="4e6f7-114">Skype 的业务互操作性</span><span class="sxs-lookup"><span data-stu-id="4e6f7-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="4e6f7-115">Skype 的业务客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="4e6f7-115">Skype for Business Client Interoperability</span></span>
