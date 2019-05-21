---
title: 对 Skype for Business 客户端和 Skype for business 服务器使用双因素身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d4136e61-c3ab-4b26-85c8-c1b2c24f5ee3
description: '摘要: 在 Skype for business 服务器和 Skype for business 中使用双因素身份验证。'
ms.openlocfilehash: 532e7567444b78dd30d053cf91aef1c10f0970bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286107"
---
# <a name="use-two-factor-authentication-with-skype-for-business-client-and-skype-for-business-server"></a>对 Skype for Business 客户端和 Skype for business 服务器使用双因素身份验证
 
**摘要:** 对 Skype for business 服务器和 Skype for business 使用双因素身份验证。
  
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>首次登录 Skype for Business

在安装 Skype for Business 时, 通常会自动配置您的登录信息。 但首次使用 Skype for Business 时, 您可能需要手动启动客户端。
  
### <a name="to-sign-in-for-the-first-time"></a>首次登录

1. 登录到您的组织的网络。
    
2. 选择 "**启动** > **所有程序** > **Skype for business**"。
    
    您应该会看到登录屏幕。
    
    - 如果登录地址框已经填充，请确认显示的地址是否正确。
    
    - 如果不正确, 或者如果该框为空, 请输入您的登录地址 (这通常与您的电子邮件地址相同)。
    
    - 如果显示空密码框，请添加您的密码。
    
3. 选择“登录”****。
    
## <a name="sign-out-of-skype-for-business"></a>注销 Skype for Business

使用 Skype for Business 完成后, 您可以从 "文件" 菜单中关闭显示、注销会话或退出程序。 下表说明了这些选项之间的差异。
  
|**选项**|**执行的结果**|**如何执行**|
|:-----|:-----|:-----|
|关闭  <br/> |关闭您的显示器, 但让使用您的用户 ID 标识的 Skype for business 会话继续运行。 因此，您可以继续接收通知并与其他人互动。 <br/> <br/> 你可以随时通过单击任务栏上的 "Skype for Business" 图标或屏幕底部的通知区域来恢复显示。  <br/> | 在 Skype for Business 主窗口中, 执行下列操作之一: <br/> 1. 选择 "**选项**" 按钮, 然后选择 "**文件** > **关闭**"。  <br/> 2. 单击窗口右上角的 "**关闭**" 按钮 (X)。 <br/> |
|注销  <br/> |结束与你的用户 ID 相关联的会话, 但 Skype for business 将继续在后台运行。 注销时，登录窗口将会出现。  <br/> **提示:** 选择 **"注销时删除我的登录信息**", 从计算机中删除您的登录 ID 和密码记录。 这样做使支持人员可以更轻松地解决登录问题。 还通过使未经授权的用户难以使用您的凭据登录来帮助确保您的登录信息更安全。 <br/> |在 Skype for business 主窗口中, 选择 "**选项**" 按钮, 然后选择 "**文件** > **注销**"。  <br/> |
|退出  <br/> |结束您的 Skype for Business 会话并在您的计算机上关闭 Skype for business。 退出后, 如果要重新启动, 请选择 "**启动** > **所有**> Skype for business 程序"。 <br/> |在 Skype for business 主窗口中, 选择 "**选项**" 按钮, 然后选择 "**文件** > **退出**"。  <br/> |
   
## <a name="sign-in-to-skype-for-business-with-a-smart-card"></a>使用智能卡登录 Skype for Business

一些组织现在使用多步骤登录过程（称为双重身份验证）来为其用户提高安全性。 如果您希望使用此选项, 则需要 "智能卡" 才能登录 Skype for Business。 智能卡可以是物理卡, 也可以是虚拟的:
  
- **物理**关于信用卡的大小。 登录时请将其插入到智能卡读卡器中。
    
- **虚拟**不是物理对象, 而是写入计算机上的特殊芯片的电子标识符, 其实质上是将智能卡构建到计算机中。 仅适用于包含 TPM (受信任的平台模块) 芯片的 Windows 8 计算机。
    
### <a name="enroll-your-smart-card"></a>注册智能卡

在使用智能卡登录之前, 卡必须 "已注册", 即你的用户凭据必须使用卡进行标识。 不管是物理智能卡还是虚拟智能卡都是如此。 此过程可能已由您的 Skype for Business 服务器管理员执行。 如果你不确定是否已完成, 请与他们进行核对。
  
> [!NOTE]
> 由于每个虚拟智能卡仅与安装它的设备相关联, 因此需要为你使用的每个 Windows 8 计算机注册一个单独的卡。 
  
### <a name="to-manually-enroll-your-smart-card"></a>手动注册智能卡

1. 登录到运行 Skype for Business 的计算机。
    
2. 使用 Internet Explorer, 浏览到您的组织的证书颁发机构 Web 注册页面。 
    
    如果尚不具备此资源的 web 地址, 请询问您的 Skype for Business Server 管理员。 URL 将如下所示: https://MyCA。[公司名称] .com/certsrv。
    
    > [!NOTE]
    > 如果您使用的是 Internet Explorer 10, 您可能需要在 "兼容模式" 下查看此网站。 
  
3. 当系统提示您登录到证书页面时, 请使用您的域帐户 (而不是计算机管理员) 登录。
    
4. 在网站的“欢迎”页面上，选择“申请证书”****。
    
5. 单击“高级申请”****。
    
6. 选择“创建并向此 CA 提交一个申请”****，然后单击“下一步”****。
    
7. 现在, 你将看到一个名为 "智能卡注册站" 的页面。 批准申请以安装 ActiveX 控件，然后填写“高级证书申请”表单，如下所示：
    
    a. 从“证书模板”**** 下拉列表中选择“智能卡用户”****。
    
    b. 选择“创建新密钥集”****。
    
    c. 在智能卡标签上查找制造商信息，然后从“CSP”**** 下拉列表中选择该制造商。
    
    d. 选择 " **CSP** " 作为 "请求格式" (如果尚未选中)。
    
    e.i. 从 "散列算法" 下拉列表中选择 " **sha1** " (如果尚未选中)。
    
    f. 为您的证书指定一个名称, 然后单击 "**提交**"。
    
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

首次使用你的智能卡之前, 建议你单击 "Skype for Business 登录" 页面上的 "**删除我的登录信息**"。 这样做可清除您的计算机上存储的任何登录凭据，并消除可能的错误源。
  
### <a name="to-sign-in-to-skype-for-business-with-your-smart-card-credentials"></a>使用智能卡凭据登录 Skype for Business

1. 启动 Skype for Business 客户端。
    
2. 在“登录”屏幕上，在“登录地址”**** 框中键入您的登录用户帐户名称，然后单击“登录”****。
    
3. 如果您正在使用虚拟智能卡，请跳过此步骤。
    
    如果您正在使用物理智能卡，请在出现提示时在您的智能卡读卡器中插入智能卡，然后当检测到卡时单击“确定”****。
    
4. 为您的智能卡键入 PIN 号码，然后单击“确定”****。
    
    > [!NOTE]
    > 如果您的支持人员未向您提供智能卡 PIN 号码，请使用默认值 12345678。 
  
## <a name="see-also"></a>另请参阅

[在 Skype for Business 服务器中管理双因素身份验证](two-factor-authentication.md)
  
[在 Skype for Business 服务器中配置双因素身份验证](configure-two-factor.md)
