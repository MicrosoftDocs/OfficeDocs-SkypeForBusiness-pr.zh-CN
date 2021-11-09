---
title: 管理增强型 9-1-1 和位置服务
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Skype for Business Server支持增强型 9-1-1 (E9-1-1) 客户端Skype for Business呼叫。 为 E9-1-1 配置 Skype for Business Server 时，从 Skype for Business 拨打的紧急呼叫包括紧急响应位置 (ERL) 位置信息服务数据库中的信息。
ms.openlocfilehash: 5eb5fe86449147c38c5719976f202591f13a67fb
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848525"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>管理 Skype for Busines Server 中的增强型 9-1-1 和位置服务

Skype for Business Server支持增强型 9-1-1 (E9-1-1) 客户端Skype for Business呼叫。 为 E9-1-1 配置 Skype for Business Server 时，从 Skype for Business 拨打的紧急呼叫包括紧急响应位置 (ERL) 位置信息服务数据库中的信息。 使用本文中的过程管理位置策略。

> [!Note]
> 有关部署高级企业语音（如 E9-1-1 和位置信息服务）的详细信息，请参阅部署[高级企业语音功能](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)。

在 Skype for Business Server 中，可以使用位置策略应用与增强型 9-1-1 (E9-1-1) 功能以及用户或联系人的位置设置相关的设置。 位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。 例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。

可以从"控制面板"**中的"网络** 配置"Skype for Business Server位置策略。 从Skype for Business Server控制面板中，可以查看、创建、修改或删除位置策略。 可使用以下过程查看位置策略的信息。 


## <a name="view-location-policy-information"></a>查看位置策略信息 

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**

4.  在“位置策略”页上，选择要修改的位置策略。

5.  在“编辑”菜单上，单击“显示详细信息”。
 
    > [!NOTE]  
    > 一次只能查看一个位置策略的信息。

默认情况下，存在一个名为“全局”的策略，无法将其删除或进行重命名。但是，您可以修改“全局”策略。该策略将应用于所有用户和联系人，除非您创建站点策略或每用户策略。每用户策略必须应用于特定用户。


## <a name="create-or-modify-a-location-policy"></a>创建或修改位置策略 

在Skype for Business Server中，您可以覆盖从位置信息服务请求位置更新的客户端之间的默认时间量。 默认值为 4 小时。 使用带 LocationRefreshInterval 参数的 **Set-CsLocationPolicy** cmdlet 可覆盖该默认值。


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>在"控制面板"中Skype for Business Server位置策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**

4.  在“位置策略”页上，单击“新建”，然后选择要创建的策略类型：
    
      - 要创建站点策略，请单击“站点策略”。在“选择站点”中，选择您希望应用此策略的站点，然后单击“确定”。在“新建位置策略”页上，“范围”字段包含值“站点”，“名称”字段包含所选站点的名称。您无法修改上述任意字段。站点策略自动应用于指定站点上的所有用户，并且覆盖这些用户的全局策略。
    
      - 要创建用户策略，请单击“用户策略”。在“新建位置策略”中，“范围”字段包含值“用户”。无法修改该值。在“名称”字段中，键入要赋予此策略的名称。用户策略不会自动应用于任何用户。创建用户策略后，必须手动将此策略授予您希望应用此策略的用户或网络站点。

5.  按如下所示填写剩余字段：
    
      - **启用增强型紧急服务**   选中此复选框可启用与此策略关联的 E9-1-1 用户。 启用紧急服务后，Skype for Business Server客户端将在注册时检索位置信息，并包含进行紧急呼叫时的信息。
    
      - **位置**   指定以下值之一：
        
          - **必需**   客户端在新位置注册时，将提示用户输入位置信息。用户可以消除提示，而不输入任何信息。如果输入了信息，紧急呼叫将首先由紧急服务提供商应答以确认位置，然后再将其路由到公共安全应答点 (PSAP) 接线员（即 911 接线员）。
        
          - **可选**   将不提示用户输入位置。发出呼叫而未包含位置信息时，紧急服务提供商将应答该呼叫并询问位置。
        
          - **免责声明**   此选项与"必需"相同 **，只是** 用户在未输入位置信息的情况下无法消除提示。 用户仍可以完成紧急呼叫，但在未输入信息的情况下无法完成其他呼叫。 此外，还将向用户显示免责声明文本，提醒他们拒绝输入位置信息的后果。 若要设置免责声明文本，必须使用 Skype for Business Server 命令行管理程序运行带 EnhancedEmergencyServiceDisclaimer 参数的 **Set-CsLocationPolicy** cmdlet 或 **New-CsLocationPolicy** cmdlet。 有关详细信息，请参阅[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy)或[New-CsLocationPolicy。](/powershell/module/skype/New-CsLocationPolicy)
          
    
      - **仅对紧急服务** 使用位置Skype for Business可以出于各种原因使用位置信息 (例如，通知队友你的当前位置) 。 选中该复选框可确保位置信息只能用于紧急呼叫。
    
      - **PSTN 用法**   公用电话交换网 (PSTN) 用法，用于确定将使用哪个语音路由来路由使用此配置文件的客户端发出的紧急呼叫。与此用法关联的路由应指向专用于紧急呼叫的 SIP 中继或指向将紧急呼叫路由到最近的公共安全应答点 (PSAP) 的紧急位置标识号 (ELIN) 网关。
    
      - **紧急拨打号码**   要获得紧急服务时所拨打的号码。在美国，该值为 911。该字符串必须由 0 到 9 的数字组成，其长度可以为 1 至 10 位数字。
    
      - **紧急拨号掩码**   在拨打该号码时，希望将其转换为紧急拨打号码的值。例如，如果在此字段输入值 212，而紧急拨打号码字段的值为 911，那么用户拨打 212 时，将呼叫 911。这样就允许拨打备用紧急号码，并且仍可以接通紧急服务（例如，来自使用不同紧急号码的国家/地区的人员可以尝试拨打该国家/地区的号码，而不是拨打其当前所在国家/地区的号码）。您可以通过使用分号分隔值来定义多个紧急拨号掩码。例如，212;414。该字符串的最大长度为 100 个字符。每个字符都必须为 0 到 9 的数字。
      

        > [!IMPORTANT]  
        > 请确保指定的拨号掩码值与呼叫寄存通道范围内的号码不同。 呼叫寄存路由将优先于紧急拨号字符串转换。 要查看现有呼叫寄存通道范围，请单击左侧导航栏中的“语音功能”，然后单击“呼叫寄存”。 

    
      - **通知 URI**   发出紧急呼叫时将通知的一个或多个 SIP 统一资源标识符 (URI)。例如，只要发出紧急呼叫，就会通过即时消息通知公司安全办公室。如果提供了呼叫者的位置，将在通知中包含该位置。可以使用以逗号分隔的列表包含多个 SIP URI。例如，"sip:security@litwareinc.com","sip:kmyer@litwareinc.com"。不支持通讯组列表。该字符串的长度必须为 1 到 256 个字符，并且必须以前缀“sip:”开头。单击“通知 URI”字段之前，将显示一个示例。
    
      - **会议 URI**   将作为与会者加入发出的任何紧急呼叫的第三方的 SIP URI（在这种情况下为电话号码）。例如，发出紧急呼叫时，公司安全办公室可以收到呼叫，并且可以接听或参与该呼叫（具体取决于“会议模式”字段中提供的值）。该字符串的长度必须为 1 到 256 个字符，并且必须以前缀 sip: 开头。在该字段中单击之前，将显示一个示例。
    
      - **会议模式**   如果在“会议 URI”字段中指定了一个值，“会议模式”将决定第三方是能够参与该呼叫还是只能接听呼叫。指定以下选项之一：
        
          - **单向**   第三方只能接听呼叫者与 PSAP 接线员之间的对话。
        
          - **双向**   第三方可以接听并参与呼叫者与 PSAP 接线员之间的呼叫。

6.  单击“提交”。


    > [!IMPORTANT]  
    > 创建用户策略时，起初该策略不会应用于任何用户或网络站点。 要将此策略应用于某个用户，请单击左侧导航栏中的“用户”。 查找您希望应用此策略的用户。 在“编辑”菜单上，单击“显示详细信息”。 在"**编辑服务器用户**"页上，从"位置策略"下拉列表中选择新位置策略，然后单击"提交 **"。**<BR>要将此策略应用于某个网络站点，请单击左侧导航栏中的“网络配置”，然后单击“站点”。查找您希望应用此策略的网络站点。在“编辑”菜单上，单击“显示详细信息”。在“编辑站点”中，从“位置策略”下拉列表中选择新的位置策略，然后单击“提交”。


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>在"控制面板"中Skype for Business Server位置策略

1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**

4.  在“位置策略”页上，选择要修改的位置策略。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  在“编辑位置策略”页上，根据需要修改相应的字段（有关详细信息，请参阅本主题前面介绍的“创建新的位置策略”过程中的步骤 5）。

7.  单击“提交”。

        
## <a name="delete-a-location-policy"></a>删除位置策略


1.  从 RTCUniversalServerAdmins 组 (或具有同等用户权限) 或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任意计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 

3.  在左侧导航栏中，单击"**网络配置"，** 然后单击"位置 **策略"。**

4.  在“位置策略”页上，选择要删除的位置策略。
   
    > [!NOTE]  
    > 可一次性删除多个位置策略。要执行此操作，请按住 Ctrl 键，同时选择多个策略。或者，要选中全部策略，请单击“编辑”菜单中的“全选”。


5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。

    > [!IMPORTANT]  
    > 无法删除“全局”位置策略。如果尝试删除“全局”策略，您将收到一条警告消息，而该策略将重置为其默认值。


## <a name="see-also"></a>另请参阅

[创建或修改网络站点](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](/powershell/module/skype/Get-CsLocationPolicy)