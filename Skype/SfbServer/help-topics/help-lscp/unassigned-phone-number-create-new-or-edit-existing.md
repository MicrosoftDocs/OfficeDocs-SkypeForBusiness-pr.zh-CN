---
title: 未指定的电话号码创建新模板或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。
ms.openlocfilehash: b4cdd3d4efad5299b855c546edf2359698ef6a47
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a><span data-ttu-id="1ba9c-104">未指定的电话号码： 新建或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="1ba9c-104">Unassigned Phone Number: Create New or Edit Existing</span></span>
 
<span data-ttu-id="1ba9c-p102">未分配号码是指对于组织有效但尚未分配给用户或电话的电话号码。未分配号码表标识您希望如何处理对未分配号码的调用。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-p102">Unassigned numbers are phone numbers that are valid for your organization but are not assigned to a user or a phone. The unassigned number table identifies how you want calls to unassigned numbers to be treated.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="1ba9c-107">当您创建新的未分配编号范围或编辑一个现有完成时，单击**确定**以返回到**未分配数**页列出所有数字的范围。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-107">When you are finished creating a new unassigned number range or editing an existing one, click **OK** to return to the **Unassigned Number** page that lists all the number ranges.</span></span> <span data-ttu-id="1ba9c-108">直到您单击**未分配的数**页上的**全部提交****新编号范围未分配**页或**编辑未分配编号 Rage**页所做的更改未提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-108">The changes you made on the **New Unassigned Number Range** page or the **Edit Unassigned Number Rage** page are not committed to the database until you click **Commit all** on the **Unassigned Number** page.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="1ba9c-109">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="1ba9c-109">UI Reference</span></span>

<span data-ttu-id="1ba9c-110">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-110">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="1ba9c-111">**名称**键入一个描述性的名称，用于标识未指定编号范围。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-111">**Name** Type a descriptive name that identifies the unassigned number range.</span></span> <span data-ttu-id="1ba9c-112">保存区域后，无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-112">After you save the range, this name cannot be changed.</span></span>
    
- <span data-ttu-id="1ba9c-113">**编号范围**在第一个字段中，键入未分配的编号范围的起始数。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-113">**Number range** In the first field, type the beginning number of the unassigned number range.</span></span> <span data-ttu-id="1ba9c-114">在第二个字段中，键入该范围的结束编号。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-114">In the second field, type the ending number of the range.</span></span>
    
  - <span data-ttu-id="1ba9c-115">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
  - <span data-ttu-id="1ba9c-116">如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-116">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span>
    
  - <span data-ttu-id="1ba9c-117">数量必须匹配的正则表达式 (tel:) ? (\+) ? [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ?。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-117">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="1ba9c-118">这意味着数可能开始与字符串 tel: （如果不指定该字符串它将会自动为您添加），加号 （+） 和数字 1 到 9。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-118">This means the number may begin with the string tel: (if you don't specify that string it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="1ba9c-119">电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-119">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span>
    
- <span data-ttu-id="1ba9c-120">**发布服务**选择**发布**公告应用程序处理传入呼叫或**Exchange UM**让 Exchange UM 自动助理处理传入呼叫。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-120">**Announcement service** Select **Announcement** to have the Announcement application handle the incoming call or **Exchange UM** to have an Exchange UM Auto Attendant handle the incoming call.</span></span>
    
- <span data-ttu-id="1ba9c-121">如果选择**发布****公告服务**：</span><span class="sxs-lookup"><span data-stu-id="1ba9c-121">If you selected **Announcement** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="1ba9c-122">**目标服务器的 FQDN**选择运行发布应用程序将处理传入呼叫此未分配的数字范围的应用程序服务的服务 ID。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-122">**FQDN of destination server** Select the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers.</span></span>
    
  - <span data-ttu-id="1ba9c-123">**公告**选择通知播放的这个未分配的数字范围。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-123">**Announcement** Select the announcement to be played for this range of unassigned numbers.</span></span>
    
-  <span data-ttu-id="1ba9c-124">如果您选择了**UM Exchange** **发布**服务：</span><span class="sxs-lookup"><span data-stu-id="1ba9c-124">If you selected **Exchange UM** for **Announcement service**:</span></span>
    
  - <span data-ttu-id="1ba9c-125">**自动助理的电话号码**选择交换 UM 自动助理的电话号码。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-125">**Auto Attendant phone number** Select the phone number for the Exchange UM Auto Attendant.</span></span>
    
<span data-ttu-id="1ba9c-126">有关公告的特性和功能的详细信息，请参阅规划文档中[规划业务 2015年的 Skype 的发布应用程序](../../plan-your-deployment/enterprise-voice-solution/announcement.md)。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-126">For details about Announcement features and capabilities, see [Plan for the Announcement application in Skype for Business 2015](../../plan-your-deployment/enterprise-voice-solution/announcement.md) in the Planning documentation.</span></span> <span data-ttu-id="1ba9c-127">有关使用未分配的数字范围的详细信息，请参阅操作文档中的[配置路由的未指定的电话号码](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1ba9c-127">For details about working with unassigned number ranges, see [Configure Routing of Unassigned Phone Numbers](http://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx) in the Operations documentation.</span></span>
  

