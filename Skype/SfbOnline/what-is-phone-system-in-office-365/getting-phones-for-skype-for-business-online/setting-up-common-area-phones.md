---
title: 设置公用区域电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
description: 了解获取正确的固件，如果需要对其进行更新、 分配许可证和为公用区域电话配置设置的部署步骤。
ms.openlocfilehash: bcf7d8eaf287af0b801168c62e7c22915f735aa2
ms.sourcegitcommit: 6b868f683e1f2354eb42fdf33911e77b7a3a83e2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2018
---
# <a name="set-up-common-area-phones"></a>设置公用区域电话
公用区域电话 （帽） 通常位于类似会议厅区域或可供很多人的另一个区域。 例如，接收区域电话，门电话或会议室电话，大写设置为设备，而不是用户和自动登录到网络。 下面的步骤中，我们将帮助您与调用计划的电话系统，以便您可以为您的组织中部署这些类型的电话的帐户设置。

## <a name="prerequisites-for-common-area-phones"></a>公用区域电话的先决条件

首先需要执行的是以确认您具有以下：

 - 购买公共区域电话的许可证和调用规划。
 - 搜索和购买已批准的电话 (查看列表[此处](deploying-skype-for-business-online-phones.md))。         
 - 更新电话上的固件 （请参阅支持固件[本主题中](getting-phones-for-skype-for-business-online.md)。  您可以通过执行此操作来检查您的电话上的固件：       
    - **Polycom VVX 电话**： 转到**设置** > **状态** > **平台** > **应用程序** > **主**。
    - **Yealink 电话**： 主要电话屏幕上转到**状态**。
    - **AudioCodes 电话**： 转到**菜单** > **设备状态** > 从开始屏幕的**固件版本**。 
    - **Lync Phone Edition (LPE) 电话**： 转到**菜单** > **系统信息**开始屏幕。

    固件更新由 Skype for Business 服务管理。 每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。 

    根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。 您可以通过使用[Set CsIPPhonePolicy](https://docs.microsoft.com/powershell/module/skype/set-csipphonepolicy) cmdlet 并将*EnableDeviceUpdate*参数设置为禁用设备更新设置`false`。

## <a name="setting-up-a-common-area-phone"></a>设置公用区域电话
您将需要执行以下步骤：

### <a name="set-up-your-user-account-for-the-phone"></a>设置您的电话的用户帐户

#### <a name="step-1---buy-the-licenses"></a>步骤 1-购买许可证
1. 在 Office 365 管理中心，转到**帐单** > **购买服务**，并将其添加**其他计划**。

    ![盖 license.png](../../images/cap-license.png)
2. **公用区域电话**上单击 > **立即购买**> 上**立即购买****签出**页上单击。
3. 单击以展开**加载项订阅**，然后单击上若要购买调用规划。 选择**国内调用计划**或**规划国内和国际呼叫**。

> [!Note]
> 您无需电话系统许可证。 它包含使用**公用区域电话**的许可证。

许可证的详细信息，请参阅[业务和 Microsoft 团队授权加载项的 Skype](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)。

#### <a name="step-2---create-a-new-user-account-for-the-phone-and-assign-the-licenses"></a>步骤 2-创建新的用户帐户的电话和分配许可证
1. 在 Office 365 管理中心，转到**用户** > **活动用户** > **添加用户**。
2. 放入**用户名**类似"Main"的第一个名称和"接收"的第二个名称。
3. 如果不是，则自动生成类似"Main 接收"将其放在一个**显示名称**。
4. 放入类似"MainReception"或"Mainlobby"**用户名**。
5. 为公用区域电话，您可能需要手动设置密码或您的公用区域电话的所有有相同的密码。 此外，您可能会认为取消选择**进行此更改其密码它们首次登录时的用户**信息。

    > [!Tip]
    > 等待 ！ 不要单击**添加**！ 嗯，如果未单击**添加**执行这： Office 365 管理中心 >**用户** > **活动用户**，然后查找用户。 然后在用户的属性页上，单击**产品许可证**，然后单击**编辑**。 在**产品许可证**页上，打开**公用区域电话**和选取是**国内调用规划**或国内和**国际呼叫规划**。

6. 如果仍然存在，则将许可证分配给该用户。 在同一页上，单击以展开**产品许可证**。 启用以下：
    - 公用区域电话
    - 然后，您需要选择是**国内调用规划**或国内和**国际呼叫规划**。
     
    分配许可证将显示如下：

    ![TurnOnCapLicense.png](../../images/cap-license-turn-on.png)

    > [!Note]
    > 只要您知道，业务计划 2 的 Skype 随**公用区域电话**的许可证。

有关详细信息，请参阅[添加用户](https://support.office.com/article/1970f7d6-03b5-442f-b385-5880b9c256ec)。

#### <a name="step-3---assign-a-phone-number-to-the-user"></a>步骤 3-向用户分配电话号码
![sfb-徽标-30x30.png](../../images/sfb-logo-30x30.png) **使用业务管理中心的 Skype**
1. 在 Office 365 管理中心 >**管理中心** > **for Business 的 Skype**。
2. 在**业务管理中心的 Skype** >  **语音** > **电话号码**。
3. 从的电话号码列表中选择一个号码，然后单击**分配**。
4. 在**分配**页上，在**语音用户**框中输入用于电话然后选择下拉列表中**选择一个语音用户**的用户的用户的名称。 
5. 您有时将需要添加紧急地址。 一旦您搜索，查找下**选择紧急地址**选取适合您。
6. 单击**保存**和您的用户应如下所示：

    ![盖-用户 number.png](../../images/cap-user-number.png)

   > [!Note]
   > 用户将仅显示它们是否能应用的**电话系统**许可。 如果您刚这，然后有时计有点显示在列表中的用户。

更多的东西，请参阅[为用户获取电话号码](../../what-are-calling-plans-in-office-365/getting-phone-numbers-for-your-users.md)。

如果您想知道，您还可使您的电话号码与另一个运营商和"*端口*"或其转移到 Office 365。 请参阅[传输到 Office 365 的电话号码](../../what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365.md)。

## <a name="step-4---setting-up-your-phone"></a>步骤 4-设置您的电话

**在电话上设置模式**

电话或电话必须必须打开公用区域电话模式。 您可能想要检查的以确保这些操作。 

**下面是一个有关如何设置 Polycom VVX 电话示例**

- 通过执行以下步骤为 Polycom VVX 启用公用区域电话模式：
    1. 在浏览器中，连接到的 web 接口，以便您可以启用帽模式。
    2. 然后转至**设置****业务设置 Skype**选项中，选择**公用区域电话**。
    3. 单击**是**以保存您的设置。

- 既然帽模式已启用，则设置使用电话的显示电话。 显示应显示**CaAP 已启用**。 然后执行以下操作：

    1. 单击**设置**。
    2. 选择**高级**。
    3. 输入密码。
    4. 在**管理设置**中，选择**公共区域电话设置**。
    5. 启用**上限**和**帽管理员模式**。
    6. 单击**保存配置**。

- 确定，现在您的电话已准备以便您可以在主屏幕上登录。

    1. 通过选择**设置**登录 > **功能** > **for Business 的 Skype。**
    2. 选择**用户凭据**，然后选择**web 登录助手 （帽）**生成代码。
    3. 转到[设置门户](http://aka.ms/skypecap)，并以**管理员**身份登录。
    4. 输入显示名称 （例如，Main 接收）。

       > [!Note]
       > 如果选中**为公用区域电话的搜索**，则清除该复选框，并再次进行搜索。

    5. 在配对的代码窗口中，输入电话上显示的代码，并单击**设置**。

        以下此最后一步，电话应自动登录。

### <a name="related-topics"></a>相关主题

- 了解有关在[部署的 Skype Online 业务电话的](deploying-skype-for-business-online-phones.md)可用电话。
- [获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)


