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
ms.localizationpriority: medium
description: 在停用池之前，您必须对旧池中的每个会议目录执行以下过程。
ms.openlocfilehash: 5d4333f74c1d45e57e45c66c8de6f3e279cee01f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596146"
---
# <a name="move-conference-directories"></a>移动会议目录

在停用池之前，您必须对旧池中的每个会议目录执行以下过程。
  
### <a name="to-move-a-conference-directory-to-skype-for-business-server-2019"></a>将会议目录移动到 Skype for Business Server 2019

1. 打开"Skype for Business Server命令行管理程序"。
    
2. 若要获取组织中会议目录的标识，请运行以下命令：
    
   ```PowerShell
   Get-CsConferenceDirectory
   ```

    上述命令返回组织的所有会议目录。 因此，您可能希望将结果限制为要停用的池。 例如，如果要停用具有完全限定域名 (FQDN) pool01.contoso.net 的池，请使用此命令将返回的数据限制为该池中的会议目录：
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
   ```

    该命令仅返回 ServiceID 属性包含 FQDN 参数的会议 pool01.contoso.net。
    
3. 若要移动会议目录，请对池中的每个会议目录运行以下命令：
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
   ```

    例如，若要移动会议目录 3，请使用此命令，将 Skype for Business Server 2019 池指定为 TargetPool：
    
   ```PowerShell
   Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
   ```

    如果要移动池上的所有会议目录，请使用类似如下的命令：
    
   ```PowerShell
   Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"
   ```

下载 [卸载 Microsoft 旧版和删除服务器角色](https://go.microsoft.com/fwlink/p/?linkId=246227) ，查看有关停用旧池的全面分步说明。
  
移动会议目录时，可能会遇到以下错误：
  
```console
WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.
```

当命令行管理程序需要更新的 Active Directory 权限集Skype for Business Server完成任务时，通常会发生此错误。 若要解决此问题，请关闭命令行管理程序的当前实例，然后打开命令行管理程序的新实例，然后重新运行命令以移动会议目录。
  

