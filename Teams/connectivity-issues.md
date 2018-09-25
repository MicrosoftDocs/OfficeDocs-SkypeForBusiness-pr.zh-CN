---
title: 对 Microsoft Teams 客户端的连接问题进行故障排除
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
description: 对 Microsoft Teams 客户端的连接问题（主要是由防火墙或代理连接导致的）进行故障排除，以及了解如何解决问题。
appliesto:
- Microsoft Teams
ms.openlocfilehash: b95ed6f223b9ec2f5c72a0d387fc1bfd9e693881
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012134"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="3f7ba-103">对 Microsoft Teams 客户端的连接问题进行故障排除</span><span class="sxs-lookup"><span data-stu-id="3f7ba-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="3f7ba-104">在 Microsoft Teams 客户端上发现的大多数问题都可以追溯到防火墙或代理连接。</span><span class="sxs-lookup"><span data-stu-id="3f7ba-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="3f7ba-105">确认是否在你的防火墙或代理中打开了必需的 URL、IP 地址和端口可以最大限度地减少不必要的故障排除</span><span class="sxs-lookup"><span data-stu-id="3f7ba-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="3f7ba-106">有关 Url 和 Ip 的 Microsoft 团队所需的特定信息，请参阅[Office 365 Url 和 IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支持文章。</span><span class="sxs-lookup"><span data-stu-id="3f7ba-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="3f7ba-107">以下应用场景需要在防火墙中打开特定的 URL 和端口。</span><span class="sxs-lookup"><span data-stu-id="3f7ba-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="3f7ba-108">身份验证</span><span class="sxs-lookup"><span data-stu-id="3f7ba-108">Authentication</span></span>

-   <span data-ttu-id="3f7ba-109">Microsoft Teams 客户端连接</span><span class="sxs-lookup"><span data-stu-id="3f7ba-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="3f7ba-110">协作</span><span class="sxs-lookup"><span data-stu-id="3f7ba-110">Collaboration</span></span>

-   <span data-ttu-id="3f7ba-111">媒体</span><span class="sxs-lookup"><span data-stu-id="3f7ba-111">Media</span></span>

-   <span data-ttu-id="3f7ba-112">共享服务</span><span class="sxs-lookup"><span data-stu-id="3f7ba-112">Shared Services</span></span>

-   <span data-ttu-id="3f7ba-113">第三方集成</span><span class="sxs-lookup"><span data-stu-id="3f7ba-113">Third Party Integration</span></span>

-   <span data-ttu-id="3f7ba-114">Skype for Business 互操作性</span><span class="sxs-lookup"><span data-stu-id="3f7ba-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="3f7ba-115">Skype for Business 客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="3f7ba-115">Skype for Business Client Interoperability</span></span>
