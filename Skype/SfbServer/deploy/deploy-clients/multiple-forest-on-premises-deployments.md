---
title: Skype会议室系统多林本地部署
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 阅读本主题，了解如何在多林Skype部署会议室系统。
ms.openlocfilehash: 34b52f32ec3f1c611d8560c8f053e7fbe16b53bf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857039"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype会议室系统多林本地部署
 
阅读本主题，了解如何在多林Skype部署会议室系统。
  
> [!NOTE]
> 为了在多个林中部署，Skype 2014 年 8 月 26 Exchange Server发布的 2013 CU6。 避免对会议室系统重新Skype邮箱。 使用新的 (删除旧邮箱，然后) 会议室系统Skype资源邮箱。 若要通过删除邮箱来还原丢失的会议，请参阅连接[或还原已删除的邮箱](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help)。 
  
创建邮箱后，可以使用Set-CalendarProcessing配置邮箱。 有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6。 为 Skype 会议室系统创建 Exchange 资源邮箱后，按照单林本地部署下为 Skype for Business 启用 Skype 会议室系统帐户中的步骤为 Skype for Business 启用帐户。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>选项 1：创建新的资源邮箱

若要Skype多林环境中部署会议室系统：
  
1. 在 Active Directory 身份验证 (林) 创建链接用户 (LinkedRoomTest) 。
    
2. 在命令行管理程序Exchange Server命令：
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>选项 2：将现有会议室邮箱更改为Skype链接 (会议室) 邮箱

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```