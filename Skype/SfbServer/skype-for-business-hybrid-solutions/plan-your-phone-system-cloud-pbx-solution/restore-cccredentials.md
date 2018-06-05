---
title: 还原 CcCredentials
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
ms.openlocfilehash: bb74444c5f63b792abf6c12c317c1a824298426c
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569731"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="bdd13-103">还原 CcCredentials</span><span class="sxs-lookup"><span data-stu-id="bdd13-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="bdd13-104">还原抄送凭据 cmdlet 还原所有业务云连接器 Edition 部署中的当前 Skype 的凭据。</span><span class="sxs-lookup"><span data-stu-id="bdd13-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="bdd13-105">此 cmdlet 适用于 Skype 的业务云连接器 Edition 2.1。</span><span class="sxs-lookup"><span data-stu-id="bdd13-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="bdd13-106">详细说明</span><span class="sxs-lookup"><span data-stu-id="bdd13-106">Detailed Description</span></span>

<span data-ttu-id="bdd13-107">还原 CcCredentials cmdlet 清除所有凭据，并提示您重新输入用于当前 Skype 商业云连接器部署的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="bdd13-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="bdd13-108">参数</span><span class="sxs-lookup"><span data-stu-id="bdd13-108">Parameters</span></span>

<span data-ttu-id="bdd13-109">无</span><span class="sxs-lookup"><span data-stu-id="bdd13-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="bdd13-110">输入类型</span><span class="sxs-lookup"><span data-stu-id="bdd13-110">Input Types</span></span>

<span data-ttu-id="bdd13-111">无。</span><span class="sxs-lookup"><span data-stu-id="bdd13-111">None.</span></span> <span data-ttu-id="bdd13-112">还原 CcCredentials cmdlet 不接受通过管道传递的输入。</span><span class="sxs-lookup"><span data-stu-id="bdd13-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="bdd13-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="bdd13-113">Return Types</span></span>

<span data-ttu-id="bdd13-114">无。</span><span class="sxs-lookup"><span data-stu-id="bdd13-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="bdd13-115">示例</span><span class="sxs-lookup"><span data-stu-id="bdd13-115">Example</span></span>

<span data-ttu-id="bdd13-116">以下示例恢复所有凭据的当前云连接器部署：</span><span class="sxs-lookup"><span data-stu-id="bdd13-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="bdd13-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdd13-117">See also</span></span>

[<span data-ttu-id="bdd13-118">Get CcCredential</span><span class="sxs-lookup"><span data-stu-id="bdd13-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="bdd13-119">设置 CcCredential</span><span class="sxs-lookup"><span data-stu-id="bdd13-119">Set-CcCredential</span></span>](set-cccredential.md)
  

