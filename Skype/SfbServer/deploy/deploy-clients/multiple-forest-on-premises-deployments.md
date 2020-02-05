---
title: Skype 会议室系统多林本地部署
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6793fca0-3970-44e4-8703-1925428c1967
description: 阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
ms.openlocfilehash: ac9a5edac94d182812aefaf9eb817765c7af6444
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768815"
---
# <a name="skype-room-system-multiple-forest-on-premises-deployments"></a>Skype 会议室系统多林本地部署
 
阅读本主题，了解如何在多林本地环境中部署 Skype 会议室系统。
  
> [!NOTE]
> 为了在多个目录林中部署，Skype 会议室系统需要在2013年8月 26 2014 日发布的 Exchange Server CU6。 避免重新使用 Skype 会议室系统的现有邮箱。 为 Skype 会议室系统使用新的（删除旧邮箱和重新创建）资源邮箱。 若要还原通过删除邮箱而丢失的会议，请参阅[连接或还原已删除的邮箱](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)。 
  
在创建邮箱之后，你可以使用 Set-CalendarProcessing 配置邮箱。 有关更多详细信息，请参阅单林本地部署下的步骤 3 至 6。 为 Skype 会议室系统创建 Exchange 资源邮箱后，请按照在单个林本地部署中启用 Skype for business 的 Skype 会议室系统帐户中的步骤启用 Skype for business 帐户。
  
## <a name="option-1-create-a-new-resource-mailbox"></a>方法 1：创建新的资源邮箱

要在多林环境中部署 Skype 会议室系统，请执行以下操作：
  
1. 在 Active Directory（身份验证林）中创建链接用户 (LinkedRoomTest)。
    
2. 在 Exchange Server 命令行管理程序中运行以下命令：
    
   ```powershell
   $cred = Get-Credential AuthForest\LinkedRoomTest
   new-mailbox -Alias LinkedRoomTest -LinkedMasterAccount AuthForest\LinkedRoomTest -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -UserPrincipalName LinkedRoomTest@ExchangeForest.contoso.comm -Name LinkedRoomTest -LinkedCredential $cred -LinkedRoom
   ```

## <a name="option-2-change-an-existing-room-mailbox-to-skype-room-system-linked-resource-mailbox"></a>选项2：将现有会议室邮箱更改为 Skype 会议室系统（链接）资源邮箱

```powershell
$cred=Get-Credential AuthForest\LinkedRoomTest1
Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
```


