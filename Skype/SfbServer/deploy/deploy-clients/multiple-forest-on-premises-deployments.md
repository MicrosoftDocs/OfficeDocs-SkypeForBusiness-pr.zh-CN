---
title: Skype 会议室系统多林本地部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: eb5aa2cbe3bef26602279ffa9d4a5dc38a7e7bc2
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775037"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="b70c3-103">Skype 会议室系统多林本地部署</span><span class="sxs-lookup"><span data-stu-id="b70c3-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="b70c3-104">阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="b70c3-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b70c3-105">为了在多个目录林中部署，Skype 会议室系统需要在2013年8月 26 2014 日发布的 Exchange Server CU6。</span><span class="sxs-lookup"><span data-stu-id="b70c3-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="b70c3-106">避免重新使用 Skype 会议室系统的现有邮箱。</span><span class="sxs-lookup"><span data-stu-id="b70c3-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="b70c3-107">为 Skype 会议室系统使用新的（删除旧邮箱和重新创建）资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="b70c3-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="b70c3-108">若要还原通过删除邮箱而丢失的会议，请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b70c3-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="b70c3-109">在创建邮箱之后，你可以使用 Set-CalendarProcessing 配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="b70c3-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="b70c3-110">有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="b70c3-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="b70c3-111">为 Skype 会议室系统创建 Exchange 资源邮箱后，请按照在单个林本地部署中启用 Skype for business 的 Skype 会议室系统帐户中的步骤启用 Skype for business 帐户。</span><span class="sxs-lookup"><span data-stu-id="b70c3-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="b70c3-112">方法 1：创建新的资源邮箱</span><span class="sxs-lookup"><span data-stu-id="b70c3-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="b70c3-113">要在多林环境中部署 Skype 会议室系统，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b70c3-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="b70c3-114">在 Active Directory（身份验证林）中创建链接用户 (LinkedRoomTest)。</span><span class="sxs-lookup"><span data-stu-id="b70c3-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="b70c3-115">在 Exchange Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b70c3-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="b70c3-116">选项2：将现有会议室邮箱更改为 Skype 会议室系统（链接）资源邮箱</span><span class="sxs-lookup"><span data-stu-id="b70c3-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


