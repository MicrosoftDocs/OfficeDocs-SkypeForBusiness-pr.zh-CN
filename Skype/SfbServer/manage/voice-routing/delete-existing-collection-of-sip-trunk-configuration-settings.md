---
title: 删除现有 SIP 中继配置设置集合Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。 '
ms.openlocfilehash: 98e255f82face68132b24f798f45bc12134c9b3cbbbebe1fce5ac886361a7b46
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333334"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a>删除现有 SIP 中继配置设置集合Skype for Business Server

SIP 中继配置设置定义了中介服务器和服务提供商的公用电话交换网 (PSTN) 网关、IP 公用交换机 (PBX) 或会话边界控制器 (SBC) 之间的关系和功能。这些设置按下面的指示执行此类操作：

- 是否应对中继启用媒体旁路。
- 发送实时传输控制协议 (RTCP) 数据包的条件。
- 每个中继上是否需要安全实时协议 (SRTP) 加密。

在安装Skype for Business Server时，将创建 SIP 中继配置设置的全局集合。 此全局集合设置无法删除。 但是，您可以使用 Skype for Business ServerControl 面板或[Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 将全局集合中的属性"重置"为默认值。 例如，如果已将 Enable3pccRefer 属性设置为 True，则当您重置全局集合时，Enable3pccRefer 属性将还原为其默认值 False。

管理员还可以在站点作用域或服务作用域（针对单个 PSTN 网关）创建自定义中继配置设置；这些自定义设置可以删除。在删除这些自定义设置时，请注意以下事项：

- 如果删除了服务作用域设置，由这些设置管理的 SIP 中继将由应用于这些站点的设置（如果存在）管理。如果站点设置不存在，这些中继随后会由中继配置设置的全局集合管理。
- 如果删除了站点作用域设置，由这些设置管理的任何 SIP 中继都将立即由中继配置设置的全局集合管理。

**使用"控制面板"删除Skype for Business Server配置设置** 

1. 在"Skype for Business Server控制面板"中，单击"**语音路由**"，然后单击"**中继配置"。**
2. 在 **"Trunk 配置"** 选项卡上，选择要删除的 SIP 中继配置设置的集合，单击"编辑"，然后单击"删除 **"。** 若要在同一操作中删除多个集合，请单击第一个要删除的集合，然后按住 Ctrl 键并单击任何其他要删除的集合。
3. 集合的“状态”属性将更新为“未提交”。若要提交更改和删除集合，请单击“提交”，然后单击“全部提交”。
4. 在“未提交的语音配置设置”对话框中，单击“确定”。
5. 在 **"Skype for Business Server控制面板**"对话框中，单击"确定 **"。**
6. If you change your mind and decide not to delete the collection， click **Commit**， and then click **Cancel All Uncommitted Changes**. 当显示 **Skype for Business Server控制面板**"对话框时，单击"确定 **"。**

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a>使用 cmdlet 删除中继Windows PowerShell设置


可以通过使用 Windows PowerShell **和 Remove-CsTrunkConfiguration** cmdlet 删除中继配置设置。 可以从命令行管理程序或 Skype for Business Server远程会话中运行此 cmdlet Windows PowerShell。 

**删除指定的设置集合**

以下命令将删除应用于 Redmond 站点的中继配置设置：

`Remove-CsTrunkConfiguration -Identity site:Redmond`

**删除应用于网站范围的所有集合**

以下命令将删除应用于服务作用域的所有中继配置设置：

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

**删除启用了媒体旁路的所有集合**

以下命令将删除启用了媒体旁路的所有中继配置设置：

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

有关详细信息，请参阅 [Remove-CsTrunkConfiguration](/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet 的帮助主题。