---
title: 未分配的电话号码创建新的或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: 43be74f40742428fd14aada2e2060ededb5c277a
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/08/2018
ms.locfileid: "22138593"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="55b10-104">未分配的电话号码： 创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="55b10-104">Unassigned Phone Number: Create New or Edit Existing</span></span>

> [!NOTE]
> <span data-ttu-id="55b10-105">Exchange UM 仍可在 Skype 的业务服务器 2019年与 Exchange 2013 或 Exchange 2016 集成 for Business 2019 Skype 时。</span><span class="sxs-lookup"><span data-stu-id="55b10-105">Exchange UM remains available in Skype for Business Server 2019 when you integrate Skype for Business 2019 with Exchange 2013 or Exchange 2016.</span></span> <span data-ttu-id="55b10-106">由于 Exchange 2019 中支持的变化，Exchange UM 集成正在注销 emphasised 支持云语音邮件和云自动助理功能。</span><span class="sxs-lookup"><span data-stu-id="55b10-106">Due to changes in support in Exchange 2019, Exchange UM integration is being de-emphasised in favor of Cloud Voicemail and Cloud Auto Attendant features.</span></span>  
 
<span data-ttu-id="55b10-p103">未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。</span><span class="sxs-lookup"><span data-stu-id="55b10-p103">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="55b10-109">创建一个新的未分配号码范围或编辑现有完成后，单击**确定**返回到**未分配号码**页，其中列出了所有的号码范围。</span><span class="sxs-lookup"><span data-stu-id="55b10-109">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="55b10-110">单击**全部提交****未分配号码**页上，在**新建未分配号码范围**页上或**编辑未分配号码 Rage**页所做的更改才提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="55b10-110">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="55b10-111">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="55b10-111">UI Reference</span></span>

<span data-ttu-id="55b10-112">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="55b10-112">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="55b10-113">**名称**键入标识未分配号码范围的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="55b10-113">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="55b10-114">保存范围后，无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="55b10-114">After you save the range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="55b10-115">**号码范围**在第一个字段中，键入未分配号码范围的开始号码。</span><span class="sxs-lookup"><span data-stu-id="55b10-115">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="55b10-116">在第二个字段中，键入该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="55b10-116">In the second field, type the ending number of the range.</span></span>
    
  - <span data-ttu-id="55b10-117">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="55b10-117">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="55b10-118">如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。</span><span class="sxs-lookup"><span data-stu-id="55b10-118">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
  - <span data-ttu-id="55b10-119">数必须匹配的正则表达式 (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?。</span><span class="sxs-lookup"><span data-stu-id="55b10-119">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="55b10-120">这意味着数可能以字符串 tel 开头: （如果不指定该字符串它将自动添加为您），一个加号 （+） 和一个数字 1 至 9。</span><span class="sxs-lookup"><span data-stu-id="55b10-120">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="55b10-121">电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</span><span class="sxs-lookup"><span data-stu-id="55b10-121">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
- <span data-ttu-id="55b10-122">**公告服务**选择**通知**能够处理传入呼叫通知应用程序或**Exchange UM**以具有 Exchange UM 自动助理处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="55b10-122">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>
    
- <span data-ttu-id="55b10-123">如果选择**通知****通知**服务：</span><span class="sxs-lookup"><span data-stu-id="55b10-123">If you selected **Announcement** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="55b10-124">**目标服务器的 FQDN**选择运行将处理到此未分配号码范围的传入呼叫通知应用程序的应用程序服务的服务 ID。</span><span class="sxs-lookup"><span data-stu-id="55b10-124">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>
    
  - <span data-ttu-id="55b10-125">**通知**选择要为此未分配号码范围播放的通知。</span><span class="sxs-lookup"><span data-stu-id="55b10-125">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>
    
-  <span data-ttu-id="55b10-126">如果选择**Exchange UM** **通知**服务：</span><span class="sxs-lookup"><span data-stu-id="55b10-126">If you selected **Exchange UM** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="55b10-127">**自动助理电话号码**选择 Exchange UM 自动助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="55b10-127">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>
    
<span data-ttu-id="55b10-128">有关通知特性和功能的详细信息，请参阅规划文档中的[规划 Skype for Business 中的通知应用程序](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。</span><span class="sxs-lookup"><span data-stu-id="55b10-128">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="55b10-129">有关使用未分配号码范围的详细信息，请参阅操作文档中的[配置路由的未分配电话号码](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。</span><span class="sxs-lookup"><span data-stu-id="55b10-129">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>
  

