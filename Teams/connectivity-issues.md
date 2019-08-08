---
title: 使用 Microsoft Teams 客户端解决连接性问题
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: 解决 Microsoft 团队客户端的连接问题, 主要由防火墙或代理连接引起, 并了解如何修复它。
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79718ebc58205cd63ab291f0985e4dd7e452be3e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236548"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="44ad2-103">使用 Microsoft Teams 客户端解决连接性问题</span><span class="sxs-lookup"><span data-stu-id="44ad2-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="44ad2-104">通过 Microsoft 团队客户端发现的大多数问题都可以追溯到防火墙或代理连接。</span><span class="sxs-lookup"><span data-stu-id="44ad2-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="44ad2-105">验证在防火墙或代理中打开所需的 Url、IP 地址和端口是否会最大限度地减少不必要的故障排除。</span><span class="sxs-lookup"><span data-stu-id="44ad2-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="44ad2-106">有关 Microsoft 团队所需的 Url 和 IPs 的特定信息, 请参阅[Office 365 url 和 IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支持文章。</span><span class="sxs-lookup"><span data-stu-id="44ad2-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="44ad2-107">以下方案需要在防火墙中打开特定的 Url 和端口。</span><span class="sxs-lookup"><span data-stu-id="44ad2-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="44ad2-108">身份验证</span><span class="sxs-lookup"><span data-stu-id="44ad2-108">Authentication</span></span>

-   <span data-ttu-id="44ad2-109">Microsoft 团队客户端连接</span><span class="sxs-lookup"><span data-stu-id="44ad2-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="44ad2-110">开展</span><span class="sxs-lookup"><span data-stu-id="44ad2-110">Collaboration</span></span>

-   <span data-ttu-id="44ad2-111">媒体</span><span class="sxs-lookup"><span data-stu-id="44ad2-111">Media</span></span>

-   <span data-ttu-id="44ad2-112">共享服务</span><span class="sxs-lookup"><span data-stu-id="44ad2-112">Shared Services</span></span>

-   <span data-ttu-id="44ad2-113">第三方集成</span><span class="sxs-lookup"><span data-stu-id="44ad2-113">Third Party Integration</span></span>

-   <span data-ttu-id="44ad2-114">Skype for Business 互操作性</span><span class="sxs-lookup"><span data-stu-id="44ad2-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="44ad2-115">Skype for Business 客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="44ad2-115">Skype for Business Client Interoperability</span></span>
