---
title: 在 Lync 2010 客户端计算机上配置个人联系人存储
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要：配置旧客户端使用的个人联系人存储。
ms.openlocfilehash: 9a9b5938d7e97460a6b8582f1563eeeb4c369272
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749353"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>在 Lync 2010 客户端计算机上配置个人联系人存储
  
如果要集成 Skype for Business Server 2015 和 Exchange Server 2016 或 Exchange Server 2013，则应该配置客户端使用的个人联系人存储。 特别是，您应Skype for Business将 Exchange 用作个人联系人存储，同时确保用户无法替代该决定。 这可以通过在每个客户端计算机上创建和配置注册表值来完成。
  
> [!NOTE]
> 以下过程仅适用于使用 Lync 2010 客户端或更早版本客户端的客户端。 Lync 2013 客户端和Skype for Business客户端将不能覆盖联系人存储设置。
  
要在单个计算机上配置此值，请完成下列过程：
  
1. 在客户端计算机上，单击"**开始"，** 然后单击"运行 **"。**
2. 在" **运行** "对话框中，键入 regedit，然后按 Enter。
3. 在注册表编辑器中，展开"HKEY_LOCAL_MACHINE"、"**软件****"、"** 策略"和 **"Microsoft"，** 然后展开"Communicator"。 
4. 右键单击 **"Communicator"，** 指向"新建"，然后单击 **"DWORD (32 位) 值"。**
5. 创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。
6. 验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。

如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。 有关在组策略Windows 10的详细信息，请参阅创建[组策略对象](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)一文。
