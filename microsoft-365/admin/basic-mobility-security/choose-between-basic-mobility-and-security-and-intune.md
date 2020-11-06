---
title: 기본 이동성 및 보안 및 Intune 중에서 선택
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 이동성 및 보안은 Microsoft 365 계획의 일부입니다.
ms.openlocfilehash: b9568d0aad03fc3c8a5c81d02f98f5b238124a82
ms.sourcegitcommit: 5a355bde865369f64ea1788a378da23c65b1d249
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/06/2020
ms.locfileid: "48930168"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>기본 이동성 및 보안 또는 Intune 중에서 선택

[Microsoft Intune](https://docs.microsoft.com/mem/intune/) 은 특정 microsoft 365 계획에 포함 된 독립 실행형 제품으로, 기본 이동성 및 보안은 Microsoft 365 계획의 일부입니다. 

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>기본 이동성 및 보안 및 Intune의 가용성
 
기본 Mobility and Security 및 Intune은 다음 표에 설명 된 것과 같이 다양 한 계획에 포함 되어 있습니다.

|**플랜**|**기본 이동성 및 보안**|**Microsoft Intune**|
|:-----|:-----|:-----|
|Microsoft 365 앱|예|아니요|
|Microsoft 365 Business Basic|예|아니요|
|Microsoft 365 Business Standard|예|아니요|
|Office 365 E1 |예|아니요|
|Office 365 E3 |예|아니요|
|Office 365 E5 |예|아니요|
|Microsoft 365 Business Premium |예|예|
|Microsoft 365 Firstline 3 |예|예|
|Microsoft 365 Enterprise E3 |예|예|
|Microsoft 365 Enterprise E5 |예|예|
|Microsoft 365 교육 A1 |예|예|
|Microsoft 365 Education A3 |예|예|
|Microsoft 365 Education A5 |예|예|
|Microsoft Intune |아니요|예|
|Enterprise Mobility & 보안 E3 |아니요|예|
|Enterprise Mobility & 보안 E5 |아니요|예|

>[!NOTE]
>이미 Microsoft Intune을 사용 하 고 있는 경우에는 기본 이동성 및 보안 사용을 시작할 수 없습니다.

 자세한 내용은 [Microsoft 365 및 Office 365 platform 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)참조 하십시오. 

## <a name="differences-in-capabilities"></a>기능의 차이점

Microsoft Intune과 기본 제공 되는 기본 이동성 및 보안 둘 다 조직의 모바일 장치를 관리할 수 있는 기능을 제공 하지만 다음 표에 설명 된 것과 같은 기능에는 주요 차이점이 있습니다.

>[!NOTE]
>*기본 mobility And security을 먼저 설정한 다음 Microsoft Intune을 추가 하 여* 동일한 Microsoft 365 Business Standard 조 직에서 Intune과 기본 이동성 및 보안을 모두 사용 하 여 사용자 및 모바일 장치를 관리할 수 있습니다. 이를 통해 기본 모바일 및 보안 기능 또는 기능이 풍부한 Intune 솔루션을 선택할 수 있습니다. Intune 기능을 사용 하기 위해 Intune 라이선스를 할당 합니다.

|**기능 영역**|**주요 기능**|**기본 이동성 및 보안**|**Microsoft Intune**|
|:-----|:-----|:-----|:-----|
|장치 유형|여러 OS 플랫폼 및 주요 관리 모드 변형 관리 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|장치 준수|장치 수준 PIN 잠금 및 jailbreak 검색 등의 보안 정책을 설정 하 고 관리 합니다. |Android 9 이상 장치에 대 한 제한 [세부 정보](capabilities.md)를 참조 하세요. |예|
|장치 규정 준수에 따른 조건부 액세스 |비규격 장치가 클라우드의 회사 전자 메일 및 데이터에 액세스 하지 못하도록 합니다. |Windows 10에서는 지원 되지 않습니다.<br/>Exchange Online, SharePoint Online 및 Outlook에 대 한 액세스를 제어 하는 것으로 제한 됩니다. |아니요 |
|장치 구성  |장치 설정 구성 (예: 카메라 사용 안 함)|장치 준수|장치 수준 PIN 잠금 및 jailbreak 검색 등의 보안 정책을 설정 하 고 관리 합니다. |Android 9 이상 장치에 대 한 제한 [세부 정보](capabilities.md)를 참조 하세요. |예|
 |제한 된 설정 집합입니다. |예|
|전자 메일 프로필  |장치에서 기본 전자 메일 프로필을 프로 비전 합니다. |예|예|
|WiFi 프로필 |장치에서 기본 WiFi 프로필을 프로 비전 합니다. |아니요|예|
|VPN 프로필 |장치에 기본 VPN 프로필을 프로 비전 합니다. |아니요|예|
|MDM 응용 프로그램 관리 |내부 기간 업무 (lob) 앱 및 앱 스토어를 사용자에 게 배포 합니다. |아니요|예|
|MAM |사용자가 복사, 잘라내기, 붙여넣기, 다른 이름으로 저장 같은 작업을 회사 데이터에 대해 승인 된 앱 으로만 제한 하 여 Office mobile 및 기간 업무 (lob) 앱을 사용 하 여 회사 정보에 안전 하 게 액세스할 수 있도록 합니다. |아니요|예|
|Managed browser  |에 지 앱을 사용 하 여 보다 안전한 웹 검색을 사용 하도록 설정 합니다. |아니요|예|
|제로 터치 등록 프로그램 Autopilot) |많은 수의 회사가 소유한 장치를 등록 하 고 사용자 설치를 간소화 합니다. |아니요|예|
|||

위의 표에 나열 된 기능 외에도 기본 Mobility and Security 및 Intune에는 모두 인터넷을 통해 장치에 명령을 전송 하는 원격 작업 집합이 포함 되어 있습니다. 예를 들어 개인 데이터를 그대로 두거나 (사용 중지), 직원의 장치에서 Office 앱을 제거 하거나 (초기화) 디바이스를 공장 설정으로 다시 설정 (전체 지우기) 한 후 직원의 장치에서 Office 데이터를 제거할 수 있습니다. 

기본 이동성 및 보안 원격 작업에는 사용 중지, 지우기 및 전체 지우기가 포함 됩니다. 기본 이동성 및 보안 작업에 대 한 자세한 내용은 [기본 이동성 및 보안 기능](capabilities.md)을 참조 하세요.

Intune을 사용 하는 경우 다음과 같은 일련의 작업을 사용할 수 있습니다.

-   Autopilot reset (Windows만
-  [Bitlocker 키 순환](https://docs.microsoft.com/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Windows만 해당)
-  [초기화, 사용 중지 또는 수동으로 장치 unenrolling](https://docs.microsoft.com/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [정품 인증](https://docs.microsoft.com/mem/intune/remote-actions/device-activation-lock-disable)   을 사용 하지 않도록 설정 (iOS에만 해당)
-  [새로 시작](https://docs.microsoft.com/mem/intune/remote-actions/device-fresh-start)   (Windows만 해당)
- [전체 검색](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Windows 10만 해당)
- [장치 찾기](https://docs.microsoft.com/mem/intune/remote-actions/device-locate)   (iOS에만 해당)
- [손실 모드](https://docs.microsoft.com/mem/intune/remote-actions/device-lost-mode)   (iOS만 해당)- [빠른 검사](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)(Windows 10만 해당)
- [Android 용 원격 제어](https://docs.microsoft.com/mem/intune/remote-actions/teamviewer-support)
- [원격 잠금](https://docs.microsoft.com/mem/intune/remote-actions/device-remote-lock)
- [장치 이름 바꾸기](https://docs.microsoft.com/mem/intune/remote-actions/device-rename)
-  다시 시작 [암호](https://docs.microsoft.com/mem/intune/remote-actions/device-passcode-reset) [다시](https://docs.microsoft.com/mem/intune/remote-actions/device-restart)설정   (Windows 전용)
-  Windows Defender 보안 인텔리전스 업데이트 (Windows만 해당)
-  Windows 10 PIN 다시 설정 (Windows 전용)
-  [사용자 지정 알림 보내기](https://docs.microsoft.com/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [장치 동기화](https://docs.microsoft.com/mem/intune/remote-actions/device-sync)

Intune 작업에 대 한 자세한 내용은 [Microsoft Intune 설명서](https://docs.microsoft.com/mem/intune/)를 참조 하세요.