---
title: 规划 SIP 网关
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
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
description: 详细了解 SIP 网关，例如要求和优势。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 817f3dc7ce7f0b6f407607417c0cadb92b65e943
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514747"
---
# <a name="plan-for-sip-gateway"></a>SIP 网关计划

SIP 网关允许组织将任何兼容的 SIP 设备与 Microsoft Teams，以保留对 SIP 设备的投资。 现在，可以使用公司Teams登录，然后使用兼容的 SIP 设备拨打和接听电话。 兼容的设备可以是具有Skype for Business SIP 固件的 IP 电话、具有多平台 SIP 固件的 Cisco IP 电话，或者来自 Poly、Yealink 和 AudioCodes 等供应商的 SIP 设备。 若要了解如何为 SIP 网关配置 SIP 设备，请参阅 [配置 SIP 网关](sip-gateway-configure.md)。

## <a name="benefits-of-sip-gateway"></a>SIP 网关的好处

SIP 网关将兼容的 SIP 设备连接到 Teams，以帮助用户无缝迁移到Teams服务。 使用 SIP 网关，用户可以执行以下所有操作：

- **进行调用：** SIP 设备用户可以呼叫公用电话交换电话网络 (PSTN) 、呼叫其他 SIP 设备以及呼叫Teams Skype for Business用户。 SIP 设备用户只能呼叫具有电话号码的用户。
- **接收呼叫：** SIP 设备用户可以从 PSTN、拥有 SIP 设备的 Teams 或 Skype for Business 用户、来自 Teams 和 Skype for Business 客户端应用程序接收呼叫。 SIP 设备充当Teams终结点。 入站呼叫也将分叉到用户的 SIP 设备。
- **多个同时调用：** 呼叫中的 SIP 设备用户可以将呼叫置于保持状态以拨打或接听其他呼叫。 SIP 设备用户还可以召开两次通话。
- **请勿打扰：** SIP 设备用户可以在设备上设置"请勿打扰"，以便设备不会拨打传入呼叫。 这不会影响用户对所有其他终结点Teams状态。
- **保持/恢复和静音/取消静音：** SIP 设备用户可以通过使用设备上这些操作的功能来保持呼叫、恢复呼叫或者将呼叫静音和取消静音。
- **语音邮件：** SIP 设备用户可以收听呼叫者留下的电子存储语音消息。
- **消息等待指示器：** SIP 设备用户可以接收通知，在有新的语音邮件时提醒他们。
- **登录和注销：** SIP 设备用户可以在设备上登录Teams注销。
- **双音多频率：** SIP 设备用户可以在交互式语音响应呼叫期间按数字键提供输入。
- **Teams会议：** SIP 设备用户Teams拨会议访问号码加入会议。 会议参与者可以通过拨出到用户的电话号码或只需单击"加入请求"来添加参与者，将 SIP 设备用户添加到会议，这也会提醒用户的 SIP 设备。 通过拨出来宾用户号码以包括该来宾Teams可以将来自另一组织的来宾用户添加到会议。
- **呼叫转接：** SIP 设备用户可以转接呼叫。 SIP 网关支持失明和咨询传输。
- **本地呼叫转发：** SIP 设备用户可以为设备设置 (、超时和) 转发规则。 如果设备已连接到 SIP 网关，则呼叫将基于设备用户设置的规则重定向到目标地址。 若要使本地呼叫转发工作，管理员必须将 `AllowCallRedirect` 中的 属性设置为 `Set-CsTeamsCallingPolicy` `Enabled`。 


## <a name="requirements-to-use-sip-gateway"></a>使用 SIP 网关的要求

Teams必须已启用 PSTN 呼叫的电话号码，以便使用 SIP 网关。

### <a name="hardware-software-and-licenses"></a>硬件、软件和许可证

如果你有 3PIP 或 SIP 设备，则必须具有： 
- 用于通过 E5 电话系统 (或独立许可证的许可证) 
- PSTN (，即，通过呼叫) 、直接路由或接线员Microsoft Teams电话号码连接
- 适用于任何电话设备的公用区域设备许可证

## <a name="compatible-devices"></a>兼容的设备

|供应商    |模型      |最低固件版本|已批准的固件版本|说明|链接|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |运行企业固件的设备必须转换为多平台固件。 阅读右侧指南，了解如何操作。|[Cisco 固件转换指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11.3.5MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3MPP  |   |   |
|**Poly**  |           |            |           |设备将自动重新启动并安装所选固件。|   |
|          |Trio 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Yealink 支持](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**Audiocodes**|       |            |           |某些 AudioCodes SIP 设备需要预配 URL 设置。 在右侧为受影响的 AudioCodes 设备下载并安装升级文件。 |[AudioCodes 中受影响设备的可下载文件](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405         |2.2.8      |2.2.16.570 |   |   |
|          |405HD       |3.2.1      |2.2.16.570 |   |   |
|          |420HD       |3.2.1      |2.2.16.570 |   |   |
|          |430HD       |3.2.1      |2.2.16.570 |   |   |
|          |440HD       |3.2.1      |2.2.16.570 |   |   |
|          |450HD       |3.2.1      |3.4.6.687  |   |   |
|          |C450HD      |3.2.1      |3.4.6.687  |   |   |
|          |445HD       |3.2.1      |3.4.6.687  |   |   |
|          |RX50        |3.2.1      |3.4.6.687  |   |   |

> [!NOTE]
> 对于某些设备，最低固件版本大于已批准的固件版本。 这是因为 3.X 版本是 Skype for Business 版本。 我们将 SIP 版本更新为 2.X。
