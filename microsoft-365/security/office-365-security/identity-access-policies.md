---
title: 일반 id 및 장치 액세스 정책-Microsoft 365 for enterprise | Microsoft Docs
description: 권장 되는 일반적인 id 및 장치 액세스 정책 및 구성에 대해 설명 합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- remotework
- m365solution-identitydevice
- m365solution-scenario
ms.openlocfilehash: b4468bfc7ef4b6f76d44b328f4e5b6d61d7f06ac
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357842"
---
# <a name="common-identity-and-device-access-policies"></a>일반 ID 및 장치 액세스 정책

이 문서에서는 azure Active Directory (Azure AD) 응용 프로그램 프록시를 사용 하 여 게시 된 온-프레미스 응용 프로그램을 포함 하 여 Microsoft 365 클라우드 서비스에 대 한 액세스를 보호 하기 위한 일반적인 권장 정책을 설명 합니다.

이 지침은 새로 프로 비전 된 환경에서 권장 정책을 배포 하는 방법에 대해 설명 합니다. 별도의 랩 환경에서 이러한 정책을 설정 하면 프로덕션 전 및 프로덕션 환경에 대 한 롤아웃을 준비 하기 전에 권장 정책을 이해 하 고 평가할 수 있습니다. 새로 프로 비전 된 환경은 평가 요구 사항을 반영 하기 위해 클라우드 전용 또는 하이브리드 일 수 있습니다.

## <a name="policy-set"></a>정책 집합

다음 다이어그램에서는 권장 되는 정책 집합을 보여 줍니다. 각 정책이 적용 되는 보호 계층과 정책이 Pc 또는 휴대폰 및 태블릿에서 적용 되는지, 아니면 두 장치 범주 모두를 보여 줍니다. 또한 이러한 정책을 구성 하는 위치를 나타냅니다.

[![Id 및 장치 액세스 구성에 대 한 일반 정책](../../media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

[이 이미지의 더 큰 버전 보기](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/Identity_device_access_policies_byplan.png)

다음은 개별 정책에 대 한 링크를 포함 하는 한 페이지 PDF 요약입니다.

[![Microsoft 365 유인물의 Id 및 장치 보호를 위한 축소판 그림](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br/>  [PDF](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| 로 보기 [PDF로 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

이 문서의 나머지 부분에서는 이러한 정책을 구성 하는 방법에 대해 설명 합니다.

> [!NOTE]
> 장치를 원하는 사용자가 소유 하 고 있는지 확인 하기 위해 Intune에서 장치를 등록 하기 전에 MFA (multi-factor authentication)를 사용 하도록 요구 하는 것이 좋습니다. 장치 준수 정책을 적용 하려면 먼저 Intune에서 장치를 등록 해야 합니다.

이러한 작업을 완료 하는 데 필요한 시간을 제공 하려면이 표에 나열 된 순서 대로 기준 정책을 구현 하는 것이 좋습니다. 그러나 중요 및 높은 규제 수준의 보호를 위한 MFA 정책은 언제 든 지 구현 될 수 있습니다.

|보호 수준|정책|추가 정보|
|---|---|---|
|**기준**|[로그인 위험이 *보통* 또는 *높을* 때 MFA 필요](#require-mfa-based-on-sign-in-risk)||
||[최신 인증을 지원하지 않는 클라이언트 차단](#block-clients-that-dont-support-modern-authentication)|최신 인증을 사용 하지 않는 클라이언트는 조건부 액세스 정책을 우회할 수 있으므로 이러한 정책 들을 차단 하는 것이 중요 합니다.|
||[위험이 높은 사용자는 암호를 변경해야 함](#high-risk-users-must-change-password)|계정의 높은 위험 활동이 검색 되는 경우 로그인 할 때 사용자가 암호를 변경 하도록 합니다.|
||[앱 데이터 보호 정책 적용](#apply-app-data-protection-policies)|플랫폼 당 하나의 Intune 앱 보호 정책 (Windows, iOS/iPadOS, Android)|
||[승인 된 앱 및 앱 보호 필요](#require-approved-apps-and-app-protection)|IOS, iPadOS 또는 Android를 사용 하 여 휴대폰 및 태블릿에서 모바일 앱 보호를 적용 합니다.|
||[장치 준수 정책 정의](#define-device-compliance-policies)|각 플랫폼에 대 한 정책 1 개|
||[호환 PC 필요](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Windows 또는 MacOS를 사용 하 여 Pc의 Intune 관리를 적용 합니다.|
|**중요**|[로그인 위험이 *낮음*, *중간* 또는 *높은* 경우 MFA 필요](#require-mfa-based-on-sign-in-risk)||
||[준수 Pc *및* 모바일 장치 요구](#require-compliant-pcs-and-mobile-devices)|Pc (Windows 또는 MacOS)와 휴대폰 또는 태블릿 (iOS, iPadOS 또는 Android) 모두에 대해 Intune 관리를 적용 합니다.|
|**매우 엄격한 규제**|[*항상* MFA 필요](#require-mfa-based-on-sign-in-risk)|
|

## <a name="assigning-policies-to-groups-and-users"></a>그룹 및 사용자에 게 정책 할당

정책을 구성 하기 전에 각 보호 계층에 사용 중인 Azure AD 그룹을 확인 합니다. 일반적으로 기본 보호는 조직의 모든 사람에 게 적용 됩니다. 기준 및 중요 보호 둘 다에 포함 된 사용자는 모든 기본 정책이 적용 되 고 중요 한 정책도 함께 제공 됩니다. 보호는 누적 되며 가장 제한적인 정책이 적용 됩니다.

조건부 액세스 제외를 위해 Azure AD 그룹을 만드는 것이 좋습니다. **지정** 섹션에 있는 **사용자 및 그룹** 설정의 **제외** 값에서 모든 조건부 액세스 정책에이 그룹을 추가 합니다. 이렇게 하면 액세스 문제를 해결 하는 동안 사용자에 게 액세스 권한을 제공 하는 방법이 제공 됩니다. 이 방법은 임시 솔루션 으로만 권장 됩니다. 이 그룹에서 변경 사항을 모니터링 하 고 제외 그룹이 의도 한 대로 사용 되 고 있는지 확인해 보십시오.

다음은 MFA를 요구 하기 위한 그룹 할당 및 제외의 예입니다.

![MFA 정책에 대 한 그룹 할당 및 제외 예](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

결과는 다음과 같습니다.

- 로그인 위험이 보통 또는 높을 때 MFA를 사용 하려면 모든 사용자가 필요 합니다.

- 경영 지팡이 그룹의 구성원은 로그인 위험이 낮음, 중간 또는 높음을 할 때 MFA를 사용 해야 합니다.

  이 경우 Executive 스태프 그룹의 구성원은 기본 및 중요 조건부 액세스 정책을 모두 일치 시킵니다. 두 정책에 대 한 액세스 제어는 결합 되어 있으며,이 경우에는 중요 한 조건부 액세스 정책과 동일 합니다.

- MFA를 사용 하려면 최상위 암호 프로젝트 X 그룹의 구성원이 항상 필요 합니다.

  이 경우 상위 보안 프로젝트 X 그룹의 구성원은 기준 및 높은 규제 조건부 액세스 정책을 모두 일치 시킵니다. 두 정책 모두에 대 한 액세스 제어를 결합 합니다. 높은 규제 대상 조건부 액세스 정책에 대 한 액세스 제어는 더 제한적 이므로 사용 됩니다.

그룹 및 사용자에 게 더 높은 수준의 보호를 적용할 때는 주의 해야 합니다. 예를 들어 상위 보안 프로젝트 X 그룹의 구성원은 Project X에 대 한 높은 규제 된 콘텐츠에서 작업을 수행 하 고 있지 않더라도 로그인 할 때마다 MFA를 사용 해야 합니다.

이러한 권장 사항의 일부로 만들어진 모든 Azure AD 그룹은 Microsoft 365 그룹으로 만들어야 합니다. 이는 Microsoft 팀 및 SharePoint에서 문서를 보호할 때 민감도 레이블을 배포 하는 데 중요 합니다.

![Microsoft 365 그룹을 만드는 화면 캡처](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>로그인 위험을 기반으로 MFA 요구

사용자가 사용을 요청 하기 전에 MFA를 등록 해야 합니다. Microsoft 365 E5를 사용 하는 경우 Microsoft 365 E3에 Id & Threat Protection 추가 기능 365, EMS E5 또는 개별 Azure AD Premium P2 라이선스가 있는 경우, Azure AD Id 보호와 함께 MFA 등록 정책을 통해 사용자가 MFA에 등록 하도록 요구할 수 있습니다. [필수 구성 요소 작업](identity-access-prerequisites.md) 에는 모든 사용자를 MFA에 등록 하는 작업이 포함 됩니다.

사용자가 등록 되 면 새 조건부 액세스 정책을 사용 하 여 로그인 하기 위해 MFA를 요구할 수 있습니다.

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
2. Azure services 목록에서 **Azure Active Directory** 를 선택 합니다.
3. **관리** 목록에서 **보안** 을 선택 하 고 **조건부 액세스** 를 선택 합니다.
4. **새 정책을** 선택 하 고 새 정책의 이름을 입력 합니다.

다음 표에서는 로그인 위험에 따라 MFA를 요구 하는 조건부 액세스 정책 설정에 대해 설명 합니다.

**지정** 섹션에서 다음을 수행 합니다.

|설정|속성|값|참고|
|---|---|---|---|
|사용자 및 그룹|포함|사용자와 그룹 > 사용자 및 그룹을 선택 합니다. 대상 지정 된 사용자 계정을 포함 하는 특정 그룹 **을** 선택 합니다.|파일럿 사용자 계정을 포함 하는 그룹으로 시작 합니다.|
||제외|**사용자 및 그룹**: 조건부 액세스 예외 그룹을 선택 합니다. 서비스 계정 (앱 id)|멤버 자격은 필요에 따라 임시로 수정 해야 합니다.|
|클라우드 앱 또는 작업|**포함 > 클라우드 앱**|**앱**:이 정책을 적용할 앱을 선택 합니다. 예를 들어 Exchange Online을 선택 합니다.||
|조건|||사용자 환경 및 요구 사항에 맞는 조건을 구성 합니다.|
||로그인 위험||다음 표의 지침을 참조 하십시오.|
|

### <a name="sign-in-risk-condition-settings"></a>로그인 위험 조건 설정

대상으로 지정 하는 보호 수준에 따라 위험 수준 설정을 적용 합니다.

|보호 수준|필요한 위험 수준 값|조치|
|---|---|---|
|기준|높음, 중간|두 확인란을 모두 선택 합니다.|
|중요|높음, 중간, 낮음|세 가지를 모두 선택 합니다.|
|매우 엄격한 규제||항상 MFA를 적용 하려면 모든 옵션을 선택 하지 않은 상태로 유지 합니다.|
|

**액세스 제어** 섹션에서 다음을 수행 합니다.

|설정|속성|값|조치|
|---|---|---|---|
|권한 부여|**Grant access**||선택한|
|||**다단계 인증 필요**|수표|
||**선택된 컨트롤이 모두 필요함**||선택한|
|

**허용** 설정을 저장 하려면 **선택을** 선택 합니다.

마지막으로 **정책을 사용 하도록 설정을** 선택한 다음 **만들기** **를 선택** 합니다.

또한 [if](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 정책을 테스트할 수도 있습니다.

## <a name="block-clients-that-dont-support-modern-authentication"></a>최신 인증을 지원하지 않는 클라이언트 차단

이러한 표의 설정을 사용 하 여 최신 인증을 지원 하지 않는 클라이언트를 차단 합니다.

최신 인증을 suppport 하는 Microsoft 365의 클라이언트 목록에 대해서는 [이 문서](../../enterprise/microsoft-365-client-support-modern-authentication.md) 를 참조 하십시오.

**지정** 섹션에서 다음을 수행 합니다.

|설정|속성|값|참고|
|---|---|---|---|
|사용자 및 그룹|포함|사용자와 그룹 > 사용자 및 그룹을 선택 합니다. 대상 지정 된 사용자 계정을 포함 하는 특정 그룹 **을** 선택 합니다.|파일럿 사용자 계정을 포함 하는 그룹으로 시작 합니다.|
||제외|**사용자 및 그룹**: 조건부 액세스 예외 그룹을 선택 합니다. 서비스 계정 (앱 id)|멤버 자격은 필요에 따라 임시로 수정 해야 합니다.|
|클라우드 앱 또는 작업|**포함 > 클라우드 앱**|**앱 선택**: 최신 인증을 지원 하지 않는 클라이언트에 해당 하는 앱을 선택 합니다.||
|조건|**클라이언트 앱**|**구성을** 보려면 **예** 를 선택 합니다. <br/> **브라우저** 및 **모바일 앱 및 데스크톱 클라이언트** 에 대 한 확인 표시 지우기||
|

**액세스 제어** 섹션에서 다음을 수행 합니다.

|설정|속성|값|조치|
|---|---|---|---|
|권한 부여|**액세스 차단**||선택한|
||**선택된 컨트롤이 모두 필요함**||선택한|
|

**허용** 설정을 저장 하려면 **선택을** 선택 합니다.

마지막으로 **정책을 사용 하도록 설정을** 선택한 다음 **만들기** **를 선택** 합니다.

[If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 정책을 테스트 하는 것이 좋습니다.

Exchange Online에서는 인증 정책을 사용 하 여 [기본 인증을 사용 하지 않도록 설정](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)하 여 모든 클라이언트 액세스 요청이 최신 인증을 사용 하도록 할 수 있습니다.

## <a name="high-risk-users-must-change-password"></a>위험이 높은 사용자는 암호를 변경해야 함

로그인 할 때 모든 높은 위험 사용자의 손상 된 계정이 강제로 암호 변경을 수행 하 게 하려면 다음 정책을 적용 해야 합니다.

사용자의 관리자 자격 증명을 사용하여 [Microsoft Azure Portal(https://portal.azure.com)](https://portal.azure.com/)에 로그인한 다음 **Azure AD ID 보호 > 사용자 위험 정책** 으로 이동합니다.

**지정** 섹션에서 다음을 수행 합니다.

|유형|속성|값|조치|
|---|---|---|---|
|사용자|포함|**모든 사용자**|선택한|
|사용자 위험|**High**||선택한|
|

두 번째 **지정** 섹션에서 다음을 수행 합니다.

|유형|속성|값|조치|
|---|---|---|---|
|Access|**액세스 허용**||선택한|
|||**암호 변경 필요**|수표|
|

**완료** 를 선택 하 여 **Access** 설정을 저장 합니다.

마지막으로 **정책 적용** 에 대해 **을 선택한 다음** **저장** 을 선택 합니다.

[If](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-whatif) 도구를 사용 하 여 정책을 테스트 하는 것이 좋습니다.

이 정책을 [AZURE AD 암호 보호 구성과](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad)함께 사용 하 여 알려진 약한 암호와 해당 변형 및 조직과 관련 된 추가 약한 용어를 감지 하 고 차단 합니다. Azure AD 암호 보호를 사용 하면 변경 된 암호가 강력한 암호를 확인할 수 있습니다.

## <a name="apply-app-data-protection-policies"></a>앱 데이터 보호 정책 적용

앱 (응용 프로그램 보호 정책)은 허용 되는 앱과 조직 데이터로 수행할 수 있는 작업을 정의 합니다. 앱에서 제공 하는 선택 사항에 따라 조직에서 특정 요구에 맞게 보호를 조정할 수 있습니다. 어떤 경우에는 전체 시나리오를 구현 하는 데 어떤 정책 설정이 필요한 지 명확 하지 않을 수 있습니다. 조직이 모바일 클라이언트 끝점 강화를 우선 순위를 지정 하는 데 도움이 되도록 Microsoft는 iOS 및 Android 모바일 앱 관리를 위한 앱 데이터 보호 프레임 워크에 대 한 분류를 도입 했습니다.

앱 데이터 보호 프레임 워크는 세 가지 고유한 구성 수준으로 구성 되며, 각 수준은 이전 수준을 구성 합니다.

- **엔터프라이즈 기본 데이터 보호** (수준 1)는 앱이 PIN을 사용 하 여 보호 되 고 선택 된 지우기 작업을 수행 하도록 합니다. Android 장치의 경우이 수준에서는 Android 장치 증명의 유효성을 검사 합니다. Exchange Online 사서함 정책에 비슷한 데이터 보호 제어 기능을 제공 하는 항목 수준 구성으로, 앱에 대 한 사용자 인구를 소개 합니다.
- **엔터프라이즈 향상 데이터 보호** (수준 2)에서는 앱 데이터 누출 방지 메커니즘과 최소 OS 요구 사항이 도입 되었습니다. 이 구성은 회사 또는 학교 데이터에 액세스 하는 대부분의 모바일 사용자에 게 적용 되는 구성입니다.
- **엔터프라이즈 높은 데이터 보호** (수준 3) 고급 데이터 보호 메커니즘, 향상 된 PIN 구성 및 앱 모바일 위협 방어를 도입 합니다. 이 구성은 높은 위험 수준 데이터에 액세스 하는 사용자에 게 적합 합니다.

각 구성 수준 및 보호 해야 하는 최소 앱에 대 한 구체적인 권장 사항을 보려면 [앱 보호 정책을 사용 하 여 데이터 보호 프레임 워크](https://docs.microsoft.com/mem/intune/apps/app-protection-framework)를 검토 하세요.

[Id 및 장치 액세스 구성](microsoft-365-policies-configurations.md)에 설명 된 원칙을 사용 하 여 기준 및 중요 보호 계층은 수준 2 enterprise 향상 된 데이터 보호 설정과 밀접 하 게 매핑됩니다. 높은 규제 보호 계층은 수준 3 enterprise 고급 데이터 보호 설정에 밀접 하 게 매핑됩니다.

|보호 수준|앱 보호 정책|추가 정보|
|---|---|---|
|기준|[수준 2 향상 된 데이터 보호](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|수준 2에 적용 된 정책 설정에는 수준 1에 대해 권장 되는 모든 정책 설정이 포함 되며, 수준 1 보다 더 복잡 한 구성을 구현 하기 위해 아래 정책 설정만 추가 하거나 업데이트 합니다.|
|중요|[수준 2 향상 된 데이터 보호](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|수준 2에 적용 된 정책 설정에는 수준 1에 대해 권장 되는 모든 정책 설정이 포함 되며, 수준 1 보다 더 복잡 한 구성을 구현 하기 위해 아래 정책 설정만 추가 하거나 업데이트 합니다.|
|높은 규제|[수준 3 enterprise 높은 데이터 보호](https://docs.microsoft.com/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|수준 3에 적용 된 정책 설정에는 수준 1 및 2에 권장 되는 모든 정책 설정이 포함 되며, 수준 2 보다 더 복잡 한 구성을 구현 하기 위해 아래 정책 설정만 추가 하거나 업데이트 합니다.|
|

Microsoft Endpoint Manager에서 데이터 보호 프레임 워크 설정을 사용 하 여 각 플랫폼 (iOS 및 Android)에 대해 새 앱 보호 정책을 만들려면 다음을 수행할 수 있습니다.

1. [Microsoft Intune을 사용 하 여 앱 보호 정책을 만들고 배포 하는 방법](https://docs.microsoft.com/mem/intune/apps/app-protection-policies)의 단계에 따라 정책을 수동으로 만듭니다.
2. [Intune PowerShell 스크립트](https://github.com/microsoftgraph/powershell-intune-samples)를 사용 하 여 샘플 [Intune 앱 보호 정책 구성 프레임 워크 JSON 템플릿을](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) 가져옵니다.

## <a name="require-approved-apps-and-app-protection"></a>승인 된 앱 및 앱 보호 필요

Intune에서 적용 한 앱 보호 정책을 적용 하려면 승인 된 클라이언트 앱이 필요한 조건부 액세스 정책을 만들고 앱 보호 정책에서 설정 해야 합니다.

앱 보호 정책을 적용 하려면 requires 앱 [보호 정책에 조건부 액세스를 사용한 클라우드 앱 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)에 설명 된 정책 집합이 필요 합니다. 이러한 정책은 이러한 권장 되는 id 및 액세스 구성 정책 집합에 포함 됩니다.

승인 된 앱 및 앱 보호가 필요한 조건부 액세스 정책을 만들려면 [시나리오 1: microsoft 365 앱에 승인 365 된 앱 (앱 보호 정책 포함](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies))이 필요 하며,이 정책은 Outlook for IOS 및 Android를 허용 하지만 OAuth 가능 exchange ActiveSync 클라이언트는 exchange Online에 연결 하는 것을 차단 합니다.

   > [!NOTE]
   > 이 정책은 모바일 사용자가 해당 앱을 사용 하 여 모든 Office 끝점에 액세스할 수 있도록 합니다.

Exchange Online에 대 한 모바일 액세스를 사용 하도록 설정 하는 경우 [activesync를 차단](secure-email-recommended-policies.md#block-activesync-clients)하는 클라이언트를 구현 하 여 기본 인증을 활용 하는 exchange ActiveSync 클라이언트가 exchange online에 연결 하지 못하도록 합니다. 이 정책은이 문서 맨 위의 그림에 나와 있지 않습니다. [전자 메일 보안에 대 한 정책 권장 사항](secure-email-recommended-policies.md)에 설명 되어 있습니다.

 이러한 정책은 부여 컨트롤을 활용 하 여 [승인 된 클라이언트 앱을 필요로](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) 하며 [앱 보호 정책이 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)합니다.

마지막으로 iOS 및 Android 장치에서 다른 클라이언트 앱에 대해 레거시 인증을 차단 하면 이러한 클라이언트가 조건부 액세스 정책을 무시할 수 없습니다. 이 문서의 지침을 팔 로우 하는 경우에 [는 최신 인증을 지원 하지 않는 클라이언트](#block-clients-that-dont-support-modern-authentication)에 대 한 차단이 이미 구성 되어 있습니다.

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>장치 준수 정책 정의

장치 준수 정책은 장치가 준수 하는 것으로 확인 하기 위해 충족 해야 하는 요구 사항을 정의 합니다. Microsoft Endpoint Manager 관리 센터 내에서 Intune 장치 준수 정책을 만듭니다.

각 PC, 휴대폰 또는 태블릿 플랫폼에 대 한 정책을 만들어야 합니다.

- Android 장치 관리자
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 이상
- Windows 10 이상

장치 준수 정책을 만들려면 관리자 자격 증명을 사용 하 여 [Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com) 에 로그인 한 다음 **장치**  >  **준수 정책**  >  **정책** 으로 이동 합니다. **정책 만들기** 를 선택 합니다.

장치 준수 정책이 배포 되려면 사용자 그룹에 할당 되어야 합니다. 정책을 만들고 저장 한 후 할당 합니다. 관리 센터에서 정책을 선택한 다음 **할당** 을 선택 합니다. 정책을 수신 하려는 그룹을 선택한 후 **저장** 을 선택 하 여 해당 그룹 할당을 저장 하 고 정책을 배포 합니다.

Intune에서 준수 정책을 만드는 방법에 대 한 단계별 지침은 Intune 설명서의 [Microsoft Intune에서 준수 정책 만들기](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy) 를 참조 하세요.

### <a name="recommended-settings-for-windows-10-and-later"></a>Windows 10 이상에 대 한 권장 설정

정책 만들기 프로세스의 **2 단계: 준수 설정** 에 구성 된 대로 Windows 10 이상을 실행 하는 pc에는 다음과 같은 설정이 권장 됩니다.

**Windows 상태 증명 서비스 평가 규칙을 > 장치 상태** 를 확인 하려면이 표를 참조 하십시오.

|속성|값|조치|
|---|---|---|
|BitLocker 필요|할|선택한|
|장치에서 보안 부팅이 사용 되도록 설정 해야 합니다.|할|선택한|
|코드 무결성 필요|할|선택한|
|

**장치 속성** 의 경우 IT 및 보안 정책에 따라 운영 체제 버전에 적합 한 값을 지정 합니다.

**Configuration Manager 규정 준수** 에 대해 **필수** 를 선택 합니다.

**시스템 보안** 에 대해서는이 표를 참조 하세요.

|유형|속성|값|조치|
|---|---|---|---|
|암호|모바일 장치의 잠금을 해제 하는 데 암호 필요|할|선택한|
||단순 암호|차단|선택한|
||암호 유형|장치 기본값|선택한|
||최소 암호 길이|6 |타이핑|
||암호를 요구 하기 전까지 최대 비활성 시간 (분)|15 |타이핑 <br/> 이 설정은 Android 버전 4.0 이상 또는 KNOX 4.0 이상에 대해 지원 됩니다. IOS 장치에서는 iOS 8.0 이상에 대해 지원 됩니다.|
||암호 만료(일)|41|타이핑|
||다시 사용 하지 못하도록 할 이전 암호 수|5 |타이핑|
||장치가 유휴 상태에서 반환 될 때 암호 필요 (Mobile 및 Holographic)|할|Windows 10 이상 버전에서 사용 가능|
|암호화|장치에서 데이터 저장소 암호화|할|선택한|
|장치 보안|방화벽이|할|선택한|
||바이러스 검사|할|선택한|
||백신|할|선택한 <br/> 이 설정을 사용 하려면 Windows 보안 센터에 등록 된 스파이웨어 방지 솔루션이 필요 합니다.|
|Defender|Microsoft Defender 맬웨어 방지|할|선택한|
||Microsoft Defender 맬웨어 방지 최소 버전||타이핑 <br/> Windows 10 desktop에 대해서만 지원 됩니다. 최신 버전에서 최대 5 개까지 남은 버전은 Microsoft에서 권장 됩니다.|
||Microsoft Defender 맬웨어 방지 서명이 최신 상태입니다.|할|선택한|
||실시간 보호|할|선택한 <br/> Windows 10 desktop에만 지원 됨|
|

#### <a name="microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender

|유형|속성|값|조치|
|---|---|---|---|
|끝점 규칙에 대 한 Microsoft Defender|장치가 컴퓨터 위험 점수에 있거나 그 아래에 있어야 합니다.|보통|선택한|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>준수 Pc 필요 (준수 전화 및 태블릿 제외)

준수 Pc를 요구 하는 정책을 추가 하기 전에 관리를 위한 장치를 Intune에 등록 해야 합니다. 장치가 원하는 사용자의 소유 인지 확인 하기 위해 장치를 Intune에 등록 하기 전에 다단계 인증을 사용 하는 것이 좋습니다.

준수 Pc를 요구 하려면:

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
2. Azure services 목록에서 **Azure Active Directory** 를 선택 합니다.
3. **관리** 목록에서 **보안** 을 선택 하 고 **조건부 액세스** 를 선택 합니다.
4. **새 정책을** 선택 하 고 새 정책의 이름을 입력 합니다.

5. **할당** 에서 **사용자 및 그룹** 을 선택 하 고 정책을 적용할 사용자를 포함 합니다. 조건부 액세스 제외 그룹도 제외 합니다.

6. **할당** 에서 **클라우드 앱 또는 작업** 을 선택 합니다.

7. 포함 하는 경우에 **는** **앱 선택을** 선택 하 > 선택한 다음 **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예를 들어 Exchange Online을 선택 합니다. 완료 되 면 **선택을** 선택 합니다.

8. 규격 Pc (준수 전화 및 태블릿 제외)를 요구 하려면 **할당** 에서 **장치 플랫폼 > 조건을** 선택 합니다. **구성을** 보려면 **예** 를 선택 합니다. **장치 플랫폼 선택을** 선택 하 고 **Windows** 및 **Macos** 를 선택한 다음 **완료** 를 선택 합니다.

9. **액세스 제어** 에서 **부여** 를 선택 합니다.

10. **액세스 허용** 을 선택한 다음 **장치가 호환 되는 것으로 표시 되어** 있는지 확인 합니다. 여러 컨트롤의 경우 **선택한 모든 컨트롤 필요** 를 선택 합니다. 완료 되 면 **선택을** 선택 합니다.

11. **정책 사용** **에 대 한** 설정을 선택 하 고 **만들기** 를 선택 합니다.

> [!NOTE]
> 이 정책을 사용 하기 전에 장치가 호환 되는지 확인 합니다. 그렇지 않으면 사용자 계정이 조건부 액세스 제외 그룹에 추가 될 때까지이 정책을 잠그거나 변경할 수 없게 됩니다.

## <a name="require-compliant-pcs-and-mobile-devices"></a>준수 Pc *및* 모바일 장치 요구

모든 장치에 대 한 준수를 요구 하려면:

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
2. Azure services 목록에서 **Azure Active Directory** 를 선택 합니다.
3. **관리** 목록에서 **보안** 을 선택 하 고 **조건부 액세스** 를 선택 합니다.
4. **새 정책을** 선택 하 고 새 정책의 이름을 입력 합니다.

5. **할당** 에서 **사용자 및 그룹** 을 선택 하 고 정책을 적용할 사용자를 포함 합니다. 조건부 액세스 제외 그룹도 제외 합니다.

6. **할당** 에서 **클라우드 앱 또는 작업** 을 선택 합니다.

7. 포함 하는 경우에 **는** **앱 선택을** 선택 하 > 선택한 다음 **클라우드 앱** 목록에서 원하는 앱을 선택 합니다. 예를 들어 Exchange Online을 선택 합니다. 완료 되 면 **선택을** 선택 합니다.

8. **액세스 제어** 에서 **부여** 를 선택 합니다.

9. **액세스 허용** 을 선택한 다음 **장치가 호환 되는 것으로 표시 되어** 있는지 확인 합니다. 여러 컨트롤의 경우 **선택한 모든 컨트롤 필요** 를 선택 합니다. 완료 되 면 **선택을** 선택 합니다.

10. **정책 사용** **에 대 한** 설정을 선택 하 고 **만들기** 를 선택 합니다.

> [!NOTE]
> 이 정책을 사용 하기 전에 장치가 호환 되는지 확인 합니다. 그렇지 않으면 사용자 계정이 조건부 액세스 제외 그룹에 추가 될 때까지이 정책을 잠그거나 변경할 수 없게 됩니다.

## <a name="next-step"></a>다음 단계

[![3 단계: 게스트 및 외부 사용자에 대 한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[게스트 및 외부 사용자에 대 한 정책 권장 사항에 대해 자세히 알아보기](identity-access-policies-guest-access.md)
