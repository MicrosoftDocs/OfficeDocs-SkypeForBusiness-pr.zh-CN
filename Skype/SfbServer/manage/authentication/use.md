---
title: 对 Skype for Business 客户端 和 Skype for Business Server 2015 使用双重身份验证
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 摘要： 使用双因素身份验证 Skype 业务服务器 2015年和 Skype 的业务。
ms.openlocfilehash: 6bb2133533b640cd573730ca608f5845164ea282
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server-2015"></a>对 Skype for Business 客户端 和 Skype for Business Server 2015 使用双重身份验证
 
**摘要：**使用 Skype 业务服务器 2015年和 Skype 业务两因素身份验证。
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

安装 Skype 业务时，您的登录信息是通常自动配置。 但第一次使用 Skype 业务，您可能需要手动启动客户端。
  
### <a name="to-sign-in-for-the-first-time"></a>首次登录

1. 登录到您的组织的网络。
    
2. 选择**开始** > **所有程序** > **业务的 Skype**。
    
    您应该会看到登录屏幕。
    
    - 如果登录地址框已经填充，请确认显示的地址是否正确。
    
    - 如果不正确，或者如果此框为空，请输入登录地址 （这通常是您的电子邮件地址相同）。
    
    - 如果显示空密码框，请添加您的密码。
    
3. 选择“登录”****。
    
## <a name="sign-out-of-skype-for-business"></a>注销 Skype for Business

使用 Skype 业务操作完成后，您可以关闭显示器，登录到您的会话，或退出程序，请从文件菜单。 下表说明了这些选项之间的差异。
  
|**选项**|**它的作用**|**如何执行它**|
|:-----|:-----|:-----|
|关闭  <br/> |关闭显示器，但让 Skype 业务会话标识与用户 ID 继续运行。 因此，您可以继续接收通知并与其他人互动。 <br/> <br/> 您可以随时重新显示通过单击 Skype 业务通知区域位于屏幕底部任务栏上的图标。  <br/> | 在 Skype 业务主窗口中，执行下列操作： <br/> 1.选择**选项**按钮，然后选择**文件** > **关闭**。  <br/> 2.单击窗口右上角的**关闭**按钮 (X)。 <br/> |
|注销  <br/> |结束与您的用户 ID，但 Skype 业务关联的会话将会继续在后台运行。 注销时，登录窗口将会出现。  <br/> **提示：**退出来从计算机中删除您的登录 ID 和密码的记录后，请选择**删除我的登录信息**。 这样做使支持人员可以更轻松地解决登录问题。 还通过使未经授权的用户难以使用您的凭据登录来帮助确保您的登录信息更安全。 <br/> |在 Skype 业务主窗口中，选择**选项**按钮，然后选择**文件** > **签出**。  <br/> |
|退出  <br/> |业务会话结束您 Skype 和关闭您的计算机上的 Skype 业务。 退出后，如果您想要重新启动，请选择**开始** > **所有程序**> Skype 业务。 <br/> |在 Skype 业务主窗口中，选择**选项**按钮，然后选择**文件** > **退出**。  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>使用智能卡登录 Skype for Business

一些组织现在使用多步骤登录过程（称为双重身份验证）来为其用户提高安全性。 如果希望您要使用此选项，您将需要"智能卡"登录 Skype 业务。 智能卡可以是物理或虚拟：
  
- **物理**关于信用卡的大小。 登录时请将其插入到智能卡读卡器中。
    
- **虚拟**不是一个物理对象，但电子标识符获取写入您实质上可用于智能卡构建到您的计算机的计算机上的特殊芯片。 只可使用与 Windows 8 计算机包含 TPM （可信平台模块） 芯片。
    
### <a name="enroll-your-smart-card"></a>注册智能卡

您可以使用智能卡登录之前，卡必须"登记"— — 您的用户凭据即具有被识别的卡。 不管是物理智能卡还是虚拟智能卡都是如此。 此过程可能已被执行的业务服务器 2015年管理员为您 Skype。 如果您不确定是否这样做了，请检查它们。
  
> [!NOTE]
> 因为每个虚拟智能卡是只与该设备上安装了，一个单独的卡将需要为每个您所使用的 Windows 8 计算机注册。 
  
### <a name="to-manually-enroll-your-smart-card"></a>手动注册智能卡

1. 登录到您的计算机将是 Skype 的业务上。
    
2. 使用 Internet Explorer，浏览到您的组织的证书颁发机构 Web 注册页。 
    
    如果尚不具备，询问业务服务器管理员为您 Skype 此资源的 web 地址。 该 URL 将如下所示： https://MyCA。[yourcompanyname].com/certsrv。
    
    > [!NOTE]
    > 如果您正在使用 Internet Explorer 10，您可能需要在兼容模式下查看该网站。 
  
3. 当出现提示时登录到证书页上时，日志上使用您的域帐户 （而不是作为计算机的管理员）。
    
4. 在网站的“欢迎”页面上，选择“申请证书”****。
    
5. 单击“高级申请”****。
    
6. 选择“创建并向此 CA 提交一个申请”****，然后单击“下一步”****。
    
7. 现在您将看到名为智能卡注册站的页面。 批准申请以安装 ActiveX 控件，然后填写“高级证书申请”表单，如下所示：
    
    a. 从“证书模板”****下拉列表中选择“智能卡用户”****。
    
    b. 选择“创建新密钥集”****。
    
    c. 在智能卡标签上查找制造商信息，然后从“CSP”****下拉列表中选择该制造商。
    
    d. 如果没有选中它，作为请求格式，选择**的 CSP** 。
    
    电子。 如果尚未选中，请选择**sha1**哈希算法下拉列表中，从。
    
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
    
14. 单击“确定”****以确认显示的证书包含您的信息。
    
15. 看到已颁发证书的通知后，单击“安装此证书”****以完成注册过程。
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡凭据登录 Skype for Business

第一次使用您的智能卡之前，建议您单击 Skype 业务登录页上的**删除我的登录信息**。 这样做可清除您的计算机上存储的任何登录凭据，并消除可能的错误源。
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡凭据登录 Skype for Business

1. 启动业务客户端的 Skype。
    
2. 在“登录”屏幕上，在“登录地址”****框中键入您的登录用户帐户名称，然后单击“登录”****。
    
3. 如果您正在使用虚拟智能卡，请跳过此步骤。
    
    如果您正在使用物理智能卡，请在出现提示时在您的智能卡读卡器中插入智能卡，然后当检测到卡时单击“确定”****。
    
4. 为您的智能卡键入 PIN 号码，然后单击“确定”****。
    
    > [!NOTE]
    > 如果您的支持人员未向您提供智能卡 PIN 号码，请使用默认值 12345678。 
  
## <a name="see-also"></a>另请参阅

#### 

[管理在 Skype 的业务服务器 2015年的双因素身份验证](two-factor-authentication.md)
  
[在 Skype 为业务服务器 2015年配置两因素身份验证](configure.md)

