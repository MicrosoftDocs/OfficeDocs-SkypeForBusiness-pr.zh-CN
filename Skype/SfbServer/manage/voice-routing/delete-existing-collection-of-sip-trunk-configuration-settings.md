---
title: 在 Skype for Business Server 中删除 SIP 中继配置设置的现有集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。 '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274931"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>在 Skype for Business Server 中删除 SIP 中继配置设置的现有集合

SIP 中继配置设置定义了在服务提供商处中介服务器和公共交换电话网络 (PSTN) 网关、IP 公共分支 exchange (PBX) 或会话边界控制器 (SBC) 之间的关系和能力。 这些设置可执行如下所指定内容的操作：

- 是否在中继上启用媒体旁路功能。
- 发送实时传输控制协议 (RTCP) 数据包的条件。
- 每个主干上是否需要安全的实时协议 (SRTP) 加密。

安装 Skype for Business 服务器时, 将为你创建一个全局 SIP 中继配置设置集合。 此全局集合设置无法删除。 但是, 你可以使用 Skype for Business ServerControl 面板或[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 将全局集合中的属性 "重置" 为其默认值。 例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。

管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：

- 如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。
- 如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。

**通过 Skype for Business 服务器控制面板删除中继配置设置** 

1. 在 "Skype for Business 服务器" 控制面板中, 单击 "**语音路由**", 然后单击 "**中继配置**"。
2. 在 "**中继配置**" 选项卡上, 选择要删除的 SIP 中继配置设置的集合, 单击 "**编辑**", 然后单击 "**删除**"。 若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。
3. 集合的“状态”**** 属性将更新为“未提交”****。若要提交更改和删除集合，请单击“提交”****，然后单击“全部提交”****。
4. 在“未提交的语音配置设置”**** 对话框中，单击“确定”****。
5. 在 " **Skype For Business 服务器控制面板**" 对话框中, 单击 **"确定"**。
6. 如果你改变主意并决定不删除集合, 请单击 "**提交**", 然后单击 "**取消所有未提交的更改**"。 当出现 " **Skype For Business 服务器控制面板**" 对话框时, 单击 **"确定"**。

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell cmdlet 删除中继配置设置


你可以使用 Windows PowerShell 和**new-cstrunkconfiguration** cmdlet 删除中继配置设置。 你可以从 Skype for Business Server Management Shell 或 Windows PowerShell 的远程会话中运行此 cmdlet。 

**删除指定的设置集合**

以下命令将删除应用于 Redmond 站点的中继配置设置：

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**删除适用于站点范围的所有集合**

以下命令将删除应用于服务作用域的所有中继配置设置：

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**删除启用了媒体旁路的所有集合**

以下命令将删除启用了媒体旁路的所有中继配置设置：

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

有关详细信息, 请参阅[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 的帮助主题。
