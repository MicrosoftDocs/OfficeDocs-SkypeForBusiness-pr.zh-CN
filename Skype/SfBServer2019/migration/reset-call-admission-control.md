---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 如果旧版前端池承载呼叫允许控制（CAC），则必须将 CAC 托管到 Skype for Business Server 2019 池，然后才能删除旧版前端池。
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753294"
---
# <a name="reset-call-admission-control"></a>重置呼叫允许控制

如果旧版前端池承载呼叫允许控制（CAC），则必须将 CAC 托管到 Skype for Business Server 2019 池，然后才能删除旧版前端池。
  
### <a name="to-reset-cac"></a>重置 CAC

1. 打开拓扑生成器。
    
2. 右键单击站点节点，然后单击“编辑属性”****。
    
3. 在“呼叫允许控制设置”**** 下，确保选择“启用呼叫允许控制”****。 
    
4. 在 "**前端池" 下运行呼叫允许控制（CAC）**，选择要承载 CAC 的 Skype For business Server 2019 池，然后单击 **"确定"**。
    
5. 发布拓扑。
    

