---
title: Windows 장치에서 Office 2013에 대해 최신 인증 사용
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Microsoft Office 2013이 설치 된 장치에 대해 최신 인증을 사용 하도록 레지스트리 키를 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 8edcedefc04d5018b8b61022c26cbe027f7c24a9
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779968"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Windows 장치에서 Office 2013에 대해 최신 인증 사용

Office 2013이 설치되어 있는 Windows 장치에 대해 최신 인증을 사용하려면 특정 레지스트리 키를 설정해야 합니다.
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Office 2013 클라이언트에 대해 최신 인증 사용

> [!NOTE]
> Office 2016 클라이언트에 대해 이미 최신 인증이 사용되고 있는 경우 Office 2016에 대해 레지스트리 키를 설정할 필요가 없습니다. 
  
To enable modern authentication for any devices running Windows (for example on laptops and tablets), that have Microsoft Office 2013 installed, you need to set the following registry keys. The keys have to be set on each device that you want to enable for modern authentication:
  
|**레지스트리 키**|**유형**|**값** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1   |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1  |
   
레지스트리 키를 설정한 후에는 Microsoft 365와 함께 [MFA (다단계 인증)](set-up-multi-factor-authentication.md) 를 사용 하도록 Office 2013 장치 앱을 설정할 수 있습니다. 
  
If you're currently signed-in with any of the client apps, you need to sign out and sign back in for the change to take effect. Otherwise, the MRU and roaming settings will be unavailable until the ADAL identity is established.
  
## <a name="disable-modern-authentication-on-devices"></a>장치에서 최신 인증을 사용하지 않음

장치에서 최신 인증을 사용하지 않으려면 장치의 다음 레지스트리 키를 설정합니다.
  
|**레지스트리 키**|**유형**|**값**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|개|
   
## <a name="related-articles"></a>관련 문서
[두 번째 확인 방법으로 Office 2013에 로그인](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)

  

