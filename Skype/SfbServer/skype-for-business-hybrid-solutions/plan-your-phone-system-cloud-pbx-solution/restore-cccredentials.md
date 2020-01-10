---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-凭据 cmdlet 用于还原当前 Skype for business Cloud Connector Edition 部署的所有凭据。
ms.openlocfilehash: adac3f0b9ca6cf392b537a9c5d0f2095021c7120
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003242"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="63226-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="63226-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="63226-104">Restore Cc-凭据 cmdlet 用于还原当前 Skype for business Cloud Connector Edition 部署的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="63226-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="63226-105">此 cmdlet 适用于 Skype for Business 云连接器版本2.1。</span><span class="sxs-lookup"><span data-stu-id="63226-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="63226-106">详细说明</span><span class="sxs-lookup"><span data-stu-id="63226-106">Detailed Description</span></span>

<span data-ttu-id="63226-107">Restore-CcCredentials cmdlet 将清理所有凭据，并提示你重新输入用于当前 Skype for Business 云连接器部署的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="63226-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="63226-108">参数</span><span class="sxs-lookup"><span data-stu-id="63226-108">Parameters</span></span>

<span data-ttu-id="63226-109">无</span><span class="sxs-lookup"><span data-stu-id="63226-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="63226-110">输入类型</span><span class="sxs-lookup"><span data-stu-id="63226-110">Input Types</span></span>

<span data-ttu-id="63226-111">无。</span><span class="sxs-lookup"><span data-stu-id="63226-111">None.</span></span> <span data-ttu-id="63226-112">Restore CcCredentials cmdlet 不接受流水线输入。</span><span class="sxs-lookup"><span data-stu-id="63226-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="63226-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="63226-113">Return Types</span></span>

<span data-ttu-id="63226-114">无。</span><span class="sxs-lookup"><span data-stu-id="63226-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="63226-115">示例</span><span class="sxs-lookup"><span data-stu-id="63226-115">Example</span></span>

<span data-ttu-id="63226-116">以下示例将还原当前云连接器部署的所有凭据：</span><span class="sxs-lookup"><span data-stu-id="63226-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="63226-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63226-117">See also</span></span>

[<span data-ttu-id="63226-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="63226-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="63226-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="63226-119">Set-CcCredential</span></span>](set-cccredential.md)
  

