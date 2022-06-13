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
ms.openlocfilehash: a715e913966040c5406901403b90d5a6a421e2e4
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045871"
---
# <a name="plan-for-sip-gateway"></a>规划 SIP 网关

SIP 网关允许组织将任何兼容的 SIP 设备与Microsoft Teams配合使用，以保留对 SIP 设备的投资。 现在，可以使用公司凭据登录Teams，并使用兼容的 SIP 设备进行和接听呼叫。 兼容设备可以Skype for Business具有标准 SIP 固件的 IP 电话、具有多平台 SIP 固件的 Cisco IP 电话，或来自 Poly、Yealink 和 AudioCode 等供应商的 SIP 设备。 若要了解如何为 SIP 网关配置 SIP 设备，请参阅 [配置 SIP 网关](sip-gateway-configure.md)。

## <a name="benefits-of-sip-gateway"></a>SIP 网关的优势

SIP 网关将兼容的 SIP 设备连接到Teams，以帮助用户无缝迁移到Teams电话。 使用 SIP 网关，用户可以执行以下所有操作：

- **进行呼叫：** SIP 设备用户可以调用公共交换电话网络 (PSTN) 、其他 SIP 设备，以及Teams和Skype for Business用户。 SIP 设备用户只能呼叫具有电话号码的用户。
- **接收呼叫：** SIP 设备用户可以从 PSTN、具有 SIP 设备的Teams或Skype for Business用户以及Teams和Skype for Business客户端应用程序接听呼叫。 SIP 设备充当Teams终结点。 入站调用也将分叉到用户的 SIP 设备。
- **多个同时调用：** 呼叫中的 SIP 设备用户可以暂停呼叫以发出或接收其他呼叫。 SIP 设备用户还可以召开两次电话会议。
- **请勿打扰：** SIP 设备用户可以在设备上设置不打扰，这样设备就不会为传入呼叫响铃。 这不会影响用户对所有其他Teams终结点的状态。
- **保留/恢复和静音/取消静音：** SIP 设备用户可以使用设备上这些操作的功能来保留、恢复或静音和取消调用。
- **语音 信箱：** SIP 设备用户可以侦听呼叫者留给他们的电子存储语音消息。
- **消息等待指示器：** SIP 设备用户可以在收到新的语音邮件时接收通知，并发出警报。
- **登录和注销：** SIP 设备用户可以在设备上登录和注销Teams。
- **双色调多频：** SIP 设备用户可以按数字键在交互式语音响应呼叫期间提供输入。
- **Teams会议：** SIP 设备用户可以通过拨打会议访问号码加入Teams会议。 会议参与者可以通过拨出用户的电话号码将 SIP 设备用户添加到会议，或者只需单击“加入请求”添加参与者，也会提醒用户的 SIP 设备。 另一个组织的来宾用户可由参与者添加到Teams会议，该参与者会拨通来宾用户的号码以包括该来宾。
- **呼叫传输：** SIP 设备用户可以传输呼叫。 SIP 网关支持盲目传输和协商传输。
- **本地呼叫转接：** SIP 设备用户可以始终 (超时和设备忙) 设置转发规则。 如果设备已连接到 SIP 网关，则会根据设备用户设置的规则将调用重定向到目标地址。 若要使本地呼叫转接正常工作，管理员必须将属性`Set-CsTeamsCallingPolicy`设置`AllowCallRedirect`为 `Enabled`。

## <a name="requirements-to-use-sip-gateway"></a>使用 SIP 网关的要求

Teams用户必须具有启用了 PSTN 呼叫的电话号码才能使用 SIP 网关。

### <a name="hardware-software-and-licenses"></a>硬件、软件和许可证

如果有 3PIP 或 SIP 设备，则必须具有：

- 通过 E5 或独立许可证) 电话系统 (的许可证
- PSTN 启用 (，即通过Microsoft Teams呼叫计划、直接路由或运营商连接) 电话号码
- 任何公共区域设备的通用区域电话许可证

## <a name="compatible-devices"></a>兼容的设备

|供应商    |模型      |最小固件版本|已批准的固件版本|说明|链接|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |运行企业固件的设备必须转换为多平台固件。 阅读右侧的指南以了解如何操作。|[Cisco 固件转换指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
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
|**聚**  |           |            |           |设备将自动重启并安装所选固件。|   |
|          |三重奏 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |三重奏 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
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
|**Audiocodes**|       |            |           |某些 AudioCodes SIP 设备需要预配 URL 设置。 在右侧下载并安装受影响的 AudioCodes 设备的升级文件。 |[AudioCodes 中受影响设备的可下载文件](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
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
> 对于某些设备，最低固件版本大于批准的固件版本。 这是因为 3.X 版本是Skype for Business版本。 我们更新 SIP 版本，该版本为 2.X。
