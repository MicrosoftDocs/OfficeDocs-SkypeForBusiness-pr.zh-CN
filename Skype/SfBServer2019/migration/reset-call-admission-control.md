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
description: 如果旧前端池托管呼叫允许控制 (CAC) ，则必须将 CAC 托管移动到 Skype for Business Server 2019 池，然后才能删除旧前端池。
ms.openlocfilehash: c3ebb748d877e88060b699b1599c39038124565df361c5032533260e4c5643e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54334564"
---
# <a name="reset-call-admission-control"></a>重置呼叫允许控制

如果旧前端池托管呼叫允许控制 (CAC) ，则必须将 CAC 托管移动到 Skype for Business Server 2019 池，然后才能删除旧前端池。
  
### <a name="to-reset-cac"></a>重置 CAC

1. 打开拓扑生成器。
    
2. 右键单击站点节点，然后单击“编辑属性”。
    
3. 在“呼叫允许控制设置”下，确保选择“启用呼叫允许控制”。 
    
4. 在"前端 **池以运行 CAC** (CAC) "下，选择要承载 CAC 的 Skype for Business Server 2019 池，然后单击"确定 **"。**
    
5. 发布拓扑。
    

