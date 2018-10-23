---
title: 配置 Active Directory 联合身份验证服务 (AD FS 2.0)
TOCTitle: 配置 Active Directory 联合身份验证服务 (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn308561(v=OCS.15)
ms:contentKeyID: 56271127
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Active Directory 联合身份验证服务 (AD FS 2.0)
 

_**上一次修改主题：** 2016-12-08_

下面一节介绍如何配置 Active Directory 联合身份验证服务 (AD FS 2.0) 以支持多重身份验证。有关如何安装 AD FS 2.0 的信息，请参阅 AD FS 2.0 分步说明和操作指南：[http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374)。

> [!NOTE]  
> 安装 AD FS 2.0 时，请勿使用 Windows Server Manager 添加联合身份验证服务角色。请下载并安装 Active Directory 联合身份验证服务 2.0 RTW 程序包：<a href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</a>。


**针对双重身份验证配置 AD FS**

1.  使用域管理员帐户登录到 AD FS 2.0 计算机。

2.  启动 Windows PowerShell。

3.  从 Windows PowerShell 命令行，运行以下命令：
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  与具有 2013 年 7 月 Lync Server 2013 累积更新的各个 Lync Server 2013（控制器、企业版池和 Standard Edition 服务器）建立合作关系，将通过运行以下命令为其启用被动身份验证，请替换为特定于您的部署的服务器名称：
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  从“管理工具”菜单中，启动 AD FS 2.0 管理控制台。

6.  展开“信任关系” \>“依赖方信任”。

7.  验证是否为您的具有 2013 年 7 月 Lync Server 2013 累积更新的 Lync Server 2013（企业版池和 Standard Edition 服务器）创建了新信任。

8.  使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发授权规则：
    

    ```
    $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
    ```
    ```    
    Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 

        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
    ```

9.  使用 Windows PowerShell 通过运行以下命令为您的依赖方信任创建并分配颁发转换规则：
    

    ```
    $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
    ```

    
    ```   
    Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
    ```

10. 从 AD FS 2.0 管理控制台中，右键单击您的依赖方信任并选择“编辑声明规则”。

11. 选择“颁发授权规则”选项卡，并验证是否已成功创建新的授权规则。

12. 选择“颁发转换规则”选项卡，并验证是否已成功创建新的转换规则。

