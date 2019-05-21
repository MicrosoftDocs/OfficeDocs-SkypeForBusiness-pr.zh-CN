---
title: 什么是紧急位置、地址和呼叫路由？
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: c7e1bb719f0292bd605f920517017d2d4f6cae65
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288155"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>什么是紧急位置、地址和呼叫路由？

当您在 Office 365 中配置呼叫计划时, 您必须为每个电话号码分配一个紧急地址, 以便您获取电话号码或将其分配给用户以支持紧急呼叫。 您必须先创建并验证紧急地址, 然后才能将紧急地址分配给电话号码。 验证可确保已识别紧急地址, 并且其格式正确, 可供紧急响应服务使用。 或者, 您可以在 "紧急地址" 中添加一个位置, 以便为用户提供更具体的位置。 例如, 紧急位置可以是链接到特定紧急地址的楼层、翼形或办公室。 虽然紧急地址已验证, 但位置不是。
  
## <a name="what-are-emergency-addresses"></a>什么是紧急地址？

有效电话号码必须有紧急地址, 但在需要时取决于国家/地区。 在美国, 向用户分配了一个电话号码时, 需要紧急地址。 对于其他国家或地区 (如欧洲、中东和非洲 (EMEA)), 当您从 Office 365 获取电话号码或从其他服务提供商或运营商处转移时, 需要使用紧急地址。
  
紧急地址可能被称为市政地址、街道地址或物理地址。 它是你的组织业务经营场所的街道或市镇地址。 例如, 地址 12345 "北卡罗来纳州"、 *"雷德蒙"、"WA" 和 "WA 98052* " 用于将紧急呼叫路由到相应的派遣机构, 并帮助查找紧急呼叫方。 如果你的企业有多个物理位置，你可能需要多个紧急地址。
  
验证紧急地址需要确保它是合法且格式正确的紧急响应服务。 可以创建并保存未经过验证的紧急地址, 但只有经过验证的地址才能与用户相关联。 验证和保存紧急地址后，即可将其分配给用户。 如果需要更改保存的已验证紧急地址，你需要创建一个新紧急地址。
  
## <a name="what-are-emergency-locations"></a>什么是紧急位置？

紧急位置与紧急地址相关联, 以便在大楼内提供更准确的位置。 紧急位置通常是用户所在的楼层、侧楼或办公室编号。 您可以拥有与紧急地址相关联的无限数量的位置。 
  
向用户分配紧急地址时, 它实际上是分配地址时引用的位置 ID。 位置 ID 包括引用的紧急地址 (街道或市政地址)。 对于不需要内部生成位置的情况, 将在紧急地址中包含一个默认紧急位置。 
  
## <a name="what-is-emergency-call-routing"></a>什么是紧急呼叫路由？

紧急地址和位置在将紧急呼叫发送到相应的派遣中心时, 在向相应的派遣中心发出紧急呼叫响应过程中使用。 当团队或 Skype for Business 用户拨打紧急电话号码时, 呼叫如何路由到服务公共安全应答点 (PSAP) 将因国家/地区而异。 在某些国家/地区 (如美国和英国), 将在将呼叫连接到相应的派遣中心之前, 先对呼叫进行筛选以确定用户的当前位置。 在其他国家/地区, 呼叫将直接路由到派遣中心, 为与紧急呼叫方相关联的电话号码提供服务。
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>为用户创建、添加和分配紧急位置和地址

1. **计划紧急地点**。 第一步是为紧急位置进行规划。 您需要列出所有物理地址。 然后, 根据这一点, 确定紧急地址的位置是否需要以及是否需要。 例如, 如果某一企业拥有3个以上的多个办公楼, 则可能需要有3个紧急地址, 其中 "楼层 1-4" 列为每个的位置。
    
2. **创建和验证紧急位置**。 下一步是创建和验证您的紧急地址。 当你创建紧急地址时，可以验证它。 若要创建紧急地址, 请参阅为[您的组织添加或删除紧急地址](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization)。
    
    > [!IMPORTANT]
    > [!重要信息] 验证街道或市镇地址涉及确保该地址是合法的并且格式设置正确。 部分正确的紧急地址 (如城市名称错误) 可能仍通过验证。 验证过程使用给定的地址的所有部分，确定它是否包含足够的信息来将呼叫路由到适当的紧急派遣中心。 如果是这样, 它将按验证返回, 然后可以分配给电话号码。 
  
3. **获取电话号码**。 下一步是为你的用户获取电话号码。 你可以通过从 Office 365 获取新的电话号码或通过将现有电话号码"转网"或转移到 Office 365 来获取号码。 若要查看完整步骤, 请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。
    
4. **分配电话号码**。 最后一步是使用户能够拨打和接听电话。 要执行此操作，你必须为每个用户分配电话号码。 请参阅为[用户分配、更改或删除电话](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)号码以分配电话号码。

> [!NOTE]
> 如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>相关主题
[什么是地址验证？](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

