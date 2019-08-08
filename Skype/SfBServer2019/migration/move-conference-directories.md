---
title: 移动会议目录
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 在取消池之前, 必须针对旧版池中的每个会议目录执行以下过程。
ms.openlocfilehash: cc989e752e69db31f338b493c403b8b8d4c252cc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237735"
---
# <a name="move-conference-directories"></a>移动会议目录

在解除池之前, 必须针对旧版池中的每个会议目录执行以下过程。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>将会议目录移动到 Skype for business Server 2019

1. 打开 Skype for Business 服务器命令行管理程序。
    
2. 若要获取组织中的会议目录的标识, 请运行以下命令:
    
   ```
   Get-CsConferenceDirectory
   ```

    上面的命令返回你的组织中的所有会议目录。 因此, 你可能希望将结果限制为即将停止的池。 例如, 如果你使用完全限定的域名 (FQDN) pool01.contoso.net 取消池, 请使用此命令将返回的数据限制为来自该池中的会议目录:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    该命令仅返回 ServiceID 属性包含 FQDN pool01.contoso.net 的会议目录。
    
3. 若要移动会议目录, 请对池中的每个会议目录运行以下命令:
    
   ```
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    例如, 若要移动会议目录 3, 请使用此命令, 将 Skype for Business Server 2019 池指定为 TargetPool:
    
   ```
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    如果要移动池中的所有会议目录, 请使用类似于以下内容的命令:
    
   ```
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

下载[Microsoft 旧版和删除服务器角色](https://go.microsoft.com/fwlink/p/?linkId=246227), 获取有关取消旧版池的全面的分步说明。
  
移动会议目录时, 可能会遇到以下错误:
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

此错误通常在 Skype for Business 服务器管理外壳需要更新的一组 Active Directory 权限以完成任务时出现。 若要解决此问题, 请关闭该命令行管理程序的当前实例, 然后打开一个新的 Shell 实例, 然后重新运行该命令以移动会议目录。
  

