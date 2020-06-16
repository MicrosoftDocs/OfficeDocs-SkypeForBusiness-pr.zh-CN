---
title: Skype for Business Online 中使用用户标识和标记作用域的 cmdlet
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use a user identity and the tag scope
ms:assetid: 344a21b0-5301-4e77-853a-970bb1c11e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362781(v=OCS.15)
ms:contentKeyID: 56558838
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9adf86a6ec6d2bd859411005dcc67b0dcbe09c7f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755114"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope"></a>Skype for Business Online 中使用用户标识和标记作用域的 cmdlet

 


**Grant-Cs** cmdlet （用于为用户分配策略）需要两个标识符：用户标识（identity 参数）和每用户策略的标识（PolicyName 参数）。 例如，若要向用户 Ken Myer 分配语音策略 RedmondVoicePolicy，请使用以下命令：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

向用户分配策略时有两个要记住的事项。 首先，只能分配每个用户的策略。 您不能向用户分配全局策略。 例如，以下命令将失败：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "global"

此命令将失败，因为无需分配全局策略。 如果要使用全局策略管理用户，只需确保为该用户分配每用户策略即可。 如果没有为用户分配每用户策略，则将自动使用全局策略管理用户。


> [!NOTE]  
> 如果已为用户分配每用户策略，并且您想要取消分配该策略并改为由全局策略管理的用户，该怎么办？ 在这种情况下，您将首先使用以下语法，它通过向该用户授予 null 策略来取消分配每个用户的策略：<BR>Set-csvoicepolicy – Identity "Ken Myer" – PolicyName $Null



其次，请记住，每个用户的策略是在标记作用域创建的。 但是，在指定策略名称时，可以省略标记**前缀**。 这两个命令相同：

    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "tag:RedmondVoicePolicy"
    Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

如果要返回所有每用户策略的标识（或者至少，指定类型的每个用户的所有策略，如语音策略），请使用与以下类似的命令：

    Get-CsVoicePolicy -Filter "tag:*"

以下 cmdlet 使用用户标识和标记作用域：

  - [Grant-Set-csclientpolicy](https://technet.microsoft.com/library/gg412942\(v=ocs.15\))

  - [Grant-Set-csconferencingpolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\))

  - [Grant-Grant-csdialplan](https://technet.microsoft.com/library/gg398547\(v=ocs.15\))

  - [Grant-Set-csexternalaccesspolicy](https://technet.microsoft.com/library/gg425942\(v=ocs.15\))

  - [Grant-CsHostedVoicemailPolicy](https://technet.microsoft.com/library/gg412829\(v=ocs.15\))

  - [Grant-Set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\))

## <a name="see-also"></a>另请参阅


[Skype for Business Online 中的标识、范围和租户](identities-scopes-and-tenants-in-skype-for-business-online.md)  
[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))

