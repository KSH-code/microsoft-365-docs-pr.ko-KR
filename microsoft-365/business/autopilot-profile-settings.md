---
title: AutoPilot 프로필 설정 정보
ms.author: sirkkuw
author: Sirkkuw
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: AutoPilot 프로필은 Windows가 사용자 장치에 설치 되는 방법을 제어 하는 데 도움이 됩니다. 이 프로필에는 Cortana 설치 건너뛰기와 같은 기본 설정과 선택적 설정이 포함 되어 있습니다.
ms.openlocfilehash: cd66627943301f4a4f2410bafeff6074919ec29d
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/27/2019
ms.locfileid: "37287478"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot 프로필 설정 정보

## <a name="autopilot-profile-settings"></a>AutoPilot 프로필 설정

AutoPilot 프로필을 사용 하 여 사용자 장치에 Windows를 설치 하는 방법을 제어할 수 있습니다. 프로필에는 다음 설정이 포함 됩니다.
  
 **자동으로 설정 되는 AutoPilot 기본 기능 (필수):**
  
|**설정**|**설명**|
|:-----|:-----|
|Cortana, OneDrive 및 OEM 등록 건너뛰기  <br/> |Cortana 및 개인 OneDrive와 같은 소비자 앱의 설치를 건너뜁니다. 장치 사용자가 장치에서 로컬 관리자 인 경우에는 나중에이를 설치할 수 있습니다. Microsoft 365 Business에서 장치를 관리 하므로 원래 제조업체 등록을 건너뜁니다.  <br/> |
|회사 브랜드의 로그인 환경  <br/> |회사의 [Office 365 로그인 페이지에 회사 브랜드 추가](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)를 사용 하는 경우에는 장치 사용자에 게 로그인 할 때 해당 환경이 제공 됩니다.  <br/> |
|구성 된 AAD 계정을 사용 하는 MDM 자동 등록  <br/> |사용자 id는 Azure Active directory에서 관리 되며, 사용자는 Microsoft 365 Business 자격 증명을 사용 하 여 Windows 및 Office 365에 로그인 합니다.  <br/> |
   
 **선택적 설정:**
  
|**설정**|**설명**|
|:-----|:-----|
|개인 정보 설정 건너뛰기 (기본적으로 해제)  <br/> |이 옵션을 **On**으로 설정 하면 장치 사용자가 처음 로그인 할 때 장치 및 Windows에 대 한 사용권 계약을 볼 수 없습니다.  <br/> |
|사용자가 로컬 관리자가 될 수 없음  <br/> |이 옵션을 **On**으로 설정 하면 장치 사용자가 Cortana와 같은 개인 앱을 설치할 수 없게 됩니다.  <br/> |
   
