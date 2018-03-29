---
title: 在 Skype for Business Server 中配置智能联系人列表
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 10/20/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4eecb5f7-3ef7-4582-a6cb-9f4aa068338d
description: 摘要： 了解如何打开 Skype 业务客户端中的智能联系人列表功能。
ms.openlocfilehash: f5b5b8f7baa0ce848765a0f2b62aabb118ecb224
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-smart-contacts-list-in-skype-for-business-server"></a>在 Skype for Business Server 中配置智能联系人列表
 
**摘要：**了解如何打开 Skype 业务客户端中的智能联系人列表功能。
  
智能联系人列表功能支持自动填充最终用户的联系人列表。 后第一个使用 Skype 的业务，您的用户将自动看到他们的经理和其他人在他们的团队。 在默认情况下，Office 365 提供用户启用此功能，但您必须显式启用该功能为您的内部用户通过配置客户端策略设置。
  
配置此功能时，请记住以下几点：
  
- 用户，到 13 时，将自动添加到智能联系人列表以下列顺序：
    
  1. 经理
    
  2. 按字母顺序显示下属
    
  3. 按字母顺序显示同事
    
- 当用户第一次登录时，系统将创建一个名为“我的组”的新组。 组会自动填充与用户的 AD 组关系基于在经理字段中填充用户别名中的人。 请注意，在“我的组”最初填充之后，对 AD 组成员资格做任何更改都不会引起“我的组”发生更新。 如果用户删除某个联系人或组，则不会重新创建联系人或组。 
    
- 如果自动标记功能启用，将为列表中的联系人标记状态更改。 自动标记功能默认情况下启用，但是您可以选择将其禁用。 
    
- 组中的所有新用户都会收到通知，知晓他们已被添加到联系人列表。 用户可以手动选择将新成员添加到其“我的组”或其选择的其他组。
    
- 此功能仅适用于首次登录的用户。 如果用户以前曾从任何设备（例如，任何移动设备或 Mac）登录，则该用户无法使用该功能。
    
## <a name="configure-smart-contacts-list"></a>配置智能联系人列表

要为您的用户启用智能联系人列表功能，需要执行以下步骤： 
  
- 创建一个新的 CsClientPolicy 条目并将其添加到全局客户端策略。 
    
- 确保将通讯簿搜索设置为仅限 Web 搜索。
    
### <a name="create-a-policy-entry-to-enable-smart-contacts-list"></a>创建策略条目以启用智能联系人列表

若要创建一个策略项，以便启用智能联系人列表功能，使用[New CsClientPolicyEntry](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicyentry?view=skype-ps) cmdlet EnableClientAutoPopulateWithTeam 选项，如下所示：
  
```
$x=New-CsClientPolicyEntry -Name EnableClientAutoPopulateWithTeam -Value $True
```

接下来，使用[一组 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) cmdlet 将更改写入到的全局策略，如下所示：
  
```
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}
```

也可以选择创建策略来关闭自动标记功能，如下所示：
  
```
$x=New-CsClientPolicyEntry -Name TagContactsInClientAutoPopulatedGroup -Value $False
Set-CsClientPolicy -Identity Global -PolicyEntry @{Add=$x}

```

还必须将对应策略的 AddressBookAvailability 参数设置为 WebSearchOnly。 有关详细信息，请参阅[设置 CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps)。 
  
### <a name="troubleshoot"></a>疑难解答

如果智能联系人列表未按预期工作，请检查以下各项：
  
- 验证配置。 
    
- 确认广告组织信息进行填充。
    
- 收集的业务客户端登录 Skype 新用户进行进一步分析。
    
- 请确认 Skype 业务客户端用户界面不会显示一条消息，它不能连接到通讯簿。 确认通讯簿的连接，执行业务客户端搜索栏的 Skype 用户搜索。
    
- 如果连接到通讯簿时出现问题，请使用 Strace 收集 HTTPS 跟踪和 HTTPReplay，以分析收集的跟踪。 有关详细信息，请参阅[相关的博客文章](https://blogs.msdn.microsoft.com/canberrapfe/2012/06/04/have-you-ever-wondered-what-web-service-urls-are-used-by-the-lync-client-strace-is-your-tool/)。
    
- AD DS 复制问题可能导致当用户首次登录 Skype 业务无法解析的联系人。
    

