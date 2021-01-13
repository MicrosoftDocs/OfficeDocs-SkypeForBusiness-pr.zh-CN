---
title: 在 Lync 2010 客户端计算机上配置个人联系人存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 摘要：配置旧客户端使用的个人联系人存储。
ms.openlocfilehash: 66ef1c3726ea020669894769b48b2313e1da2e0e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833932"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>在 Lync 2010 客户端计算机上配置个人联系人存储
  
如果要集成 Skype for Business Server 2015 和 Exchange Server 2016 或 Exchange Server 2013，则应该配置客户端使用的个人联系人存储。 特别是，你应配置 Skype for Business 以将 Exchange 用作个人联系人存储，同时确保用户无法覆盖该决定。 这可以通过在每个客户端计算机上创建和配置注册表值来完成。
  
> [!NOTE]
> 以下过程仅对使用 Lync 2010 客户端或更早版本客户端是必需的。 Lync 2013 客户端以及所有 Skype for Business 客户端将不能替代联系人存储设置。
  
要在单个计算机上配置此值，请完成下列过程：
  
1. 在客户端计算机上，单击 **"开始**"，然后单击"运行 **"。**
2. 在 **"运行** "对话框中，键入 regedit，然后按 Enter。
3. 在注册表编辑器中，HKEY_LOCAL_MACHINE、软件、策略 **、Microsoft，****然后展开** Communicator。   
4. 右 **键Communicator，** 指向 **"** 新建"，然后单击 **" (32 位) 的 DWORD。**
5. 创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。
6. 验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。

如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。 有关在 Windows 10 中执行此操作的详细信息，请参阅"创建 [组策略对象"](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) 文章。
  
