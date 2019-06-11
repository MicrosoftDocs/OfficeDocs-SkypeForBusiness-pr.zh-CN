---
title: Skype for Business Online 中使用用户标识和标记作用域的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab087388feb37ca8299cae8e4246484e4c23a88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837091"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Skype for Business Online 中使用用户标识和标记作用域的 cmdlet

 


**授权-Cs** cmdlet (用于为用户分配策略) 需要两个标识符: 用户标识 (identity 参数) 和每用户策略的标识 (PolicyName 参数)。 例如, 若要向用户 Ken Myer 分配语音策略 RedmondVoicePolicy, 请使用以下命令:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

向用户分配策略时需要注意两个事项。 首先, 只能分配每个用户的策略。 不能将全局策略分配给用户。 例如, 此命令将失败:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

此命令失败, 因为无需分配全局策略。 如果想要使用全局策略管理用户, 请确保不要为该用户分配每用户策略。 如果没有为用户分配每用户策略, 则将通过使用全局策略自动管理该用户。


> [!NOTE]  
> 如果用户以前已分配了每用户策略, 并且想要取消分配该策略, 并且用户改为由全局策略管理的用户, 该怎么办？ 在这种情况下, 你将首先使用以下语法, 该语法通过向该用户授予 null 策略来取消每用户策略:<BR>授权-CsVoicePolicy-身份 "Ken Myer"-PolicyName $Null



其次, 请记住, 每个用户的策略是在标记作用域创建的。 但是, 你可以在指定策略名称时省略标记**前缀**。 这两个命令相同:

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

如果你想要为你的所有每用户策略 (或者至少是指定类型的每个用户策略, 如语音策略) 返回标识, 请使用类似下面的命令:

    Get-CsVoicePolicy -Filter "tag:*"

以下 cmdlet 使用用户标识和标记作用域:

  - [授权-Set-csclientpolicy](https://technet.microsoft.com/en-us/library/gg412942\(v=ocs.15\))

  - [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\))

  - [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\))

  - [授权-CsExternalAccessPolicy](https://technet.microsoft.com/en-us/library/gg425942\(v=ocs.15\))

  - [授权-CsHostedVoicemailPolicy](https://technet.microsoft.com/en-us/library/gg412829\(v=ocs.15\))

  - [授权-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的身份、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))

