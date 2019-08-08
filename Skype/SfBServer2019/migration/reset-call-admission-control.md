---
title: 重置呼叫允许控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 如果旧版前端池是托管呼叫许可控制 (CAC), 则必须先将 CAC 托管版迁移到 Skype for business Server 2019 池, 然后才能删除旧的前端池。
ms.openlocfilehash: 812391eda436906020c41b14a53c8ea18c4b1aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241323"
---
# <a name="reset-call-admission-control"></a>重置呼叫允许控制

如果旧版前端池是托管呼叫许可控制 (CAC), 则必须先将 CAC 托管版迁移到 Skype for business Server 2019 池, 然后才能删除旧的前端池。
  
### <a name="to-reset-cac"></a>重置 CAC

1. 打开拓扑生成器。
    
2. 右键单击 "网站" 节点, 然后单击 "**编辑属性**"。
    
3. 在 "**呼叫许可控制" 设置**下, 请确保已选中 "**启用呼叫许可控制**"。 
    
4. 在 "**前端池" 下运行呼叫许可控制 (CAC)**, 选择要托管 CAC 的 Skype For business Server 2019 池, 然后单击 **"确定"**。
    
5. 发布拓扑。
    

