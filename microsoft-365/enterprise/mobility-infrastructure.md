---
title: 5번째 작업 단계 - 모바일 장치 관리
description: Microsoft 365 Enterprise는 Microsoft Intune을 사용 하는 모바일 장치 관리를 포함 합니다. 요구 사항 및 필수 구성 요소를 검토 하 고, Azure Active Directory 리소스를 사용 하 여 Intune을 설정 하 고, iOS, macOS, Android 및 Windows 장치를 등록 하 고, 앱을 배포 하 고, 프로필 구성 및 준수 정책을 사용 하 고, Microsoft 365 Enterprise를 통해 모바일 장치 관리에 조건부 액세스를 사용 하도록 설정
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 설명서, 모바일 장치 관리, Intune
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/03/2019
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
ms.openlocfilehash: a957ef037aed1f9aba923af428c2a440790dbfba
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153895"
---
# <a name="phase-5-mobile-device-management-for-microsoft-365-enterprise"></a>단계 5: Microsoft 365 엔터프라이즈에 대 한 모바일 장치 관리

![5단계: 모바일 디바이스 관리](../media/deploy-foundation-infrastructure/mobiledevicemgmt_icon.png)

*이 기능은 Microsoft 365 Enterprise E3 및 E5 버전에 적용 됩니다.*

Microsoft 365 Enterprise에는 조직 내에서 장치 및 해당 앱을 관리 하는 데 도움이 되는 기능이 포함 되어 있습니다. Microsoft Intune을 사용 하 여 iOS, Android, macOS 및 Windows 장치를 관리 하 여 데이터를 비롯 한 조직의 리소스에 대 한 액세스를 보호할 수 있습니다. 

이 단계에서는 Intune에서 장치를 등록 하 고 정책을 만들고 적용 하 여 데이터를 안전 하 고 보호 하는 데 도움이 됩니다. Intune 설명서의 전체 라이브러리는 [온라인에서 확인할 수 있습니다](https://docs.microsoft.com/intune). 시작 하기 전에 [Intune 배포 계획, 디자인 및 구현 가이드](https://docs.microsoft.com/intune/planning-guide) 를 검토 하는 것도 좋은 방법입니다.

## <a name="step-1-plan-for-your-scenario"></a>1 단계: 시나리오 계획

모바일 장치를 관리 하는 주요 이유 중 하나는 조직의 리소스를 보호 하 고 보호 하는 것입니다. [Microsoft Intune을 사용 하는 일반적인 방법은](https://docs.microsoft.com/intune/common-scenarios) Office 365 전자 메일 및 데이터 보호를 비롯 한 실제 세계의 몇 가지 예를 나열 하는 것입니다.

Intune에서는 MDM (모바일 장치 관리) 또는 MAM (모바일 응용 프로그램 관리)를 사용 하 여 조직에 대 한 액세스를 관리할 수 있는 옵션을 제공 합니다. MDM은 사용자가 Intune에서 장치를 "등록" 하는 경우입니다. 등록 된 사용자는 관리 되는 장치 이며 조직에서 사용 하는 모든 정책, 규칙 및 설정을 받을 수 있습니다. 예를 들어 특성 앱을 설치 하 고 암호 정책을 만들고 VPN 연결을 설치 하는 등의 다양 한 방법을 사용할 수 있습니다.

개인 장치를 사용 하는 사용자는 장치를 등록 하거나 Intune 및 정책으로 관리 하지 않을 수 있습니다. 하지만 여전히 조직의 리소스 및 데이터를 보호 해야 합니다. 이 시나리오에서는 MAM을 사용 하 여 앱을 보호할 수 있습니다. 예를 들어 장치에서 SharePoint에 액세스할 때 사용자가 PIN을 입력 해야 하는 MAM 정책을 사용할 수 있습니다.

또한 개인 또는 조직 소유 장치를 관리 하는 방법을 결정 합니다. 사용 방식에 따라 장치를 다르게 처리할 수도 있습니다. 예를 들어 HR (인사) 또는 판매 사용자의 사용자에 대 한 다른 요금제를 사용할 수 있습니다. [모바일 장치 관리 사용 방법 식별-사례 시나리오](https://docs.microsoft.com/intune/planning-guide-scenarios) 를 시작 하 고, 이러한 시나리오에 대 한 몇 가지 지침을 포함할 수 있습니다.

## <a name="step-2-get-your-prerequisites"></a>2 단계: 필수 구성 요소 가져오기

다음으로, 이전 단계에서 만든 시나리오 및 요구 사항에 따라 필수 구성 요소를 가져옵니다. [계획 구현](https://docs.microsoft.com/intune/planning-guide-onboarding) 모든 요구 사항을 나열 합니다. 다음은 Intune을 사용 하 여 Microsoft 365을 수행 하는 데 필요한 중요 한 항목입니다.

- **Intune 구독**: microsoft 365에 포함 되어 있으며 [Azure 포털](https://portal.azure.com) 의 microsoft Intune에 대 한 액세스를 제공 합니다.
- **Office 365 구독**: Microsoft 365에 포함 되어 있으며 전자 메일을 비롯 한 office 앱에 사용 됩니다.
- **Azure Active Directory (AZURE AD) premium**: Microsoft 365에 포함 되어 있으며, 사용자 또는 보안 그룹을 만드는 데 사용 됩니다. 이러한 그룹은 사용자가 만든 Intune 정책 (예: 암호 길이를 강제 하 여 장치 잠금 해제)을 수신 합니다. [2 단계: id](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) 를 사용할 수 있습니다.

조직의 요구 사항에 따라 몇 가지 추가 요구 사항이 있을 수 있습니다. 예를 들어 iOS 장치를 관리 하려는 경우 Apple MDM 푸시 인증서가 필요 합니다. 온-프레미스 Exchange를 사용 하는 경우 온-프레미스 Exchange 커넥터가 필요 합니다. 이러한 추가 요구 사항은 이러한 단계에 도달 하면 요약 됩니다.

## <a name="step-3-set-up-intune"></a>3 단계: Intune 설정

Intune에서는 도메인, 사용자 및 그룹을 비롯 하 여 Azure AD의 다양 한 기능을 사용 합니다. 회사의 요구 사항에 맞게 새 사용자 및 새 그룹을 만들 수도 있습니다. 예를 들어 **iOS 장치**또는 **모든 HR 사용자**라는 그룹을 만들 수 있습니다.  단순 또는 고급 규칙을 기반으로 사용자 또는 장치 그룹을 작성할 수 있도록 하는 [동적 그룹](https://docs.microsoft.com/intune/groups-add) 을 활용 합니다.

이 단계에서는 Intune을 설정 하 고 장치를 관리할 수 있도록 준비 하는 과정을 중점적으로 설명 합니다.

1. **[장치가 지원 되는지 확인](https://docs.microsoft.com/intune/supported-devices-browsers)** 합니다. IOS, macOS, Android, Galaxy 및 Windows 장치는 Intune에서 지원 되는지 확인 합니다. 조직에 지원 되지 않는 장치가 포함 되어 있는 경우 정책이 이러한 장치에 적용 되지 않습니다.

2. **[도메인 이름을 사용자 지정](https://docs.microsoft.com/intune/custom-domain-name-configure)** 합니다. 기본적으로 **your-domain.onmicrosoft.com** 와 같은 이름의 도메인은 Azure AD에서 자동으로 만들어집니다. 조직에 맞게 **onmicrosoft.com** 를 사용자 지정할 수 있습니다. 사용자 지정 하는 경우 Intune에 연결 하 고 리소스를 사용 하는 경우 사용자에 게 익숙한 도메인이 제공 됩니다.

3. **[Intune에 로그인](https://docs.microsoft.com/intune/account-sign-up)** 합니다. 로그인 할 때 조직에 대 한 정보를 입력 하 라는 메시지가 표시 될 수 있습니다. Intune은 Microsoft 365에 포함 되어 있으며 [microsoft 365 관리 센터](https://admin.microsoft.com)에서 직접 열 수 있습니다. [Azure portal](https://portal.azure.com)에서 직접 Intune을 열 수도 있습니다.

4. **[모바일 장치 관리 구성을 선택](https://docs.microsoft.com/intune/mdm-authority-set)** 합니다. 처음 Intune을 사용 하려면 장치 관리를 사용 하도록 설정 해야 합니다. Intune은 클라우드 전용 서비스, Intune 및 Microsoft Endpoint Configuration Manager를 사용한 하이브리드 또는 Office 365에 대 한 모바일 장치 관리를 사용 하 여 사용할 수 있습니다. 조직에 가장 적합 한 설정을 선택할 수 있습니다.

5. **[사용자를 추가](https://docs.microsoft.com/intune/users-add)** 하 고 **[그룹을 추가](https://docs.microsoft.com/intune/groups-add)** 합니다. 

   수동으로 사용자를 추가 하거나 하이브리드 id 및 Azure AD Connect를 사용 하 여 온-프레미스 사용자 계정을 Intune과 동기화 할 수 있습니다. 특정 사용자에 게 관리자 역할을 제공할 수도 있습니다. 장치가 키오스크 장치와 같은 "userless" 장치를 제외 하 고는 사용자가 필요 합니다.

   Azure AD 그룹은 Intune에서 디바이스 및 사용자를 관리 하는 방법을 간소화 하는 데 사용 됩니다. 그룹을 사용 하 여 다양 한 작업을 수행할 수 있습니다. 예를 들어 조직에서는 Android 장치에 특정 앱이 필요 합니다. Android 장치 그룹을 만들고이 앱이 포함 된 정책을 그룹에 배포할 수 있습니다.

    Intune에서는 [2 단계: Identity](https://docs.microsoft.com/microsoft-365/enterprise/identity-infrastructure) 로 만든 사용자 또는 그룹을 추가할 수 있습니다.

6. **[라이선스를 할당](https://docs.microsoft.com/intune/licenses-assign)** 합니다. Intune에서 등록할 사용자 또는 장치의 경우 intune 서비스에 액세스 하려면 Intune 서비스를 사용 하는 Microsoft 365 라이선스가 필요 합니다. Microsoft Intune 서비스가 기본적으로 사용 하도록 설정 되어 있는 microsoft 365 라이선스를 마이크로소프트 365 관리 센터에서 또는 PowerShell을 사용 하 여 할당 합니다.

## <a name="step-4-enroll-devices"></a>4 단계: 장치 등록

장치를 관리 하려면 Intune에서 장치를 등록 해야 합니다. 관리자는 사용자 및 장치에 대 한 등록 제한 및 정책을 설정 합니다. 각 장치 플랫폼 (iOS, Android, macOS 및 Windows)에는 다양 한 옵션이 있습니다. 사용자가 직접 등록할 수 있습니다. 또는 사용자가 장치에 로그인 하는 것 만으로 등록을 자동화할 수 있습니다.

Intune을 사용 하는 경우에는 등록이 중요 한 단계입니다. [장치 등록](https://docs.microsoft.com/intune/device-enrollment) 여러 장치에 대 한 단계를 나열 합니다.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: iOS 및 Android 장치 등록](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md) |
|||


## <a name="step-5-add-and-deploy-apps"></a>5 단계: 앱 추가 및 배포

모바일 장치의 앱은 사용자가 회사 리소스에 액세스 하는 가장 빠른 방법입니다. 

개인 장치 및 회사 장치를 포함 하 여 다른 장치와 마찬가지로 앱을 사용 하는 경우 문제가 발생 합니다. 또한 사용자의 생산성을 유지 하면서 조직의 리소스 및 데이터를 보호 하려고 합니다.

Intune은 앱 추가, 다른 사용자 또는 그룹에 할당 및 기타 주요 세부 정보 검토를 포함 하 여 앱을 관리할 수 있습니다. 예를 들어 설치에 실패 한 앱을 확인 하 고 앱 버전을 확인할 수 있습니다.

사용자가 모바일 장치를 사용 하는 경우 첫 번째 작업 중 하나는 조직 전자 메일 및 문서에 액세스 하는 것입니다. Intune을 사용 하면 장치에 미리 설치 되어 있는 전자 메일 앱을 사용 하 여 [전자 메일 설정을 만들고 배포할](https://docs.microsoft.com/intune/email-settings-configure) 수 있습니다. 

[앱 추가](https://docs.microsoft.com/intune/apps/apps-add) 문서에는 조직 내 장치에서 앱을 추가, 배포, 모니터링, 구성 및 보호 하기 위한 단계가 나열 되어 있습니다.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 장치 준수 정책](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md) |
|||

## <a name="step-6-turn-on-compliance-and-conditional-access"></a>6 단계: 규정 준수 및 조건부 액세스 설정

이전 단계에서는 환경을 설정 하 고 Intune을 사용 하도록 설정한 다음 이제 규정 준수 및 조건부 액세스를 사용 하 여 몇 가지 정책을 만들 준비가 되었습니다.

준수 및 조건부 액세스는 장치를 관리 하는 데 중요 합니다. 조직의 리소스를 보호 하기 위해 [준수 정책이](https://docs.microsoft.com/intune/device-compliance-get-started) 만들어집니다. 준수 정책을 만들 때는 장치에 필요한 표준 또는 "베이스 라인"을 정의 합니다. 예를 들어 허용 또는 허용 되지 않는 위협 수준을 선택 하 고, 탈 옥 장치를 차단 하 고, 암호 길이를 요구 하는 등의 옵션을 선택할 수 있습니다. 이러한 장치가 규칙을 충족 하지 않는 경우에는 해당 디바이스가 호환 되지 않는 경우에는 리소스에 대 한 액세스를 차단할 수 있습니다.

이 "차단"은 [조건부 액세스](https://docs.microsoft.com/intune/conditional-access)를 도입 합니다. 장치가 호환 되지 않는 것으로 간주 되는 경우에는 전자 메일, SharePoint 등에 대 한 액세스를 차단할 수 있습니다.

[Azure portal](https://portal.azure.com) 의 Intune을 사용 하면 이러한 정책을 만들고 사용자 및 장치에 적용할 수 있습니다. 최상의 방법은 small를 시작 하 고 미리 구성 된 방법을 사용 하는 것입니다. 예를 들어 탈 옥 장치를 차단 하는 iOS 정책을 만듭니다. Apply (Intune에서 "할당") 정책을 파일럿 또는 테스트 그룹에 적용 합니다. 초기 테스트를 수행한 후 파일럿 그룹에 더 많은 사용자를 추가 합니다. 미리 구성 된 방법을 사용 하면 광범위 한 사용자 유형에 서 피드백을 얻을 수 있습니다.

시작 하는 데 도움을 받으려면 [장치 준수 정책 시작](https://docs.microsoft.com/intune/device-compliance-get-started) 및 [조건부 액세스 및 Intune에 대 한 자세한 정보](https://docs.microsoft.com/intune/conditional-access) 를 참조 하세요.

## <a name="step-7-apply-features-and-settings"></a>7 단계: 기능 및 설정 적용

이러한 기능과 설정은 대개 Intune의 "멋진" 부분으로 간주 되며 매우 강력 합니다. 조건부 액세스를 사용 하 여 준수 정책을 성공적으로 적용 한 후에는 **장치 프로필**을 만들 수 있습니다.

[Azure portal](https://portal.azure.com) 의 Intune을 사용 하면 장치 플랫폼-IOS, Macos, Android 및 Windows를 기반으로 다른 프로필을 만들 수 있습니다. 예를 들어, 다음을 수행할 수 있습니다.

- Windows 10 장치에서 Endpoint protection을 사용 하 여 암호화를 포함 하 여 서로 다른 BitLocker 옵션을 사용 하도록 설정 합니다.
- IOS 장치에서 제한 된 앱 기능을 사용 하 여 설치할 수 있는 승인 된 앱 목록을 만듭니다. 또는 금지 된 앱 목록을 만듭니다.
- 키오스크 설정을 사용 하 여 키오스크 모드에서 실행 되는 Android 장치에서 사용할 수 있는 앱을 선택 합니다.
- MacOS를 실행 하는 장치에서 Wi-fi 연결과 보안 유형을 포함 한 해당 설정을 적용 합니다.

장치 [에 기능 및 설정 적용 디바이스 프로필을 사용 하 여](https://docs.microsoft.com/intune/device-profiles) 프로필을 읽고 프로필을 만드는 방법에 대 한 자세한 내용을 확인할 수 있습니다.

Small을 시작 하 고 미리 구성 된 접근 방식을 사용 합니다. 파일럿 또는 테스트 그룹에 프로필을 할당 합니다. 그런 다음 더 많은 파일럿 그룹에 프로필을 할당 합니다.

## <a name="step-8-get-to-know-the-other-features"></a>8 단계: 다른 기능에 대해 알아보기

Intune은 강력한 서비스 이며 많은 기능을 포함 합니다. 다음은 Intune을 사용 하 여 수행할 수 있는 몇 가지 작업입니다.

- Windows [장치](https://docs.microsoft.com/intune/windows-update-for-business-configure) & [pc](https://docs.microsoft.com/intune/keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune)및 [iOS](https://docs.microsoft.com/intune/software-updates-ios) 장치에서 소프트웨어 및 업데이트 관리
- Windows 10 장치에서 [Microsoft DEFENDER ATP (Advanced Threat Protection)](https://docs.microsoft.com/intune/advanced-threat-protection) 를 설정 하 고 규정 준수 및 조건부 액세스를 사용 하 여 SharePoint 또는 Exchange Online과 같은 회사 리소스에 대 한 액세스를 보호 합니다.
- [감시](https://docs.microsoft.com/intune/lookout-mobile-threat-defense-connector), [Symantec](https://docs.microsoft.com/intune/skycure-mobile-threat-defense-connector)및 기타 모바일 방어 위협 파트너 사용
- 인증서를 발급 하 고 갱신 하기 위한 [파트너 CA (인증 기관)](https://docs.microsoft.com/intune/certificate-authority-add-scep-overview) 추가
- [최종 사용자에 게](https://docs.microsoft.com/intune/end-user-educate) 회사 포털 앱에 대 한 지침을 제공 하 고 앱을 가져옵니다.
- 감사 로그를 사용 하 여 [앱](https://docs.microsoft.com/intune/apps-monitor) 및 [장치 준수 및 구성 프로필](https://docs.microsoft.com/intune/compliance-policy-monitor)을 모니터링 하 고 원격 분석을 수행 합니다. 또한 [Intune 데이터 웨어하우스에](https://docs.microsoft.com/intune/reports-nav-create-intune-reports) 연결 하 고 Power BI를 사용 하 여 더 많은 보고 요구 사항을 추가로 확인할 수도 있습니다.


## <a name="identity-and-device-access-recommendations"></a>ID 및 장치 액세스 권장 사항

Microsoft에서는 직원 안전과 생산성을 유지하기 위해 [ID 및 디바이스 액세스](microsoft-365-policies-configurations.md)에 대한 권장 사항을 제공합니다. 장치 액세스용으로이 단계에 나와 있는 단계와 함께 다음 문서의 권장 사항과 설정을 사용 합니다.

- [필수 구성 요소](identity-access-prerequisites.md)
- [일반 ID 및 장치 액세스 정책](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

Microsoft의 IT 전문가가 [EMS를 사용 하 여 장치를 관리](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR8)하는 방법을 알아봅니다.

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso의 Microsoft 365 Enterprise 사용 방식

Contoso Corporation (가상의 대표적인 다국적 기업)이 Microsoft 365 클라우드 서비스와 함께 [모바일 장치 관리 인프라를 배포](contoso-mdm.md) 하는 방법을 알아봅니다.

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>다음 단계

[모바일 장치 관리 인프라 종료 조건](mobility-infrastructure-exit-criteria.md)

