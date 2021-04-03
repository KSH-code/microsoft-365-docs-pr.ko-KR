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
description: AutoPilot 프로필을 사용하면 Windows가 사용자 장치에 설치되는 방법을 제어할 수 있습니다. 프로필에는 Cortana 설치 건너뛰기 같은 기본 및 선택적 설정이 포함되어 있습니다.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578510"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot 프로필 설정 정보

## <a name="autopilot-profile-settings"></a>AutoPilot 프로필 설정

AutoPilot 프로필을 사용하여 사용자 장치에 Windows가 설치되는 방법을 제어할 수 있습니다. 프로필에는 다음 설정이 포함되어 있습니다.
  
 **자동 설정되는 AutoPilot 기본 기능(필수)**
  
|**설정**|**설명**|
|:-----|:-----|
|Cortana, OneDrive 및 OEM 등록 건너뛰기  <br/> |Cortana 및 개인 OneDrive와 같은 소비자 앱의 설치를 건너뜁. 사용자가 디바이스의 로컬 관리자인 경우 장치 사용자는 나중에 이를 설치할 수 있습니다. 장치를 Microsoft 365 Business Premium에서 관리하기 때문에 원래 제조업체 등록을 건너뜁니다.  <br/> |
|회사 브랜드로 로그인 환경  <br/> |회사에 Microsoft [365](../admin/setup/customize-sign-in-page.md)로그인에 회사 브랜드 추가 페이지가 있는 경우 장치 사용자는 로그인할 때 해당 환경을 얻게 됩니다.  <br/> |
|구성된 AAD 계정을 통해 MDM 자동 등록  <br/> |사용자 ID는 Azure Active Directory에서 관리되고 사용자는 Microsoft 365 Business Premium 자격 증명을 사용하여 Windows 및 Microsoft 365에 로그인합니다.  <br/> |
   
 **선택적 설정:**
  
|**설정**|**설명**|
|:-----|:-----|
|개인 정보 설정 건너뛰기(기본적으로 해제)  <br/> |이 옵션을 으로 설정하면 장치 사용자가 처음 로그인할 때 장치 및 Windows에 대한 사용권 계약이 표시되지 않습니다.  <br/> |
|사용자가 로컬 관리자가 되기를 허용하지 않습니다.  <br/> |이 옵션을 으로 설정하면 장치 사용자가 Cortana와 같은 개인 앱을 설치할 수 없습니다.<br/> |
