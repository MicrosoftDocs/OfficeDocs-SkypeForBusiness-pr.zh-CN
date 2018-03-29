---
title: 在 Skype for Business Server 中部署 Skype 会议室系统
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99443d60-e64a-4a8a-a7bf-95f790b0ad5c
description: 了解如何执行部署 Skype 的空间系统，会议房间解决方案包含集成的硬件和软件的优化加入 Skype 业务会议。
ms.openlocfilehash: 11cbae1cdbdd0585a2ea67625179ee7862309723
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-system-in-skype-for-business-server"></a>在 Skype for Business Server 中部署 Skype 会议室系统
 
了解如何执行部署 Skype 的空间系统，会议房间解决方案包含集成的硬件和软件的优化加入 Skype 业务会议。
  
> [!NOTE]
> 为此目的内容、 业务智能的空间系统，Crestron RL 的 Skype 和 Polycom CX8000 称为 Skype 的空间系统。 
  
 Skype 的空间系统是物理的会议室中的业务会议优化的 Skype 业务统一的通信客户端的 Skype。
  
Skype 的空间系统客户端的开发是从业务客户端的 Skype 通过 Skype 业务 SDK。 在部分抑制的 UI 模式在后台运行业务客户端的 Skype。 Skype 业务客户端控制的视频库和内容舞台前部文件室的屏幕上。 Skype 的空间系统客户端提供用于控制会议和显示控制台体验。 Skype 的空间系统提供了： 
  
- 一键式与会体验
    
- 多视图视频库的自动设置 
    
- 会议室前方的屏幕上的启用触摸的白板 
    
- 集成日历，可用于访问计划会议
    
- 内容共享和交换 
    
本文档将指导您完成配置业务服务器和 Exchange Server Skype 在 Skype 的空间系统。 另请参阅由您的管理员联系，将引导您完成在会议室中设置的装置 PC 和设备提供 Skype 的空间系统安装指南。 
  
## <a name="prerequisites"></a>先决条件

Skype 的空间系统的要求如下： 
  
- Exchange 资源邮箱帐户，促进为在 Exchange Server（首选 2013）上启用了自动发现服务的会议室安排日历计划。
    
- 启用业务的 Skype 的空间系统帐户业务服务器池 （企业版或标准版） Skype 上 Skype。
    
- Skype 的空间系统客户端装置的 PC 安装所需的全部软件。 家用电脑必须运行 Windows 7 Embedded Standard 操作系统。 此硬件连同所有设备（显示屏、摄像头、麦克风、扬声器）由 OEM 合作伙伴提供。
    
- 如果您决定将 Skype 的空间系统装置电脑加入到 Active Directory 域服务 (AD DS) 域，您必须指定组策略设置不会影响与 Skype 的空间系统。 或者，你可以将此家用电脑留在工作组中。 
    
- 此文档指定的运行 cmdlet 所需的合适用户权限。CsMeetingRoom cmdlet 是在 CsUser cmdlet 之后建模的。因此，运行 CsUser cmdlet 所需的所有基于角色的访问控制 (RBAC) 角色也适用于 CsMeetingRoom cmdlet。 
    
## <a name="supported-topologies"></a>支持的拓扑

下表指示 Skype 的空间系统之间各种业务和 Exchange 拓扑结构，在内部或在云中的 Skype 的部署的客户端互操作性： 
  

|**拓扑**|**广告**|**Skype for Business**|**Exchange**|
|:-----|:-----|:-----|:-----|
|内部部署  <br/> |内部部署  <br/> |内部部署  <br/> |内部部署  <br/> |
|Office 365 多租户 (O365MT)  <br/> |Online  <br/> |Online  <br/> |联机  <br/> |
|Office 365 专用  <br/> （请联系您的服务提供商）  <br/> |内部部署  <br/> |联机  <br/> |联机  <br/> |
|混合（拆分域）  <br/> 不支持  <br/> |内部部署  <br/> 内部部署  <br/> 内部部署  <br/> |内部部署  <br/> 联机  <br/> Online  <br/> |Online  <br/> 联机  <br/> 内部部署  <br/> |
   
Lync Server 2013 之前的版本部分受支持。 在这些方案中，Skype 的空间系统可以参与 Skype （那些由用户计划宿主 Lync Server 2010） 的业务会议，只要会议是"公用"，意味着会议不为自定义的受限制的访问。 
  
Skype 的空间系统不能早于 Lync Server 2013 穴 Lync 服务器版本上。 当 Skype 的空间系统无法连接到 Exchange 可检索日历设置--例如，当 Skype 的空间系统帐户配置没有 Exchange 邮箱或不能访问 Exchange-立即开会和特别会议将工作，但加入已安排的会议不会。 
  
下表指示 Skype 的空间系统客户端支持的 Exchange Server 版本： 
  

|**Exchange**|**内部部署**|**联机**|**混合**|
|:-----|:-----|:-----|:-----|
|Exchange 2010  <br/> |是（仅限单林）  <br/> |不适用  <br/> |不适用  <br/> |
|Exchange 2013  <br/> |是（多林支持适用于 Exchange 2013 CU6 和更高版本）  <br/> |是  <br/> |是  <br/> |
|Exchange 2016  <br/> |是 （多目录林提供支持）  <br/> |是  <br/> |是  <br/> |
   

