---
title: 기본 이동성 및 보안 기능
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
description: 기본 이동성 및 보안은 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다.
ms.openlocfilehash: aed4f4c2d252e487d24496ac00f3de24bc57ab55
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545899"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>기본 이동성 및 보안 기능

기본 이동성 및 보안은 조직의 라이선스를 받은 Microsoft 365 사용자가 사용 하는 Iphone, Ipad, Androids 및 Windows phone과 같은 모바일 장치를 보호 하 고 관리 하는 데 도움이 됩니다. 지원 되는 모바일 장치 및 앱에 대 한 조직의 Microsoft 365 전자 메일 및 문서에 대 한 액세스를 제어 하는 데 도움이 되는 설정을 사용 하 여 모바일 장치 관리 정책을 만들 수 있습니다. 장치를 분실하거나 도난 당한 경우 장치의 데이터를 원격으로 지워 중요한 조직 정보를 제거할 수 있습니다.

## <a name="supported-devices"></a>지원되는 장치

기본 이동성 및 보안을 사용 하 여 다음 장치를 보호 하 고 관리할 수 있습니다.

- iOS 11.0 이상 버전
    
- Android 5.0 이상 버전<sup>3</sup>
    
- Windows 8.1<sup>1</sup>
    
- Windows 8.1 RT<sup>1</sup>
    
- Windows 10<sup>2</sup>
    
- Windows 10 모바일<sup>2</sup>   

<sup>1</sup> Windows 8.1 RT 장치에 대 한 액세스 제어는 Exchange ActiveSync로 제한 됩니다.

<sup>2</sup> Windows 8.1 RT 장치에 대 한 액세스 제어는 Exchange ActiveSync로 제한 됩니다.
Windows 10에 대 한 액세스 제어를 사용 하려면 Azure AD Premium이 포함 된 구독 및 장치를 Azure Active Directory에 가입 해야 합니다.

<sup>3</sup> Windows 8.1 RT 장치에 대 한 액세스 제어는 Exchange ActiveSync로 제한 됩니다.
6 월 2020 이후 Android 버전 9 이상이 Samsung Knox 장치를 제외 하 고 암호 설정을 관리할 수 없습니다.

>[!NOTE]
>이전 버전 OS에서 이미 등록 된 장치는 기능이 통지 없이 변경 될 수 있지만 계속 해 서 작동 합니다.

조직의 사용자가 기본 Mobility and Security에서 지원 하지 않는 모바일 장치를 사용 하는 경우에는 Exchange ActiveSync 앱에 해당 장치에 대 한 Microsoft 365 전자 메일 액세스를 차단 하 여 조직의 데이터를 보다 안전 하 게 유지할 수 있습니다. Exchange ActiveSync를 차단 하는 단계는 [기본 이동성 및 보안에서 장치 액세스 설정 관리](manage-device-access-settings.md)를 참조 하십시오.

## <a name="access-control-for-microsoft-365-email-and-documents"></a>Microsoft 365 전자 메일 및 문서에 대 한 액세스 제어

다음 표에 나와 있는 여러 유형의 모바일 장치에 대해 지원 되는 앱은 사용자의 장치에 적용 되는 새 모바일 장치 관리 정책이 있고 사용자가 이전에 장치를 등록 하지 않은 경우에 사용자가 기본 이동성 및 보안에 등록 하 라는 메시지를 표시 합니다. 사용자의 장치가 정책을 준수 하지 않는 경우 정책을 설정 하는 방법에 따라 사용자가 이러한 앱에서 Microsoft 365 리소스에 액세스 하지 못하도록 차단 되거나, Microsoft 365에서 정책 위반을 보고할 수 있습니다.

|**제품**|**iOS 10.0 이상**|**Android 5.0 이상**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync에는 Exchange ActiveSync 버전 14.1 이상을 사용 하는 기본 제공 전자 메일 및 타사 앱 (예 TouchDown)이 포함 되어 있습니다. |메일로 |전자 메일 |
|**Office**   및 **비즈니스용 OneDrive** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**휴대폰 및 태블릿**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **휴대폰만 해당:** <br/> Office Mobile |

>[!NOTE]
- >IOS 10.0 이상 버전에 대 한 지원에는 iPhone 및 iPad 장치가 포함 됩니다.
- >BlackBerry OS 장치 관리는 Microsoft 365 용 모바일 장치 관리에서 지원 되지 않습니다. Blackberry의 BBCS (BlackBerry Business Cloud Services)를 사용 하 여 BlackBerry OS 장치를 관리 합니다. Android OS를 실행 하는 Blackberry 장치는 표준 Android 장치로 지원 됨
- >사용자가 모바일 브라우저를 사용 하 여 Microsoft 365 SharePoint 사이트, Office Online의 문서 또는 Outlook Web App에서 전자 메일에 액세스 하는 경우 등록 하 라는 메시지가 표시 되지 않으며 차단 되거나 정책 위반으로 보고 되지 않습니다.
    
다음 다이어그램에서는 새 장치가 있는 사용자가 기본 이동성 및 보안을 사용 하 여 액세스 제어를 지 원하는 앱에 로그인 할 때 수행 되는 작업을 보여 줍니다. 사용자가 자신의 장치를 등록할 때까지 앱의 Microsoft 365 리소스에 액세스할 수 없게 됩니다.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="기본 모바일 및 보안 액세스 제어":::

참고: Microsoft 365 비즈니스 Standard 용 MDM에서 만든 정책 및 액세스 규칙은 exchange 관리 센터에서 만든 Exchange ActiveSync 모바일 장치 사서함 정책 및 장치 액세스 규칙을 재정의 합니다. 장치를 Microsoft 365 Business Standard 용 MDM에 등록 한 후에는 장치에 적용 된 모든 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙이 무시 됩니다. Exchange ActiveSync에 대 한 자세한 정보는 exchange [activesync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380)를 참조 하십시오.

## <a name="policy-settings-for-mobile-devices"></a>모바일 장치에 대한 정책 설정

특정 설정을 사용 하 여 액세스를 차단 하는 정책을 만드는 경우 [microsoft 365 전자 메일 및 문서에 대 한 액세스 제어](capabilities.md)에 나열 된 지원 되는 앱을 사용 하면 사용자가 microsoft 365 리소스에 액세스할 수 없게 됩니다. 

사용자가 Microsoft 365 리소스에 액세스 하지 못하도록 차단 하는 설정은 다음 섹션에 나와 있습니다.

- 보안
    
- 암호화
    
- 암호 해독
    
- 관리되는 전자 메일 프로필  

예를 들어 다음 다이어그램에는 등록된 장치를 사용하는 사용자가 장치에 적용되는 모바일 장치 관리 정책의 보안 설정을 준수하지 않는 경우 수행되는 작업을 보여 줍니다. 사용자가 기본 이동성 및 보안을 사용 하 여 액세스 제어를 지 원하는 앱에 로그인 합니다. 장치가 보안 설정을 준수 하기 전 까지는 앱의 Microsoft 365 리소스에 액세스할 수 없습니다.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="기본 모바일 및 보안 준수 메시지":::

다음 섹션에는 Microsoft 365 조직 리소스에 연결 하는 모바일 장치를 보호 하 고 관리 하는 데 사용할 수 있는 정책 설정이 나와 있습니다.

## <a name="security-settings"></a>보안 설정

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|암호 필요|예|예|예|
|단순한 암호 금지|예|아니요|아니요|
|영숫자 암호 필요|예|아니요|아니요|
|최소 암호 길이 |예|예|예|
|장치 데이터를 지우기 전 로그인 실패 횟수 |예|예|예|
|장치가 잠기기 전 비활성화 시간(분) |예|예|예|
|암호 만료(일) |예|예|예|
|암호 기록 기억 및 재사용 금지 |예|예|예|

## <a name="encryption-settings"></a>암호화 설정 

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|장치<sup>1</sup> 에서 데이터 암호화 필요 |아니요|예|예|

<sup>1</sup> Samsung Knox에서는 저장소 카드에서 암호화를 요구할 수도 있습니다. 

## <a name="jail-broken-setting"></a>암호 해독 설정 

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|장치의 암호를 해독하거나 장치를 루트 경로로 지정할 수 없음 |예|예|예|

## <a name="managed-email-profile-option"></a>관리되는 전자 메일 프로필 옵션 

다음 옵션은 사용자가 수동으로 만든 전자 메일 프로필을 사용 하는 경우 Microsoft 365 전자 메일에 액세스 하지 못하도록 차단할 수 있습니다. 전자 메일에 액세스하려면 iOS 장치의 사용자가 수동으로 만든 전자 메일 프로필을 삭제해야 합니다. 프로필을 삭제 하면 장치에 새 프로필이 자동으로 만들어집니다. 최종 사용자가 준수 하는 방법에 대 한 자세한 내용은 [기존 전자 메일 계정을](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found)참조 하십시오.

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|전자 메일 프로필이 관리됨 |예|아니요|아니요|

## <a name="cloud-settings"></a>클라우드 설정 

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|암호화된 백업 필요 |예|아니요|아니요|
|클라우드 백업 차단 |예|아니요|아니요|
|문서 동기화 차단 |예|아니요|아니요|
|사진 동기화 차단  |예|아니요|아니요|
|Google 백업 허용  |해당 없음|아니요|예|
|Google 계정 자동 동기화 허용  |해당 없음|아니요|예|

## <a name="system-settings"></a>시스템 설정 

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|화면 캡처 차단 |예|아니요|예|
|장치에서 진단 데이터 전송 차단 |예|아니요|예|

## <a name="application-settings"></a>응용 프로그램 설정 

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|장치에서 비디오 회의 차단 |예|아니요|아니요|
|응용 프로그램 저장소에 대한 액세스 차단 |예|아니요|예|
|응용 프로그램 저장소에 액세스할 때 암호 필요 |아니요|예|예|

## <a name="device-capabilities-settings"></a>장치 기능 설정 

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|이동식 저장소와 연결 차단 |예|예|아니요|
|Bluetooth 연결 차단 |예|예|아니요|

## <a name="additional-settings"></a>추가 설정

보안 & 준수 센터 PowerShell cmdlet을 사용 하 여 다음과 같은 추가 정책 설정을 지정할 수 있습니다. 자세한 내용은 [Security & 준수 센터 PowerShell](https://docs.microsoft.com/powershell/exchange/scc-powershell)를 참조 하세요.

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|
|:-----|:-----|:-----|
|CameraEnabled|예|예|
|RegionRatings|예|아니요|
|MoviesRatings|예|아니요|
|TVShowsRating |예|아니요|
|AppsRatings |예|아니요|
|AllowVoiceDialing |예|아니요|
|AllowVoiceAssistant |예|아니요|
|AllowAssistantWhileLocked  |예|아니요|
|AllowPassbookWhileLocked |예|아니요|
|MaxPasswordGracePeriod |예|아니요|
|PasswordQuality |아니요|예|
|SystemSecurityTLS  |예|아니요|
|WLANEnabled  |아니요|아니요|

## <a name="settings-supported-by-windows"></a>Windows에서 지원 되는 설정 

Windows 10 장치는 모바일 장치로 등록 하 여 관리할 수 있습니다. 적용 가능한 정책이 배포 되 면 Windows 10 장치를 사용 하는 사용자는 기본 제공 전자 메일 앱을 처음 사용할 때 Microsoft 365 전자 메일에 액세스 하기 위해 기본 이동성 및 보안을 등록 해야 합니다 (Azure AD premium 구독이 필요 함).

다음 설정은 모바일 장치로 등록 된 Windows 10 장치에 대해 지원 됩니다. 이러한 설정은 사용자가 Microsoft 365 리소스에 액세스 하지 못하도록 차단 하지 않습니다.

### <a name="security-settings"></a>보안 설정

- 영숫자 암호 필요

- 최소 암호 길이
    
- 장치 데이터가 지워지기 전 로그인 오류 횟수
    
- 장치가 잠기기 전 비활성화 시간(분)
    
- 암호 만료(일)
    
- 암호 기록 저장 및 재사용 금지   

>[!NOTE]
>다음 설정은 암호를 규정 하는 로컬 Windows 계정만 제어 합니다. Join 도메인 또는 Azure Active Directory를 통해 제공 되는 Windows 계정은 이러한 설정의 영향을 받지 않습니다.

### <a name="system-settings"></a>시스템 설정

장치에서 진단 데이터 보내기를 차단 합니다.

### <a name="additional-settings"></a>추가 설정

PowerShell cmdlet을 사용 하 여 다음과 같은 추가 정책 설정을 지정할 수 있습니다.

- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus   

- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    

## <a name="remotely-wipe-a-mobile-device"></a>원격으로 모바일 장치의 데이터 지우기

장치를 분실 하거나 도난당 한 경우 중요 한 조직 데이터를 제거 하 고 **데이터 손실 방지**  >  **장치 관리**> 보안 & 준수 센터에서 초기화를 수행 하 여 Microsoft 365 조직 리소스에 대 한 액세스를 방지할 수 있습니다. 선택적 지우기를 수행하여 조직 데이터만 제거하거나, 전체 지우기를 수행하여 장치에서 모든 정보를 삭제하고 장치를 처음 출시될 때의 설정으로 복원합니다.

자세한 내용은 [기본 Mobility And Security에서 모바일 장치 초기화](wipe-mobile-device.md)를 참조 하세요.

## <a name="related-topics"></a>관련 항목

[Microsoft 365의 기본 모바일 및 보안 개요](overview.md)

[기본 모바일 및 보안에서 장치 보안 정책 만들기](create-device-security-policies.md)