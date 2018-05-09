---
title: 部署 Skype for Business Online 电话
description: 了解获取正确的固件，如果需要对其进行更新、 分配许可证和为公用区域电话配置设置的部署步骤。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a>公用区域电话
公用区域电话或盖，通常放置在共享区域并不与单个用户关联。 例如，接收区域电话，门电话或会议室电话，大写设置为设备，而不是用户和自动登录到网络。 在下面的步骤中，我们将帮助您为 Microsoft 电话系统与调用计划设置帐户，然后部署帽。

## <a name="prerequisites-for-common-area-phones"></a>公用区域电话的先决条件

确认您具有以下内容：

    - 购买公共区域电话 SKU 
    - 更新的固件 （请参阅支持固件主题中https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)
    - 批准 （查看在列表的电话https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones) 


## <a name="check-the-firmware-for-your-phone"></a>检查您的电话的固件
- **Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.
- **Yealink 电话** ，请转到电话主屏幕上的" **状态** "。
- **AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen. 
- **Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.

固件更新由 Skype for Business 服务管理。 每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。 

根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。 您可以通过使用[Set CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet 并将_EnableDeviceUpdate_参数设置为禁用设备更新设置`false`。

## <a name="create-cap"></a>创建盖
通过配置之前设置物理电话的设置创建帽。

#### <a name="purchase-the-common-area-phone-sku"></a>购买公共区域电话 SKU。 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a>设置公用区域电话<!-- this section could use a screen shot-->

**创建用户** 
1. 分配公用区域电话 SKU
2. 分配调用规划 （如果与调用计划使用 Microsoft 电话系统）。 
3. 分配 Business Admin Center Skype 中可用的电话号码或请求新的电话号码。

**创建新用户**

1. 在设置窗格中，存在一个选项，输入名字和姓氏名称 (例如，接收 Main)。
2. 输入显示名称 （必需），例如，"Main 接收。"
3. 输入用户名 （必需），例如"MainReception"@"域"（公司或企业名称）
4. 输入位置 （国家/地区）。

**分配公用区域电话 SKU**在 Office 365 管理中心，转到**帐单 > 购买服务**并将其添加**公用区域电话**

**分配呼叫帽 SKU 中的计划**

1. 选择调用计划启用电话。 
2. 添加业务 Online 计划 2 中帽 SKU 中启用电话系统和 Skype 的帽。 <!-- odd order for step -->

**分配电话号码**
1. 检查下可用的电话号码**语音 > 电话号码**。
2. 从可用的电话号码的号码列表中选择一个号码。
3. 确认您的选择通过选择**语音**和**电话号码**。

    >[注意]语音用户仅显示是否他们所应用，电话系统许可，尽管甚至应用后，可能需要刷新的时间。 当时重新 Skype 打开业务管理中心帮助。
    
## <a name="configure-phone"></a>配置电话

**准备物理电话** 

所选的电话需要有公用区域电话模式。 

***示例 Polycom VVX 电话***

通过执行以下步骤来启用 Polycom VVX 公共区域电话模式：
1. 在浏览器中，使用 web 界面启用 VVX 帽模式
2. 转至**设置**业务设置选项 Skype 中，选择**公用区域电话**。
3. 单击**保存**以保存您的配置设置。

既然帽电话模式已启用，则设置使用电话的显示电话。

1. 在设置，选择**高级**。
2. 输入密码。
3. 在管理设置中，选择**公共区域电话设置**。
4. 启用 Common Area Phone and 帽管理
5. 选择**保存配置**。

您的电话登录在主屏幕上时将创建以下情况下已准备好进行设置。

1. 通过选择登录**设置 > 功能 > for Business 的 Skype。**
2. 选择用户凭据，然后选择选择**web 登录助手 （帽）**生成代码正在
3. 转到设置门户http://aka.ms/skypecap，并以**管理员身份**登录。
4. 输入显示名称 （例如，Main 接收） 以查看您帽。

>[注意]如果"为公用区域电话的搜索"被选中，清除该复选框，并再次进行搜索。

5. 在配对的代码窗口中，输入电话上显示的代码，并单击**设置**。

预缴税金此最后一步，电话应自动登录。

了解有关在可用电话[](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)。


