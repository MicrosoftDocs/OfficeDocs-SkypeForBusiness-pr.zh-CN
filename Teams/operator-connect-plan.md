---
title: 运算符连接
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解操作员连接，例如要求和部署规划。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 088b36f546cebe67e10d840075e601e96a6df6e2
ms.sourcegitcommit: 39d26edd43b6066d5a6dee2a5ad1354a1e560a0d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694537"
---
# <a name="plan-for-operator-connect"></a>规划操作员连接

>[!NOTE]
>运算符连接目前仅在公共 **预览版中可用**。 公共预览版允许测试即将推出的功能并提供反馈。 公共预览版中包含的功能可能不完整，可能发生更改，在云中不受Office 365 政府版支持。

运营商连接是提供 PSTN 公用电话交换 (PSTN) 连接Teams和电话系统。  

本文介绍权益和要求，并列出参与操作员和连接的操作员。  如果确定"操作员连接是适合组织的解决方案，阅读本文后，请参阅配置运算符[连接。](operator-connect-configure.md)  

## <a name="benefits"></a>优点

使用接线连接，如果现有运营商是 Microsoft 接线员连接参与者，他们可管理将 PSTN 呼叫引入 Teams。 操作员连接计划提供以下优势：

- **利用现有合同，或查找新的操作员。** 保留首选的操作员和合同，或者从一系列参与的运营商中选择一个新的，以满足业务需求。

- **操作员管理的基础结构。** 运营商管理 PSTN 呼叫服务和会话边界控制器 (SDC) ，从而节省硬件购买和管理费用。

- **更快、更轻松地部署。** 你可以快速连接到接线员并将电话号码分配给用户 -- 全部Teams管理中心。

- **增强的支持和可靠性。** 操作员提供技术支持和共享服务级别协议来改善支持服务，而由 Azure 提供支持的直接对等互连则创建一对一网络连接以提高可靠性。

## <a name="requirements"></a>要求

 如果连接，操作员管理可能是适合组织的解决方案：

- Microsoft 呼叫计划在你的地理位置不可用。
- 首选操作员是 Microsoft Operator 连接参与者。
- 您希望查找新的接线员，以在 Teams。

若要使用"接线员"连接电话号码分配，请确保你的用户：

- Teams 电话许可。 有关详细信息，请参阅[什么是电话系统？和Teams](what-is-phone-system-in-office-365.md)[向用户分配附加许可证](teams-add-on-licensing/assign-teams-add-on-licenses.md)。
- 在 TeamsOnly 模式下。 若要了解有关详细信息，[请参阅了解Microsoft Teams Skype for Business共存和互操作性](teams-and-skypeforbusiness-coexistence-and-interoperability.md)。

## <a name="available-operators"></a>可用运算符

以下运算符是 Microsoft Operator 连接参与者：

| 接线员 | 功能 | 国家/地区覆盖范围 |
| --- | --- | --- |
| `BT`  | 通话 | 比利时、丹麦、芬兰、法国、德国、爱尔兰、意大利、卢森堡、荷兰、挪威、波兰、南非、西班牙、瑞典、瑞士、英国 |
| `Intrado` | 通话 | 比利时、加拿大、丹麦、法国、德国、爱尔兰、卢森堡、荷兰、西班牙、瑞典、英国、美国  |
| `NTT`  | 通话 | 奥地利、比利时、巴西、加拿大、捷克、丹麦、芬兰、法国、德国、爱尔兰、意大利、卢森堡、墨西哥、荷兰、挪威、波兰、葡萄牙、波多黎各、罗马尼亚、南非、西班牙、瑞典、瑞士、英国、美国 |
| `NuWave` | 通话 | 奥地利、比利时、加拿大、丹麦、法国、德国、爱尔兰、意大利、荷兰、葡萄牙、西班牙、瑞典、瑞士、英国、美国   |
| `Orange Business Services` | 通话 | 奥地利、比利时、捷克、丹麦、芬兰、法国、法属 Guiana、德国、瓜德罗普、爱尔兰、意大利、卢森堡、马提克隆、马约特、荷兰、挪威、波兰、葡萄牙、留尼西亚、圣巴塞勒米、圣马丁、西班牙、斯瓦巴德、瑞典、瑞士、英国  |
| `Pure IP` | 通话 | 澳大利亚、奥地利、比利时、巴西、保加利亚、加拿大、智利、哥伦比亚、克罗地亚、塞浦路斯、捷克、丹麦、芬兰、法国、德国、希腊、香港特别行政区、爱尔兰、意大利、日本、立陶宛、卢森堡、马来西亚、墨西哥、荷兰、新西兰、挪威、秘鲁、波兰、葡萄牙、波多黎各、罗马尼亚、新加坡、斯洛伐克、斯洛文尼亚、南非、西班牙、瑞典、瑞士、英国、美国  |
| `Rogers Business` | 通话 | 加拿大  |
| `TATA Communications` | 通话 | 澳大利亚、奥地利、比利时、加拿大、捷克、丹麦、法国、德国、香港特别行政区、匈牙利、爱尔兰、意大利、马来西亚、墨西哥、荷兰、新西兰、波兰、葡萄牙、罗马尼亚、新加坡、韩国、西班牙、瑞典、瑞士、泰国、英国、美国 |
| `Telekom Deutschland` | 通话 | 德国  |
| `Telenor` | 通话 | 丹麦、芬兰、挪威、瑞典  |
| `Verizon` | 通话 | 美国 |
