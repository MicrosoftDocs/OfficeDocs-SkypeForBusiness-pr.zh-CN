---
title: 位置策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: fa1ca0907d3316066e2ca6e1fcf8a1d09a9c315a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy"></a>位置策略
 
位置策略确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。 
  
位置策略包括全局策略以及可选的一个或多个站点和用户策略：
  
- **全球政策：**默认情况下创建全球政策。 可以编辑全局策略，但无法将其删除。 如果您尝试删除全局策略，则所有设置将重置为默认值。
    
- **网站策略 （可选）：**您可以创建一个或多个站点的位置策略，其中每个适用的特定网站。 站点策略会覆盖全局策略。
    
- **用户策略 （可选）：**您可以创建一个或多个用户的位置策略，其中每个适用于特定用户或用户组。 用户策略会覆盖全局策略和站点策略。
    
> [!NOTE]
> 也可以向网络站点（即子网组）分配位置策略。 分配给网络站点的位置策略优先于所有其他用户策略。 有关使用 cmdlet 分配到网络站点的位置策略的详细信息，请参阅[添加到业务服务器 2015年的 Skype 的网络站点的位置策略](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。 有关使用 Skype 业务服务器控件面板将位置策略指派给网络站点的详细信息，请参阅[配置网络站点](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。 
  
“**位置策略**”页显示一个为组织定义的所有位置策略的列表。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**位置策略**”页上执行以下任务：
  
- 创建新的站点位置策略或用户位置策略
    
- 更改全局策略或现有站点策略或用户策略
    
- 删除站点策略或用户策略
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个命令。
  
- **新**启动一个新网站的位置策略或用户的位置策略。
    
- **编辑**打开所选的位置策略对其进行编辑，在列表中，选择所有位置策略或删除选定的站点策略或用户策略。
    
    > [!NOTE]
    > 对于全局策略，“**删除**”会将设置重置为默认值。
  
- **刷新**刷新列表中的位置策略。
    
下表介绍了该页上的各个字段。
  
- **名称**标识的位置策略。
    
- **作用域**标识位置策略的作用域： 全局站点或用户。
    
- **E9-1-1**已检查如果分配了此位置策略为用户启用 E9-1-1。
    
- **位置**指定将提示用户输入位置信息，和当他们的客户端使用 Skype 注册业务服务器在一个新的位置，是否他们看到免责声明，如果它们消除而无需输入位置信息的提示。
    
- **PSTN 使用情况**指定公用交换的电话网络 (PSTN) 用法，用来确定语音路由用于路由使用此配置文件从客户端的紧急电话。
    
- **E9-1-1 号**指定拨号连接紧急服务的数量。
    
- **E9-1-1 掩码**指定用户拨，然后转换成紧急拨数字的号码。
    
企业语音紧急服务的特性和功能的详细信息，请参阅规划文档中[概述的 E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。 有关使用位置策略的详细信息，请参阅操作文档中的[配置位置策略](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。
  

