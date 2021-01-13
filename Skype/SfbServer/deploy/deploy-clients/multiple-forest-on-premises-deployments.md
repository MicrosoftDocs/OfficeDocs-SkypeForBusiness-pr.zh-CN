---
title: Skype 会议室系统多林本地部署
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: 168244033a681b9aa9dc6e4c9697b7e3c7e89127
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805742"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="89e3a-103">Skype 会议室系统多林本地部署</span><span class="sxs-lookup"><span data-stu-id="89e3a-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="89e3a-104">阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="89e3a-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="89e3a-105">为了在多林中部署，Skype 会议室系统Exchange Server 2014 年 8 月 26 日发布的 2013 CU6。</span><span class="sxs-lookup"><span data-stu-id="89e3a-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="89e3a-106">避免将现有邮箱重新用于 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="89e3a-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="89e3a-107">使用新的 (删除旧邮箱，然后为 Skype 会议室) 重新创建资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="89e3a-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="89e3a-108">若要通过删除邮箱来还原丢失的会议，请参阅["连接"或"还原已删除的邮箱"。](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="89e3a-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="89e3a-109">创建邮箱后，可以使用Set-CalendarProcessing配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="89e3a-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="89e3a-110">有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="89e3a-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="89e3a-111">为 Skype 会议室系统创建 Exchange 资源邮箱后，按照单林本地部署下为 Skype for Business 启用 Skype 会议室系统帐户中的步骤操作，为 Skype for Business 启用帐户。</span><span class="sxs-lookup"><span data-stu-id="89e3a-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="89e3a-112">选项 1：创建新的资源邮箱</span><span class="sxs-lookup"><span data-stu-id="89e3a-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="89e3a-113">在多林环境中部署 Skype 会议室系统：</span><span class="sxs-lookup"><span data-stu-id="89e3a-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="89e3a-114">在 Active Directory (身份验证) 林 (LinkedRoomTest) 。</span><span class="sxs-lookup"><span data-stu-id="89e3a-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="89e3a-115">在命令行管理程序Exchange Server命令：</span><span class="sxs-lookup"><span data-stu-id="89e3a-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="89e3a-116">选项 2：将现有会议室邮箱更改为链接 (Skype 会议室) 邮箱</span><span class="sxs-lookup"><span data-stu-id="89e3a-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


