---
title: 用于双重身份验证与 Skype 的业务客户端和 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 摘要： 业务服务器和 Skype for Business 使用与 Skype 的双重身份验证。
ms.openlocfilehash: c1d67682f229a22f4674e5643ccf8d3a99a59f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919456"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>用于双重身份验证与 Skype 的业务客户端和 Skype 业务服务器
 
**摘要：** 使用双重身份验证 Skype 业务服务器和 Skype 的业务。
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

安装 for Business 的 Skype 时，通常是自动配置您的登录信息。 但第一次 Skype 用于业务，您可能需要手动启动客户端。
  
### <a name="to-sign-in-for-the-first-time"></a>首次登录

1. 登录到贵组织的网络。
    
2. 选择**启动** > **所有程序** > **for Business 的 Skype**。
    
    您应该会看到登录屏幕。
    
    - 如果登录地址框已经填充，请确认显示的地址是否正确。
    
    - 如果不正确，或者框为空，输入登录地址 （这通常是您的电子邮件地址相同）。
    
    - 如果显示空密码框，请添加您的密码。
    
3. 选择“登录”****。
    
## <a name="sign-out-of-skype-for-business"></a>注销 Skype for Business

完成 for Business 使用 Skype 时，您可以关闭显示，登录到您的会话，或退出程序，所有从文件菜单。 下表说明了这些选项之间的差异。
  
|**选项**|**执行的结果**|**如何执行**|
|:-----|:-----|:-----|
|关闭  <br/> |关闭您显示，但允许 Skype 业务会话标识与您的用户 ID 继续运行。 因此，您可以继续接收通知并与其他人互动。 <br/> <br/> 您可以通过单击任务栏上或在屏幕底部的通知区域上的业务图标 Skype 获取随时后显示。  <br/> | 在业务主窗口的 Skype，执行以下任一操作： <br/> 1.选择**选项**按钮，然后选择**文件** > **关闭**。  <br/> 2.在窗口的右上角，单击**关闭**按钮 (X)。 <br/> |
|注销  <br/> |结束与您的用户 ID 但 for Business 的 Skype 关联的会话继续在后台运行。 注销时，登录窗口将会出现。  <br/> **提示：** 注销若要从计算机中删除您的登录 ID 和密码的记录时，请选择**删除我登录信息**。 这样做使支持人员可以更轻松地解决登录问题。 还通过使未经授权的用户难以使用您的凭据登录来帮助确保您的登录信息更安全。 <br/> |在业务主窗口的 Skype，选择**选项**按钮，然后选择**文件** > **注销**。  <br/> |
|退出  <br/> |业务会话结束您 Skype，并在计算机上关闭 for Business 的 Skype。 如果您想要重新启动，选择退出之后中,**启动** > **所有程序**> for Business 的 Skype。 <br/> |在业务主窗口的 Skype，选择**选项**按钮，然后选择**文件** > **退出**。  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>使用智能卡登录 Skype for Business

一些组织现在使用多步骤登录过程（称为双重身份验证）来为其用户提高安全性。 如果希望您要使用此选项，您将需要"智能卡"登录到 for Business 的 Skype。 物理或虚拟，可以是智能卡：
  
- **物理**有关信用卡号的大小。 登录时请将其插入到智能卡读卡器中。
    
- **虚拟**不是物理对象，但在您的计算机，实质上用于智能卡构建到您的计算机获取写入到一个特殊芯片电子标识符。 仅可与 Windows 8 的计算机包含 TPM （受信任平台模块） 芯片一起使用。
    
### <a name="enroll-your-smart-card"></a>注册智能卡

您可以使用智能卡登录之前，请在卡片必须"注册"— 即，您的用户凭据必须与卡标识。 不管是物理智能卡还是虚拟智能卡都是如此。 此过程可能已被签出的企业服务器管理员将 Skype 执行。 如果您不确定是否已完成的则检查与他们。
  
> [!NOTE]
> 因为每个虚拟智能卡仅与设备相关联安装它的、 一张卡将需要您使用的每台 Windows 8 计算机的注册。 
  
### <a name="to-manually-enroll-your-smart-card"></a>手动注册智能卡

1. 登录到您将在运行 for Business 的 Skype 的计算机上。
    
2. 使用 Internet Explorer，浏览到您的组织的证书颁发机构 Web 注册页。 
    
    如果没有已将您 Skype 业务服务器管理员寻求此资源的 web 地址。 URL 将如下所示： https://MyCA。[yourcompanyname].com/certsrv。
    
    > [!NOTE]
    > 如果您正在使用 Internet Explorer 10，您可能需要在兼容模式下查看该网站。 
  
3. 当提示您登录到证书页上时，记录使用您的域帐户 （而不是作为您的计算机的管理员）。
    
4. 在网站的“欢迎”页面上，选择“申请证书”****。
    
5. 单击“高级申请”****。
    
6. 选择“创建并向此 CA 提交一个申请”****，然后单击“下一步”****。
    
7. 现在，您将看到调用智能卡注册站页面。 批准申请以安装 ActiveX 控件，然后填写“高级证书申请”表单，如下所示：
    
    a. 从“证书模板”**** 下拉列表中选择“智能卡用户”****。
    
    b. 选择“创建新密钥集”****。
    
    c. 在智能卡标签上查找制造商信息，然后从“CSP”**** 下拉列表中选择该制造商。
    
    d. 选择**CSP**作为请求格式，如果尚未选择它。
    
    e。 从哈希算法下拉列表中，选择**sha1** ，如果尚未选择它。
    
    f。 为您的证书的名称将识别，并单击**提交**。
    
8. 现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”****。
    
9. 出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”****。
    
    > [!NOTE]
    > 如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。 
  
10. 选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。
    
11. 现在在连接到注册站的读卡器中插入空智能卡，然后单击“注册”****。
    
12. 出现提示时，输入您的个人标识号 (PIN)，然后单击“确定”****。
    
    > [!NOTE]
    > 如果您的技术支持人员未向您提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值 12345678。 
  
13. 选择可在首次使用智能卡时强制用户（您）更改 PIN 的选项。
    
14. 单击“确定”**** 以确认显示的证书包含您的信息。
    
15. 看到已颁发证书的通知后，单击“安装此证书”**** 以完成注册过程。
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡凭据登录 Skype for Business

在首次使用您的智能卡之前，建议您单击 Skype 业务登录页上的**删除我登录的信息**。 这样做可清除您的计算机上存储的任何登录凭据，并消除可能的错误源。
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡凭据登录 Skype for Business

1. 启动业务客户端 Skype。
    
2. 在“登录”屏幕上，在“登录地址”**** 框中键入您的登录用户帐户名称，然后单击“登录”****。
    
3. 如果您正在使用虚拟智能卡，请跳过此步骤。
    
    如果您正在使用物理智能卡，请在出现提示时在您的智能卡读卡器中插入智能卡，然后当检测到卡时单击“确定”****。
    
4. 为您的智能卡键入 PIN 号码，然后单击“确定”****。
    
    > [!NOTE]
    > 如果您的支持人员未向您提供智能卡 PIN 号码，请使用默认值 12345678。 
  
## <a name="see-also"></a>另请参阅

[管理 Skype 中的业务服务器的双重身份验证](two-factor-authentication.md)
  
[在 Skype for Business Server 中配置双重身份验证](configure-two-factor.md)
