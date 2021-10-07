---
title: 기본 이동성 및 보안과 Intune 중 선택
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 기본 모바일 및 보안은 기본 Microsoft 365 있습니다.
ms.openlocfilehash: 0a461bc7462300bb2b27b5d027c2b4d4582b7d14
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166233"
---
# <a name="choose-between-basic-mobility-and-security-or-intune"></a>기본 이동성 및 보안 또는 Intune 중 선택

[Microsoft Intune](/mem/intune/) 기본 이동성 및 보안은 Microsoft 365 계획에 포함되어 있는 독립 실행형 Microsoft 365 제품입니다.

 ## <a name="availability-of-basic-mobility-and-security-and-intune"></a>기본 이동성 및 보안 및 Intune의 가용성

기본 이동성 및 보안과 Intune은 다음 표에 설명된 다양한 계획에 포함되어 있습니다.

| 계획 | 기본 모바일 및 보안 | Microsoft Intune |
|:-----|:-----|:-----|
|Microsoft 365 앱|예|아니요|
|Microsoft 365 Business Basic|예|아니요|
|Microsoft 365 Business Standard|예|아니요|
|Office 365 E1 |예|아니요|
|Office 365 E3 |예|아니요|
|Office 365 E5 |예|아니요|
|Microsoft 365 Business Premium |예|예|
|Microsoft 365 일선 3 |예|예|
|Microsoft 365 Enterprise E3 |예|예|
|Microsoft 365 Enterprise E5 |예|예|
|Microsoft 365 Education A1 |예|예|
|Microsoft 365 Education A3 |예|예|
|Microsoft 365 Education A5 |예|예|
|Microsoft Intune |아니요|예|
|Enterprise Mobility & Security E3 |아니요|예|
|Enterprise Mobility 및 Security E5 |아니요|예|

> [!NOTE]
> 이미 기본 이동성 및 보안을 사용하고 있는 경우 기본 이동성 및 보안을 사용할 Microsoft Intune.

 자세한 내용은 Microsoft 365 [및 Office 365 서비스 설명을 참조하세요.](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)

## <a name="differences-in-capabilities"></a>기능의 차이점

Microsoft Intune 기본 제공 Basic Mobility and Security를 사용하면 조직에서 모바일 장치를 관리할 수 있지만 다음 표에 설명된 기능과는 주요 차이점이 있습니다.

> [!NOTE]
> 기본 이동성 및 보안을 먼저 설정한 다음 을 추가하여 동일한 Microsoft 365 Business Standard 조직에서 Intune 및 *Basic Mobility and Security를* 모두 사용하여 사용자와 모바일 장치를 관리할 Microsoft Intune. 이렇게 하면 기본 Mobility and Security 또는 기능이 풍부한 Intune 솔루션을 선택할 수 있습니다. Intune 기능을 사용하도록 설정하려면 Intune 라이선스를 할당합니다.

| 기능 영역 | 주요 기능 | 기본 모바일 및 보안 | Microsoft Intune |
|:-----|:-----|:-----|:-----|
|장치 유형|다양한 OS 플랫폼 및 주 관리 모드 변형 관리 |Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>|Windows<br/>iOS<br/>Android<br/>Android Samsung KNOX<br/>mac OS, iPad OS|
|장치 준수|장치 수준 PIN 잠금 및 탈옥 감지와 같은 보안 정책을 설정하고 관리합니다. |Android 9 이상 디바이스에 대한 제한 사항 자세한 [내용은 을 참조합니다.](capabilities.md) |예|
|장치 준수에 기반한 조건부 액세스 |비영리 장치가 클라우드에서 회사 전자 메일 및 데이터에 액세스하지 못하게 합니다. |지원되지 Windows 10.<br/>Exchange Online, SharePoint Online 및 Outlook. |예 |
|장치 구성  |장치 설정 구성(예: 카메라 사용 안 하도록 설정)|제한된 설정 집합입니다.|예|
|전자 메일 프로필  |장치에서 기본 전자 메일 프로필을 프로비전합니다. |예|예|
|WiFi 프로필 |장치에서 기본 WiFi 프로필을 프로비전합니다. |아니요|예|
|VPN 프로필 |장치에서 기본 VPN 프로필을 프로비전합니다. |아니요|예|
|모바일 응용 프로그램 관리  |내부 업무용 앱과 앱 스토어에서 사용자에게 배포합니다. |아니요|예|
|모바일 응용 프로그램 보호  |사용자가 알고 있는 Office 모바일 및 업무용 앱을 사용하여 회사 정보에 안전하게 액세스할 수 있도록 하면서 복사, 잘라 내기, 붙여넣기 및 저장과 같은 작업을 회사 데이터에 대해 승인된 앱으로만 제한함으로써 데이터의 보안을 보장할 수 있습니다. 장치가 기본 Mobility and Security에 등록되지 않은 경우에도 작동합니다. MAM 정책을 사용하여 앱 데이터 보호를 참조하세요. |아니요|예|
|관리되는 브라우저  |에지 앱을 사용하여 보다 안전한 웹 검색을 사용하도록 설정하세요. |아니요|예|
|제로 터치 등록 프로그램(AutoPilot) |많은 수의 회사 소유 장치를 등록하고 사용자 설정을 간소화합니다. |아니요|예|
|||

위의 표에 나열된 기능 외에도 기본 Mobility and Security 및 Intune에는 인터넷을 통해 디바이스에 명령을 보내는 원격 작업 집합이 포함되어 있습니다. 예를 들어 개인 데이터를 Office 동안 직원의 장치에서 Office 데이터를 제거하거나(사용 중지), 직원의 장치에서 Office 앱을 제거(지우기) 또는 장치를 공장 설정(전체 지우기)으로 다시 설정할 수 있습니다.

기본 Mobility and Security 원격 작업에는 사용 중지, 지우기 및 전체 지우기 작업이 포함됩니다. 기본 이동성 및 보안 작업에 대한 자세한 내용은 [Basic Mobility and Security의 기능을 참조하세요.](capabilities.md)

Intune을 사용하면 다음과 같은 작업 집합이 있습니다.

-   Autopilot 재설정(Windows 전용)
-  [Bitlocker 키 회전](/mem/intune/protect/encrypt-devices#rotate-bitlocker-recovery-keys)   (Windows 전용)
-  [장치 초기화, 사용 중지 또는 수동으로 장치 초기화 사용](/mem/intune/remote-actions/devices-wipe#delete-devices-from-the-intune-portal)
-  [활성화 loc를 사용하지 않도록 설정](/mem/intune/remote-actions/device-activation-lock-disable)   (iOS만 해당)
-  [새 시작](/mem/intune/remote-actions/device-fresh-start)   (Windows 전용)
- [전체 검사](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)   (Windows 10 전용)
- [장치 찾기](/mem/intune/remote-actions/device-locate)   (iOS만 해당)
- [손실 모드](/mem/intune/remote-actions/device-lost-mode)   (iOS만 해당) - [빠른 검사(Windows 10](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)전용)
- [Android용 원격 제어](/mem/intune/remote-actions/teamviewer-support)
- [원격 잠금](/mem/intune/remote-actions/device-remote-lock)
- [장치 이름 바꾸기](/mem/intune/remote-actions/device-rename)
-  [암호 다시 설정](/mem/intune/remote-actions/device-passcode-reset) [다시 시작(Windows](/mem/intune/remote-actions/device-restart)   전용)
-  보안 Windows Defender 업데이트(Windows 전용)
-  Windows 10 PIN 재설정(Windows만 해당)
-  [사용자 지정 알림 보내기](/mem/intune/remote-actions/custom-notifications#send-a-custom-notification-to-a-single-device)   (Android, iOS, iPad OS)
-  [장치 동기화](/mem/intune/remote-actions/device-sync)

Intune 작업에 대한 자세한 내용은 [설명서에서 Microsoft Intune 참조하세요.](/mem/intune/)
