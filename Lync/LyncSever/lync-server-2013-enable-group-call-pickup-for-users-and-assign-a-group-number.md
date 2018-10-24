---
title: 为用户启用组内呼叫应答并分配组号码
TOCTitle: 为用户启用组内呼叫应答并分配组号码
ms:assetid: c33bb6c2-d43b-4fb6-a0fa-6d82a7b09abe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945650(v=OCS.15)
ms:contentKeyID: 52061113
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为用户启用组内呼叫应答并分配组号码

 

_**上一次修改主题：** 2013-01-30_

将组内呼叫应答组号码添加到呼叫寄存轨道表后，可以向用户分配这些组号码并为他们启用组内呼叫应答。可使用辅助扩展功能激活 (SEFAUtil) 资源工具包工具分配组号码并启用组内呼叫应答。

> [!NOTE]  
> 在混合部署中，不要向在线驻留的用户分配组内呼叫应答组。在线驻留的用户无法参与组内呼叫应答。也就是说，他们的呼叫无法由其他用户应答，他们也无法应答对其他用户的呼叫。



## 为用户分配组号码并启用组内呼叫应答

1.  使用管理员权限登录安装了 SEFAUtil 工具的计算机。

2.  在该命令行处，运行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /enablegrouppickup:<group number>
    
    例如，将组号码 199 分配给用户：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /enablegrouppickup:199 

## 另请参阅

#### 任务

[为用户禁用组内呼叫应答](lync-server-2013-disable-group-call-pickup-for-users.md)

