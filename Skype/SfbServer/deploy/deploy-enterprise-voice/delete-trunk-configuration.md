---
title: 删除现有的 SIP 中继配置设置中 Skype 业务服务器集合
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 摘要： 了解如何使用适用于业务 Server Control Panel Skype 删除中继配置设置的集合。
ms.openlocfilehash: 27e022588798e848cf690bb643d921e46d827b39
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890535"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>删除现有的 SIP 中继配置设置中 Skype 业务服务器集合
 
**摘要：** 了解如何使用适用于业务 Server Control Panel Skype 删除中继配置设置的集合。
  
SIP 中继配置设置可定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置可执行如下所指定内容的操作：
  
- 是否在中继上启用媒体旁路功能。
    
- 发送实时传输控制协议 (RTCP) 数据包所依据的条件。
    
- 在每个中继上是否需要安全实时传输协议 (SRTP) 加密。
    
在安装 Skype 业务服务器时，会为您创建 SIP 中继配置设置的全局集合。 此全局集合设置无法删除。 但是，您可以使用业务 Server Control Panel 或[Remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet Skype 为其默认值"重置"中的全局集合的属性。 例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。
  
管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：
  
- 如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。
    
- 如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>删除与 Skype 的中继配置设置的业务 Server Control Panel

1. 在业务 Server Control Panel 的 Skype，单击**语音路由**，然后单击**Trunk 配置**。
    
2. 在“Trunk 配置”**** 选项卡上，选择要删除的 SIP 中继配置设置的集合，单击“编辑”****，然后单击“删除”****。若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。
    
3. 集合的“状态”**** 属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。
    
4. 在“未提交的语音配置设置”**** 对话框中，单击“确定”****。
    
5. 在**业务 Server Control Panel 的 Skype**对话框中单击**确定**。
    
6. 如果你改变了想法并决定不删除集合，请单击“**提交**”，然后单击“**取消所有未提交的更改**”。 **Skype 的业务 Server Control Panel**对话框出现时，单击**确定**。
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用 Skype 业务 Server 命令行管理程序 Cmdlet 删除中继配置设置

您可以使用 Skype 的业务 Server 命令行管理程序和**Remove-cstrunkconfiguration** cmdlet 删除中继配置设置。 您能运行此 cmdlet 从 Skype 业务 Server 命令行管理程序或从远程会话的 Skype 的业务 Server Management Shell。
  
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

有关详细信息，请参阅[Remove-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet 的帮助主题。
  

