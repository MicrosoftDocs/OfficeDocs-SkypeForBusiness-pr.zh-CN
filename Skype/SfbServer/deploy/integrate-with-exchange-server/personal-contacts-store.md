---
title: 在客户端计算机上为 Skype for Business Server 2015 配置个人联系人存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要： 配置使用 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年个人联系人存储库。
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a>在客户端计算机上为 Skype for Business Server 2015 配置个人联系人存储
 
**摘要：**配置使用 Exchange Server 2016年或 Exchange Server 2013年和 Skype 业务服务器 2015年个人联系人存储库。
  
如果您正在集成 Skype 业务服务器 2015年和 Exchange Server 2016年或 Exchange Server 2013年，应将个人联系人存储库配置运行 Skype 业务的所有客户端计算机上。 特别是，您应该配置 Skype 为企业与个人的联系人存储库，使用 Exchange，并在同一时间，确保用户将不能重写该决定。 这可以通过在各客户端计算机上创建和配置注册表值来完成。
  
请注意，这不需要运行业务的 Skype 的计算机上。
  
要在单个计算机上配置此值，请完成下列过程：
  
1. 在客户端计算机上，单击“**开始**”，然后单击“**运行**”。
    
2. 在“**运行**”对话框中，键入“regedit”，然后按 Enter。
    
3. 在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。
    
4. 右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。
    
5. 在创建新值之后，键入 PersonalContactStoreOverride，然后按 enter 键以便重命名值。
    
6. 验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。
    
如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。 有关详细信息，请参阅组策略文档，网址[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543)。
  

