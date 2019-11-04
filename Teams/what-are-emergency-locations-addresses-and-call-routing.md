---
title: 什么是紧急位置、地点和呼叫路由？
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
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.locations.emergencyaddresses.overview
- ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
description: '了解紧急地点、地点和紧急呼叫路由的定义，以及如何规划和为用户分配。 '
ms.openlocfilehash: 4dbfe8d2a10c24ae66967030007328d2b9422e34
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925383"
---
# <a name="what-are-emergency-locations-places-and-call-routing"></a>什么是紧急位置、地点和呼叫路由？

配置呼叫计划时，您必须为每个电话号码分配一个紧急位置（当您获取电话号码或将其分配给用户时），以便支持紧急呼叫。 您必须先添加并验证紧急位置，然后才能将紧急地点分配给电话号码。 验证可确保已识别紧急位置，并且该位置采用紧急响应服务可以使用的正确格式。 如果需要，您可以在紧急位置中添加一个位置，以便为用户提供更具体的位置。 例如，位置可以是链接到特定紧急位置的楼层、翼形或办公室。 虽然紧急位置已经过验证，但不会出现任何地方。
  
## <a name="what-are-emergency-locations"></a>什么是紧急位置？

有效电话号码需要紧急位置，并且在需要时取决于国家/地区。 在美国，如果向用户分配了一个号码，则需要紧急位置。 对于其他国家或地区（如欧洲、中东和非洲（EMEA）），当你获取来自团队的电话号码或从其他服务提供商或运营商转移到团队时，需要紧急位置。
  
紧急地点可能被称为市政地址、街道地址或具有可选位置的物理地址。 这是您的组织的公司位置的街道或市政地址。 例如，地址 12345 "北卡罗来纳州"、 *"雷德蒙"、"WA" 和 "WA 98052* " 用于将紧急呼叫路由到相应的派遣机构，并帮助查找紧急呼叫方。 如果您的企业有多个物理业务位置，则很可能需要多个紧急位置。
  
验证紧急地址需要确保它合法且已正确设置紧急响应服务的格式。 可以添加和保存未验证的紧急位置，但只能将已验证的位置与用户相关联。 验证并保存紧急位置后，您可以将其分配给用户。 要更改已保存和验证的紧急位置，您需要创建一个新的。
  
## <a name="what-are-places"></a>有什么地方？

一个位置与紧急位置相关联，以便在大楼内提供更准确的位置。 一个位置通常是用户所在的楼层、建筑物的翼形或办公室号码。 您可以拥有与紧急地址相关联的无限位数。
  
向用户分配紧急位置时，它实际上是分配位置时引用的位置 ID。 位置 ID 包括引用的紧急地址（街道或市政地址）。 对于不需要内部部署位置的情况，将在紧急位置附带一个默认位置。
  
## <a name="what-is-emergency-call-routing"></a>什么是紧急呼叫路由？

紧急位置和地点在将紧急呼叫发送到相应的派遣中心时，在向相应的派遣中心发出紧急响应的过程中使用。 当团队用户拨打紧急号码时，呼叫如何路由到服务公共安全应答点（PSAP）因国家和地区而异。 在某些国家/地区（如美国和英国），在将呼叫连接到相应的派遣中心之前，将首先筛选呼叫以确定用户的当前位置。 在其他国家和地区，呼叫直接路由到派遣中心，为与紧急呼叫方相关联的电话号码提供服务。
  
## <a name="create-add-and-assign-emergency-locations-and-places-to-your-users"></a>为您的用户创建、添加和分配紧急位置和位置

1. **计划紧急地点**。 第一步是为紧急位置进行规划。 列出所有物理地址。 然后，根据这一点，确定是否需要紧急位置的位置以及是否需要这些位置（如果有）。 例如，如果一位企业有三个办公楼，每个都有四个楼层，则可能需要有三个紧急位置，其中第一到四个是第一和第四个。
    
2. **添加紧急位置**。 下一步是添加紧急位置。 若要了解详细信息，请参阅为[你的组织添加、更改或删除紧急位置](add-change-remove-emergency-location-organization.md)。
    
    > [!IMPORTANT]
    > 验证街道或市政地址涉及确保其合法且格式正确。 部分正确的紧急地址（如城市名称）可能仍然通过验证。 验证过程使用给定地址的所有部分来确定它是否包含足够的信息，以将呼叫路由到相应的紧急派遣中心。 如果是这样，它将按验证返回，然后可以分配给电话号码。
  
3. **获取电话号码**。 下一步是为你的用户获取电话号码。 你可以通过从 Office 365 获取新的电话号码或通过将现有电话号码"转网"或转移到 Office 365 来获取号码。 若要查看完整步骤，请参阅[将电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)。
    
4. **分配电话号码**。 最后一步是使用户能够拨打和接听电话。 要执行此操作，你必须为每个用户分配电话号码。 请参阅为[用户分配、更改或删除电话](/microsoftteams/assign-change-or-remove-a-phone-number-for-a-user)号码以分配电话号码。

> [!NOTE]
> 如果您需要获得比这更多的电话号码，[请与 PSTN 服务支持人员联系](manage-phone-numbers-for-your-organization/contact-pstn-service-desk.md)。

    
## <a name="related-topics"></a>相关主题

[用于通话套餐的不同类型的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)