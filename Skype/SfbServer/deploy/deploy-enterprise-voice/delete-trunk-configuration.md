---
title: Skype for Business Server：删除 SIP 中继配置设置的现有集合
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
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 摘要：了解如何使用"控制面板"删除中继配置Skype for Business Server集合。
ms.openlocfilehash: 294a6c2e39387aa9245af0c23eec56d1fd59dbc2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772863"
---
# <a name="skype-for-business-server-delete-an-existing-collection-of-sip-trunk-configuration-settings"></a>Skype for Business Server：删除 SIP 中继配置设置的现有集合 
 
**摘要：** 了解如何使用"控制面板"删除中继配置Skype for Business Server集合。
  
SIP 中继配置设置定义中介服务器与服务提供商的公用电话交换网 (PSTN) 网关、IP-Public 交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。 这些设置按下面的指示执行此类操作：
  
- 是否应该在中继上启用媒体旁路
    
- 发送实时传输控制协议 (RTCP) 的条件
    
- 每个中继上是否需要安全实时传输 (SRTP) 加密
    
在安装Skype for Business Server时，将创建 SIP 中继配置设置的全局集合。 此全局集合设置无法删除。 但是，您可以使用 Skype for Business Server 或[Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) cmdlet 将全局集合中的属性"重置"为默认值。 例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。
  
管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。 删除这些自定义设置时，请记住以下事项：
  
- 如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。
    
- 如果删除站点范围的设置，则由这些设置管理的任何 SIP 中继现在都将由中继配置设置的全局集合管理。
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a>使用控制面板删除中继Skype for Business Server设置

1. 在Skype for Business Server控制面板"中，单击"**语音路由**"，然后单击"**中继配置"。**
    
2. 在 **"Trunk 配置"** 选项卡上，选择要删除的 SIP 中继配置设置的集合，单击"编辑"，然后单击"删除 **"。** 若要在同一操作中删除多个集合，请单击要删除的第一个集合，然后按住 Ctrl 键，然后单击任何其他要删除的集合。
    
3. 集合的“状态”属性将更新为“未提交”。若要提交更改和删除集合，请单击“提交”，然后单击“全部提交”。
    
4. 在“未提交的语音配置设置”对话框中，单击“确定”。
    
5. 在 **"Skype for Business Server控制面板**"对话框中，单击"确定 **"。**
    
6. 如果您改变了想法并决定不删除集合，请单击“提交”，然后单击“取消所有未提交的更改”。 当显示 **Skype for Business Server控制面板**"对话框时，单击"确定 **"。**
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a>使用命令行管理设置 Cmdlet 删除Skype for Business Server配置配置

可以使用命令行管理程序和 **Remove-CsTrunkConfiguration** cmdlet Skype for Business Server中继配置设置。 可以从命令行管理程序或 Skype for Business Server命令行管理程序的远程会话中运行此 cmdlet Skype for Business Server cmdlet。
  
### <a name="to-remove-a-specified-collection-of-settings"></a>删除指定的设置集合

- 以下命令将删除应用于 Redmond 站点的中继配置设置：
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a>删除应用于网站范围的所有集合

- 以下命令将删除应用于服务作用域的所有中继配置设置：
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a>删除启用了媒体旁路的所有集合

- 以下命令将删除启用了媒体旁路的所有中继配置设置：
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

有关详细信息，请参阅 [Remove-CsTrunkConfiguration](/powershell/module/skype/remove-cstrunkconfiguration) cmdlet 的帮助主题。
