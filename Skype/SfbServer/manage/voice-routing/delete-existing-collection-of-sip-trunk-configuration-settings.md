---
title: 删除现有的 SIP 中继配置设置中 Skype 业务服务器集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。 '
ms.openlocfilehash: 144d40f45853b0d0e3031f9d491fa1a3b1491ba8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33896314"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>删除现有的 SIP 中继配置设置中 Skype 业务服务器集合

SIP 中继配置设置定义的关系和中介服务器和公用电话交换网 (pstn) 网关、 IP 公用交换机 (PBX) 或服务提供商会话边界控制器 (SBC) 之间的功能。 这些设置可执行如下所指定内容的操作：

- 是否在中继上启用媒体旁路功能。
- 在其下发送实时传输控制协议 (RTCP) 数据包的条件。
- 是否每个中继上是否需要安全实时协议 (SRTP) 加密。

在安装 Skype 业务服务器时，会为您创建 SIP 中继配置设置的全局集合。 此全局集合设置无法删除。 但是，您可以使用业务 ServerControl 面板或[Remove-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet Skype 为其默认值"重置"中的全局集合的属性。 例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。

管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：

- 如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。
- 如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。

**删除与 Skype 的中继配置设置的业务 Server Control Panel** 

1. 在业务 Server 控制面板的 Skype，单击**语音路由**，，然后单击**Trunk 配置**。
2. 在**Trunk 配置**选项卡中，选择的 SIP 中继配置设置，以删除，再单击**编辑**，然后单击**删除**集合。 若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。
3. 集合的“状态”**** 属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。
4. 在“未提交的语音配置设置”**** 对话框中，单击“确定”****。
5. 在**业务 Server Control Panel 的 Skype**对话框中，单击**确定**。
6. 如果改变了主意并且决定不删除集，单击**提交**，，然后单击**取消所有未提交的更改**。 **Skype 的业务 Server Control Panel**对话框出现时，单击**确定**。

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 删除中继配置设置


您可以使用 Windows PowerShell 和**Remove-cstrunkconfiguration** cmdlet 删除中继配置设置。 可以从 Skype 业务 Server 命令行管理程序或从 Windows PowerShell 远程会话来运行此 cmdlet。 

**删除指定的设置集合**

以下命令将删除应用于 Redmond 站点的中继配置设置：

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**删除适用于站点范围的所有集合**

以下命令将删除应用于服务作用域的所有中继配置设置：

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**删除启用了媒体旁路的所有集合**

以下命令将删除启用了媒体旁路的所有中继配置设置：

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

有关详细信息，请参阅[Remove-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 的帮助主题。
