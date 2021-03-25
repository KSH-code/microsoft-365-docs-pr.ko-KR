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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Office 365 E3에서 Microsoft 365 Business Premium으로 비즈니스를 이동하는 방법을 학습합니다.
ms.openlocfilehash: cb70260201686cae02428c715ac98ffe2f88787f
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198100"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>Office 365 E3에서 Microsoft 365 Business Premium으로 마이그레이션

Microsoft 365 Business Premium에는 동급 최고의 클라우드 기반 생산성 앱을 간단한 장치 관리 및 보안과 결합하여 중소기업에 필요한 모든 것이 있습니다. 현재 Office 365 E3 구독이 있지만 직원이 300명을 넘지 않는 경우 추가 보안 기능을 위해 Microsoft 365 Business Premium으로 전환하는 것이 있습니다.

마이그레이션은 간단합니다. 먼저 라이선스를 전환하면 현재 구독의 모든 데이터 및 사용자 정보가 유지 관리됩니다. 마이그레이션 후 Microsoft 365 Business Premium에 추가된 기능을 설정해야 합니다.

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Office 365 E3와 Microsoft 365 Business Premium의 차이점

이 표에서는 Microsoft 365 Business Premium과 Office 365 E3의 차이점을 보여줍니다.

| 기능    | Microsoft 365 Business Premium의 지원    | Office 365 E3의 지원 | 
|:-------|:-----|:-----|
| **On-premises**        | | | 
| Office 앱<sup>1</sup>    | 비즈니스용 Microsoft 365 앱    | 엔터프라이즈용 Microsoft 365 앱 | 
| **클라우드 생산성 앱**        | | | 
| Exchange Online 및 Outlook    | 사서함당 50GB 저장소 제한 및 제한 없는 Exchange Online Archiving    | 사서함당 100GB 저장소 제한 및 제한 없는 Exchange Online Archiving | 
| Teams    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png) | 
| 비즈니스용 OneDrive    | 사용자당 1 TB 저장소 제한    | 무제한 | 
| Yammer, SharePoint Online, Planner, Stream    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png) | 
| StaffHub    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png) | 
| Outlook Customer Manager    | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | | 
| **위협 방지**        | | | 
| Office 365용 Defender 플랜 1 | ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | 포함되지 않지만 에 추가할 수 있습니다. | 
| **ID 관리**        | | | 
| 하이브리드 Azure AD(Azure Active Directory) 계정, Azure AD MFA(다단계 인증), 조건부 액세스,온-프레미스 ID에 대한 암호 쓰기 저장에 대한 셀프 서비스 암호 재설정|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    |  | 
| **장치 및 앱 관리**        | | |
| Microsoft Intune, Windows AutoPilot|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    |  |
| 공유 컴퓨터 활성화|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    | ![Office 365 E3에 포함](../media/check-mark.png)| 
| Win 7/8.1 Pro 라이선스에서 Windows 10 Pro로 업그레이드 권한|     ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)    || 
| **정보 보호**        | | |
|Office 365 데이터 손실 방지|    ![Microsoft 365 Business Premium에 포함](../media/check-mark.png)|![Office 365 E3에 포함](../media/check-mark.png)|
|Azure Information Protection 계획 1, Bitlocker 적용|![Microsoft 365 Business Premium에 포함](../media/check-mark.png)||
|Azure Information Protection 계획 1, 민감도 레이블|![Microsoft 365 Business Premium에 포함](../media/check-mark.png)||
|**CAL(클라이언트 액세스 라이선스)**|||
|Enterprise CAL Suite(Exchange, SharePoint, Skype)||![Office 365 E3에 포함](../media/check-mark.png)|

<sup>1</sup> Office 앱의 Microsoft 365 Business Premium 버전은 그룹 정책, 앱 원격 분석, 업데이트 컨트롤, 스프레드시트 비교 및 문의 또는 비즈니스 인텔리전스를 통한 볼륨 정품 인증을 포함하지 않습니다.

## <a name="migration"></a>마이그레이션

구독을 마이그레이션하려면 일부 [](../commerce/subscriptions/change-plans-manually.md) 사용자만 Microsoft 365 Business Premium으로 이동하려는 경우 요금제 수동 변경을 참조하세요. 모든 사람을 [자동으로](../commerce/subscriptions/upgrade-to-different-plan.md)업그레이드하거나 파트너와 협력하여 E3 구독 및 라이선스를 Microsoft 365 Business Premium 구독으로 이동할 수도 있습니다.
다음 섹션에서는 필요한 변경 내용(있는 경우)과 마이그레이션 후 할 수 있는 작업을 설명합니다.

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 구독 구성 및 데이터
마이그레이션하기 전에 다음을 포함하는 현재 구독 또는 데이터를 변경할 필요가 없습니다.

- DNS 레코드 및 도메인 이름과 같은 구독 구성
- 사용자 및 그룹 계정 및 인증 설정(예: 다단계 인증 또는 조건부 액세스 정책)
- 생산성 서비스 구성 및 해당 데이터(예: Teams, Exchange Online 사서함, SharePoint Online 사이트, 비즈니스용 OneDrive 폴더 및 OneNote 전자 필기장)
- Office 응용 프로그램은 자동으로 확장됩니다. Office 365 최신 라이선스는 72시간마다 사용자의 라이선스 할당을 확인하고 Office 응용 프로그램을 사용자 구독과 일치하는 버전으로 변환합니다.

### <a name="windows-10"></a>Windows 10

Windows가 Windows Pro 크리에이터 업데이트에 아직 없는 경우 Windows Pro 크리에이터스 업데이트로 [업그레이드합니다.](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>사용자 장치 및 파일을 보호하기 위한 정책 설정

> [!NOTE]
> Office 365 MDM 정책 및 장치를 설정하면 해당 장치가  Microsoft 365 관리 센터의 장치 페이지에 나열됩니다. 설정한 모든 정책은 [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)포털의 클래식 정책 목록에 표시됩니다.

Microsoft 365 Business Premium에 라이선스를 할당한 후 사용자의 장치 및 파일 보호를 시작할 수 있습니다.

조직의 모든 사람을 Microsoft 365 Business Premium으로 업그레이드한 경우 홈 페이지에 설정 마법사가 표시될 수 있으며 설정 마법사 단계에 따라 [파일](set-up.md) 및 모바일 장치를 보호할 수 있습니다.

장치 페이지에서 다음 단계를 완료할 수 있습니다.
  
1. 관리 센터의 왼쪽 네비게이트에서 장치 **정책으로** \> **이동하세요.**
    
2. 장치 **정책 페이지에서** 추가를 **선택합니다.**
    
3. 정책 **추가 창에서** 정책에 이름을 지정한 다음  드롭다운에서 정책 유형을 선택 합니다. 
    
     Windows 10뿐만 아니라 Android 및 iPhone 장치에서 파일을 보호하기 위한 응용 프로그램 정책을 설정할 수 있으며 회사 소유의 Windows 10 장치에 대한 장치 구성 정책을 설정할 수 있습니다. 자세한 내용은 다음 링크를 참조하세요.
    
  - [Android 또는 iOS 장치에서 앱 보호 설정 설정하기](app-protection-settings-for-android-and-ios.md)
    
  - [Windows 10 장치에서 응용 프로그램 보호 설정 설정하기](protection-settings-for-windows-10-devices.md)
    
  - [Windows 10 PC에 대한 장치 보호 설정 설정](protection-settings-for-windows-10-pcs.md)
  
4. 정책을 설정하면 사용자와 직원이 장치를 설정할 수 있습니다.
    
  - Windows 장치에 대한 단계는 [Microsoft 365 Business Premium](set-up-windows-devices.md) 사용자를 위한 Windows 장치 설치를 참조하세요. 
    
  - Android 휴대폰 및 iPhone에 대한 단계는 [Microsoft 365 Business Premium](set-up-mobile-devices.md) 사용자를 위한 모바일 장치 설치를 참조하세요. 
  
### <a name="mailbox-size"></a>사서함 크기

Microsoft 365 Business Premium의 저장소 제한은 50GB로, Exchange Online 계획 1을 사용하게 됩니다. Microsoft 365 Business Premium으로 마이그레이션하는 동안 사용자가 50GB의 사서함 저장소를 초과하는 경우 이 사용자에게 Exchange Online 계획 2를 할당하고 Exchange Online 계획 1을 제거하는 것이 좋습니다.


### <a name="threat-protection"></a>위협 방지

Microsoft 365 Business Premium으로 마이그레이션한 후 Office 365용 Defender가 있습니다. 개요는 [Microsoft Defender for Office 365를](../security/office-365-security/defender-for-office-365.md) 참조하세요. 설정하는 내용은 [안전한](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)링크 [설정,](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)안전한 첨부 파일 설정 및 [Office 365용 Defender에서](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)피싱 방지 설정 을 참조하세요.

### <a name="sensitivity-labels"></a>민감도 레이블

민감도 레이블 사용을 시작하기 위해 민감도 레이블 개요를 [참조하고](../compliance/sensitivity-labels.md) 민감도 레이블 비디오를 만들고 [관리하세요.](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)
