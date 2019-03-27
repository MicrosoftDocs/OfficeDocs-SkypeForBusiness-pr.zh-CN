---
title: 管理增强型的 9-1-1 和位置服务
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 业务服务器支持增强型 9-1-1 (E9-1-1) 从 Skype 调用业务客户端。 当配置 Skype 业务服务器 E9-1-1 时，从 for Business 的 Skype 发出紧急呼叫包括紧急响应位置 (ERL) 从位置信息服务数据库的信息。
ms.openlocfilehash: 31e1d529c8fb60145bc1ab4a22a75660d9f3ef63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895151"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>增强型的 9-1-1 和 Skype 中的位置服务管理业务服务器 （英文）

Skype 业务服务器支持增强型 9-1-1 (E9-1-1) 从 Skype 调用业务客户端。 当配置 Skype 业务服务器 E9-1-1 时，从 for Business 的 Skype 发出紧急呼叫包括紧急响应位置 (ERL) 从位置信息服务数据库的信息。 使用本文中的过程管理位置策略。

> [!Note]
> 有关部署高级的企业语音功能，如 E9-1-1 和位置信息服务的详细信息，请参阅[部署高级企业语音功能](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)。

在业务服务器 Skype，您可以使用位置策略将应用设置相关的增强型 9-1-1 (E9-1-1) 功能并为用户或联系人的位置设置。 位置策略确定是否为用户启用的 E9-1-1，如果是这样的行为的紧急呼叫的是。 例如，可以使用位置策略定义哪个号码构成紧急呼叫 (例如，美国的 911)、 是否应自动通知公司安全，并应如何路由呼叫。

您可以为业务 Server Control Panel 中 Skype 配置从**网络配置**组的位置策略。 从业务 Server Control Panel Skype 可以查看、 创建、 修改或删除位置策略。 使用以下过程可以查看有关位置策略的信息。 


## <a name="view-location-policy-information"></a>查看位置策略信息 

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**位置策略**。

4.  在**位置策略**页上，选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。
 
    > [!NOTE]  
    > 您只能查看一次一个位置策略的信息。

一个策略，调用全局存在默认情况下，无法删除或重命名。 但是，您可以修改全局策略。 除非您创建站点策略或每用户策略，此策略将应用于所有用户和联系人。 必须将每用户策略应用于特定用户。


## <a name="create-or-modify-a-location-policy"></a>创建或修改位置策略 

在业务服务器 Skype，您可以重写的默认位置信息服务从一个位置更新的客户端请求之间的时间量。 默认值是 4 个小时。 使用带有 LocationRefreshInterval 参数**集 CsLocationPolicy** cmdlet 可重写默认值。


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>若要为业务 Server Control Panel Skype 创建新的位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**位置策略**。

4.  在**位置策略**页上，单击**新建**，然后选择您想要创建的策略的类型:
    
      - 若要创建站点策略，请单击**站点策略**。 在**选择站点**，选择要向其应用该策略，并单击**确定**的网站。 **新的位置策略**页上，在**范围**字段包含值**网站**和**名称**字段包含所选的站点的名称。 不能修改这些字段之一。 网站策略自动应用于指定网站上的所有用户和重写这些用户的全局策略。
    
      - 若要创建**用户策略**，请单击**用户策略**。 在**新的位置策略**，**范围**字段包含**用户**的值。 不能修改此值。 在**名称**字段中，键入您想要授予此策略的名称。 用户策略不会自动应用于任何用户。 创建用户策略后, 必须手动授予用户或到您要向策略应用的网络站点策略。

5.  如下所示填写剩余字段：
    
      - **启用增强型紧急服务**   选中此复选框，以使 E9-1-1 与此策略关联的用户。 启用紧急服务后，业务 Server 客户端的 Skype 将检索上注册的位置信息，并进行紧急呼叫时包含的信息。
    
      - **位置**   指定下列值之一：
        
          - **所需**   将提示用户输入位置信息时客户端注册新的位置。 用户可以消除提示符处，无需输入任何信息。 如果输入的信息，则紧急呼叫将先回答紧急服务服务提供商验证之前被路由到公共安全应答点 (PSAP) 运算符 （即，911 运算符） 的位置。
        
          - **不需要**   用户将不会提示的位置。 当不具有位置信息进行呼叫时，紧急服务提供商将应答的呼叫，并提出的位置。
        
          - **免责声明**   此选项是**所需**相同，但用户无法关闭提示符处，无需输入位置信息。 用户仍可以完成紧急呼叫，但没有任何其他呼叫可以完成无需输入信息。 此外，将向用户通知他们到拒绝输入位置信息的后果显示免责声明文本。 若要设置的免责声明文本，您必须使用业务 Server 命令行管理程序 Skype 运行带有 EnhancedEmergencyServiceDisclaimer 参数**集 CsLocationPolicy** cmdlet 或**New-cslocationpolicy** cmdlet。 有关详细信息，请参阅[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy)或[New-cslocationpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)。
          
    
      - **仅用于紧急服务的使用位置**Skype for Business 可用于位置信息 （例如，通知您的当前位置的团队成员） 的各种原因。 选中此复选框，以确保位置信息仅适用于用于紧急呼叫。
    
      - **PSTN 用法**   交换网将用于确定的语音路由将用于将来自客户端使用此配置文件的紧急呼叫路由的电话交换网 (PSTN) 用法。 与此用法的路由应指向专用紧急呼叫或到最接近公共安全应答点 (PSAP) 的紧急呼叫路由的紧急位置标识号 (ELIN) 网关的 SIP 中继。
    
      - **紧急拨号号码**   要获得紧急服务时所拨打的号码。 在美国此值是 911。 该字符串必须由 0 到 9 的数字，可以是介于 1 至 10 位数字的长度。
    
      - **紧急拨号掩码**   您想要将转换紧急拨号号码值的值，当它时所拨打的号码。 例如，如果在此字段中输入的值为 212 具有紧急拨号号码字段的值为 911，如果用户拨打 212 将对 911 进行呼叫。 这样就允许拨打备用紧急号码，并且仍可接通紧急服务（例如，来自使用不同紧急号码的国家/地区的人员可以尝试拨打自己国家/地区的号码，而不是拨打其当前所在国家/地区的号码）。 可以通过使用分号分隔值来定义多个紧急拨号掩码。 例如，212;414。 字符串的最大长度为 100 个字符。 每个字符都必须为 0 到 9 的数字。
      

        > [!IMPORTANT]  
        > 确保指定的拨号掩码值不是为号码的呼叫寄存通道范围相同。 呼叫寄存路由将优先于紧急拨号字符串转换。 若要查看现有呼叫寄存轨道范围，单击左侧的导航栏中的**语音功能**，然后单击**呼叫寄存**。 

    
      - **通知 URI**   一个或多个 SIP 统一资源标识符 (Uri) 进行紧急呼叫时收到通知。 例如，公司安全 office 无法通过即时消息通知进行紧急呼叫时。 如果呼叫者的位置是可将通知中包括该位置。 多个 SIP Uri 可作为以逗号分隔列表。 例如，"sip:security@litwareinc.com"、"sip:kmyer@litwareinc.com"。 支持通讯组列表。 字符串必须介于 1 到 256 个字符的长度，必须以前缀开头"sip:"。 在通知 URI 字段中单击之前会显示一个示例。
    
      - **会议 URI**   SIP URI，在此示例中的电话号码，将在会议中所做的任何紧急呼叫到第三方。 例如，公司安全 office 无法进行紧急呼叫时接收呼叫和收听或参与 （具体取决于在**会议模式**字段中提供的值） 该呼叫。 字符串必须介于 1 到 256 个字符的长度，必须以前缀 sip 开头:。 在此字段中单击之前，将显示一个示例。
    
      - **会议模式**   **会议模式**如果在**会议 URI**字段中指定一个值，确定是第三方可以参与呼叫，还是只能接听。 指定以下选项之一：
        
          - **单向**   第三方只能接听呼叫者与 PSAP 接线员之间的对话。
        
          - **双向**   第三方可以接听并参与呼叫者与 PSAP 接线员之间的呼叫。

6.  单击“**提交**”。


    > [!IMPORTANT]  
    > 当您创建的用户策略时，最初该策略不适用于向任何用户或网络站点。 要将策略应用于用户，请单击左侧的导航栏中的**用户**。 查找您要向其应用策略的用户。 在“编辑”**** 菜单上，单击“显示详细信息”****。 在**编辑 Server 用户**页上，从**位置策略**下拉列表中选择新的位置策略，然后单击**提交**。<BR>要将策略应用于网络站点中，单击左侧的导航栏中的**网络配置**，然后单击**网站**。 找到要向其应用策略的网络站点。 在“编辑”**** 菜单上，单击“显示详细信息”****。 在**编辑站点**，从**位置策略**下拉列表中选择新的位置策略，然后单击**提交**。


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>修改业务 Server Control Panel Skype 中的某个位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**位置策略**。

4.  在**位置策略**页上，选择要修改的位置策略。

5.  在“编辑”**** 菜单上，单击“显示详细信息”****。

6.  在**编辑位置策略**页上，根据需要修改字段 （有关详细信息，本主题前面的"创建新的位置策略"中，请参阅第 5 步过程）。

7.  单击“**提交**”。

        
## <a name="delete-a-location-policy"></a>删除位置策略


1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 

3.  在左侧的导航栏中，单击**网络配置**，然后单击**位置策略**。

4.  在**位置策略**页上，选择要删除的位置策略。
   
    > [!NOTE]  
    > 您可以一次删除多个位置策略。 若要执行此操作，请按住 CTRL 并按住 CTRL 键选择多个策略。 或者，若要选择所有策略，请**都选择全部**上单击**编辑**菜单。


5.  在**编辑**菜单上，单击**删除**。

6.  单击“**确定**”。

    > [!IMPORTANT]  
    > 无法删除全局位置策略。 如果尝试删除全局策略，您将收到一条警告消息，该策略将重置为其默认值。


## <a name="see-also"></a>另请参阅

[创建或修改网络站点](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[新 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[设置 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[删除 CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
