---
title: 用于测试直接路由会话边框控制器连接的 PowerShell 脚本
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本示例测试 Microsoft 团队中的直接路由会话边界控制器连接。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43d1514eff811461ac8b6ad73f7c2a215205f4e3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951257"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="9117c-103">用于测试直接路由会话边框控制器连接的 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="9117c-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="9117c-104">SIP 测试客户端是一个示例 PowerShell 脚本，可用于测试 Microsoft 团队中的直接路由会话边界控制器（SBC）连接。</span><span class="sxs-lookup"><span data-stu-id="9117c-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="9117c-105">此脚本通过直接路由测试客户配对的会话初始协议（SIP）干线的基本功能。</span><span class="sxs-lookup"><span data-stu-id="9117c-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="9117c-106">该脚本将 SIP 测试提交给测试运行程序，等待结果，然后以可读的格式呈现。</span><span class="sxs-lookup"><span data-stu-id="9117c-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="9117c-107">你可以使用此脚本测试以下方案：</span><span class="sxs-lookup"><span data-stu-id="9117c-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="9117c-108">出站和入站呼叫</span><span class="sxs-lookup"><span data-stu-id="9117c-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="9117c-109">同时拨打</span><span class="sxs-lookup"><span data-stu-id="9117c-109">Simultaneous ring</span></span>
- <span data-ttu-id="9117c-110">媒体升级</span><span class="sxs-lookup"><span data-stu-id="9117c-110">Media escalation</span></span>
- <span data-ttu-id="9117c-111">顾问式转移</span><span class="sxs-lookup"><span data-stu-id="9117c-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="9117c-112">下载脚本和文档</span><span class="sxs-lookup"><span data-stu-id="9117c-112">Download the script and documentation</span></span>

<span data-ttu-id="9117c-113">下载[SIP 测试器客户端脚本和文档](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="9117c-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="9117c-114">SIP 测试客户端脚本仅支持 adal.ps 版本3.19.8.1。</span><span class="sxs-lookup"><span data-stu-id="9117c-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="9117c-115">如果使用 adal.ps 的更高版本，则会返回错误。</span><span class="sxs-lookup"><span data-stu-id="9117c-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
