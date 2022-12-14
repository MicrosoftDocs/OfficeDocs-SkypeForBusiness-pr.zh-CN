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
- highpri
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
ms.openlocfilehash: 5d2bd923835da3c9ffcbf32e0675f1f0e4e63bd3
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392212"
---
# <a name="plan-for-sip-gateway"></a>规划 SIP 网关

SIP 网关允许组织将任何兼容的 SIP 设备与 Microsoft Teams 配合使用，以保留对 SIP 设备的投资。 现在，可以使用公司凭据登录到 Teams，并使用兼容的 SIP 设备拨打和接听呼叫。 兼容设备可以是Skype for Business具有标准 SIP 固件的 IP 电话、具有多平台 SIP 固件的 Cisco IP 电话，或来自 Poly、Yealink 和 AudioCodes 等供应商的 SIP 设备。 若要了解如何为 SIP 网关配置 SIP 设备，请参阅 [配置 SIP 网关](sip-gateway-configure.md)。

## <a name="benefits-of-sip-gateway"></a>SIP 网关的优势

SIP 网关将兼容的 SIP 设备连接到 Teams，以帮助用户无缝迁移到 Teams 电话。 使用 SIP 网关，用户可以执行以下所有操作：

- **进行调用：** SIP 设备用户可以拨打公用电话交换网 (PSTN) 、其他 SIP 设备以及 Teams 和 Skype for Business 用户。 SIP 设备用户只能呼叫具有电话号码的用户。
- **接听呼叫：** SIP 设备用户可以从 PSTN、Teams 或具有 SIP 设备的Skype for Business用户以及 Teams 和Skype for Business客户端应用程序接收呼叫。 SIP 设备充当 Teams 终结点。 入站呼叫也将分叉到用户的 SIP 设备。
- **多个同时调用：** 呼叫中的 SIP 设备用户可以将呼叫置于保留状态以拨打或接听其他呼叫。 SIP 设备用户还可以接听两个呼叫。
- **请勿打扰：** SIP 设备用户可以在设备上设置“请勿打扰”，以便设备不会针对传入呼叫响铃。 这不会影响用户在所有其他 Teams 终结点上的状态。
- **保持/恢复和静音/取消静音：** SIP 设备用户可以使用设备上这些操作的功能来保持和恢复呼叫，或者将呼叫静音和取消静音。
- **语音 信箱：** SIP 设备用户可以收听呼叫者留给他们的电子存储的语音消息。
- **消息等待指示器：** SIP 设备用户可以在收到新的语音邮件消息时发出警报的通知。
- **登录和注销：** SIP 设备用户可以在设备上登录和注销 Teams。
- **双音多频：** SIP 设备用户可以按数字键在交互式语音响应呼叫期间提供输入。
- **Teams 会议：** SIP 设备用户可以通过拨打会议访问号码加入 Teams 会议。 会议参与者可以通过拨出用户的电话号码将 SIP 设备用户添加到会议，或者只需单击“请求加入”来添加参与者，也会提醒用户的 SIP 设备。 另一个组织的来宾用户可由拨出来宾用户的号码以包含该来宾的参与者添加到 Teams 会议。
- **呼叫转接：** SIP 设备用户可以转移呼叫。 SIP 网关支持盲目传输和咨询式传输。
- **本地呼叫转接：** SIP 设备用户可以始终 (设备超时和繁忙) 设置转发规则。 如果设备已连接到 SIP 网关，则呼叫将根据设备用户设置的规则重定向到目标地址。 若要使本地呼叫转接正常工作，管理员必须将 中的 属性设置为 `AllowCallRedirect` `Enabled`。`Set-CsTeamsCallingPolicy`
- **卸载过时的设备：** SIP 网关支持自动卸载为租户预配的过时设备。 如果配对 (已登录) 设备在 30 天内未连接，则会在 14 天后注销 (未配对) 设备。 出厂重置后，可以重新载入已卸载的设备。

## <a name="requirements-to-use-sip-gateway"></a>使用 SIP 网关的要求

Teams 用户必须具有启用了 PSTN 呼叫的电话号码才能使用 SIP 网关。

> [!NOTE]
> SIP 网关不适用于政府环境， (GCC、GCC High 和 DoD) 。

### <a name="hardware-software-and-licenses"></a>硬件、软件和许可证

如果你有 3PIP 或 SIP 设备，则必须：

- 通过 E5 或独立许可证Microsoft Teams、Skype for Business Online 计划 2 和 Microsoft 365 电话系统 (的许可证) 
- PSTN 启用 (，即通过Microsoft Teams 通话套餐、直接路由或运营商连接) 电话号码
- 适用于任何公共区域 **设备的Microsoft Teams 共享** 设备许可证

## <a name="compatible-devices"></a>兼容的设备

|供应商    |模型      |最低固件版本|批准的固件版本|说明|链接|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |运行企业固件的设备必须转换为多平台固件。 阅读右侧的指南以了解如何操作。|[Cisco 固件转换指南](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832<sup>1</sup>       |11.3.5MPP   |11-3-7MPP  |   |   |
|          |6821<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7811<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7821<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7841<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7861<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8811<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8841<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8845<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8851<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8861<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8865<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|**聚**  |           |            |           |设备将自动重新启动并安装所选固件。|   |
|          |三重 8500  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |VVX150<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX301<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX311<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX401<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX411<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX501<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX601<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |Rove B2    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove B4    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |罗夫 30    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |罗夫 40    |8.0.3.0010  |8.0.3.0010 |   |   |
|**Yealink**|          |            |           |   |[Yealink 支持](https://support.yealink.com/)|
|          |T21P       |83          |34.72.0.75 |   |   |
|          |T21P_E2    |83          |52.84.0.125|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G<sup>1</sup>      |83          |69.86.0.15 |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30<sup>1</sup>       |83          |124.86.0.40|   |   |
|          |T30P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T33G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T41S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T43U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|          |T46S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T46U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T48U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T53<sup>1</sup>       |83          |96.86.5.1  |   |   |
|          |T53W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T54W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T57W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |W56H                  |            |61.85.0.56 |   |   |
|          |W73H                  |            |116.85.0.38|   |   |
|          |W59R                  |            |115.85.0.56|   |   |
|          |W70B NOAM             |            |146.85.5.4 |   |   |
|          |W70B EMEA             |            |146.85.5.2 |   |   |
|          |W70B APAC             |            |146.85.5.3 |   |   |
|          |W80 NOAM              |            |130.85.5.5 |   |   |
|          |W80 EMEA              |            |130.85.5.6 |   |   |
|          |W80 APAC              |            |130.85.5.4 |   |   |
|          |W90 NOAM              |            |130.85.5.5 |   |   |
|          |W90 EMEA              |            |130.85.5.6 |   |   |
|          |W90 APAC              |            |130.85.5.4 |   |   |
|**Audiocodes**|       |            |           |某些 AudioCodes SIP 设备需要预配 URL 设置。 在右侧下载并安装受影响的 AudioCodes 设备的升级文件。 |[AudioCodes 上受影响设备的可下载文件](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405<sup>1</sup>        |2.2.8      |2.2.16.589 |   |   |
|          |405HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |405HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |420HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |420HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |430HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |430HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |440HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704 |   |   |
|          |445HDG<sup>1</sup>     |3.2.1      |3.4.6.704 |   |   |
|          |450HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |C450HD<sup>1</sup>     |3.2.1      |3.4.6.704  |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |RX50<sup>1</sup>       |3.2.1      |3.4.6.704  |   |   |
|**Specspecink**|       |           |           |   |[Specspecink 支持](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |手机 |   |
|          |7212        |PCS22B     |PCS22B     |手机 |   |
|          |7502        |PCS22B     |PCS22B     |手机 |   |
|          |7522        |PCS22B     |PCS22B     |手机 |   |
|          |7532        |PCS22B     |PCS22B     |手机 |   |
|          |7622        |PCS22B     |PCS22B     |手机 |   |
|          |7642        |PCS22B     |PCS22B     |手机 |   |
|          |7722        |PCS22B     |PCS22B     |手机 |   |
|          |7742        |PCS22B     |PCS22B     |手机 |   |
|          |IP-DECT Server 200 |PCS22Ab |PCS22Ab |IP-DECT 服务器 |   |
|          |IP-DECT Server 400 |PCS22Ab |PCS22Ab |IP-DECT 服务器 |   |
|          |IP-DECT Server 6500 |PCS22Ab |PCS22Ab |IP-DECT 服务器 |   |
|          |虚拟 IP-DECT 服务器 One |PCS22Ab |PCS22Ab |IP-DECT 服务器 |   |
|          |IP-DECT 基站 |PCS22Ab |PCS22Ab |IP-DECT 服务器 |   |
|**Ascom**|       |           |           |   |[Ascom 支持](https://www.ascom.com/products-and-services/services/support-and-maintenance/)|
|          |Ascom d43        |2.11.4     |2.11.4     |手机 |   |
|          |Ascom d63        |2.11.4     |2.11.4     |手机 |   |
|          |Ascom d81        |4.13.1     |4.13.1     |手机 |   |
|          |Ascom d83        |4.13.1     |4.13.1     |手机 |   |
|          |Ascom Myco 3 DECT        |3.4.1     |3.4.1     |手机 |   |
|          |IP-DECT 接入点 IPBSx        |11.8.8     |11.8.8     |IP-DECT 接入点 |   |
|          |IP-DECT 网关 IPBL     |11.8.8     |11.8.8     |IP-DECT 网关 |   |
|          |TDM 基站        |R3N     |R3N     |IP-DECT 基站 |   |
|          |IP-DECT 虚拟设备 IPVM        |11.8.8     |11.8.8     |IP-DECT 服务器 |   |

<sup>1</sup> 设备支持使用 SIP 网关 (E911) 进行动态紧急呼叫。

> [!NOTE]
> 客户可以使用 AudioCodes OVOC 和 Poly Lens 分别管理其 AudioCodes 400 系列和 Poly VVX/Trio 设备的设备端配置。

> [!NOTE]
> 从Specspecink IP-DECT 服务器通过无线接收固件更新。

> [!NOTE]
> Ascom 手机通过无线接收来自 Ascom IP-DECT 服务器的固件更新。

> [!NOTE]
> 对于 Yealink DECT 基站，请使用上面列出的相应区域特定固件版本，以获得最佳通话体验。

> [!NOTE]
> 对于支持查询，将 IP-DECT 系统与 Teams SIP 网关配合使用的客户应联系其 DECT 制造商或其实现渠道合作伙伴。

> [!NOTE]
> 对于某些设备，最低固件版本大于批准的固件版本。 这是因为 3.X 版本是Skype for Business版本。 我们将更新 SIP 版本 2.X。
