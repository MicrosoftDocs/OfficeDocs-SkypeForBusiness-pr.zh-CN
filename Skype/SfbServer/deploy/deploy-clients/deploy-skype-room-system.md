---
title: Skype 会议室系统的部署概述
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
ms.collection: M365-voice
description: 阅读有关如何执行部署 Skype 会议室系统，会议房间解决方案集成的硬件和软件的优化业务会议加入 Skype 组成。
ms.openlocfilehash: 26ce5f6e50d26b408a8bce5d167e4e7b6046e514
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012565"
---
# <a name="deployment-planning-for-skype-room-system-in-skype-for-business"></a>部署规划中的业务的 Skype 的 Skype 会议室系统
 
阅读有关如何执行部署 Skype 会议室系统，会议房间解决方案集成的硬件和软件的优化业务会议加入 Skype 组成。
  
> [!NOTE]
> 对于此内容，Skype 的业务智能会议室系统 Crestron RL 和 Polycom CX8000 称为 Skype 会议室系统。 

> [!NOTE]
> Microsoft 团队聊天室是一种不同的产品具有不同的依赖项以及部署过程。 有关 Microsoft 团队聊天室的信息，请参阅[规划 Microsoft 团队 Rooms](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)。
  
 Skype 会议室系统是业务统一的通信客户端中物理会议室的业务会议优化的 Skype Skype。
  
从业务客户端 Skype 开发的 Skype 会议室 System 客户端是使用 Skype 业务 SDK。 在后台部分禁止显示在 UI 模式中运行业务客户端的 Skype。 业务客户端 Skype 控制视频库和在前面的聊天室在屏幕上的内容容器。 Skype 会议室系统客户端提供有关用于控制会议和显示控制台体验。 Skype 会议室系统提供了： 
  
- 一键式与会体验
    
- 多视图视频库的自动设置 
    
- 会议室前方的屏幕上的启用触摸的白板 
    
- 集成日历，可用于访问计划会议
    
- 内容共享和交换 
    
本文档指导您完成业务 Server 和 Exchange Server 设置中 Skype 的 Skype 会议室系统。 请参阅您的管理员，指导您完成在会议室中设置的装置 PC 和设备提供的 Skype 会议室系统安装指南。 
  
## <a name="prerequisites"></a>先决条件

以下是 Skype 会议室系统要求： 
  
- Exchange 资源邮箱帐户，促进为在 Exchange Server（首选 2013）上启用了自动发现服务的会议室安排日历计划。
    
- 启用业务的 Skype 会议室系统帐户上为业务服务器池 （Enterprise 或 Standard Edition） Skype Skype。
    
- Skype 会议室系统客户端设备 PC 了所有必需软件。 家用电脑必须运行 Windows 7 Embedded Standard 操作系统。 此硬件连同所有设备（显示屏、摄像头、麦克风、扬声器）由 OEM 合作伙伴提供。
    
- 如果您决定 Skype 会议室系统装置 PC 加入 Active Directory 域服务 (AD DS) 域，则必须指定不会干扰 Skype 会议室系统的组策略设置。 或者，你可以将此家用电脑留在工作组中。 
    
- 此文档指定的运行 cmdlet 所需的合适用户权限。CsMeetingRoom cmdlet 是在 CsUser cmdlet 之后建模的。因此，运行 CsUser cmdlet 所需的所有基于角色的访问控制 (RBAC) 角色也适用于 CsMeetingRoom cmdlet。 
    
## <a name="supported-topologies"></a>支持的拓扑

下表指示 Skype 会议室系统之间的业务和 Exchange 拓扑，本地或云中的 Skype 的各种部署的客户端互操作性： 
  

|**拓扑**|**AD**|**Skype for Business**|**交换**|
|:-----|:-----|:-----|:-----|
|内部部署  <br/> |内部部署  <br/> |内部部署  <br/> |内部部署  <br/> |
|Office 365 多租户 (O365MT)  <br/> |Online  <br/> |Online  <br/> |Online  <br/> |
|Office 365 专用  <br/> （联系服务提供商）  <br/> |内部部署  <br/> |Online  <br/> |Online  <br/> |
|混合（拆分域）  <br/> 不支持  <br/> |内部部署  <br/> 内部部署  <br/> 内部部署  <br/> |内部部署  <br/> Online  <br/> Online  <br/> |Online  <br/> Online  <br/> 内部部署  <br/> |
   
Lync Server 2013 之前的版本部分受支持。 在以下情况下，Skype 会议室系统可以参加 Skype 业务会议 （由用户安排的那些驻留在 Lync Server 2010），只要会议是"公共"，这意味着会议不为自定义受限制的访问。 
  
Skype 会议室系统无法早于 Lync Server 2013 驻留在 Lync server 版本上。 当 Skype 会议室系统无法连接到 Exchange 检索日历设置--例如，没有为 Skype 会议室系统帐户配置不 Exchange 邮箱或无法访问 Exchange-时立即开会和临时会议将工作，但加入不会预定的会议。 
  
下表指示 Skype 会议室系统与 Exchange Server 版本的客户端可支持性： 
  

|**交换**|**内部部署**|**Online**|**混合**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |是（仅限单林）  <br/> |不适用  <br/> |不适用  <br/> |
|Exchange 2013  <br/> |是（多林支持适用于 Exchange 2013 CU6 和更高版本）  <br/> |是  <br/> |是   <br/> |
|Exchange 2016  <br/> |是 （多林提供支持）  <br/> |是   <br/> |是  <br/> |
   

