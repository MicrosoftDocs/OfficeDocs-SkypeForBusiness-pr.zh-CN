---
title: "什么是紧急位置、地址和呼叫路由？"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: get-started-article
f1_keywords:
- ms.lync.lac.AddressAndLocation
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: 589bf5f5-490a-4215-8588-99bab7d33e31
description: "Learn what emergency address, location, and emergency call routing are, and how to plan and assign them to your users. "
---

# 什么是紧急位置、地址和呼叫路由？

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明]。
  
要在 Office 365 中配置调用计划，它是必需的紧急地址分配给每个电话号码时，您可以获得的电话号码，或者当其分配给用户支持紧急呼叫。电话号码紧急的地址之前，必须创建并验证紧急的地址。验证确保紧急地址被识别和处于可以由紧急响应服务使用的正确格式。（可选） 可以添加紧急地址中的某个位置，提供更多特定位置的用户。例如，floor、 机翼或链接到特定紧急地址的 office，则可能是紧急的位置。 即使紧急地址进行验证，则不可位置。
  
## 什么是紧急地址？

紧急地址需要活动的电话号码，但时，它是必需的依赖于国家/地区。 在美国，紧急地址时 **需要** 数字分配给用户。为其他国家/地区，如欧洲、 中东和非洲 (EMEA) 紧急地址时 **需要** Office 365 中或从另一个服务提供商或运营商传输，获取电话号码。
  
紧急的地址可能称为市镇地址、 街道地址或实际地址。它是位置的企业的您的组织的街道或市镇地址。 例如，  *12345 北美主街道，Redmond，WA 98052*  用于传送到相应派遣机构紧急呼叫，并可帮助查找紧急呼叫者的地址。很可能会需要多个紧急地址如果您的公司有多个物理业务位置。
  
验证紧急地址涉及确保它合法和紧急响应服务正确格式。可以创建并保存未验证，紧急地址，但只有验证的地址可与用户相关联。验证紧急地址并将其保存后，可以将它分配给用户。如果您需要更改已保存的验证紧急地址，您需要创建一个新。
  
## 什么是紧急位置？

紧急位置都具有以为更准确的位置在办公楼紧急地址相关联。紧急位置通常是平面布置、 构建机翼或办公室号码用户所在的位置。您可以添加任意的数量的位置与紧急地址关联。
  
向用户分配紧急地址，实际上是分配地址时引用的位置 ID。 位置 ID 包括引用的紧急地址（街道或市镇地址）。 如果不需要建筑内的位置，则紧急地址将包括默认紧急位置。 
  
## 什么是紧急呼叫路由？

紧急地址和位置路由到相应派遣中心的紧急呼叫过程中时使用调度紧急的第一个响应。 当 Skype for Business 用户拨紧急的数字时，如何将呼叫路由到服务公共安全回答点 (PSAP) 将会因国家/地区。 某些国家/地区，例如在美国和英国，呼叫会先进行检查，以确定当前位置的用户，然后才能连接到相应派遣中心呼叫。 在其他国家/地区，呼叫将被直接路由到调度中心提供与紧急呼叫关联的电话号码。
  
## 创建、 添加和分配给您的用户的紧急位置和地址

1. **规划紧急位置**第一步是规划紧急的位置。您需要列出所有您的实际地址。 然后，基础，确定是否需要紧急地址的位置，并且如果是这样，什么是。例如，如果企业具有 3 办公楼每个与 4 楼层，很可能，还需要具有楼层 1-4 对于每个列为位置 3 紧急的地址。
    
2. **创建并验证紧急位置** 下一步是创建和验证紧急地址。当你创建紧急地址时，可以验证它。要创建紧急地址，请参阅[为你的组织添加或删除紧急地址](add-or-remove-an-emergency-address-for-your-organization.md)。
    
    > [!IMPORTANT]
    > 验证的街道或市镇地址涉及确保它合法和正确格式。很可能部分正确的紧急地址，例如输入错误名称的城市，可能仍通过通过验证。验证过程使用给定的地址的所有部分确定它是否包含足够的信息来传送到相应的紧急派遣中心呼叫。 如果是这样，它会返回验证，然后可以分配给电话号码。 
  
3. **获取电话号码**下一步是为您的用户获取电话号码。通过 Office 365 中收到新的电话号码或""导入或将您现有的电话号码，通过转到 Office 365，您可以执行此操作。若要完成的步骤，请参阅[将电话号码转移到 Office 365](transfer-phone-numbers-to-office-365.md)。
    
4. **分配电话号码**最后一步是使用户能够拨打和接听电话呼叫。若要执行此操作，您必须为每个用户分配电话号码。请参阅[为用户分配、更改或删除电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)分配电话号码。
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  
## 另请参阅
<a name="MT_Footer"> </a>

#### 其他资源

[Skype for Business Online： 紧急呼叫免责声明标签](https://go.microsoft.com/fwlink/?LinkID=692099)
  
[紧急呼叫条款和条件](emergency-calling-terms-and-conditions.md)
  
[音频会议免费拨出时间段](../accessibility-and-regulatory/audio-conferencing-complimentary-dial-out-period.md)

