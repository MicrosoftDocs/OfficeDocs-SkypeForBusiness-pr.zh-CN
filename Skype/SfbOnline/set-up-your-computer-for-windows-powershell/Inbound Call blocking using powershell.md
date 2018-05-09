---
title: 使用 Powershell 为 Skype 阻止的业务联机的入站呼叫
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 05/07/2018
ms.topic: article
ms.assetid: ''
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 PowerShell 管理业务 online Skype 中阻止的入站的呼叫。
ms.openlocfilehash: 10aa92233f2a804edffef8bf6d5b8e5dd7746b06
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2018
---
# <a name="inbound-pstn-call-blocking-for-calling-plans"></a>入站 PSTN 呼叫阻止呼叫计划

为业务联机调用计划的 Skype 现在支持阻止从公用电话交换网 (PSTN) 的入站调用。 此功能允许租户的定义，以便可以根据列表用于匹配检查到租户每个传入 PSTN 呼叫的呼叫者 ID 的号码模式的全局列表。 如果进行匹配时，被拒绝的传入呼叫。 

此入站的呼叫阻止功能仅适用于源自 PSTN 的入站呼叫并仅适用于在租户全局范围在每个用户分别上不可用。

此功能尚不可用的直接路由。

>[注意]阻止呼叫者可能会遇到略有不同行为时其已被阻止。 将基于行为阻止呼叫者的运营商如何处理呼叫不允许成功完成的通知。 示例可能包括运营商消息指出拨出，无法完成呼叫或放呼叫。

## <a name="call-blocking-admin-controls-and-information"></a>阻止管理控件和信息的呼叫
仅使用 PowerShell 提供管理阻止的号码的控件。 号码块模式定义为正则表达式模式。 表达式的顺序并不重要 – 在列表中匹配的第一个模式将导致呼叫被阻止。 新的数字或模式添加或删除被阻止呼叫者列表可能需要多达 24 小时到要变为活动状态的模式。

## <a name="call-blocking-powershell-commands"></a>调用阻止 PowerShell 命令

*InboundBlockedNumberPattern*通过**新建**、**获取**、**设置**和**删除**的*CsInboundBlockedNumberPattern*命令管理号码模式。  

您可以使用这些 cmdlet，包括切换的给定模式激活的功能来管理给定的模式。
- *Get CsInboundBlockedNumberPattern*返回所有被阻止的号码模式添加到每个包括名称、 说明、 已启用 (True/False) 和模式租户列表的列表。
- *新 CsInboundBlockedNumberPattern*向租户列表中被阻止的号码模式。
- *删除 CsInboundBlockedNumberPattern*从租户列表中删除被阻止的号码模式。
- *设置 CsInboundBlockedNumberPattern*修改租户列表中的阻止号码模式的一个或多个参数。
- *TenantBlockedCallingNumbers*查看和激活整个调用阻止功能是通过 CsTenantBlockingCallingNumbers 命令获取和设置进行管理。 
- *Get CsTenantBlockedCallingNumbers*返回全局阻止号码列表包括启用 (True/False) 的参数。 没有无法手动以外修改来关闭该功能完全上/的单个全局租户策略。
- *设置 CsTenantBlockedCallingNumbers*允许修改全局租户阻止呼叫在租户级别打开/关闭。

### <a name="examples"></a>示例
#### <a name="blocking-a-number"></a>阻止数字

本示例中，-启用和-说明参数是可选的：

`New-CsInboundBlockedNumberPattern -Name “<name>” -Enabled $True -Description “<description>” -Pattern “^[+]?13125550000”`

 创建新的模式将默认情况下添加模式为已启用，并说明始终是和可选字段，用于提供了详细信息。 

我们建议您提供有意义的名称，可以轻松地理解模式已添加为什么。 对于只需阻止垃圾邮件号码，视为相同命名规则匹配的号码模式为正在，且在说明根据需要添加其他信息。

使用正则表达式 (regex) 匹配模式。 允许的前测试和验证复制时间。

#### <a name="allowing-a-number"></a>允许使用数量

在此示例中，如果 (is?) 需要 identity 参数：`Remove-CsInboundBlockedNumberPattern -Identity “<identity>”`
 
如果不知道标识，使用*Get-CsInb undBlockedNumberPattern* cmdlet 可以先找到正确的模式，并记下标识。 然后，运行*删除*cmdlet 并传递相应的 Identity 值。

允许的前测试和验证复制时间。
#### <a name="view-all-number-patterns"></a>查看所有的号码模式
运行此 cmdlet 将返回租户的所有列表输入阻止号码：`Get-CsInboundBlockedNumberPattern`

使用内置 PowerShell 筛选功能来分析所需的返回的值。

#### <a name="a-note-on-regex"></a>正则表达式上一条注释
如上文所述，是通过模式匹配的阻止呼叫者使用正则表达式 (regex)。 有多个工具可以联机帮助验证正则表达式模式匹配。 如果您不熟悉正则表达式模式，建议您花一些时间来熟悉基础知识，以确保获取预期的结果，使用工具，用于验证模式匹配，然后将新阻止号码的匹配项添加到您的租户。 

## <a name="related-topics"></a>相关主题
[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md)