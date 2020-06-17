---
title: 移动会议目录
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 在取消池的授权之前，必须为旧版池中的每个会议目录执行以下过程。
ms.openlocfilehash: 8a25b955ae769a712750ff08325b3fa29538be8a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752494"
---
# <a name="move-conference-directories"></a>移动会议目录

在取消池的授权之前，必须为旧版池中的每个会议目录执行以下过程。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>将会议目录移动到 Skype for Business Server 2019

1. 打开 Skype for Business Server 命令行管理程序。
    
2. 若要获取组织中会议目录的标识，请运行以下命令：
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    上述命令将返回组织中的所有会议目录。 因此，您可能希望将结果限制为即将停止的池。 例如，如果您要使用完全限定的域名（FQDN） pool01.contoso.net 取消池，请使用以下命令将返回的数据限制为来自该池的会议目录：
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    该命令仅返回 ServiceID 属性包含 FQDN pool01.contoso.net 的会议目录。
    
3. 若要移动会议目录，请为池中的每个会议目录运行以下命令：
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    例如，若要移动会议目录3，请使用此命令，将 Skype for Business Server 2019 池指定为 TargetPool：
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    如果要移动池中的所有会议目录，请使用类似如下的命令：
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

下载[Microsoft 旧版并删除服务器角色](https://go.microsoft.com/fwlink/p/?linkId=246227)，以获取有关退役旧池的全面的分步说明。
  
移动会议目录时，可能会遇到以下错误：
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

如果 Skype for Business Server 命令行管理程序需要一组更新的 Active Directory 权限才能完成任务，则通常会发生此错误。 若要解决此问题，请关闭命令行管理程序的当前实例，然后打开一个新的命令行管理程序实例，然后重新运行该命令以移动会议目录。
  

