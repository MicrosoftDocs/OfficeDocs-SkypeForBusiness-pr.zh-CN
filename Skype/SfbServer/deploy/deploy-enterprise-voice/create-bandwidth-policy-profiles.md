---
title: 在服务器创建带宽策略Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: 创建或修改带宽策略，企业语音呼叫允许控制Skype for Business Server。
ms.openlocfilehash: 4ba24c7f1fa170386e6d74fc34ef99e580d5ac91
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583206"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a>在服务器创建带宽策略Skype for Business Server 
 
创建或修改带宽策略，企业语音呼叫允许控制Skype for Business Server。 
  
“带宽策略”定义对实时音频和视频内容的带宽使用量的限制。 带宽策略应用于bandwidth策略配置文件，这些策略配置文件可应用于多个网络站点以用于呼叫允许控制。
  
有关应在 CAC 部署中设置哪些带宽限制的指南，请参阅在 Skype for Business Server 中规划[呼叫允许Skype for Business Server。](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
以下过程中创建的示例策略会为音频总流量、各个音频会话、视频总流量和各个视频会话设置限制。例如，5Mb_Link 带宽策略配置文件将设置以下限制： 
  
- 音频限制：2,000 kbps
    
- 音频会话限制：200 kbps
    
- 视频限制：1,400 kbps
    
- 视频会话限制：700 kbps
    
> [!NOTE]
> 最小音频会话限制值为 40 kbps。最小视频会话限制值为 100 kbps。 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a>使用命令行管理程序创建带宽Skype for Business Server配置文件

1. 启动命令行Skype for Business Server：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击"Skype for Business Server **命令行管理程序"。**
    
2. 对于要创建的每个带宽策略配置文件，请运行 New-CsNetworkBandwidthPolicyProfile cmdlet。例如，运行：
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a>使用控制面板创建带宽Skype for Business Server配置文件

1. 打开Skype for Business Server控制面板"。
    
2. 在左侧导航栏中，单击“网络配置”。
    
3. 单击“策略配置文件”导航按钮。
    
4. 单击“新建”。
    
5. 在“新建策略配置文件”页上，单击“名称”，然后键入带宽策略配置文件的名称。
    
6. 单击“音频限制”，然后键入允许的所有音频会话组合的最大 kbps 数。
    
7. 单击“音频会话限制”，然后键入允许的每个单独音频会话的最大 kbps 数。
    
8. 单击“视频限制”，然后键入允许的所有视频会话组合的最大 kbps 数。
    
9. 单击“视频会话限制”，然后键入允许的每个单独视频会话的最大 kbps 数。
    
10. （可选）单击“说明”，然后键入其他信息来说明该带宽策略配置文件。
    
11. 单击“提交”。
    
12. 要完成为拓扑创建带宽策略配置文件，请为其他带宽策略配置文件的设置重复步骤 4 至步骤 11。
    
## <a name="see-also"></a>另请参阅

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)