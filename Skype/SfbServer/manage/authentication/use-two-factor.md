---
title: 将双重身份验证与 Skype for Business 客户端和 Skype for Business Server 一同使用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: 摘要：对 Skype for Business Server 和 Skype for Business 使用双重身份验证。
ms.openlocfilehash: 72ec3570d632eecefd28ebfd0aa50eb70c54ff99
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806533"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>将双重身份验证与 Skype for Business 客户端和 Skype for Business Server 一同使用
 
**摘要：** 将双重身份验证与 Skype for Business Server 和 Skype for Business 一同使用。
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

安装 Skype for Business 时，通常会自动配置登录信息。 但是，第一次使用 Skype for Business 时，可能需要手动启动客户端。
  
### <a name="to-sign-in-for-the-first-time"></a>首次登录

1. 登录到组织的网络。
    
2. 选择 **"**  >  **启动 Skype** for  >  **Business 的所有程序"。**
    
    你应该会看到登录屏幕。
    
    - 如果已填写登录地址框，请确认显示的地址正确。
    
    - 如果不正确，或者框为空，请输入登录地址 (该地址通常与电子邮件地址相同) 。
    
    - 如果显示空密码框，请添加密码。
    
3. 选择 **"登录"。**
    
## <a name="sign-out-of-skype-for-business"></a>注销 Skype for Business

使用完 Skype for Business 后，你可以关闭屏幕、注销会话或退出程序，所有这些都来自"文件"菜单。 下表说明了这些选项之间的差异。
  
|**选项**|**功能**|**如何执行**|
|:-----|:-----|:-----|
|关闭  <br/> |关闭你的屏幕，但允许使用你的用户 ID 标识的 Skype for Business 会话继续运行。 这样，你可以继续获取通知并与他人交互。 <br/> <br/> 你随时都可以通过单击任务栏上的 Skype for Business 图标或屏幕底部的通知区域来恢复显示。  <br/> | 在 Skype for Business 主窗口中，执行下列操作之一： <br/> 1. 选择 **"选项"** 按钮，然后选择"**文件**  >  **关闭"。**  <br/> 2. 单击窗口右上角 (X) 的"关闭"按钮。 <br/> |
|注销  <br/> |结束与用户 ID 关联的会话，但 Skype for Business 继续在后台运行。 注销时，将显示登录窗口。  <br/> **提示：****Select Delete my sign-in information** when you sign out to remove the record of your logon ID and password from the computer. 这样做可能会让支持人员更轻松地排查登录问题。 它还可以帮助确保登录信息更加安全，因为未经授权的用户很难使用凭据登录。 <br/> |在 Skype for Business 主窗口中，选择 **"选项"** 按钮，然后选择"**文件**  >  **注销"。**  <br/> |
|Exit  <br/> |结束你的 Skype for Business 会话并关闭你的计算机上 Skype for Business。 退出后，如果要重新启动，**请选择"启动** Skype for Business >  >  所有程序"。 <br/> |在 Skype for Business 主窗口中，选择"选项 **"按钮，** 然后选择"**文件**  >  **退出"。**  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>使用智能卡登录 Skype for Business

一些组织现在使用多步骤登录过程（称为双重身份验证）来增强用户的安全性。 如果你希望使用此选项，则需要"智能卡"登录 Skype for Business。 智能卡可以是物理智能卡，也可以虚拟智能卡：
  
- **物理** 关于信用卡的大小。 登录时将其插入智能卡读卡器。
    
- **虚拟** 不是物理对象，而是写入计算机上特殊芯片的电子标识符，这本质上将智能卡生成到计算机中。 仅适用于包含 TPM 和受信任的平台模块或芯片 (Windows 8) 。
    
### <a name="enroll-your-smart-card"></a>注册智能卡

在可以使用智能卡登录之前，该卡必须"已注册"，即用户凭据必须用卡标识。 这是卡片是物理卡还是虚拟卡的情况。 此过程可能已经由 Skype for Business Server 管理员执行。 如果不确定是否已完成，请与他们核实。
  
> [!NOTE]
> 由于每个虚拟智能卡仅与其安装的设备相关联，因此需要为使用的每个 Windows 8 计算机注册单独的卡。 
  
### <a name="to-manually-enroll-your-smart-card"></a>手动注册智能卡

1. 登录到将运行 Skype for Business 的计算机。
    
2. 使用Internet Explorer，浏览到组织的"证书颁发机构 Web 注册"页。 
    
    如果尚未提供此资源的 Web 地址，请询问 Skype for Business Server 管理员。 URL 将如下所示 https://MyCA ：.[yourcompanyname].com/certsrv。
    
    > [!NOTE]
    > 如果你使用的是Internet Explorer 10，可能需要在兼容模式下查看此网站。 
  
3. 当系统提示你登录认证页面时，使用域帐户登录 (而不是以计算机管理员) 。
    
4. 在网站欢迎页面上，选择 **"请求证书"。**
    
5. 选择 **"高级请求"。**
    
6. 选择 **"创建"，然后向此 CA** 提交请求，然后单击"下 **一步"。**
    
7. 现在，你将看到一个称为"智能卡注册站"的页面。 批准安装证书ActiveX，然后完成"高级证书申请"表单，如下所示：
    
    a. 从 **"证书模板** "下拉列表 **中选择** 智能卡用户。
    
    b. 选择 **"新建密钥集"。**
    
    c. 在智能卡标签上查找制造商信息，然后从 **云** 解决方案提供商下拉列表中选择该制造商。
    
    d. 选择 **CSP** 作为请求格式（如果尚未选择）。
    
    e. 从"哈希算法"下拉列表中选择 **sha1（** 如果尚未选择）。
    
    f. 为证书指定你将识别的名称，然后单击"提交 **"。**
    
8. 现在，将空白智能卡插入连接到注册站的读卡器中，然后单击"注册 **"。**
    
9. 当系统提示时，在 PIN (输入) ，然后单击"确定 **"。**
    
    > [!NOTE]
    > 如果技术支持人员未提供用于注册智能卡的特殊 PIN，请使用默认的智能卡 PIN 值，即 12345678。 
  
10. 选择强制用户更改 () 第一次使用智能卡时更改 PIN。
    
11. 现在，将空白智能卡插入连接到注册站的读卡器中，然后单击"注册 **"。**
    
12. 当系统提示时，在 PIN (输入) ，然后单击"确定 **"。**
    
    > [!NOTE]
    > 如果技术支持人员未提供用于注册智能卡的特殊 PIN，请使用默认的智能卡 PIN 值，即 12345678。 
  
13. 选择强制用户更改 () 第一次使用智能卡时更改 PIN。
    
14. 单击 **"** 确定"确认显示的证书上包含你的信息。
    
15. 在看到证书颁发通知后，单击"安装 **此证书** "以完成注册过程。
    
### <a name="sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡凭据登录 Skype for Business

首次使用智能卡之前，建议在 Skype for Business 登录页面上单击"删除我的登录信息"。 这样做可清除存储在您的计算机上的任何登录凭据，并消除可能的错误源。
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡凭据登录 Skype for Business

1. 启动 Skype for Business 客户端。
    
2. 在"登录"屏幕上，在登录地址框中键入登录用户帐户名，然后单击 **"登录"。**
    
3. 如果使用的是虚拟智能卡，请跳过此步骤。
    
    如果使用物理智能卡，请将智能卡插入智能卡读卡器，并提示你这样做，然后在检测到智能卡时单击"确定"。 
    
4. 键入智能卡的 PIN 号，然后单击"**确定"。**
    
    > [!NOTE]
    > 如果支持人员未分配智能卡 PIN 号码，请使用默认值 12345678。 
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business Server 中管理双重身份验证](two-factor-authentication.md)
  
[在 Skype for Business Server 中配置双重身份验证](configure-two-factor.md)
