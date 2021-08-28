---
title: 外部应用程序常规设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: 若要编辑已定义的受信任应用程序服务器的属性，请遵循以下说明。
ms.openlocfilehash: a19a2271caebe2dc0acc6c2c0609e76abfdb338c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626874"
---
# <a name="external-application-general-settings-expander"></a>外部应用程序常规设置扩展器
 
若要编辑已定义的受信任应用程序服务器的属性，请遵循以下说明。
  
您可以修改以下两部分：
  
> 常规设置
> 
> 下一跃点设置
    
## <a name="general-settings"></a>常规设置

可以修改受信任应用程序服务器池的当前完全限定域名 (FQDN)。编辑池的 FQDN。新条目必须具有域名系统 (DNS) 主机 (A) 记录，客户端或服务器才能连接到新池名称。
  
如果需要该池配置数据的副本，请选中“允许将配置数据复制到此池”。如果不希望复制配置数据，请清除复选标记。
  
## <a name="next-hop-settings"></a>下一跃点设置

通过从下拉列表 Enterprise Edition中选择定义的前端池或Standard Edition前端服务器，可以指定受信任应用程序服务器池的下一个跃点服务器。 控制器或控制器池不是受信任应用程序服务器下一跃点的有效选择，不会显示在列表中。
  

单击 **"确定** "接受并保存更改。 单击“取消”将放弃所做的更改并退出属性页面。
  

