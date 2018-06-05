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
ms.openlocfilehash: b075b3191581f5f5f9b4a89ee6e28986effe02d4
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569531"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype 会议室系统多林本地部署
 
阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
  
> [!NOTE]
> 为了在多个林中部署，Skype 会议室系统要求 2014 年 8 月 26 日发布的 Exchange Server 2013 CU6。 避免 Skype 会议室 system 重新使用现有的邮箱。 使用新 （删除旧的邮箱并重新创建） 的 Skype 会议室系统资源邮箱。 若要还原的会议丢失通过删除邮箱，请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx)。 
  
在创建邮箱之后，你可以使用 Set-CalendarProcessing 配置邮箱。 有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6。 在创建后 Skype 会议室系统，Exchange 资源邮箱帐户启用 for Business 的 Skype 按照中启用 Skype 会议室系统帐户的步骤为 for Business 的 Skype 下的单林本地部署。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>方法 1：创建新的资源邮箱

在多林环境中部署 Skype 会议室系统：
  
1. 在 Active Directory（身份验证林）中创建链接用户 (LinkedRoomTest)。
    
2. 在 Exchange Server 命令行管理程序中运行以下命令：
    
   ```
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>选项 2： 更改现有的会议室邮箱到 Skype 会议室系统 （链接） 的资源邮箱

```
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


