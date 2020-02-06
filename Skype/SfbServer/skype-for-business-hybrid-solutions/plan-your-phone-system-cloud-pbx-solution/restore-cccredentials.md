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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: aeca610b-db0a-45cf-95b9-ae9a6bbccb45
description: Restore Cc-凭据 cmdlet 用于还原当前 Skype for business Cloud Connector Edition 部署的所有凭据。
ms.openlocfilehash: b2cd35b284bcd7e49aabbaa3055c397915565d09
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824238"
---
# <a name="restore-cccredentials"></a><span data-ttu-id="e3d70-103">Restore-CcCredentials</span><span class="sxs-lookup"><span data-stu-id="e3d70-103">Restore-CcCredentials</span></span>
 
<span data-ttu-id="e3d70-104">Restore Cc-凭据 cmdlet 用于还原当前 Skype for business Cloud Connector Edition 部署的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="e3d70-104">The Restore Cc-Credentials cmdlet restores all credentials of the current Skype for Business Cloud Connector Edition deployment.</span></span> 
  
<span data-ttu-id="e3d70-105">此 cmdlet 适用于 Skype for Business 云连接器版本2.1。</span><span class="sxs-lookup"><span data-stu-id="e3d70-105">This cmdlet applies to Skype for Business Cloud Connector Edition 2.1.</span></span>
  
```powershell
Restore-CcCredentials 
```

## <a name="detailed-description"></a><span data-ttu-id="e3d70-106">详细说明</span><span class="sxs-lookup"><span data-stu-id="e3d70-106">Detailed Description</span></span>

<span data-ttu-id="e3d70-107">Restore-CcCredentials cmdlet 将清理所有凭据，并提示你重新输入用于当前 Skype for Business 云连接器部署的所有凭据。</span><span class="sxs-lookup"><span data-stu-id="e3d70-107">The Restore-CcCredentials cmdlet cleans up all credentials and prompts you to re-enter all the credentials used for the current Skype for Business Cloud Connector deployment.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="e3d70-108">参数</span><span class="sxs-lookup"><span data-stu-id="e3d70-108">Parameters</span></span>

<span data-ttu-id="e3d70-109">无</span><span class="sxs-lookup"><span data-stu-id="e3d70-109">None</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e3d70-110">输入类型</span><span class="sxs-lookup"><span data-stu-id="e3d70-110">Input Types</span></span>

<span data-ttu-id="e3d70-111">无。</span><span class="sxs-lookup"><span data-stu-id="e3d70-111">None.</span></span> <span data-ttu-id="e3d70-112">Restore CcCredentials cmdlet 不接受流水线输入。</span><span class="sxs-lookup"><span data-stu-id="e3d70-112">The Restore-CcCredentials cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e3d70-113">返回类型</span><span class="sxs-lookup"><span data-stu-id="e3d70-113">Return Types</span></span>

<span data-ttu-id="e3d70-114">无。</span><span class="sxs-lookup"><span data-stu-id="e3d70-114">None.</span></span>
  
## <a name="example"></a><span data-ttu-id="e3d70-115">示例</span><span class="sxs-lookup"><span data-stu-id="e3d70-115">Example</span></span>

<span data-ttu-id="e3d70-116">以下示例将还原当前云连接器部署的所有凭据：</span><span class="sxs-lookup"><span data-stu-id="e3d70-116">The following example restores all credentials of the current Cloud Connector deployment:</span></span>
  
```powershell
    PS C:\>Restore-CcCredentials
```

## <a name="see-also"></a><span data-ttu-id="e3d70-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3d70-117">See also</span></span>

[<span data-ttu-id="e3d70-118">Get-CcCredential</span><span class="sxs-lookup"><span data-stu-id="e3d70-118">Get-CcCredential</span></span>](get-cccredential.md)
  
[<span data-ttu-id="e3d70-119">Set-CcCredential</span><span class="sxs-lookup"><span data-stu-id="e3d70-119">Set-CcCredential</span></span>](set-cccredential.md)
  

