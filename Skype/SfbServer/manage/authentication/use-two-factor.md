---
title: 在客户端和客户端Skype for Business双重Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 摘要：将双重身份验证与 Skype for Business Server 和 Skype for Business。
ms.openlocfilehash: 5b1003c78020e1181112a0ccadaf66a7d1dd4da4
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58587120"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>在客户端和客户端Skype for Business双重Skype for Business Server
 
**摘要：** 将双重身份验证与 Skype for Business Server 和 Skype for Business。
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次Skype for Business登录

安装登录信息时，通常会自动Skype for Business登录信息。 但是第一次Skype for Business时，可能需要手动启动客户端。
  
### <a name="to-sign-in-for-the-first-time"></a>首次登录

1. 登录到组织的网络。
    
2. 选择 **"开始**  >  **所有程序**  >  **Skype for Business"。**
    
    应看到登录屏幕。
    
    - 如果已填写登录地址框，请确认显示的地址正确。
    
    - 如果不正确，或者框为空，请输入你的登录地址 (该地址通常与电子邮件地址) 。
    
    - 如果显示一个空密码框，请添加您的密码。
    
3. 选择 **"登录"。**
    
## <a name="sign-out-of-skype-for-business"></a>注销Skype for Business

当你使用完Skype for Business，你可以关闭屏幕、注销会话或退出程序，所有这些操作都从"文件"菜单中完成。 下表说明了这些选项之间的差异。
  
|**选项**|**功能**|**如何执行**|
|:-----|:-----|:-----|
|关闭  <br/> |关闭屏幕，但允许Skype for Business标识的用户 ID 的会话继续运行。 这样，你可以继续获取通知并与他人交互。 <br/> <br/> 通过单击任务栏或屏幕底部的通知区域上的 Skype for Business 图标，你随时都可以重新显示屏幕。  <br/> | 在Skype for Business窗口上，执行下列操作之一： <br/> 1. 选择"**选项"** 按钮，**然后选择"文件** 关闭  >  **"。**  <br/> 2. 单击 **窗口** () 右上角的 X 窗口的"关闭"按钮。 <br/> |
|注销  <br/> |结束与用户 ID 关联的会话，Skype for Business继续在后台运行。 注销时，将显示登录窗口。  <br/> **提示：** 选择 **"注销时** 删除我的登录信息"，从计算机中删除登录 ID 和密码记录。 这样做可能会让支持人员更轻松地排查登录问题。 它还可以帮助确保你的登录信息更安全，因为未经授权的用户很难使用你的凭据登录。 <br/> |在"Skype for Business"主窗口中，选择"**选项**"按钮，然后选择"**文件**  >  **注销"。**  <br/> |
|Exit  <br/> |结束Skype for Business会话，并Skype for Business关闭计算机。 退出后，如果要重新启动，请选择"开始  >  **所有** 程序"> Skype for Business。 <br/> |在主Skype for Business上，选择"**选项**"按钮，然后选择"文件 **退出**  >  **"。**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>登录以Skype for Business智能卡登录

一些组织现在使用多步骤登录过程（称为双重身份验证）来增强用户的安全性。 如果预计使用此选项，则需要使用"智能卡"登录Skype for Business。 智能卡可以是物理智能卡，也可以虚拟智能卡：
  
- **物理** 关于信用卡大小。 登录时将其插入智能卡读卡器。
    
- **虚拟** 不是物理对象，而是写入到计算机上特殊芯片的电子标识符，这实际上将智能卡生成到计算机中。 仅可用于包含 TPM Windows 8受信任的平台模块或芯片 () 计算机。
    
### <a name="enroll-your-smart-card"></a>注册智能卡

在可以使用智能卡登录之前，该卡必须"已注册"，即用户凭据必须用卡标识。 这是卡片是物理卡还是虚拟卡的情况。 此过程可能已经由您的管理员Skype for Business Server执行。 如果您不确定是否已完成操作，请与他们核实。
  
> [!NOTE]
> 由于每个虚拟智能卡仅与其安装的设备关联，因此需要为使用的每台计算机注册Windows 8卡。 
  
### <a name="to-manually-enroll-your-smart-card"></a>手动注册智能卡

1. 登录到要运行此Skype for Business的计算机。
    
2. 使用 Internet Explorer，浏览到您组织的"证书颁发机构 Web 注册"页。 
    
    如果Skype for Business Server此资源的 Web 地址，请咨询管理员。 URL 将如下所示 https://MyCA ：.[yourcompanyname].com/certsrv。
    
    > [!NOTE]
    > 如果你使用的是 Internet Explorer 10，可能需要在兼容模式下查看此网站。 
  
3. 当系统提示你登录到认证页面时，使用域帐户登录 (而不是以计算机管理员) 。
    
4. 在网站"欢迎"页上，选择 **"请求证书"。**
    
5. 选择 **"高级请求"。**
    
6. 选择 **"创建并提交对此 CA 的请求"，** 然后单击"下一 **步"。**
    
7. 现在，你将看到一个称为智能卡注册站的页面。 批准安装证书ActiveX，然后完成"高级证书请求"表单，如下所示：
    
    a. 从 **"证书模板** " **下拉列表中选择** "智能卡用户"。
    
    b. 选择 **创建新密钥集**。
    
    c. 在智能卡标签上查找制造商信息，然后从 **云** 解决方案提供商下拉列表中选择该制造商。
    
    d. 选择 **"CSP"** 作为"请求格式"（如果尚未选择）。
    
    e. 从 **"哈希** 算法"下拉列表中选择"sha1"（如果尚未选择）。
    
    f. 为证书指定你将识别的名称，然后单击"提交 **"。**
    
8. 现在，将空白智能卡插入连接到注册站的读卡器中，**然后单击注册。**
    
9. 当系统提示时，输入你的个人标识号 (PIN) ，然后单击"确定 **"。**
    
    > [!NOTE]
    > 如果技术支持人员未提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值，该值12345678。 
  
10. 选择强制用户更改 () 第一次使用智能卡时更改 PIN 的选项。
    
11. 现在，将空白智能卡插入连接到注册站的读卡器中，**然后单击注册。**
    
12. 当系统提示时，输入你的个人标识号 (PIN) ，然后单击"确定 **"。**
    
    > [!NOTE]
    > 如果技术支持人员未提供用于注册智能卡的特殊 PIN，请使用默认智能卡 PIN 值，该值12345678。 
  
13. 选择强制用户更改 () 第一次使用智能卡时更改 PIN 的选项。
    
14. 单击 **"** 确定"以确认显示的证书上包含你的信息。
    
15. 在看到证书已颁发通知后，单击" **安装此证书** "以完成注册过程。
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>登录以Skype for Business智能卡凭据登录

在首次使用智能卡之前，建议在登录页面上单击"删除我的登录Skype for Business信息。  这样做可清除存储在您的计算机上的任何登录凭据，并消除可能的错误源。
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡Skype for Business登录

1. 启动 Skype for Business 客户端。
    
2. 在"登录"屏幕上，在"登录地址"框中键入你的登录用户帐户名称，然后单击"**登录"。**
    
3. 如果使用的是虚拟智能卡，请跳过此步骤。
    
    如果使用的是物理智能卡，请将智能卡插入智能卡读卡器，并提示你这样做，然后在检测到智能卡时单击"确定"。 
    
4. 键入智能卡的 PIN 号，然后单击"确定 **"。**
    
    > [!NOTE]
    > 如果你的支持人员未分配智能卡 PIN 号码，请使用默认值，该值12345678。 
  
## <a name="see-also"></a>另请参阅

[在客户端中管理双重Skype for Business Server](two-factor-authentication.md)
  
[在客户端中配置双重Skype for Business Server](configure-two-factor.md)
