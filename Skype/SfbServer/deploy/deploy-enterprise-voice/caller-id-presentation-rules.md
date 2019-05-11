---
title: 创建或修改转换规则的呼叫者 ID 演示文稿中 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
description: 摘要： 了解如何使用适用于业务 Server Control Panel Skype 配置呼叫者 ID。
ms.openlocfilehash: f8b870e855ee002b002cbe28756a95269559cea6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893103"
---
# <a name="create-or-modify-a-translation-rule-for-caller-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="31657-103">创建或修改转换规则的呼叫者 ID 演示文稿中 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="31657-103">Create or modify a translation rule for caller ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="31657-104">**摘要：** 了解如何使用适用于业务 Server Control Panel Skype 配置呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="31657-104">**Summary:** Learn how to configure Caller ID by using the Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="31657-105">与 Skype 的企业服务器，调用的方的电话号码 （即，调用的电话号码） 可以由 E.164 格式转换为_中继对等方_（即，关联的网关、 private branch exchange （所需的本地拨号格式PBX)，或 SIP 中继)。</span><span class="sxs-lookup"><span data-stu-id="31657-105">With Skype for Business Server, the called party's phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the  _trunk peer_ (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="31657-106">为此，必须定义一个或多个转换规则，以便在将请求 URI 路由至中继对等方之前对其执行转换。</span><span class="sxs-lookup"><span data-stu-id="31657-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<span data-ttu-id="31657-107">Skype 业务服务器还提供选项还平移呼叫方的电话号码 （即，呼叫者呼叫的电话号码） 从 E.164 格式为本地拨号格式所需的中继对等方。</span><span class="sxs-lookup"><span data-stu-id="31657-107">Skype for Business Server also gives you the option to also translate the calling party's phone number (that is, the phone number that the caller is calling from) from E.164 format to the local dialing format that is required by the trunk peer.</span></span> <span data-ttu-id="31657-108">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。</span><span class="sxs-lookup"><span data-stu-id="31657-108">For example, you can write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>

### <a name="to-configure-caller-id-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="31657-109">使用适用于业务 Server Control Panel Skype 配置呼叫者 ID</span><span class="sxs-lookup"><span data-stu-id="31657-109">To configure Caller ID by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="31657-110">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="31657-110">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="31657-111">在左侧导航栏中，单击“语音路由”\*\*\*\*，然后单击“Trunk 配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31657-111">In the left navigation bar, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

3. <span data-ttu-id="31657-112">在“Trunk 配置”\*\*\*\* 页上，双击一个现有中继（例如，“全局”\*\*\*\* 中继）以显示“编辑 Trunk 配置”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="31657-112">On the **Trunk Configuration** page, double-click an existing trunk (for example, the **Global** trunk) to display the **Edit Trunk Configuration** dialog box.</span></span>

4. <span data-ttu-id="31657-113">配置呼叫者 ID 显示：</span><span class="sxs-lookup"><span data-stu-id="31657-113">To configure caller ID presentation:</span></span>

   - <span data-ttu-id="31657-114">若要从企业语音部署中可用的所有转换规则的列表中选择一个或多个规则，请单击**选择**。</span><span class="sxs-lookup"><span data-stu-id="31657-114">To choose one or more rules from a list of all translation rules available in your Enterprise Voice deployment, click **Select**.</span></span> <span data-ttu-id="31657-115">在“主叫号码转换规则”\*\*\*\* 中，单击要与中继关联的规则，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31657-115">In **Calling number translation rules**, click the rules that you want to associate with the trunk, and then click **OK**.</span></span>

   - <span data-ttu-id="31657-116">要定义新的转换规则并将其与中继相关联，请单击“新建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31657-116">To define a new translation rule and associate it with the trunk, click **New**.</span></span> <span data-ttu-id="31657-117">有关定义新的规则的详细信息，请参阅部署文档中的[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="31657-117">For details about defining a new rule, see  [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="31657-p105">要编辑已与中继关联的转换规则，请单击相应的规则名称，然后单击“显示详细信息”\*\*\*\*。有关详细信息，请参阅部署文档中的[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="31657-p105">To edit a translation rule that is already associated with the trunk, click the rule name, and then click **Show details**. For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx) in the Deployment documentation.</span></span>

   - <span data-ttu-id="31657-p106">要复制现有的转换规则以作为定义新规则的起点，请单击相应的规则名称，再单击“复制”\*\*\*\*，然后单击“粘贴”\*\*\*\*。有关详细信息，请参阅[Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="31657-p106">To copy an existing translation rule to use as a starting point for defining a new rule, click the rule name and click **Copy**, and then click **Paste**. For details, see [Defining Translation Rules](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx).</span></span>

   - <span data-ttu-id="31657-122">要从中继删除某个转换规则，请突出显示相应的规则名称，然后单击“删除”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="31657-122">To remove a translation rule from the trunk, highlight the rule name and click **Remove**.</span></span>

     > [!CAUTION]
     > <span data-ttu-id="31657-123">如果已在关联的中继对等方上配置了转换规则，则不要将任何转换规则与中继相关联，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="31657-123">Do not associate translation rules with a trunk if you have configured translation rules on the associated trunk peer, because the two rules might conflict.</span></span>


