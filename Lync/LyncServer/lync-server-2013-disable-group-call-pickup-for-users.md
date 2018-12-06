---
title: 为用户禁用组内呼叫应答
TOCTitle: 为用户禁用组内呼叫应答
ms:assetid: 91b06f9e-2840-45a2-bbb3-6a29179b9a9f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945638(v=OCS.15)
ms:contentKeyID: 52061076
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为用户禁用组内呼叫应答

 

_**上一次修改主题：** 2013-01-30_

使用以下过程为用户禁用组内呼叫应答。

> [!NOTE]  
> 当为某个用户禁用组内呼叫应答时，分配给该用户的呼叫应答组号码不再保留。如果您随后想为该用户重新启用组内呼叫应答，必须使用参数 /enablegrouppickup 再次分配呼叫应答组号码。



## 为用户禁用组内呼叫应答

1.  以管理员权限登录安装了 SEFAUtil 工具的计算机。

2.  在命令行处，运行：
    
        SEFAUtil.exe sip:<sip address of user> /server:<pool FQDN> /disablegrouppickup
    
    例如：
    
        SEFAUtil.exe katarina@contoso.com /server:pool01.contoso.com /disablegrouppickup

## 另请参阅

#### 任务

[向用户分配组内呼叫应答号码](lync-server-2013-assign-group-call-pickup-numbers-to-users.md)  
[为用户启用组内呼叫应答](lync-server-2013-enable-group-call-pickup-for-users.md)

