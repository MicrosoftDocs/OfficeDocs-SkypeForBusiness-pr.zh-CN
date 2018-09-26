---
title: 移动会议目录
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 停用池之前必须执行以下过程的每个会议目录在旧池中。
ms.openlocfilehash: 18cbada5833a5160fc1eb81560c56bc9fcff3e2a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028010"
---
# <a name="move-conference-directories"></a>移动会议目录

停用池之前, 必须执行以下过程的每个会议目录在旧池中。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>将业务服务器 2019年会议目录移到 Skype

1. 打开 Skype 业务 Server 命令行管理程序。
    
2. 若要获取组织中会议目录的标识，请运行以下命令：
    
  ```
  Get-CsConferenceDirectory
  ```

    上述命令返回组织中的所有会议目录。 因此，您可能想要将结果限制为正在停用该池。 例如，如果您要停用具有完全限定域名 (FQDN) pool01.contoso.net 池，使用此命令返回的数据限制为会议目录从该池：
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
  ```

    该命令返回其中 ServiceID 属性包含 FQDN pool01.contoso.net 仅会议目录。
    
3. 若要移动会议目录，请对池中运行的每个会议目录的以下命令：
    
  ```
  Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
  ```

    例如，若要移动会议目录 3，使用此命令中，指定为业务服务器 2019年池 Skype 作为 TargetPool:
    
  ```
  Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
  ```

    如果您想要移动的所有会议目录的池上，使用类似如下的命令：
    
  ```
  Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
  ```

有关停用旧池全面的分步说明下载[卸载旧的 Microsoft and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227) 。
  
移动会议目录时, 可能会遇到以下错误：
  
```
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

通常，当业务 Server 命令行管理程序 Skype 需要更新的 Active Directory 权限才能完成任务集，将发生此错误。 若要解决此问题，关闭当前实例的命令行管理程序，然后打开命令行管理程序的新实例并重新运行此命令移动会议目录。
  

