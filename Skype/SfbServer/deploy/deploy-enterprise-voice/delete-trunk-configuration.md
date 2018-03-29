---
title: 在 Skype for Business Server 2015 中删除现有 SIP 中继配置设置的集合
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 摘要： 了解如何通过 Skype 业务服务器控制面板删除中继配置设置的集合。
ms.openlocfilehash: 4193922cbf3c318ada0e896a6082c51f33615330
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中删除现有 SIP 中继配置设置的集合
 
**摘要：**了解如何通过 Skype 业务服务器控制面板删除中继配置设置的集合。
  
SIP 中继配置设置可定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置可执行如下所指定内容的操作：
  
- 是否在中继上启用媒体旁路功能。
    
- 发送实时传输控制协议 (RTCP) 数据包所依据的条件。
    
- 在每个中继上是否需要安全实时传输协议 (SRTP) 加密。
    
为业务服务器安装 Skype 时，为您创建的 SIP 中继配置设置一个全局集合。 此全局集合设置无法删除。 但是，可以使用 Skype 业务服务器的控制面板或[删除 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet"重置"全局集合中的属性为它们的默认值。 例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。
  
管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：
  
- 如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。
    
- 如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>若要删除与 Skype 业务服务器控件面板的中继配置设置

1. 在 Skype 业务服务器的控制面板，单击**传送语音**，然后单击**中继配置**。
    
2. 在“Trunk 配置”****选项卡上，选择要删除的 SIP 中继配置设置的集合，单击“编辑”****，然后单击“删除”****。若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。
    
3. 集合的“状态”****属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。
    
4. 在“未提交的语音配置设置”****对话框中，单击“确定”****。
    
5. 在**Skype 业务服务器控件面板的**对话框中单击**确定**。
    
6. 如果你改变了想法并决定不删除集合，请单击“**提交**”，然后单击“**取消所有未提交的更改**”。 **Skype 业务服务器控制面板**对话框出现时，单击**确定**。
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>通过 Skype 业务服务器管理外壳 Cmdlet 删除中继配置设置

通过 Skype 业务服务器管理外壳程序和**删除 CsTrunkConfiguration** cmdlet，您可以删除中继的配置设置。 您可以运行此 cmdlet 从 Skype 业务服务器管理外壳程序或从远程会话的 Skype 业务服务器管理外壳程序。
  
### <a name="to-remove-a-specified-collection-of-settings"></a>删除指定的设置集合

- 以下命令将删除应用于 Redmond 站点的中继配置设置：
    
  ```
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>删除适用于站点范围的所有集合

- 以下命令将删除应用于服务作用域的所有中继配置设置：
    
  ```
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>删除启用了媒体旁路的所有集合

- 以下命令将删除启用了媒体旁路的所有中继配置设置：
    
  ```
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

有关详细信息，请参阅[删除 CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

