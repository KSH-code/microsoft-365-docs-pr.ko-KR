---
title: AutoPilot 프로필 설정 정보
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: 작업을 자동화할 프로필 사용자 장치에 Windows 가져옵니다 설치 하는 방법을 제어 하는데 도움이 됩니다. 프로필에 기본 포함과 설정 (옵션) Cortana 설치를 건너뜁니다.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869745"
---
# <a name="about-autopilot-profile-settings"></a>AutoPilot 프로필 설정 정보

## <a name="autopilot-profile-settings"></a>작업을 자동화할 프로필 설정

사용자 장치에 작업을 자동화할 프로필을 사용 하 여 Windows 가져옵니다 설치 하는 방법을 제어할 수 있습니다. 프로필은 다음 설정을 포함 합니다.
  
 **작업을 자동화할 기본 기능 (필수) 자동으로 설정 됩니다.**
  
|**설정**|**설명**|
|:-----|:-----|
|건너뛰기 Cortana, OneDrive 및 OEM 등록  <br/> |Cortana 및 개인 OneDrive와 같은 소비자 앱의 설치를 건너뜁니다. 장치 사용자가 자신이 장치에 로컬 관리자가 나중에 이러한 설치할 수 있습니다. 장치를 관리 하 여 Microsoft 365 비즈니스에서는 원래 제조업체 등록 건너뛴 됩니다.  <br/> |
|회사 브랜드로 경험에 로그인  <br/> |회사가 [Office 365 로그인 페이지에 추가 회사 브랜딩](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a)하는 경우에 장치 사용자 로그인 할 때 해당 환경에 발생 합니다.  <br/> |
|MDM 자동 등록이 구성 된 AAD 계정 사용 합니다.  <br/> |사용자 id를 관리 하 여 Azure Active directory를 여는 하 고 사용자가 자신의 Microsoft 365 비즈니스 자격 증명을 가진 Windows 및 Office 365에 로그인 됩니다.  <br/> |
   
 **설정 (옵션):**
  
|**설정**|**설명**|
|:-----|:-----|
|개인정보 보호 설정을 건너뜁니다 (기본적으로 해제)  <br/> |이 옵션을 **On**으로 설정 하는 경우가 자신이 처음 로그인 하면 장치 사용자는 장치 및 Windows에 대 한 사용권 계약을 표시 되지 않습니다.  <br/> |
|사용자 로컬 관리자가 될 수 없도록 합니다.  <br/> |이 옵션을 **On**으로 설정 하는 경우 장치 사용자 Cortana와 같은 모든 개인 앱을 설치할 수 없습니다.  <br/> |
   
