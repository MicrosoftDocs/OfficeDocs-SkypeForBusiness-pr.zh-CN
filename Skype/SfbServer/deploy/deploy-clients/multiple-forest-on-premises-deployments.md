---
title: Skype 会议室系统多林本地部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: b5a0a2615f8174ea5e7d56dcaf0830765365bb48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype 会议室系统多林本地部署
 
阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
  
> [!NOTE]
> 要部署在多目录林中，Skype 的空间系统需要 Exchange Server 2013 CU6 发布的 8 月 26，2014年。 避免重新使用 Skype 的空间系统现有的邮箱。 使用新 （旧邮箱删除和重新创建） Skype 的空间系统的资源邮箱。 要还原丢失通过删除该邮箱的会议，请参阅[连接或恢复已删除的邮箱](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx)。 
  
在创建邮箱之后，你可以使用 Set-CalendarProcessing 配置邮箱。 有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6。 Skype 的空间系统创建 Exchange 资源邮箱后, 启用此帐户的 Skype 业务按照启用 Skype 的空间系统帐户中的步骤为 Skype 业务下单目录林内部部署。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>方法 1：创建新的资源邮箱

在多目录林环境中部署 Skype 的空间系统：
  
1. 在 Active Directory（身份验证林）中创建链接用户 (LinkedRoomTest)。
    
2. 在 Exchange Server 命令行管理程序中运行以下命令：
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>选项 2： 更改现有的会议室邮箱到 Skype 的空间系统 （链接） 的资源邮箱

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1

```


