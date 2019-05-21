---
title: 在 Lync 2010 客户端计算机上配置个人联系人存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: '摘要: 配置旧版客户端使用的个人联系人存储。'
ms.openlocfilehash: ba9cb7ee485f94162a642f8e877213a7bcd47c55
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278082"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a>在 Lync 2010 客户端计算机上配置个人联系人存储
  
如果你要集成 Skype for Business Server 2015 和 Exchange Server 2016 或 Exchange Server 2013, 则应配置客户端使用的个人联系人存储。 尤其是, 你应该配置 Skype for Business 以将 Exchange 用作个人联系人存储, 同时确保用户无法覆盖该决策。 这可以通过在各客户端计算机上创建和配置注册表值来完成。
  
> [!NOTE]
> 仅对于使用 Lync 2010 客户端或更早版本的客户端, 以下过程才是必需的。 Lync 2013 客户端和所有 Skype for business 客户端将无法选择替代联系人存储设置。
  
要在单个计算机上配置此值，请完成下列过程：
  
1. 在客户端计算机上，单击“**开始**”，然后单击“**运行**”。
2. 在“**运行**”对话框中，键入“regedit”，然后按 Enter。
3. 在注册表编辑器中，依次展开“**HKEY_LOCAL_MACHINE**”、“**Software**”、“**Policies**”、“**Microsoft**”和“**Communicator**”。
4. 右键单击“**Communicator**”，指向“**新建**”，然后单击“**DWORD（32 位）值**”。
5. 创建新值后，键入 PersonalContactStoreOverride，然后按 Enter 来重命名该值。
6. 验证将 PersonalContactStoreOverride 的值设置为 0，然后关闭注册表编辑器。

如果您要在多台计算机上执行相同的更改，则可以通过创建自定义组策略对象执行此操作。 有关在 Windows 10 中执行此操作的详细信息, 请参阅[创建组策略对象一](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)文。
  
