---
title: 用于测试直接路由会话边界控制器连接的 PowerShell 脚本
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: 使用此 PowerShell 脚本示例在 Microsoft Teams 中测试直接路由会话边界控制器连接。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834272"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a><span data-ttu-id="8312a-103">用于测试直接路由会话边界控制器连接的 PowerShell 脚本</span><span class="sxs-lookup"><span data-stu-id="8312a-103">PowerShell script to test Direct Routing Session Border Controller connections</span></span>

<span data-ttu-id="8312a-104">SIP 测试器客户端是一个示例 PowerShell 脚本，可用于测试 Microsoft Teams 中的直接路由会话边界 (SBC) 连接。</span><span class="sxs-lookup"><span data-stu-id="8312a-104">SIP Tester client is a sample PowerShell script that you can use to test Direct Routing Session Border Controller (SBC) connections in Microsoft Teams.</span></span> <span data-ttu-id="8312a-105">此脚本使用直接路由测试客户配对会话启动协议 (SIP) 的基本功能。</span><span class="sxs-lookup"><span data-stu-id="8312a-105">This script tests basic functionality of a customer-paired Session Initiation Protocol (SIP) trunk with Direct Routing.</span></span>

<span data-ttu-id="8312a-106">该脚本将 SIP 测试提交到测试运行程序，等待结果，然后以人工可读的格式显示它。</span><span class="sxs-lookup"><span data-stu-id="8312a-106">The script submits an SIP test to the test runner, waits for the result, and then presents it in a human-readable format.</span></span> <span data-ttu-id="8312a-107">可以使用此脚本测试以下方案：</span><span class="sxs-lookup"><span data-stu-id="8312a-107">You can use this script to test the following scenarios:</span></span>

- <span data-ttu-id="8312a-108">出站和入站呼叫</span><span class="sxs-lookup"><span data-stu-id="8312a-108">Outbound and inbound calls</span></span>
- <span data-ttu-id="8312a-109">同时响铃</span><span class="sxs-lookup"><span data-stu-id="8312a-109">Simultaneous ring</span></span>
- <span data-ttu-id="8312a-110">媒体升级</span><span class="sxs-lookup"><span data-stu-id="8312a-110">Media escalation</span></span>
- <span data-ttu-id="8312a-111">咨询转接</span><span class="sxs-lookup"><span data-stu-id="8312a-111">Consultative transfer</span></span>

## <a name="download-the-script-and-documentation"></a><span data-ttu-id="8312a-112">下载脚本和文档</span><span class="sxs-lookup"><span data-stu-id="8312a-112">Download the script and documentation</span></span>

<span data-ttu-id="8312a-113">下载 [SIP Tester 客户端脚本和文档](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="8312a-113">Download the [SIP Tester client script and documentation](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).</span></span>

  > [!NOTE]
  > <span data-ttu-id="8312a-114">SIP 测试器客户端脚本仅adal.ps 3.19.8.1 版。</span><span class="sxs-lookup"><span data-stu-id="8312a-114">SIP Tester client script only supports adal.ps version 3.19.8.1.</span></span> <span data-ttu-id="8312a-115">如果使用更高版本的更高版本的 adal.ps将返回错误。</span><span class="sxs-lookup"><span data-stu-id="8312a-115">An error will be returned if a later version of the adal.ps is used.</span></span>
  
  
