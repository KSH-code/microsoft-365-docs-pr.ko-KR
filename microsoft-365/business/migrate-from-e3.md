---
title: Office 365 E3에서 Microsoft 365 Business로 마이그레이션
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
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Office 365 E3에서 Microsoft 365 Business로 비즈니스를 이동 하는 방법을 알아봅니다.
ms.openlocfilehash: 54320ed60825a28147542094b19761889a70ae9f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065582"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a>Office 365 E3에서 Microsoft 365 Business로 마이그레이션 

Microsoft 365 Business는 최고급 클라우드 기반 생산성 앱과 간단한 장치 관리 및 보안을 결합 하는 소규모 기업에 필요한 모든 것을 포함 합니다. 현재 Office 365 E3 구독을 보유 하 고 있지만 300 명 이상의 직원은 없는 경우 보안 기능을 추가 하기 위해 Microsoft 365 Business로 전환 하는 것이 좋습니다.

마이그레이션을 쉽게 수행할 수 있습니다. 먼저 라이선스를 전환 하면 현재 구독의 모든 데이터 및 사용자 정보가 유지 됩니다. 마이그레이션 후 Microsoft 365 Business에 추가 된 기능을 설정 해야 합니다.

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a>Office 365 E3 및 Microsoft 365 Business의 차이점

이 표에서는 Microsoft 365 Business 및 Office 365 E3의 차이점을 보여 줍니다.

| 기능   | Microsoft 365 Business의 지원 | Office 365 E3의 지원 | 
|:-------|:-----|:-----|
| **온-프레미스**       | | | 
| Office 앱<sup>1</sup>   | Office 365 Business   | Office 365 ProPlus | 
| **클라우드 생산성 앱**       | | | 
| Exchange Online 및 Outlook   | 사서함 당 50 GB 저장소 제한 및 무제한 Exchange 온라인 보관   | 사서함 당 100 GB 저장소 제한 및 무제한 Exchange 온라인 보관 | 
| Teams | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | ![Office 365 E3에 포함](../media/check-mark.png) | 
| 비즈니스용 OneDrive | 사용자 당 1TB 저장소 제한   | 무제한 | 
| Yammer, SharePoint Online, Planner, 스트림    | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | ![Office 365 E3에 포함](../media/check-mark.png) | 
| StaffHub  | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | ![Office 365 E3에 포함](../media/check-mark.png) | 
| Outlook 고객 관리자, MileIQ  | ![Microsoft 365 Business에 포함](../media/check-mark.png)  | | 
| **위협 방지**     | | | 
| Office 365 ATP (Advanced Threat Protection) 계획 1 | ![Microsoft 365 Business에 포함](../media/check-mark.png) | 포함 되지 않지만 추가할 수 있음 | 
| **Id 관리**       | | | 
| 하이브리드 Azure Active Directory에 대 한 셀프 서비스 암호 재설정 (Azure AD) 계정, Azure MFA (다단계 인증), 조건부 액세스, 온-프레미스 id에 대 한 암호 쓰기 저장|    ![Microsoft 365 Business에 포함](../media/check-mark.png)    |  | 
| **장치 및 앱 관리**     | | |
| Microsoft Intune, Windows AutoPilot|  ![Microsoft 365 Business에 포함](../media/check-mark.png)    |  |
| 공유 컴퓨터 활성화|   ![Microsoft 365 Business에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png)| 
| Win 7/8.1 Pro 라이선스에서 Windows 10 Pro로의 업그레이드 권한|     ![Microsoft 365 Business에 포함](../media/check-mark.png)    || 
| **정보 보호**        | | |
|Office 365 데이터 손실 방지|   ![Microsoft 365 Business에 포함](../media/check-mark.png)|![Office 365 E3에 포함](../media/check-mark.png)|
|Azure Information Protection 계획 1, Bitlocker 적용|![Microsoft 365 Business에 포함](../media/check-mark.png)||
|Azure Information Protection 계획 1, 민감도 레이블|![Microsoft 365 Business에 포함](../media/check-mark.png)||
|**클라이언트 액세스 라이선스 (CAL 권한)**|||
|Enterprise CAL Suite (Exchange, SharePoint, Skype)||![Office 365 E3에 포함](../media/check-mark.png)|

<sup>1</sup> Office 앱의 Microsoft 365 Business 버전에는 그룹 정책, 앱 원격 분석, 업데이트 컨트롤, 스프레드시트 비교 및 조회, 비즈니스 인텔리전스를 통한 볼륨 정품 인증이 포함 되지 않습니다.

## <a name="migration"></a>마이그레이션

구독을 마이그레이션하려면 소수의 사용자만 Microsoft 365 Business로 이동 하려는 경우 지침을 위해 [다른 요금제로 전환을](https://docs.microsoft.com/office365/admin/misc/switch-plans-manually) 참조 하세요. [모든 사용자를 자동으로 업그레이드](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/upgrade-to-different-plan)하거나 파트너와 함께 작업 하 여 E3 구독 및 라이선스를 Microsoft 365 비즈니스 구독으로 이동할 수도 있습니다.
다음 섹션에서는 마이그레이션 후 수행 해야 하는 작업 및 변경 내용에 대해 설명 합니다.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 구독 구성 및 데이터
다음을 포함 하 여 마이그레이션하기 전에 현재 구독 또는 데이터를 변경할 필요가 없습니다.

- 구독 구성 (예: DNS 레코드 및 도메인 이름)
- 사용자 및 그룹 계정 및 인증 설정 (예: 다단계 인증 또는 조건부 액세스 정책)
- 팀, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더, OneNote 전자 필기장 등의 생산성 서비스 구성 및 데이터

### <a name="windows-10"></a>Windows 10

Windows Pro Creator update가 아직 없는 경우 windows [Pro 크리에이터 업데이트로 업그레이드](upgrade-to-windows-pro-creators-update.md)합니다.

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>사용자 장치 및 파일을 보호 하기 위한 정책 설정

> [!NOTE]
> Office 365 MDM 정책 및 장치를 설정 하는 경우 해당 장치가 Microsoft 365 관리 센터의 **장치** 페이지에 나열 됩니다. 설정 하는 모든 정책은 [Intune 포털](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)의 클래식 정책 목록에 표시 됩니다.

Microsoft 365 Business에 대 한 라이선스를 할당 한 후에는 사용자의 장치 및 파일을 보호 하기 시작할 수 있습니다.

조직의 모든 사용자를 Microsoft 365 Business로 업그레이드 한 경우 홈 페이지에 설치 마법사가 표시 되 고 [설치 마법사의 Microsoft 365 Business 설정 단계에](set-up.md) 따라 파일 및 모바일 장치를 보호할 수 있습니다.

장치 페이지에서 다음 단계를 완료할 수도 있습니다.
  
1. 관리 센터의 왼쪽 탐색 창에서 **장치** \> **정책**으로 이동 합니다.
    
2. **장치 정책** 페이지에서 **추가**를 선택 합니다.
    
3. 정책 **추가** 창에서 정책에 이름을 지정 하 고 드롭다운에서 **정책 유형을** 선택 합니다. 
    
     Windows 10과 함께 Android 및 iPhone 장치에서 파일을 보호 하기 위한 응용 프로그램 정책을 설정 하 고 Windows 10 장치를 소유한 회사에 대 한 장치 구성 정책을 설정할 수 있습니다. 자세한 내용은 다음 링크를 참조 하십시오.
    
  - [Android 또는 iOS 장치에서 앱 보호 설정 설정하기](app-protection-settings-for-android-and-ios.md)
    
  - [Windows 10 장치에서 응용 프로그램 보호 설정 설정하기](protection-settings-for-windows-10-devices.md)
    
  - [Windows 10 Pc에 대 한 장치 보호 설정 설정](protection-settings-for-windows-10-pcs.md)
  
4. 정책을 설정 하면 사용자와 직원이 장치를 설정할 수 있습니다.
    
  - Windows 장치에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위해 windows 장치 설정을](set-up-windows-devices.md) 참조 하세요. 
    
  - Android 휴대폰 및 Iphone에 대 한 단계는 [Microsoft 365 비즈니스 사용자를 위한 모바일 장치 설정을](set-up-mobile-devices.md) 참조 하세요. 

### <a name="threat-protection"></a>위협 방지

Microsoft 365 Business로 마이그레이션한 후 Office 365 ATP가 있습니다. 개요는 [Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 를 참조 하세요. 설정 하려면 [atp 안전한 링크 설정](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa), [atp 안전한 첨부 파일 설정](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)및 [atp 피싱 방지 설정을](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)참조 하세요.

### <a name="sensitivity-labels"></a>민감도 레이블

민감도 레이블 사용을 시작 하려면 [민감도 레이블 개요](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) 및 [create and manage 민감도 레이블](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9) 비디오를 참조 하세요.
