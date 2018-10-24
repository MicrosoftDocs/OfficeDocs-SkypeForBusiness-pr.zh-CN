---
title: 配置 Lync Server 被动身份验证
TOCTitle: 配置 Lync Server 被动身份验证
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn308569(v=OCS.15)
ms:contentKeyID: 56271186
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Lync Server 被动身份验证

 

_**上一次修改主题：** 2013-07-11_

以下部分介绍了如何配置具有 2013 年 7 月累积更新的 Lync Server 2013 以支持被动身份验证。启用后，启用了双重身份验证的 Lync 用户需要使用物理或虚拟智能卡和有效的 PIN 来通过具有 2013 年 7 月累积更新的 Lync 2013 客户端登录。

> [!NOTE]  
> 强烈建议用户在服务级别为注册机构和 Web 服务启用被动身份验证。如果在全局级别为注册机构和 Web 服务启用被动身份验证，则可能导致未使用具有 2013 年 7 月累积更新的 Lync 2013 桌面客户端登录的用户遭遇组织范围身份验证失败。


## Web 服务配置

以下步骤介绍了如何为将启用被动身份验证的控制器、企业池和 Standard Edition 服务器创建自定义 Web 服务配置。

**创建自定义 Web 服务配置**

1.  使用 Lync 管理员帐户登录到具有 2013 年 7 月累积更新的 Lync Server 2013 前端服务器。

2.  启动 Lync Server 2013 命令行管理程序。

3.  从 Lync Server 命令行管理程序 命令行，通过运行以下命令来为将启用被动身份验证的每个控制器、企业池和 Standard Edition 服务器创建新的 Web 服务配置：
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    
> [!NOTE]  
> WsFedPassiveMetadataUri FQDN 的值是您的 AD FS 2.0 服务器的联合身份验证服务名称。可通过从导航窗格右键单击“服务”，然后选择“编辑联合身份验证服务属性”来在 AD FS 2.0 管理控制台中找到联合身份验证服务名称值。


4.  通过运行以下命令来验证 UseWsFedPassiveAuth 和 WsFedPassiveMetadataUri 值是否设置正确：
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  对于客户端，被动身份验证是 Web 票证身份验证最少首选的身份验证方法。对于将启用被动身份验证的所有控制器、企业池和 Standard Edition 服务器，必须通过运行以下命令来在 Lync Web 服务中禁用所有其他身份验证类型：
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  通过运行以下命令来验证所有其他身份验证类型是否已成功禁用：
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

## 代理配置

当为证书身份验证禁用 Lync Web 服务时，Lync 客户端将使用不是首选的身份验证类型（如 Kerberos 或 NTLM）来向注册机构服务进行身份验证。仍然需要证书身份验证以允许 Lync 客户端检索 Web 票证，但是，必须为 Kerberos 和 NTLM 禁用注册机构服务。

以下步骤介绍了如何为将启用被动身份验证的边缘池、企业池和 Standard Edition 服务器创建自定义代理配置。

**创建自定义代理配置**

1.  从 Lync Server 命令行管理程序 命令行，通过运行以下命令来为将启用被动身份验证且具有 2013 年 7 月累积更新的 Lync Server 2013 边缘池、企业池和 Standard Edition 服务器创建新的代理配置：
    

    ```
    New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com"  
    -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
    ```
    
    ```
    New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"  
    -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
    ```

2.  通过运行以下命令来验证所有其他代理身份验证类型是否已成功禁用：
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

