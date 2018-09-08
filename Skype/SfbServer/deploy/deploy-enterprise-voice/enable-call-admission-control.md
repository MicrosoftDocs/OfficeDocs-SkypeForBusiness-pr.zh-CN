---
title: 启用 Business Server Skype 中的呼叫允许控制
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
description: 启用业务 Server 企业语音中 Skype 的呼叫允许控制。
ms.openlocfilehash: 75021b33c616fd4118a612b6e0d582459cd33b8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23881906"
---
# <a name="enable-call-admission-control-in-skype-for-business-server"></a>启用 Business Server Skype 中的呼叫允许控制
 
启用业务 Server 企业语音中 Skype 的呼叫允许控制。 
  
配置完呼叫允许控制部署的网络设置后，必须启用 CAC 来使带宽策略生效。
  
### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-management-shell"></a>若要使用 Skype 业务 Server 命令行管理程序启用呼叫允许控制

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 运行 Set-CsNetworkConfiguration cmdlet 以在网络中启用 CAC。例如，运行：
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
   ```

    如果要在网络中禁用 CAC，请运行以下命令：
    
   ```
   Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0
   ```

### <a name="to-enable-call-admission-control-by-using-skype-for-business-server-control-panel"></a>使用适用于业务 Server Control Panel Skype 启用呼叫允许控制

1. 打开 Skype 业务 Server Control Panel。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 单击“全局”**** 导航按钮。
    
4. 单击列表中的“全局”****，然后在“编辑”**** 菜单中选择“显示详细信息”****。
    
5. 在“编辑全局设置”**** 页上，选中“启用呼叫允许控制”**** 复选框。
    
    > [!NOTE]
    > 如果要在整个部署中禁用呼叫允许控制，请清除此复选框。 
  
6. 单击“**提交**”。 
    
## <a name="see-also"></a>另请参阅

[Get-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/get-csnetworkconfiguration?view=skype-ps)
  
[Set-csnetworkconfiguration](https://docs.microsoft.com/powershell/module/skype/set-csnetworkconfiguration?view=skype-ps)
  
[删除 CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkconfiguration?view=skype-ps)