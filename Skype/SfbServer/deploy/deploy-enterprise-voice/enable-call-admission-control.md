---
title: 在 Skype for Business 服务器中启用呼叫许可控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 Skype for Business Server Enterprise Voice 中启用呼叫许可控制。
ms.openlocfilehash: c5fc500b4e0839b4db43bd229087b3a6bcc7e644
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767285"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>在 Skype for Business 服务器中启用呼叫许可控制
 
在 Skype for Business Server Enterprise Voice 中启用呼叫许可控制。 
  
配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>使用 Skype for Business 服务器命令行管理程序启用呼叫许可控制

1. 启动 Skype for Business Server 命令行管理程序：依次单击“开始”****、“所有程序”**** 和“Skype for Business 2015”****，然后单击“Skype for Business Server 命令行管理程序”****。
    
2. 运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    如果要在网络中禁用 CAC，请运行以下命令：
    
   ```powershell
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>使用 Skype for Business 服务器控制面板启用呼叫许可控制

1. 打开 "Skype for Business 服务器" 控制面板。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 单击“全局”**** 导航按钮。
    
4. 单击列表中的“全局”****，然后在“编辑”**** 菜单中选择“显示详细信息”****。
    
5. 在“编辑全局设置”**** 页上，选中“启用呼叫允许控制”**** 复选框。
    
    > [!NOTE]
    > 如果要在整个部署中禁用呼叫允许控制，请清除此复选框。 
  
6. 单击“**提交**”。 
    
## <a name="see-also"></a>另请参阅

[Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[Remove-Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)
