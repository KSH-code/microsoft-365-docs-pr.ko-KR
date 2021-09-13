---
title: AutoPilot 프로필 설정 정보
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 프로필을 사용하면 사용자 장치에 Windows 방법을 제어할 수 있습니다. 프로필에는 설치 건너뛰기 같은 기본 및 선택적 Cortana 포함되어 있습니다.
ms.openlocfilehash: 9d425e73a5cedf51ce8267afa9505cbde8b97038
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184908"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot 프로필 설정 정보

## <a name="autopilot-profile-settings"></a>AutoPilot 프로필 설정

AutoPilot 프로필을 사용하여 사용자 장치에 Windows 방법을 제어할 수 있습니다. 프로필에는 다음 설정이 포함되어 있습니다.
  
 **자동 설정되는 AutoPilot 기본 기능(필수)**
  
|**설정**|**설명**|
|:-----|:-----|
|등록 Cortana, OneDrive 및 OEM 등록 건너뛰기  <br/> |앱 및 개인 앱과 같은 소비자 Cortana 설치를 OneDrive. 사용자가 디바이스의 로컬 관리자인 경우 장치 사용자는 나중에 이를 설치할 수 있습니다. 장치를 다른 제조업체에서 관리하기 때문에 원래 제조업체 등록을 Microsoft 365 Business Premium.  <br/> |
|회사 브랜드로 로그인 환경  <br/> |회사에서 로그인 [](../setup/customize-sign-in-page.md)페이지에 회사 브랜 Microsoft 365 있는 경우 장치 사용자는 로그인할 때 해당 환경을 얻게 됩니다.  <br/> |
|구성된 AAD 계정을 통해 MDM 자동 등록  <br/> |사용자 ID는 Azure Active Directory 관리되고 사용자는 사용자 자격 증명으로 Windows Microsoft 365 Microsoft 365 Business Premium 로그인합니다.  <br/> |
   
 **선택적 설정:**
  
|**설정**|**설명**|
|:-----|:-----|
|개인 정보 설정 건너뛰기(기본적으로 해제)  <br/> |이 옵션을 으로 설정하면 장치 사용자에게 장치에 대한 사용권 계약이 표시되지 Windows 처음 로그인할 때 이 옵션이 표시됩니다.  <br/> |
|사용자가 로컬 관리자가 되기를 허용하지 않습니다.  <br/> |이 옵션을 으로 설정하면 장치 사용자가 을(를) 설치하는 등의 개인 앱을 설치할 Cortana.<br/> |
