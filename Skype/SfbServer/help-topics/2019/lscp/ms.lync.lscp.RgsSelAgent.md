---
title: 选择代理
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: 代理是被指定为应答响应组呼叫的用户。 响应组必须具有一个分配的代理组来识别可接收针对响应组的呼叫的代理。 创建代理组的一种方法就是通过选择合格用户来定义自定义组。 合格的用户被启用 Skype Business Server 和企业语音。
ms.openlocfilehash: c1455dcb42a13ebd9a4edc6b922a5ff3d14a94aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989469"
---
# <a name="select-agents"></a><span data-ttu-id="adc51-106">选择代理</span><span class="sxs-lookup"><span data-stu-id="adc51-106">Select Agents</span></span>
 
<span data-ttu-id="adc51-107">代理是被指定为应答响应组呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="adc51-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="adc51-108">响应组必须具有一个分配的代理组来识别可接收针对响应组的呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="adc51-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="adc51-109">创建代理组的一种方法就是通过选择合格用户来定义自定义组。</span><span class="sxs-lookup"><span data-stu-id="adc51-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="adc51-110">合格的用户被启用 Skype Business Server 和企业语音。</span><span class="sxs-lookup"><span data-stu-id="adc51-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span> 
  
<span data-ttu-id="adc51-111">使用“**选择代理**”对话框可选择要添加到代理组的用户。</span><span class="sxs-lookup"><span data-stu-id="adc51-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="adc51-112">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="adc51-112">UI Reference</span></span>

<span data-ttu-id="adc51-113">下表介绍了“**选择代理**”对话框中的各个控件。</span><span class="sxs-lookup"><span data-stu-id="adc51-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>
  
- <span data-ttu-id="adc51-114">**查找**搜索 SIP 地址或显示用户的名称。</span><span class="sxs-lookup"><span data-stu-id="adc51-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="adc51-115">输入的地址或名称的全部或部分。</span><span class="sxs-lookup"><span data-stu-id="adc51-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="adc51-116">将搜索框保留为空，以显示所有用户启用了 Skype Business Server 和企业语音。</span><span class="sxs-lookup"><span data-stu-id="adc51-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>
    
- <span data-ttu-id="adc51-117">**若要显示的最大用户**更改显示返回的结果数。</span><span class="sxs-lookup"><span data-stu-id="adc51-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="adc51-118">此计数器用于限制搜索，如果您希望多个结果。</span><span class="sxs-lookup"><span data-stu-id="adc51-118">Use this counter to limit the search if you expect many results.</span></span>
    
<span data-ttu-id="adc51-119">下表介绍了“**选择代理**”对话框中的各个字段。</span><span class="sxs-lookup"><span data-stu-id="adc51-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>
  
- <span data-ttu-id="adc51-120">**代理**显示搜索返回的用户的用户名。</span><span class="sxs-lookup"><span data-stu-id="adc51-120">**Agent** Displays the user names returned by the search.</span></span>
    
- <span data-ttu-id="adc51-121">**SIP 地址**显示搜索返回的用户 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="adc51-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>
    
- <span data-ttu-id="adc51-122">**电话服务**显示为用户定义的**电话**字段的值。</span><span class="sxs-lookup"><span data-stu-id="adc51-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>
    
- <span data-ttu-id="adc51-123">**启用**显示为用户定义的**Lync server 启用**字段的值。</span><span class="sxs-lookup"><span data-stu-id="adc51-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>
    
<span data-ttu-id="adc51-124">有关使用代理组的详细信息，请参阅操作文档中的[Managing Agent Groups](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="adc51-124">For details about working with agent groups, see [Managing Agent Groups](http://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>
  

