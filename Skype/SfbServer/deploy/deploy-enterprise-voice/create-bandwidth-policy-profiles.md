---
title: 在 Skype for Business Server 2015 中创建带宽策略配置文件
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 创建或修改带宽策略，使用 Skype 中的企业语音呼叫允许控制业务服务器。
ms.openlocfilehash: 51516e07a75cc4239d89310c9d33194a225b3a02
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500588"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建带宽策略配置文件
 
创建或修改带宽策略，使用 Skype 中的企业语音呼叫允许控制业务服务器。 
  
带宽策略定义为实时音频和视频形式的带宽使用率限制。 带宽策略是应用的 tobandwidth 策略配置文件，它们可以应用于的呼叫允许控制的多个网络站点。
  
有关哪些带宽限制的准则应 CAC 部署中设置，请参阅[规划中的业务服务器 2015 Skype 的呼叫允许控制](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。
  
以下过程中创建的示例策略会为音频总流量、各个音频会话、视频总流量和各个视频会话设置限制。例如，5Mb_Link 带宽策略配置文件将设置以下限制： 
  
- 音频限制：2,000 kbps
    
- 音频会话限制：200 kbps
    
- 视频限制：1,400 kbps
    
- 视频会话限制：700 kbps
    
> [!NOTE]
> 最小音频会话限制值为 40 kbps。最小视频会话限制值为 100 kbps。 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>使用 Skype 业务 Server 命令行管理程序创建带宽策略配置文件

1. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
2. 对于要创建的每个带宽策略配置文件，请运行 New-CsNetworkBandwidthPolicyProfile cmdlet。例如，运行：
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>使用 Skype 业务 Server 控制面板创建带宽策略配置文件

1. 打开 Skype 业务 Server Control Panel。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 单击“策略配置文件”**** 导航按钮。
    
4. 单击“新建”****。
    
5. 在“新建策略配置文件”**** 页上，单击“名称”****，然后键入带宽策略配置文件的名称。
    
6. 单击“音频限制”****，然后键入允许的所有音频会话组合的最大 kbps 数。
    
7. 单击“音频会话限制”****，然后键入允许的每个单独音频会话的最大 kbps 数。
    
8. 单击“视频限制”****，然后键入允许的所有视频会话组合的最大 kbps 数。
    
9. 单击“视频会话限制”****，然后键入允许的每个单独视频会话的最大 kbps 数。
    
10. （可选）单击“说明”****，然后键入其他信息来说明该带宽策略配置文件。
    
11. 单击“**提交**”。
    
12. 要完成为拓扑创建带宽策略配置文件，请为其他带宽策略配置文件的设置重复步骤 4 至步骤 11。
    
## <a name="see-also"></a>另请参阅

[新 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-csnetworkbandwidthpolicyprofile](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[设置 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[删除 CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)