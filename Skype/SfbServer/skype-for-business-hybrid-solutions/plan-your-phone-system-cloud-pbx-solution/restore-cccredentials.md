---
title: Restore-CcCredentials
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: 还原抄送凭据 cmdlet 还原所有业务云连接器 Edition 部署中的当前 Skype 的凭据。
ms.openlocfilehash: 0b790b9f2edab9fade2738c3c95348be864f9017
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891466"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="f0f68-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="f0f68-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="f0f68-104">还原抄送凭据 cmdlet 还原所有业务云连接器 Edition 部署中的当前 Skype 的凭据。</span><span class="sxs-lookup"><span data-stu-id="f0f68-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="f0f68-105">此 cmdlet 适用于 Skype 的业务云连接器 Edition 2.1。</span><span class="sxs-lookup"><span data-stu-id="f0f68-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="f0f68-106">详细说明</span><span class="sxs-lookup"><span data-stu-id="f0f68-106">Detailed Description</span></span>

<span data-ttu-id="f0f68-107">还原 CcCredentials cmdlet 清除所有凭据，并提示您重新输入用于当前 Skype 商业云连接器部署的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="f0f68-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="f0f68-108">参数</span><span class="sxs-lookup"><span data-stu-id="f0f68-108">Parameters</span></span>

<span data-ttu-id="f0f68-109">无</span><span class="sxs-lookup"><span data-stu-id="f0f68-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f0f68-110">输入类型</span><span class="sxs-lookup"><span data-stu-id="f0f68-110">Input Types</span></span>

<span data-ttu-id="f0f68-111">无。</span><span class="sxs-lookup"><span data-stu-id="f0f68-111">None.</span></span> <span data-ttu-id="f0f68-112">还原 CcCredentials cmdlet 不接受通过管道传递的输入。</span><span class="sxs-lookup"><span data-stu-id="f0f68-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="f0f68-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="f0f68-113">Return Types</span></span>

<span data-ttu-id="f0f68-114">无。</span><span class="sxs-lookup"><span data-stu-id="f0f68-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="f0f68-115">示例</span><span class="sxs-lookup"><span data-stu-id="f0f68-115">Example</span></span>

<span data-ttu-id="f0f68-116">以下示例恢复所有凭据的当前云连接器部署：</span><span class="sxs-lookup"><span data-stu-id="f0f68-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="f0f68-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0f68-117">See also</span></span>

[<span data-ttu-id="f0f68-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="f0f68-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="f0f68-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="f0f68-119">Set-CcCredential</span></span>](set-cccredential.md)
  

