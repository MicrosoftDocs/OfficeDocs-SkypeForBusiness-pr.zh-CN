---
title: 位置策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
ROBOTS: NOINDEX, NOFOLLOW
description: 位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: 9299b3b909e36a0f0cbfb28b20cc989fe7e09bbd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985260"
---
# <a name="location-policy"></a>位置策略
 
位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。 
  
位置策略包括全局策略以及可选的一个或多个站点和用户策略：
  
- **全局策略：** 默认情况下创建全局策略。 可以编辑全局策略，但无法将其删除。 如果您尝试删除全局策略，则所有设置将重置为默认值。
    
- **的网站策略 （可选）：** 您可以创建一个或多个站点位置策略，其中每个适用于特定站点。 站点策略会覆盖全局策略。
    
- **用户策略 （可选）：** 您可以创建一个或多个用户位置策略，其中每个适用于特定用户或用户组。 用户策略会覆盖全局策略和站点策略。
    
> [!NOTE]
> 也可以向网络站点（即子网组）分配位置策略。 分配给网络站点的位置策略优先于所有其他用户策略。 有关使用 cmdlet 将位置策略分配给网络站点的详细信息，请参阅[Add 与网络站点中的业务服务器 Skype 位置策略](../../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。 有关使用业务 Server Control Panel 的 Skype 与网络站点分配位置策略的详细信息，请参阅[配置网络站点](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。 
  
“**位置策略**”页显示一个为组织定义的所有位置策略的列表。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**位置策略**”页上执行以下任务：
  
- 创建新的站点位置策略或用户位置策略
    
- 更改全局策略或现有站点策略或用户策略
    
- 删除站点策略或用户策略
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。
  
- **新**开始一个新的站点位置策略或用户位置策略。
    
- **编辑**打开所选的位置策略以进行编辑，在列表中，选择所有位置策略或删除所选的站点策略或用户策略。
    
    > [!NOTE]
    > 对于全局策略，“**删除**”会将设置重置为默认值。
  
- **刷新**刷新位置策略的列表。
    
下表介绍了该页上的各个字段。
  
- **名称**标识位置策略。
    
- **范围**标识位置策略的范围： 全局、 站点或用户。
    
- **E9-1-1**检查是否分配了此位置策略的用户启用了 E9-1-1。
    
- **位置**指定会提示用户输入位置信息，以及他们的客户端将 Skype 将在新位置，业务服务器注册时是否如果他们无需输入位置信息消除提示符处，他们会看到免责声明。
    
- **PSTN 用法**指定用于确定用于将来自客户端使用此配置文件的紧急呼叫路由的语音路由的公用电话交换网 (pstn) 用法。
    
- **E9-1-1 号**指定要获得紧急服务时所拨打的号码。
    
- **E9-1-1 掩码**指定将用户拨打可转换成紧急拨打号码的号码。
    
有关企业语音紧急服务特性和功能的详细信息，请参阅规划文档中[概述的 E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。 有关使用位置策略的详细信息，请参阅操作文档中的[配置位置策略](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。
  

