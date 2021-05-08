---
title: 排查客户端Teams问题
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
ms.openlocfilehash: 25a4fc51e0bb8dec810ce921e3678a529ee7a4cf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101158"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="370f7-103">使用 Microsoft Teams 客户端解决连接性问题</span><span class="sxs-lookup"><span data-stu-id="370f7-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="370f7-104">已发现的有关 Microsoft Teams 客户端的大多数问题都可追溯到防火墙或代理连接。</span><span class="sxs-lookup"><span data-stu-id="370f7-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="370f7-105">验证是否在防火墙或代理中打开了所需的 URL、IP 地址和端口可最大程度地减少不必要的故障排除。</span><span class="sxs-lookup"><span data-stu-id="370f7-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="370f7-106">有关应用程序所需的 URL 和 IP Microsoft Teams，请参阅 Microsoft 365 和 Office 365 URL 和[IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)支持一文。</span><span class="sxs-lookup"><span data-stu-id="370f7-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="370f7-107">以下方案需要在防火墙中打开特定 URL 和端口。</span><span class="sxs-lookup"><span data-stu-id="370f7-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="370f7-108">身份验证</span><span class="sxs-lookup"><span data-stu-id="370f7-108">Authentication</span></span>

- <span data-ttu-id="370f7-109">Microsoft Teams 客户端连接</span><span class="sxs-lookup"><span data-stu-id="370f7-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="370f7-110">协作</span><span class="sxs-lookup"><span data-stu-id="370f7-110">Collaboration</span></span>

- <span data-ttu-id="370f7-111">媒体</span><span class="sxs-lookup"><span data-stu-id="370f7-111">Media</span></span>

- <span data-ttu-id="370f7-112">共享服务</span><span class="sxs-lookup"><span data-stu-id="370f7-112">Shared Services</span></span>

- <span data-ttu-id="370f7-113">第三方集成</span><span class="sxs-lookup"><span data-stu-id="370f7-113">Third Party Integration</span></span>

- <span data-ttu-id="370f7-114">Skype for Business 互操作性</span><span class="sxs-lookup"><span data-stu-id="370f7-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="370f7-115">Skype for Business 客户端互操作性</span><span class="sxs-lookup"><span data-stu-id="370f7-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="370f7-116">当Teams处于脱机或低带宽情况下时</span><span class="sxs-lookup"><span data-stu-id="370f7-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="370f7-117">好消息是，Teams处于脱机状态或低带宽情况下仍保持运行。</span><span class="sxs-lookup"><span data-stu-id="370f7-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="370f7-118">Teams将现有聊天的所有未发送消息 (保存最多 24 小时) 当您重新联机时立即发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="370f7-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="370f7-119">如果脱机时间超过 24 小时，Teams选择重新发送或删除未发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="370f7-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="370f7-120">我们正在努力将此功能添加到新聊天，并且将在本文档可用时更新此文档。</span><span class="sxs-lookup"><span data-stu-id="370f7-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="370f7-121">相关主题</span><span class="sxs-lookup"><span data-stu-id="370f7-121">Related topics</span></span>

[<span data-ttu-id="370f7-122">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="370f7-122">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)