---
title: Lync 2010 客户端计算机上配置个人联系人存储
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/29/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要： 配置旧客户端使用的个人联系人存储。
ms.openlocfilehash: 4afb40f57043988768118a0b83c0afe7e9df0028
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887776"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>Lync 2010 客户端计算机上配置个人联系人存储
  
如果要集成 Skype 业务服务器 2015年和 Exchange Server 2016 或 Exchange Server 2013，您应配置客户端使用的个人联系人存储。 具体而言，应配置 Skype for Business 的个人联系人存储库，为使用 Exchange，并在同一时间中，确保用户将不能重写该决定。 这可以通过在各客户端计算机上创建和配置注册表值来完成。
  
> [!NOTE]
> 下面的过程才需要使用 Lync 2010 客户端的客户端或更早版本。 Lync 2013 客户端和所有 Skype 业务客户端不会覆盖的联系人存储库设置的选项。
  
要在单个计算机上配置此值，请完成下列过程：
  
1. 在客户端计算机上，单击“**开始**”，然后单击“**运行**”。
2. 在“**运行**”对话框中，键入“regedit”，然后按 Enter。
3. 在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。
4. 右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。
5. 创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。
6. 验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。

如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。 有关此操作 Windows 10 中的详细信息，请参阅[创建组策略对象](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)文章。
  
