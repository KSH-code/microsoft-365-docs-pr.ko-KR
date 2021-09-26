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
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 기본 모바일 및 보안은 모바일 장치를 보호하고 관리하는 데 도움이 될 수 있습니다.
ms.openlocfilehash: e2a8661766aa5d5ae7f257cc7c76d67949d9cffe
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59773946"
---
# <a name="capabilities-of-basic-mobility-and-security"></a>기본 이동성 및 보안 기능

기본 모바일 및 보안을 사용하면 조직의 라이선스가 있는 사용자가 사용하는 iPhone, iPad, Androids 및 Windows 휴대폰과 같은 모바일 Microsoft 365 보호하고 관리할 수 있습니다. 지원되는 모바일 장치 및 앱에 대한 조직의 전자 메일 및 문서에 대한 액세스를 Microsoft 365 모바일 장치 관리 정책을 만들 수 있습니다. 장치를 분실하거나 도난 당한 경우 장치의 데이터를 원격으로 지워 중요한 조직 정보를 제거할 수 있습니다.

## <a name="supported-devices"></a>지원되는 장치

기본 Mobility and Security를 사용하여 다음 장치를 보호하고 관리할 수 있습니다.

- iOS 11.0 이상 버전

- Android 5.0 이상 버전<sup>3</sup>

- Windows 8.1<sup>1</sup>

- Windows 8.1 RT<sup>1</sup>

- Windows 10<sup>2</sup>

- Windows 10 Mobile<sup>2</sup>

<sup>1</sup> RT Windows 8.1 대한 액세스 제어는 Exchange ActiveSync.

<sup>2</sup> 액세스 제어를 Windows 10 제어하려면 Azure AD Premium 포함된 구독이 필요하며 디바이스를 앱에 가입해야 Azure Active Directory.

<sup>3</sup> 2020년 6월 이후의 Android 버전은 Samsung Knox 장치를 제외한 암호 설정을 관리할 수 없습니다.

> [!NOTE]
> 이전 OS 버전에 이미 등록된 장치는 예고 없이 기능이 변경될 수 있습니다.

조직의 사용자가 기본 모바일 및 보안에서 지원되지 않는 모바일 장치를 사용하는 경우 조직의 데이터를 보다 안전하게 Exchange ActiveSync 전자 메일에 Microsoft 365 앱 액세스를 차단할 수 있습니다. 모바일 기능을 차단하는 Exchange ActiveSync 기본 이동성 및 보안에서 장치 액세스 [설정 관리를 참조하세요.](manage-device-access-settings.md)

## <a name="access-control-for-microsoft-365-email-and-documents"></a>전자 메일 및 Microsoft 365 액세스 제어

다음 표에 있는 다양한 유형의 모바일 장치에 대해 지원되는 앱은 사용자가 기본 모바일 및 보안에 등록하라는 메시지를 표시하며, 여기서 사용자의 장치에 적용되는 새로운 모바일 장치 관리 정책이 있으며 사용자가 이전에 장치를 등록하지 않은 경우 사용자의 장치가 정책을 설정하는 방법에 따라 정책을 따르지 않는 경우 사용자가 이러한 앱의 Microsoft 365 리소스에 액세스하지 못하게 차단되거나 액세스 권한이 있지만 정책 위반을 보고하지 Microsoft 365 수 있습니다.

|**제품**|**iOS 10.0 이상**|**Android 5.0 이상**|
|:-----|:-----|:-----|
|**Exchange** Exchange ActiveSync 버전 14.1 이상을 사용하는 TouchDown과 같은 기본 제공 전자 메일 및 타사 Exchange ActiveSync 포함되어 있습니다. |메일 |전자 메일 |
|**Office**   및  **비즈니스용 OneDrive** |Outlook </br>OneDrive </br>Word </br>Excel </br>PowerPoint|**휴대폰 및 태블릿의 경우**:<br/>Outlook <br/> OneDrive <br/> Word <br/> Excel <br/> PowerPoint <br/> **휴대폰만 해당:** <br/> Office Mobile |

> [!NOTE]
>
> - iOS 10.0 이상 버전에 대한 지원에는 iPhone 및 iPad 포함됩니다.
> - BlackBerry OS 디바이스 관리는 기본 보안 및 모바일에서 지원되지 않습니다. BlackBerry의 BBCS(BlackBerry Business Cloud Services)를 사용하여 BlackBerry OS 장치를 관리합니다. Android OS를 실행하는 Blackberry 디바이스는 표준 Android 장치로 지원됩니다.
> - 사용자가 모바일 브라우저를 사용하여 Microsoft 365 SharePoint 사이트, Office Online의 문서 또는 전자 메일에 액세스하는 경우 사용자에게 등록하라는 메시지가 표시되거나 정책 위반에 대해 차단되거나 Outlook Web App.

다음 다이어그램은 새 장치를 사용하는 사용자가 기본 Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인할 때 발생하는 일과를 보여줍니다. 사용자가 디바이스를 등록할 때까지 Microsoft 365 리소스에 액세스하지 못하도록 차단됩니다.

:::image type="content" source="../../media/basic-mobility-security/bms-1-access-control.png" alt-text="기본 모바일 및 보안 액세스 제어.":::

> [!NOTE]
> 기본 모바일 및 보안 for Microsoft 365 Business Standard 정책 및 액세스 규칙은 Exchange ActiveSync 관리 센터에서 만든 모바일 장치 사서함 정책 및 장치 액세스 Exchange 다시 적용됩니다. 기본 모바일 및 보안에 장치를 등록한 Microsoft 365 Business Standard 장치에 Exchange ActiveSync 모바일 장치 사서함 정책 또는 장치 액세스 규칙은 무시됩니다. 자세한 내용은 Exchange ActiveSync 에서 Exchange ActiveSync [Exchange Online.](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync)

## <a name="policy-settings-for-mobile-devices"></a>모바일 장치에 대한 정책 설정

특정 설정이 켜져 있는 액세스를 차단하는 정책을 만들면 [Microsoft 365](capabilities.md)전자 메일 및 문서에 대한 액세스 제어에 나열된 지원되는 앱을 사용할 때 사용자가 Microsoft 365 리소스에 액세스할 수 없습니다.

사용자가 리소스에 액세스하지 Microsoft 365 수 있는 설정은 다음 섹션에 있습니다.

- 보안

- 암호화

- 암호 해독

- 관리되는 전자 메일 프로필

예를 들어 다음 다이어그램에는 등록된 장치를 사용하는 사용자가 장치에 적용되는 모바일 장치 관리 정책의 보안 설정을 준수하지 않는 경우 수행되는 작업을 보여 줍니다. 사용자는 Basic Mobility and Security를 사용하여 액세스 제어를 지원하는 앱에 로그인합니다. 디바이스가 보안 설정을 준수할 때까지 Microsoft 365 리소스에 액세스하지 못하게 차단됩니다.

:::image type="content" source="../../media/basic-mobility-security/bms-2-device-not-compliant.png" alt-text="기본 모바일 및 보안 준수 메시지입니다.":::

다음 섹션에는 조직 리소스에 연결하는 모바일 장치를 보호하고 관리하는 데 사용할 수 있는 정책 Microsoft 365 나열되어 있습니다.

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
|디바이스<sup>1에서</sup> 데이터 암호화 필요 |아니요|예|예|

<sup>1</sup> Samsung Knox를 사용하면 저장소 카드에 암호화를 요구할 수도 있습니다.

## <a name="jail-broken-setting"></a>암호 해독 설정

|**설정 이름**|**iOS 7.1 이상**|**Android 5 이상**|**Samsung Knox**|
|:-----|:-----|:-----|:-----|
|장치의 암호를 해독하거나 장치를 루트 경로로 지정할 수 없음 |예|예|예|

## <a name="managed-email-profile-option"></a>관리되는 전자 메일 프로필 옵션

다음 옵션은 사용자가 수동으로 만든 전자 메일 Microsoft 365 전자 메일에 액세스하지 못하게 차단할 수 있습니다. 전자 메일에 액세스하려면 iOS 장치의 사용자가 수동으로 만든 전자 메일 프로필을 삭제해야 합니다. 프로필을 삭제하면 디바이스에 새 프로필이 자동으로 만들어집니다. 최종 사용자가 규정을 준수하는 방법에 대한 지침은 기존 전자 메일 계정을 [찾은 을 참조하세요.](/intune-user-help/existing-company-email-account-found)

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

보안 및 준수 센터 PowerShell cmdlet을 사용하여 다음과 같은 추가 & 수 있습니다. 자세한 내용은 보안 및 [준수 & PowerShell을 참조하세요.](/powershell/exchange/scc-powershell)

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

## <a name="settings-supported-by-windows"></a>설정 지원되는 Windows

모바일 장치로 Windows 10 등록하여 디바이스를 관리할 수 있습니다. 적용 가능한 정책을 배포한 후 Windows 10 장치를 사용하는 사용자는 기본 제공 전자 메일 앱을 처음 사용하여 Microsoft 365 전자 메일에 액세스할 때 기본 이동성 및 보안에 등록해야 합니다(Azure AD Premium 구독 필요).

모바일 장치로 등록된 Windows 10 다음 설정이 지원됩니다. 이러한 설정은 사용자가 리소스에 액세스하는 Microsoft 365 않습니다.

### <a name="security-settings"></a>보안 설정

- 영숫자 암호 필요

- 최소 암호 길이

- 장치 데이터가 지워지기 전 로그인 오류 횟수

- 장치가 잠기기 전 비활성화 시간(분)

- 암호 만료(일)

- 암호 기록 저장 및 재사용 금지

> [!NOTE]
> 암호를 제어하는 다음 설정은 로컬 계정만 Windows 제어합니다. Windows 또는 도메인 가입을 통해 제공된 Azure Active Directory 이러한 설정의 영향을 받지 않습니다.

### <a name="system-settings"></a>시스템 설정

장치에서 진단 데이터 전송을 차단합니다.

### <a name="additional-settings"></a>추가 설정

PowerShell cmdlet을 사용하여 이러한 추가 정책 설정을 설정할 수 있습니다.

- AllowConvenienceLogon

- UserAccountControlStatus

- FirewallStatus

- AutoUpdateStatus

- AntiVirusStatus

- AntiVirusSignatureStatus

- SmartScreenEnabled

- WorkFoldersSyncUrl

## <a name="remotely-wipe-a-mobile-device"></a>원격으로 모바일 장치의 데이터 지우기

장치를 분실하거나 도난당한 경우 보안 및 준수 센터의 데이터 손실 방지 장치 관리에서 Microsoft 365 & 데이터 손실 방지 > 데이터 지우기를 수행하여 중요한 조직 데이터를 제거하고 Microsoft 365 조직 리소스에 대한 액세스를 방지할 수   >  있습니다. 선택적 지우기를 수행하여 조직 데이터만 제거하거나, 전체 지우기를 수행하여 장치에서 모든 정보를 삭제하고 장치를 처음 출시될 때의 설정으로 복원합니다.

자세한 내용은 Basic Mobility and Security에서 모바일 장치 [지우기를 참조하세요.](wipe-mobile-device.md)

## <a name="related-content"></a>관련 콘텐츠

[Overview of Basic Mobility and Security for Microsoft 365](overview.md) (article)\
[기본 모바일 및 보안에서](create-device-security-policies.md) 장치 보안 정책 만들기(문서)