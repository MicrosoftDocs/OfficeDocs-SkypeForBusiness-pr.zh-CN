---
title: Skype 会议室系统多林本地部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: 35a6d5401b2e554cbfaa1e97c42e9a88bc3558ed
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966057"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a><span data-ttu-id="ec6c1-103">Skype 会议室系统多林本地部署</span><span class="sxs-lookup"><span data-stu-id="ec6c1-103">Skype Room System multiple forest on-premises deployments</span></span>
 
<span data-ttu-id="ec6c1-104">阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-104">Read this topic to learn how to deploy Skype Room System in a multiple forest on-premises environment.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ec6c1-105">为了在多个林中部署，Skype 会议室系统要求 2014 年 8 月 26 日发布的 Exchange Server 2013 CU6。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-105">In order to deploy in multiple forests, Skype Room System requires Exchange Server 2013 CU6 released on August 26, 2014.</span></span> <span data-ttu-id="ec6c1-106">避免 Skype 会议室 system 重新使用现有的邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-106">Avoid re-using an existing mailbox for Skype Room System.</span></span> <span data-ttu-id="ec6c1-107">使用新 （删除旧的邮箱并重新创建） 的 Skype 会议室系统资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-107">Use a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="ec6c1-108">若要还原的会议丢失通过删除邮箱，请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-108">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="ec6c1-109">在创建邮箱之后，你可以使用 Set-CalendarProcessing 配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-109">After creating the mailbox, you can use Set-CalendarProcessing to configure the mailbox.</span></span> <span data-ttu-id="ec6c1-110">有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-110">Refer to steps 3 through 6 under Single forest on-premises deployments for more details.</span></span> <span data-ttu-id="ec6c1-111">在创建后 Skype 会议室系统，Exchange 资源邮箱帐户启用 for Business 的 Skype 按照中启用 Skype 会议室系统帐户的步骤为 for Business 的 Skype 下的单林本地部署。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-111">After creating an Exchange Resource mailbox for Skype Room System, enable the account for Skype for Business by following the steps in Enabling Skype Room System Accounts for Skype for Business under Single forest on-premises deployments.</span></span>
  
## <a name="option-1-create-a-new-resource-mailbox"></a><span data-ttu-id="ec6c1-112">方法 1：创建新的资源邮箱</span><span class="sxs-lookup"><span data-stu-id="ec6c1-112">Option 1: Create a new resource mailbox</span></span>

<span data-ttu-id="ec6c1-113">在多林环境中部署 Skype 会议室系统：</span><span class="sxs-lookup"><span data-stu-id="ec6c1-113">To deploy Skype Room System in a multi-forest environment:</span></span>
  
1. <span data-ttu-id="ec6c1-114">在 Active Directory（身份验证林）中创建链接用户 (LinkedRoomTest)。</span><span class="sxs-lookup"><span data-stu-id="ec6c1-114">Create a Linked User (LinkedRoomTest) in Active Directory (Authentication Forest).</span></span>
    
2. <span data-ttu-id="ec6c1-115">在 Exchange Server 命令行管理程序中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="ec6c1-115">Run the following commands in the Exchange Server Management Shell:</span></span>
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a><span data-ttu-id="ec6c1-116">选项 2： 更改现有的会议室邮箱到 Skype 会议室系统 （链接） 的资源邮箱</span><span class="sxs-lookup"><span data-stu-id="ec6c1-116">Option 2: Change an existing room mailbox to Skype Room System (linked) resource mailbox</span></span>

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


