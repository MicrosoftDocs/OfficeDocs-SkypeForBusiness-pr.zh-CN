---
title: 选择转换规则
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: 企业语音要求所有拨号串都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会。 中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。 要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。 例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。
ms.openlocfilehash: 66e9c86679ead2832ecb8e0069e60fdcc9eae49f
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19992130"
---
# <a name="select-translation-rules"></a><span data-ttu-id="96b0c-106">选择转换规则</span><span class="sxs-lookup"><span data-stu-id="96b0c-106">Select Translation Rules</span></span>
 
 <span data-ttu-id="96b0c-107">企业语音要求所有拨号串都规范化为 E.164 格式，以便执行反向号码查找 （rnl） 会。</span><span class="sxs-lookup"><span data-stu-id="96b0c-107">Enterprise Voice requires that all dial strings be normalized to E.164 format for the purpose of performing reverse number lookup (RNL).</span></span> <span data-ttu-id="96b0c-108">中继对等方（即，关联网关、PBX 或 SIP 中继）可能要求号码采用本地拨号格式。</span><span class="sxs-lookup"><span data-stu-id="96b0c-108">The trunk peer (that is, the associated gateway, PBX, or SIP trunk) may require that numbers be in a local dialing format.</span></span> <span data-ttu-id="96b0c-109">要将 E.164 格式的号码转换为本地拨号格式，可以在将其路由至中继对等方之前，选择定义一个或多个转换规则以处理请求 URI。</span><span class="sxs-lookup"><span data-stu-id="96b0c-109">To translate numbers from E.164 format to a local dialing format, you can optionally define one or more translation rules to manipulate the Request URI before routing it to the trunk peer.</span></span> <span data-ttu-id="96b0c-110">例如，可以编写用于删除拨号串开头的 +44 并将其替换为 0144 的转换规则。</span><span class="sxs-lookup"><span data-stu-id="96b0c-110">For example, you could write a translation rule to remove +44 from the beginning of a dial string and replace it with 0144.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="96b0c-111">将一个或多个转换规则与企业语音中继配置相关联的功能旨在用作中继对等方上配置转换规则的替代项。</span><span class="sxs-lookup"><span data-stu-id="96b0c-111">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an alternative to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="96b0c-112">不关联转换规则与企业语音中继配置如果已在中继对等方上配置转换规则，因为这两种规则可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="96b0c-112">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span> 
  
<span data-ttu-id="96b0c-113">要使用现有的转换规则，请单击列表中的某个规则，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="96b0c-113">To use an existing translation rule, click a rule in the list and then click **OK**.</span></span>
  
<span data-ttu-id="96b0c-114">有关您可以使用适用于业务 Server Control Panel Skype 执行的各种过程的详细信息，请参阅[管理的 Skype 的业务服务器 2015年](../../../manage/manage.md)。</span><span class="sxs-lookup"><span data-stu-id="96b0c-114">For details about the different procedures that you can perform by using the Skype for Business Server Control Panel, see [Manage Skype for Business Server 2015](../../../manage/manage.md).</span></span>
  

