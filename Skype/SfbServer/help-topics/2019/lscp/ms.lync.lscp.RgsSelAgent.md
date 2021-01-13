---
title: 选择代理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsSelAgent
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b5cf912b-8273-4c2c-a1e5-f25530b264d0
ROBOTS: NOINDEX, NOFOLLOW
description: 代理是指定应答响应组呼叫的用户。 响应组必须具有一个分配的代理组来识别可接收针对响应组的呼叫的代理。 创建代理组的一种方法就是通过选择合格用户来定义自定义组。 符合条件的用户已启用 Skype for Business Server 和 企业语音。
ms.openlocfilehash: b2eb4baa8f969c6395f51da8153c3c34f7c3684b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824662"
---
# <a name="select-agents"></a><span data-ttu-id="89b3c-106">选择代理</span><span class="sxs-lookup"><span data-stu-id="89b3c-106">Select Agents</span></span>

<span data-ttu-id="89b3c-107">代理是指定应答响应组呼叫的用户。</span><span class="sxs-lookup"><span data-stu-id="89b3c-107">Agents are users who are designated to answer Response Group calls.</span></span> <span data-ttu-id="89b3c-108">响应组必须具有一个分配的代理组来识别可接收针对响应组的呼叫的代理。</span><span class="sxs-lookup"><span data-stu-id="89b3c-108">Response groups must have an assigned agent group that identifies the agents who can receive calls for the response group.</span></span> <span data-ttu-id="89b3c-109">创建代理组的一种方法就是通过选择合格用户来定义自定义组。</span><span class="sxs-lookup"><span data-stu-id="89b3c-109">One way to create an agent group is to define a custom group by selecting eligible users.</span></span> <span data-ttu-id="89b3c-110">符合条件的用户已启用 Skype for Business Server 和 企业语音。</span><span class="sxs-lookup"><span data-stu-id="89b3c-110">Eligible users are enabled for Skype for Business Server and Enterprise Voice.</span></span>

<span data-ttu-id="89b3c-111">使用“选择代理”对话框可选择要添加到代理组的用户。</span><span class="sxs-lookup"><span data-stu-id="89b3c-111">You use the **Select Agents** dialog box to select users to be added to an agent group.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="89b3c-112">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="89b3c-112">UI Reference</span></span>

<span data-ttu-id="89b3c-113">下表介绍了“选择代理”对话框中的各个控件。</span><span class="sxs-lookup"><span data-stu-id="89b3c-113">The following list describes the controls in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="89b3c-114">**查找** 搜索用户的 SIP 地址显示名称地址。</span><span class="sxs-lookup"><span data-stu-id="89b3c-114">**Find** Searches for the SIP address or display name for a user.</span></span> <span data-ttu-id="89b3c-115">输入地址或名称的一部分或全部。</span><span class="sxs-lookup"><span data-stu-id="89b3c-115">Enter all or part of the address or name.</span></span> <span data-ttu-id="89b3c-116">将搜索框留空，以显示已启用 Skype for Business Server 和 企业语音。</span><span class="sxs-lookup"><span data-stu-id="89b3c-116">Leave the search box empty to display all users who are enabled for Skype for Business Server and Enterprise Voice.</span></span>

- <span data-ttu-id="89b3c-117">**要显示的最大用户数** 更改显示的返回结果数。</span><span class="sxs-lookup"><span data-stu-id="89b3c-117">**Maximum users to display** Changes the number of returned results that are displayed.</span></span> <span data-ttu-id="89b3c-118">如果您希望获得许多结果，请使用此计数器来限制搜索。</span><span class="sxs-lookup"><span data-stu-id="89b3c-118">Use this counter to limit the search if you expect many results.</span></span>

<span data-ttu-id="89b3c-119">下表介绍了“选择代理”对话框中的各个字段。</span><span class="sxs-lookup"><span data-stu-id="89b3c-119">The following list describes the fields in the **Select Agents** dialog box.</span></span>

- <span data-ttu-id="89b3c-120">**代理** 显示搜索返回的用户名。</span><span class="sxs-lookup"><span data-stu-id="89b3c-120">**Agent** Displays the user names returned by the search.</span></span>

- <span data-ttu-id="89b3c-121">**SIP 地址** 显示搜索返回的用户 SIP 地址。</span><span class="sxs-lookup"><span data-stu-id="89b3c-121">**SIP address** Displays the user SIP addresses returned by the search.</span></span>

- <span data-ttu-id="89b3c-122">**电话** 显示为用户 **定义的电话** 字段的值。</span><span class="sxs-lookup"><span data-stu-id="89b3c-122">**Telephony** Displays the value of the **Telephony** field defined for users.</span></span>

- <span data-ttu-id="89b3c-123">**已启用** 显示为用户定义的 **"已启用 Lync Server"** 字段的值。</span><span class="sxs-lookup"><span data-stu-id="89b3c-123">**Enabled** Displays the value of the **Enabled for Lync Server** field defined for users.</span></span>

<span data-ttu-id="89b3c-124">有关使用代理组的详细信息，请参阅操作文档中的[Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="89b3c-124">For details about working with agent groups, see [Managing Agent Groups](https://technet.microsoft.com/library/36084cdc-38f1-4c45-922f-f81c7e86210c.aspx) in the Operations documentation.</span></span>


