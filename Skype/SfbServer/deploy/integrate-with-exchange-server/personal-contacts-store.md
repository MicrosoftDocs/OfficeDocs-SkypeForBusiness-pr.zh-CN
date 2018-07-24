---
title: 配置个人联系人存储客户端计算机上的 Skype 业务服务器
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要： 配置 Exchange Server 2016 或 Exchange Server 2013 和 Skype 由用于业务服务器的个人联系人存储。
ms.openlocfilehash: 311bab825412bae79c240ddb0f923c693b97103e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21012898"
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server"></a>配置个人联系人存储客户端计算机上的 Skype 业务服务器
 
**摘要：** 配置用于业务服务器的 Exchange Server 2016 或 Exchange Server 2013 和 Skype 的个人联系人存储。
  
如果您的业务服务器和 Exchange Server 2016 或 Exchange Server 2013 集成 Skype，然后应运行 for Business 的 Skype 任何客户端计算机上配置的个人联系人存储库。 具体而言，应配置 Skype for Business 的个人联系人存储库，为使用 Exchange，并在同一时间中，确保用户将不能重写该决定。 这可以通过在各客户端计算机上创建和配置注册表值来完成。
  
请注意，这不要求运行 for Business 的 Skype 的计算机上。
  
要在单个计算机上配置此值，请完成下列过程：
  
1. 在客户端计算机上，单击“**开始**”，然后单击“**运行**”。
    
2. 在“**运行**”对话框中，键入“regedit”，然后按 Enter。
    
3. 在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。
    
4. 右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。
    
5. 创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。
    
6. 验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。
    
如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。 有关详细信息，请参阅组策略文档[https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543)。
  

