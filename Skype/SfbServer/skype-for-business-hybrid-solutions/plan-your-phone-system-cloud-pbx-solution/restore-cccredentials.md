---
title: 还原-CcCredentials
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 还原抄送凭据 cmdlet 将恢复商务云连接器版部署当前 Skype 的所有凭据。
ms.openlocfilehash: 045d7f651408b1cbdbd508966da3272ac61d7c04
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="restore-cccredentials"></a><span data-ttu-id="825f8-103">还原-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="825f8-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="825f8-104">还原抄送凭据 cmdlet 将恢复商务云连接器版部署当前 Skype 的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="825f8-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="825f8-105">此 cmdlet 适用于 Skype 业务云连接器版本 2.1。</span><span class="sxs-lookup"><span data-stu-id="825f8-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```

Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="825f8-106">详细说明</span><span class="sxs-lookup"><span data-stu-id="825f8-106">Detailed Description</span></span>

<span data-ttu-id="825f8-107">还原 CcCredentials cmdlet 清理所有凭据，并提示您重新输入所有用于业务云连接器部署当前 Skype 的凭据。</span><span class="sxs-lookup"><span data-stu-id="825f8-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="825f8-108">参数</span><span class="sxs-lookup"><span data-stu-id="825f8-108">Parameters</span></span>

<span data-ttu-id="825f8-109">无</span><span class="sxs-lookup"><span data-stu-id="825f8-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="825f8-110">输入类型</span><span class="sxs-lookup"><span data-stu-id="825f8-110">Input Types</span></span>

<span data-ttu-id="825f8-111">无。</span><span class="sxs-lookup"><span data-stu-id="825f8-111">None.</span></span> <span data-ttu-id="825f8-112">还原-CcCredentials cmdlet 不接受管道的输入。</span><span class="sxs-lookup"><span data-stu-id="825f8-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="825f8-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="825f8-113">Return Types</span></span>

<span data-ttu-id="825f8-114">无。</span><span class="sxs-lookup"><span data-stu-id="825f8-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="825f8-115">示例</span><span class="sxs-lookup"><span data-stu-id="825f8-115">Example</span></span>

<span data-ttu-id="825f8-116">下面的示例将恢复云连接器当前部署的所有凭据：</span><span class="sxs-lookup"><span data-stu-id="825f8-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="825f8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="825f8-117">See also</span></span>

[<span data-ttu-id="825f8-118">获得 CcCredential</span><span class="sxs-lookup"><span data-stu-id="825f8-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="825f8-119">一组 CcCredential</span><span class="sxs-lookup"><span data-stu-id="825f8-119">Set-CcCredential</span></span>](set-cccredential.md)
  

