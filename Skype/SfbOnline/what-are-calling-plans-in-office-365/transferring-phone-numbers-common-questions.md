---
title: 传送电话号码的常见问题
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28cbf7d7-97f3-4a99-aa76-897022c14a24
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 以下是有关常见问题将电话号码转到 Skype 的业务。 复查答案，您应该准备好创建端口订单和转移您的电话号码。 到 Office 365 的传输电话号码的说明，请参阅。
ms.openlocfilehash: ce62365c337d94c05c7ca1b3ff1703cb39086f97
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="transferring-phone-numbers-common-questions"></a>传送电话号码的常见问题

以下是有关常见问题将电话号码转到 Skype 的业务。 复查答案，您应该准备好创建端口订单和转移您的电话号码。 有关说明，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。
  
## <a name="what-countriesregions-support-number-porting"></a>哪些国家/地区支持号码转网？

在所有受支持的国家或地区均可转网或转移电话号码，但如何提交转网订单请求取决于电话号码来自的国家或地区。 您可以看到支持的[国家和地区可用性的音频会议和调用计划](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)的国家/地区列表。 

当您进行电话号码管理任务，如传输 （移植） 数字或获取电话号码中未提供业务管理中心的 Skype 时，请参阅[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。
  
## <a name="what-numbers-can-be-transferred"></a>哪些号码可以转移？

 **你可以转移：**
  
一般来讲，你可以转移来自受支持提供商的任何电话号码，其中包括：
  
- 座机电话号码。
    
- 移动设备电话号码，例如，用于手机和平板电脑等设备的电话号码。
    
    > [!NOTE]
    > [!警告] 只能在美国和波多黎各转移移动电话号码。 
  
- 收费电话号码。
    
- 免费电话号码。
    
    > [!NOTE]
    > 通用国际免费电话号码 (UIFN) 不能转移给我们。 
  
- 服务电话号码，例如，用于会议网桥、自动助理等的电话号码。
    
- 传真电话号码，但是它们不能用于传真。它们必须被分配给一个用户。
    
- 来自电话提供商（如 Vonage 或 RingCentral）的电话号码。
    
- Skype 的混合业务的电话号码。 如果您想要转换这些数据，您需要发送电子邮件给我们在<ptn@microsoft.com>。
    
 **你无法转移：**
  
> [!NOTE]
> [!重要信息] 目前，你无法转移支持的国家/地区的任何电话号码，包括来自 VoIP 电话提供商的电话号码。 若要查看支持的国家/地区的列表，请参阅[音频会议和调用计划的国家和地区可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- 用于 DSL 线路或宽带 Internet 连接等数据连接的电话号码。
    
- 专用于收发传真的电话号码。
    
    如果你已有专用的电话号码用于收发传真，你 *可以*  将这些号码转移到 Skype for Business，但是传真服务无法继续正常使用。 传真服务对不可用 Skype 给企业客户，即使您的**电话系统**、**调用计划国内**或**国际调用计划**有许可证。
    
    如果你将电话号码转网到 Skype for Business，可以将此电话号码分配给组织中的用户，而不是将其用于收发传真。
    
> [!NOTE]
> [!警告] 在英国 (U.K.) 境内，目前不支持转移 UK 非地理号码，包括区号 0843、0844、0845、0870、0871、0872 的共享费用号码。 
  
## <a name="what-information-will-i-need-to-provide"></a>我需要提供哪些信息？

你需要拥有你的当前运营商的所有帐户信息。需要输入到转网订单中的信息大多都可以在当前服务提供商的最新帐单或发票上找到。你还需要知道帐户上的具体姓名以及要转网的号码。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什么是完整转网和部分转网？

将电话号码转网到 Office 365 时，你可以选择是转移所有号码还是部分号码。
  
- **完整转网** 这是指将你的所有号码从当前服务提供商转移到 Skype for Business Online。 当被要求您的电话号码要转移，您*必须包括*和所有您的帐户的其他电话号码的付费电话号码。
    
    例如，假设您的付费电话号码是*+1 425-555-1234*并且您想要您的 25 电话号码 (*通过 1259年 +1 425-555-1235*) 的所有端口。 按照下面的说明转网号码时，你应该输入： **+14255551234 - +14255551259** 。
    
- **部分转网** 这是指仅将你的部分电话号码从当前服务提供商或运营商转移到 Skype for Business Online。当你想要转网的某些电话号码关联到相同的付费电话号码时， ** *不能包含* ** 该付费电话号码以及你的帐户上的所有其他电话号码。
    
    例如，假设您付费的电话号码 （按钮） 是*+1 425-555-1234*并且想要端口仅您的 25 电话号码 (*+1 425-555-1235 通过 1259年*) 第 5。 遵循下面的说明进行操作来传输数字时，应输入： **+1 425 555 1235-+ 1 425 555 1239年**。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我是否可以一次性针对我的所有号码提交一个携号转网请求？
<a name="bkmk_type_1"> </a>

需要为每个运营商和每种转网号码类型提交唯一的请求。
  
例如，你需要为下列每种号码类型提交唯一的携号转网请求：
  
- 本地收费号码，也称为订阅者号码或地理号码
    
- 带区号的免费号码，如：800、844、855、866、877 和 888
    
- 移动电话号码
    
- 可以用于 Office 365 中的音频会议的服务号码。
    
下面是关于为其中每种号码类型提交携号转网请求的详细信息：
  
- 对于由不同运营商提供的 **电话号码** ，需对每个运营商提交唯一的转网请求。
    
- 带区号的 **免费号码** （如 800、844、855、866、877 和 888）不能包含在其他号码类型的携号转网请求中。 移植这些免费电话号码，您必须[手动提交自定义服务请求](manually-submit-a-custom-service-request.md);不能为业务管理中心 Skype 提交它们。 [管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)，请参阅。
    
    针对要转网的电话号码的国家/地区和类型使用正确的 LOA 是非常重要的。 您可以下载您需要[下载字母的授权 (LOA) 所需](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)的保证书。
    
- **移动电话号码** 需使用 PIN 码来授权转移操作。因此，它们需要单独的携号转网请求。
    
- **服务号码** 转网请求需单独提交。不能将它们与其他类型的号码一起提交。
    
## <a name="how-long-does-it-take-to-port-numbers"></a>转网号码需要多长时间？
<a name="bkmk_type_1"> </a>

在你完成转网订单请求之后，将需要 7 到 14 天的时间进行处理。但是，根据你的服务提供商，可能需要花费长达 30 天时间。在将电话号码转网之后，我们将向你发送一封电子邮件，告诉你可以继续操作。
  
You can check the status of your port order by going to the Skype for Business admin center > **Voice** > **Port orders**. The status will be listed in the window under the **Status** column.
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>用户（订阅者）电话号码是否可以转换为服务号码？
<a name="bkmk_type_1"> </a>

可以。 你只需要提交一个服务请求，在请求中提供你组织的租户 GUID 和你要转换的电话号码。 为此去看看[管理您的组织的电话号码](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。 
  
## <a name="common-mistakes-to-watch-out-for"></a>需要注意的常见错误
<a name="bkmk_type_1"> </a>

携号转网很简单。但是，如果电话服务提供商出现问题、订单不完整或缺少信息，或者存在拼写错误，订单可能会变得混乱。
  
以下是我们发现客户在转网号码时最常见的错误。你无需致电客户支持，只需认真查看这些错误。
  
- 确保你提供的帐户信息与你的电话运营商记录的信息完全匹配。不匹配的信息是最常见的出错原因，并会导致你的转网订单延迟。请确认满足以下条件：
    
  - 授权的名称不正确。
    
  - 地址正确。
    
  - 帐户数量不正确。
    
  - 付费电话号码 (BTN) 正确无误。
    
- 确保这些电话号码上没有启用高级呼叫控制功能，例如，呼叫寻线、独特震铃。
    
- 确保你尚未提交任何新服务订单或者与你的当前服务提供商断开连接。
    
- 请确保所有号码来自同一个运营商和同一帐户。
    
- 确保你的服务处于活动状态。冻结帐户将导致运营商无法更改帐户。获得授权的用户需要向当前运营商提交订单来取消冻结。此过程可能需要 1 到 3 周的时间，具体取决于运营商。
    
## <a name="can-you-transfer-or-port-out-numbers"></a>您可以传输或者出数字端口？
<a name="bkmk_type_1"> </a>

传输或*出端口*电话号码从 Skype 在线业务给其他电话服务提供商或运营商，您将需要设置 PIN。 设置 PIN 后，您需要将其包括在您请求端口出一个电话号码时。若要了解如何设置您的 PIN，请参阅[设置传输到新的服务提供商的数字 PIN](set-your-pin-for-transferring-numbers-to-a-new-service-provider.md)。

> [!NOTE]
> 如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/en-us/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

  
## <a name="related-topics"></a>相关主题
[用于通话套餐的不同类型的电话号码](../what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans.md)

[紧急呼叫条款和条件](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://go.microsoft.com/fwlink/?LinkID=692099)
  
  
 
