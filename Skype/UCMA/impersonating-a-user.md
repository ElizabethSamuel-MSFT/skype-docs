﻿---
title: Impersonating a user
description: Describes how to impersonate a user as it applies to Skype for Business 2015 and provides a sample code example of impersonating a user.
TOCTitle: Impersonating a user
ms:assetid: 5b22dec3-ac5a-4774-95ad-e59c6e66bd50
ms:mtpsurl: https://msdn.microsoft.com/library/Dn465984(v=office.16)
ms:contentKeyID: 65239922
ms.date: 07/27/2015
mtps_version: v=office.16
dev_langs:
- csharp
---

# Impersonating a user


**Applies to**: Skype for Business 2015

The local participant address is automatically inferred from the endpoint that is specified. If the application is trusted by Skype for Business Server 2015, the application can impersonate another user. This is normally required to offer services on behalf of a specific user who initiated the call to the application. For example, a help-desk application might want to impersonate the user who calls in for help when it directs the call to an agent who can help the user.

Before adding calls to the conversation, the application must first indicate who is being impersonated. The impersonation API can be called for both an outgoing conversation created locally when the conversation state is **Idle**, and for an incoming conversation.

The following code demonstrates impersonating the user specified by the first parameter. The second parameter specifies the phone number of the impersonated user, and the string "Help Desk" is the name that will be displayed for the impersonated user.

```csharp
conversation.Impersonate("sip:helpdesk@xyz.com", "tel:+2341234678", "Help Desk"); 
```

