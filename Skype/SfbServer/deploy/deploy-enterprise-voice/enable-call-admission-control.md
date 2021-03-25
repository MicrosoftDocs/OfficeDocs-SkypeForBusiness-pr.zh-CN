---
title: 在 Skype for Business Server 中启用呼叫允许控制
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 在 Skype for Business Server 企业语音 中启用呼叫允许控制。
ms.openlocfilehash: 2b8096a9223250cec88e57e68fdc201f5591fd92
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109858"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business Server 中启用呼叫允许控制
 
在 Skype for Business Server 企业语音 中启用呼叫允许控制。 
  
配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business Server 命令行管理程序启用呼叫允许控制

1. 启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
2. 运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    如果要在网络中禁用 CAC，请运行以下命令：
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business Server 控制面板启用呼叫允许控制

1. 打开 Skype for Business Server 控制面板。
    
2. 在左侧导航栏中，单击“网络配置”。
    
3. 单击“全局”导航按钮。
    
4. 单击列表中的“全局”，然后在“编辑”菜单中选择“显示详细信息”。
    
5. 在“编辑全局设置”页上，选中“启用呼叫允许控制”复选框。
    
    > [!NOTE]
    > 如果要在整个部署中禁用呼叫允许控制，请清除此复选框。 
  
6. 单击“提交”。 
    
## <a name="see-also"></a>另请参阅

[Get-CsNetworkConfiguration](/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-CsNetworkConfiguration](/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-CsNetworkConfiguration](/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)