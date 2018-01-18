---
title: "什么是紧急位置、地址和呼叫路由？"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: ms.lync.lac.AddressAndLocation
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: 'Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. '
ms.openlocfilehash: b6f9ffcbba68a7892a137a68565de97fe390d00f
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="what-are-emergency-locations-addresses-and-call-routing"></a>什么是紧急位置、地址和呼叫路由？

当在 Office 365 中配置调用计划时，要求每个电话号码配给一个紧急的地址，或您可以得到的电话号码时指派给用户以支持紧急电话。 将紧急的地址分配给一个电话号码之前, 必须创建并验证一个紧急的地址。 验证可确保紧急通讯被识别并且是可供紧急响应服务的正确格式。 （可选） 可以添加紧急通讯中的位置提供更具体的用户位置。 例如，紧急位置可能是地板、 翼形或链接到特定的紧急通讯的办公室。 即使紧急地址进行验证，并不是位置。
  
## <a name="what-are-emergency-addresses"></a>什么是紧急地址？

活动的电话号码，需要紧急的地址，但当它是必需是取决于国家/地区。 在美国，紧急通讯时**需要**大量分配给用户。 对于其他国家或地区，如欧洲、 中东和非洲 (EMEA) 紧急通讯时**需要**从 Office 365 或另一个服务提供商或运营商传输收到的电话号码。
  
紧急通讯可能称为市政地址、 街道地址或物理地址。 它是业务的为您的组织地点的街道或市政地址。 例如， *12345 北主街道，雷蒙德，WA 98052*用于路由到相应派遣机构的紧急电话，并以帮助定位紧急调用方的地址。 很可能会需要紧急的多个地址，如果您的公司有多个物理的营业地点。
  
验证应急通讯涉及确保它合法且紧急响应服务的格式正确。 可以创建并保存紧急地址未验证，但只有经过验证的地址可以是与用户相关联。 紧急通讯是验证并保存后，可以将它分配给用户。 如果需要更改已保存的已验证紧急地址，您将需要创建一个新。
  
## <a name="what-are-emergency-locations"></a>什么是紧急位置？

紧急位置是使建筑物内的更精确位置紧急地址相关联。 紧急的位置通常是平面布置、 建筑机翼或办公室号码用户所在的位置。 可以有无限个紧急地址相关联的位置。 
  
当用户分配一个紧急的地址，是实际分配地址时采取的引用的位置标识。 位置 ID 包含被引用的紧急地址 （街道或市政地址）。 在构建位置不需要时附带的情况下紧急地址默认紧急位置。 
  
## <a name="what-is-emergency-call-routing"></a>什么是紧急呼叫路由？

紧急的地址和位置路由到相应的派单中心的紧急电话的过程时使用调度紧急的第一反应。 当业务用户的 Skype 拨叫紧急号码时，如何将呼叫路由到服务公共安全应答点 (PSAP) 会因国家/地区。 在某些国家，如美国和英国，该调用将第一次进行检查，以连接到相应调度中心电话之前确定当前用户的位置。 在其他国家/地区，调用将被直接路由到调度中心服务的关联与紧急呼叫的电话号码。
  
## <a name="creating-adding-and-assigning-emergency-locations-and-addresses-to-your-users"></a>创建、 添加和将紧急位置和地址分配给您的用户

1. **规划对于紧急的位置**第一步是安排紧急的位置。 您需要列出所有您的物理地址。 然后，此基础，确定是否需要紧急地址的位置，如果出现这种情况，它们是什么。 例如，如果企业具有 3 办公楼每 4 厂用，很可能，必须有 3 个紧急地址，与 1-4 的位置列出每个楼层。
    
2. **创建和验证您的紧急位置**下一步是创建并验证您的紧急地址。 创建一个紧急的地址时，可以对其进行验证。 若要创建一个紧急的地址，请参阅[添加或删除为您的组织满足紧急情况](add-or-remove-an-emergency-address-for-your-organization.md)。
    
    > [!IMPORTANT]
    > 验证的街道或市政地址涉及确保它合法且格式正确。 它有可能部分正确的急诊地址，例如键入错误的城市，可能仍然通过密码验证。 验证过程使用给定地址的所有部分来确定它是否包含足够的信息路由到适当的紧急调度中心呼叫。 如果是这样，它会返回验证，然后可以分配到一个电话号码。 
  
3. **获取电话号码**下一步是获取用户的电话号码。 通过从 Office 365 中获取新的电话号码或"移植"或将对您现有的电话号码转到 Office 365 可以执行此操作。 若要查看完整的步骤，请参阅[传输到 Office 365 的电话号码](transfer-phone-numbers-to-office-365.md)。
    
4. **指定的电话号码**最后一步是使用户能够拨打和接听电话。 若要执行此操作，必须为每个用户分配一个电话号码。 请参阅[指派、 更改或删除的用户的电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)分配的电话号码。

> [!NOTE]
> 如果您需要得到比这更多的电话号码，请[联系支持业务产品的管理帮助](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

    
## <a name="related-topics"></a>相关主题
[什么是地址验证？](what-is-address-validation.md)

[不同种类的用于调用计划的电话号码](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[紧急呼叫条款和条件](../what-are-calling-plans-in-office-365/emergency-calling-terms-and-conditions.md)

[Skype for Business Online：紧急呼叫免责标签](https://go.microsoft.com/fwlink/?LinkID=692099)
