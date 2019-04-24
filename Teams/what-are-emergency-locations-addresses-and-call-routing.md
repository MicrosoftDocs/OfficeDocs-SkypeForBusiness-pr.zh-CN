---
title: 什么是紧急位置、 地址和呼叫路由？
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: 4e9fd0d3fa9fabc1f9b2176a4dc2b7ac59206352
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211705"
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>什么是紧急位置、 地址和呼叫路由？

配置时调用计划在 Office 365 中，您必须将紧急地址分配给每个电话号码，获取电话号码或将其分配给用户支持紧急呼叫时。 您可以为紧急地址分配电话号码之前，必须创建和验证紧急地址。 验证可以确保紧急地址被识别，并且是可由紧急响应 services 使用正确的格式。 或者，您可以添加内提供用户的更多特定位置的紧急地址的位置。 例如，floor、 wing 或链接到特定的紧急地址的 office，无法为紧急位置。 验证紧急地址，尽管不位置。
  
## <a name="what-are-emergency-addresses"></a>什么是紧急地址？

紧急地址需要活动的电话号码，但需要时取决于国家/地区。 在美国，紧急地址时需要一个号码分配给用户。 其他国家/地区，如欧洲、 中东和非洲 (EMEA) 中的紧急地址时需要您要从 Office 365 或从其他服务提供商或运营商传输获取电话号码。
  
紧急地址可能称为市政地址、 街道地址或物理地址。 它是你的组织业务经营场所的街道或市镇地址。 例如， *12345 北美 Main Street，Redmond，WA 98052*用于紧急呼叫路由到相应派遣机构和帮助查找紧急呼叫者的地址。 如果你的企业有多个物理位置，你可能需要多个紧急地址。
  
验证紧急地址涉及确保它合法和格式正确的应急响应服务。 可以创建并保存紧急地址不验证，但仅验证的地址可与用户相关联。 验证和保存紧急地址后，即可将其分配给用户。 如果需要更改保存的已验证紧急地址，你需要创建一个新紧急地址。
  
## <a name="what-are-emergency-locations"></a>什么是紧急位置？

紧急位置相关联的紧急的地址，以提供大厦内的更精确位置。 紧急位置通常是用户所在的楼层、侧楼或办公室编号。 您可以数量不限与紧急地址关联的位置。 
  
为用户分配的紧急地址，时，实际上引用时指定地址的位置 ID。 位置 ID 包括的引用的紧急地址 （街道或市政地址）。 默认紧急位置随中构建位置不所需的情况下紧急地址。 
  
## <a name="what-is-emergency-call-routing"></a>什么是紧急呼叫路由？

紧急地址和位置的紧急呼叫路由至相应派遣中心过程时使用派遣紧急的第一个响应者。 当工作组或业务用户的 Skype 拨打紧急号码，如何将该呼叫路由到公共安全应答点 (PSAP) 提供不同的国家/地区。 在某些国家/地区，如美国和英国，呼叫将先进行检查，以连接到相应派遣中心呼叫之前确定当前用户的位置。 在其他国家/地区，呼叫将路由到调度中心提供紧急呼叫者与关联的电话号码直接。
  
## <a name="create-add-and-assign-emergency-locations-and-addresses-to-your-users"></a>创建、 添加和将紧急位置和地址分配给您的用户

1. **规划紧急位置**。 第一步是规划您的紧急位置。 您需要的所有您的物理地址列表。 然后，此基础，确定是否需要紧急地址的位置，如果是这样，它们是什么。 例如，如果企业具有 3 办公楼每个与 4 楼层，很可能有需要 3 紧急地址，1-4 为位置列出每个楼层。
    
2. **创建和验证您紧急位置**。 下一步是创建和验证您紧急地址。 当你创建紧急地址时，可以验证它。 若要创建紧急地址，请参阅[添加或删除紧急情况地址为您的组织](/SkypeForBusiness/what-are-calling-plans-in-office-365/add-or-remove-an-emergency-address-for-your-organization)。
    
    > [!IMPORTANT]
    > [!重要信息] 验证街道或市镇地址涉及确保该地址是合法的并且格式设置正确。 则可能部分正确的紧急地址，例如键入错误市/县的名称可能仍通过验证。 验证过程使用给定的地址的所有部分，确定它是否包含足够的信息来将呼叫路由到适当的紧急派遣中心。 如果是这样，它将返回为已验证，并且然后可以分配给电话号码。 
  
3. **获取电话号码**。 下一步是为用户获取电话号码。 你可以通过从 Office 365 获取新的电话号码或通过将现有电话号码"转网"或转移到 Office 365 来获取号码。 若要查看的完整步骤，请参阅[转接到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。
    
4. **分配电话号码**。 最后一步是使用户可以发起和接收电话呼叫。 要执行此操作，你必须为每个用户分配电话号码。 请参阅[分配、 更改或删除的用户的电话号码](/SkypeForBusiness/what-are-calling-plans-in-office-365/assign-change-or-remove-a-phone-number-for-a-user)分配电话号码。

> [!NOTE]
> 如果需要获取更多电话号码，请[联系商业版产品支持人员 - 管理员帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>相关主题
[什么是地址验证？](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-is-address-validation)

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

