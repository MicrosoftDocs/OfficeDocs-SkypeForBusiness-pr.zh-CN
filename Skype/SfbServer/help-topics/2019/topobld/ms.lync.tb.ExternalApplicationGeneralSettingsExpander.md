---
title: 外部应用程序常规设置扩展器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑已定义的受信任的应用程序服务器的属性, 请按照以下说明操作。
ms.openlocfilehash: 96118d968a5c9fdf54a78df24019426e562220dd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292778"
---
# <a name="external-application-general-settings-expander"></a>外部应用程序常规设置扩展器
 
若要编辑已定义的受信任的应用程序服务器的属性, 请按照以下说明操作。
  
可以修改两个部分:
  
> 常规设置
> 
> 下一跃点设置
    
## <a name="general-settings"></a>常规设置

你可以修改受信任的应用服务器池的当前完全限定的域名 (FQDN)。 编辑池 FQDN 的名称。 在客户端或服务器可以连接到新的池名称之前, 必须为新条目存在域名系统 (DNS) 主机 (A) 记录。
  
如果需要将配置数据复制到此池, 请选择 "**启用将配置数据复制到此池**"。 如果不想复制配置数据, 请清除复选标记。
  
## <a name="next-hop-settings"></a>下一跃点设置

你可以通过从下拉列表中选择定义的企业版前端池或标准版前端服务器来指定受信任的应用程序服务器池的下一个跃点服务器。 Director 或控制器池不是受信任的应用程序服务器下一跃点的有效选择, 并且不会显示在列表中。
  

单击 **"确定"** 接受并保存所做的更改。 单击“**取消**”将放弃所做的更改并退出属性页面。
  

