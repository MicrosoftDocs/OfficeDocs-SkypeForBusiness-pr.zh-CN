---
title: 重置呼叫允许控制
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧的前端池承载呼叫允许控制 (CAC)，您必须移动 CAC 承载到业务服务器 2019年池 Skype，然后才能删除旧的前端池。
ms.openlocfilehash: 65d56d000c5bcec5f7aae73413c287dee8ab29ca
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027317"
---
# <a name="reset-call-admission-control"></a>重置呼叫允许控制

如果旧的前端池承载呼叫允许控制 (CAC)，您必须移动 CAC 承载到业务服务器 2019年池 Skype，然后才能删除旧的前端池。
  
### <a name="to-reset-cac"></a>重置 CAC

1. 打开拓扑生成器。
    
2. 右键单击网站节点，然后单击**编辑属性**。
    
3. 在**呼叫允许控制设置**中，确保选择**Enable Call Admission Control** 。 
    
4. **要运行呼叫允许控制 (CAC) 的前端池**下, 选择用于承载 CAC，业务服务器 2019年池 Skype，然后单击**确定**。
    
5. 发布拓扑。
    

