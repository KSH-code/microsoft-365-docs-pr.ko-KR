---
title: 일반 ID 및 장치 액세스 정책 - 엔터프라이즈 Microsoft 365 대한 | Microsoft Docs
description: 권장되는 일반 ID 및 장치 액세스 정책 및 구성에 대해 설명
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
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
ms.technology: mdo
ms.openlocfilehash: 1af399c8175a6e67bbf7e5e9e0a7f0900c4abd66
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963170"
---
# <a name="common-identity-and-device-access-policies"></a>일반 ID 및 장치 액세스 정책

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- Azure

이 문서에서는 Azure AD(응용 프로그램 프록시)와 함께 게시된 Microsoft 365 응용 프로그램을 포함하여 Microsoft 365 Azure Active Directory 보안에 대한 일반적인 권장 정책에 대해 설명합니다.

이 지침에서는 새로 프로비전된 환경에서 권장 정책을 배포하는 방법에 대해 논의합니다. 이러한 정책을 별도의 랩 환경에서 설정하면 사전 프로덕션 및 프로덕션 환경에 롤아웃을 준비하기 전에 권장 정책을 이해하고 평가할 수 있습니다. 새로 프로비전된 환경은 평가 요구 사항을 반영하기 위해 클라우드 전용 또는 하이브리드일 수 있습니다.

## <a name="policy-set"></a>정책 집합

다음 다이어그램에서는 권장되는 정책 집합을 보여 제공합니다. 이 매크로는 각 정책이 적용되는 보호 계층과 정책이 PC 또는 휴대폰 및 태블릿에 적용되는지 또는 두 장치 범주에 적용되는지 여부를 보여 주며, 또한 이러한 정책을 구성하는 위치도 나타냅니다.

[![ID 및 장치 액세스를 구성하기 위한 일반적인 정책입니다.](../../media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-device-access-policies-byplan.png)

다음은 개별 정책에 대한 링크가 있는 한 페이지 PDF 요약입니다.

[![ID 및 장치 보호를 위한 축소판 Microsoft 365 유인하십시오.](../../media/microsoft-365-policies-configurations/MSFT-cloud-architecture-identity-device-protection-handout.png)](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) <br> [PDF로 보기](../../downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf) \| [PDF로 다운로드](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/MSFT-cloud-architecture-identity-device-protection-handout.pdf)

이 문서의 나머지부분에서는 이러한 정책을 구성하는 방법에 대해 설명하고 있습니다.

> [!NOTE]
> 디바이스가 의도한 사용자를 소유하고 있도록 Intune에 장치를 등록하기 전에 MFA(다단계 인증)를 사용하는 것이 좋습니다. 장치 준수 정책을 적용하려면 먼저 Intune에 장치를 등록해야 합니다.

이러한 작업을 수행할 시간을 줄 수 있는 경우 이 표에 나열된 순서대로 기준 정책을 구현하는 것이 좋습니다. 그러나 중요하고 높은 규제 수준 보호 수준에 대한 MFA 정책은 어떤 경우든 구현할 수 있습니다.

|보호 수준|정책|추가 정보|라이선싱|
|---|---|---|---|
|**기준**|[로그인 위험이 중간 또는 높음인 경우 MFA *필요*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 추가 Microsoft 365 E3 또는 E5 보안 추가 기능을 사용할 수 있습니다.|
||[최신 인증을 지원하지 않는 클라이언트 차단](#block-clients-that-dont-support-multi-factor)|최신 인증을 사용하지 않는 클라이언트는 조건부 액세스 정책을 무시할 수 있으므로 이러한 정책을 차단하는 것이 중요합니다.|Microsoft 365 E3 혹은 E5|
||[위험이 높은 사용자는 암호를 변경해야 함](#high-risk-users-must-change-password)|계정에 대해 높은 위험 활동이 감지된 경우 사용자가 로그인할 때 암호를 강제로 변경합니다.|Microsoft 365 E5 추가 Microsoft 365 E3 또는 E5 보안 추가 기능을 사용할 수 있습니다.|
||[APP(응용 프로그램 보호 정책) 데이터 보호 적용](#apply-app-data-protection-policies)|플랫폼당 하나의 Intune 앱 보호 정책(Windows, iOS/iPadOS, Android).|Microsoft 365 E3 혹은 E5|
||[승인된 앱 및 앱 보호 필요](#require-approved-apps-and-app-protection)|iOS, iPadOS 또는 Android를 사용하여 휴대폰 및 태블릿에 대해 모바일 앱 보호를 적용합니다.|Microsoft 365 E3 혹은 E5|
||[장치 준수 정책 정의](#define-device-compliance-policies)|각 플랫폼에 대한 하나의 정책입니다.|Microsoft 365 E3 혹은 E5|
||[호환 PC 필요](#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Windows MACOS를 사용하여 PC의 Intune 관리를 적용합니다.|Microsoft 365 E3 혹은 E5|
|**중요**|[로그인 위험이 낮음, 보통 또는 높음인 경우 MFA *필요*](#require-mfa-based-on-sign-in-risk)||Microsoft 365 E5 추가 Microsoft 365 E3 또는 E5 보안 추가 기능을 사용할 수 있습니다.|
||[호환 PC 및 *모바일* 장치 필요](#require-compliant-pcs-and-mobile-devices)|PC(Windows 또는 macOS) 및 휴대폰 또는 태블릿(iOS, iPadOS 또는 Android)에 대해 Intune 관리를 적용합니다.|Microsoft 365 E3 혹은 E5|
|**매우 엄격한 규제**|[*항상* MFA 필요](#assigning-policies-to-groups-and-users)||Microsoft 365 E3 혹은 E5|
|

## <a name="assigning-policies-to-groups-and-users"></a>그룹 및 사용자에게 정책 할당

정책을 구성하기 전에 각 보호 계층에 사용 하는 Azure AD 그룹을 식별 합니다. 일반적으로 기준 보호는 조직의 모든 사용자에 적용됩니다. 기준 및 중요한 보호에 모두 포함된 사용자에게는 모든 기준 정책과 중요한 정책이 적용됩니다. 보호는 누적된 것이고 가장 제한적인 정책이 적용됩니다.

조건부 액세스 제외를 위한 Azure AD 그룹을 만드는 것이 좋습니다. 할당 섹션의 사용자 및 그룹 제외  값 설정에  있는 모든 조건부 액세스 정책에 이 **그룹을 추가합니다.** 이렇게 하면 액세스 문제를 해결하는 동안 사용자에게 액세스 권한을 제공하는 방법이 있습니다. 임시 솔루션으로만 권장됩니다. 이 그룹에서 변경 내용을 모니터링하고 제외 그룹이 의도한 것만 사용되고 있는지 확인

다음은 MFA를 요구하는 그룹 할당 및 제외의 예입니다.

![MFA 정책에 대한 그룹 할당 및 제외 예제](../../media/microsoft-365-policies-configurations/identity-access-policies-assignment.png)

결과는 다음과 같습니다.

- 로그인 위험이 중간 이상인 경우 모든 사용자는 MFA를 사용해야 합니다.

- Executive Staff 그룹의 구성원은 로그인 위험이 낮거나 보통 또는 높을 때 MFA를 사용해야 합니다.

  이 경우 Executive Staff 그룹의 구성원은 기준 및 중요한 조건부 액세스 정책과 일치합니다. 두 정책에 대한 액세스 제어가 결합되어 이 경우 중요한 조건부 액세스 정책과 동일합니다.

- 항상 MFA를 사용하려면 Project X 그룹의 구성원이 필요합니다.

  이 경우 Top Secret Project X 그룹의 구성원은 기준 및 높은 규제 조건부 액세스 정책 모두와 일치합니다. 두 정책에 대한 액세스 제어가 결합됩니다. 높은 규제 조건부 액세스 정책에 대한 액세스 제어가 더 제한적이기 때문에 사용됩니다.

그룹 및 사용자에게 더 높은 수준의 보호를 적용할 때 주의해야 합니다. 예를 들어 Top Secret Project X 그룹의 구성원은 로그인할 때마다 MFA를 사용해야 합니다. 이는 Project X에 대한 높은 규제 대상 콘텐츠에서 작동하지 않는 경우에도 해당됩니다.

이러한 권장 사항의 일부로 만들어진 모든 Azure AD 그룹은 해당 그룹으로 Microsoft 365 합니다. 이러한 구성은 사용자가 문서 및 문서의 문서를 보안할 때 민감도 레이블을 배포하는 Microsoft Teams SharePoint.

![Microsoft 365 예제입니다.](../../media/microsoft-365-policies-configurations/identity-device-AAD-groups.png)

## <a name="require-mfa-based-on-sign-in-risk"></a>로그인 위험에 따라 MFA 필요

사용을 요구하기 전에 사용자가 MFA에 등록하도록 해야 합니다. E5 보안 추가 Microsoft 365 E5 Microsoft 365 E3, EMS E5를 사용하는 Office 365 또는 개별 Azure AD Premium P2 라이선스를 사용하는 경우 Azure AD ID 보호와 함께 MFA 등록 정책을 사용하여 사용자가 MFA를 등록할 수 있도록 할 수 있습니다. 선행 [작업으로는](identity-access-prerequisites.md) 모든 사용자를 MFA에 등록하는 것이 포함됩니다.

사용자가 등록된 후 새 조건부 액세스 정책을 사용하여 로그인하기 위해 MFA를 요구할 수 있습니다.

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
2. Azure 서비스 목록에서 를 **Azure Active Directory.**
3. 관리 **목록에서** 보안 을 **선택한** 다음 조건부 **액세스 를 선택합니다.**
4. 새 **정책을 선택하고** 새 정책의 이름을 입력합니다.

다음 표에서는 로그인 위험에 따라 MFA를 요구하는 조건부 액세스 정책 설정에 대해 설명하고 있습니다.

배정 **섹션에서 다음을** 수행하십시오.

|설정|속성|값|참고|
|---|---|---|---|
|사용자 및 그룹|포함|**Select users and groups > Users and groups:** Select specific groups containing targeted user accounts.|파일럿 사용자 계정을 포함하는 그룹으로 시작하십시오.|
||제외|**사용자 및 그룹:** 조건부 액세스 예외 그룹을 선택합니다. 서비스 계정(앱 ID)|필요한 경우 임시로 구성원 자격을 수정해야 합니다.|
|클라우드 앱 또는 작업|**클라우드 앱 > 포함**|**앱 선택:** 이 정책을 적용할 앱을 선택합니다. 예를 들어 선택을 Exchange Online.||
|조건|||사용자 환경 및 요구에 따라 조건을 구성합니다.|
||로그인 위험||다음 표의 지침을 참조하세요.|
|

### <a name="sign-in-risk-condition-settings"></a>로그인 위험 조건 설정

대상으로 하는 보호 수준에 따라 위험 수준 설정을 적용합니다.

|보호 수준|필요한 위험 수준 값|작업|
|---|---|---|
|기준|높음, 중간|두 가지를 모두 검사합니다.|
|중요|높음, 중간, 낮음|세 가지를 모두 검사합니다.|
|매우 엄격한 규제||항상 MFA를 적용하기 위해 모든 옵션을 선택하지 않은 그대로 하세요.|
|

Access **컨트롤 섹션에서 다음을** 설명합니다.

|설정|속성|값|작업|
|---|---|---|---|
|권한 부여|**Grant access**||선택|
|||**다단계 인증 필요**|수표|
||**선택된 컨트롤이 모두 필요함**||선택|
|

**선택을** 선택하여 부여 설정을 **저장합니다.**

마지막으로 정책 **사용에 대해 을** **선택한** 다음 만들기 를 **선택합니다.**

What if 도구를 [사용하여](/azure/active-directory/active-directory-conditional-access-whatif) 정책을 테스트할 수 있습니다.

## <a name="block-clients-that-dont-support-multi-factor"></a>다단계를 지원하지 않는 클라이언트 차단

조건부 액세스 정책에 대한 다음 표의 설정을 사용하여 다단계 인증을 지원하지 않는 클라이언트를 차단합니다.

다단계 [인증을](../../enterprise/microsoft-365-client-support-multi-factor-authentication.md) 지원하는 Microsoft 365 클라이언트 목록은 이 문서를 참조하세요.

배정 **섹션에서 다음을** 수행하십시오.

|설정|속성|값|참고|
|---|---|---|---|
|사용자 및 그룹|포함|**Select users and groups > Users and groups:** Select specific groups containing targeted user accounts.|파일럿 사용자 계정을 포함하는 그룹으로 시작하십시오.|
||제외|**사용자 및 그룹:** 조건부 액세스 예외 그룹을 선택합니다. 서비스 계정(앱 ID)|필요한 경우 임시로 구성원 자격을 수정해야 합니다.|
|클라우드 앱 또는 작업|**클라우드 앱 > 포함**|**앱 선택:** 최신 인증을 지원하지 않는 클라이언트에 해당하는 앱을 선택합니다.||
|조건|**클라이언트 앱**|구성을 **위해 예를** **선택** <p> 브라우저 및 모바일  앱 및 데스크톱 **클라이언트에 대한 확인 표시 지우기**||
|

Access **컨트롤 섹션에서 다음을** 설명합니다.

|설정|속성|값|작업|
|---|---|---|---|
|권한 부여|**액세스 차단**||선택|
||**선택된 컨트롤이 모두 필요함**||선택|
|

**선택을** 선택하여 부여 설정을 **저장합니다.**

마지막으로 정책 **사용에 대해 을** **선택한** 다음 만들기 를 **선택합니다.**

[What if 도구를 사용하여](/azure/active-directory/active-directory-conditional-access-whatif) 정책을 테스트할 수 있습니다.

이 Exchange Online 정책으로 기본 인증을 [](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online)사용하지 않도록 설정할 수 있습니다. 이 경우 모든 클라이언트 액세스 요청에서 최신 인증을 강제로 사용할 수 있습니다.

## <a name="high-risk-users-must-change-password"></a>위험이 높은 사용자는 암호를 변경해야 함

로그인할 때 위험에 노출된 모든 사용자의 계정이 강제로 암호 변경을 수행하도록 보장하려면 다음 정책을 적용해야 합니다.

사용자의 관리자 자격 증명을 사용하여 [Microsoft Azure Portal(https://portal.azure.com)](https://portal.azure.com/)에 로그인한 다음 **Azure AD ID 보호 > 사용자 위험 정책** 으로 이동합니다.

배정 **섹션에서 다음을** 수행하십시오.

|유형|속성|값|작업|
|---|---|---|---|
|사용자|포함|**모든 사용자**|선택|
|사용자 위험|**High**||선택|
|

두 번째 **배정 섹션에서 다음을** 수행하십시오.

|유형|속성|값|작업|
|---|---|---|---|
|접근|**액세스 허용**||선택|
|||**암호 변경 필요**|수표|
|

**완료를** 선택하고 액세스 설정을 **저장합니다.**

마지막으로, **정책 적용에 대해 을** **선택한** 다음 저장 을 **선택합니다.**

[What if 도구를 사용하여](/azure/active-directory/active-directory-conditional-access-whatif) 정책을 테스트할 수 있습니다.

이 정책을 Azure [AD](/azure/active-directory/authentication/concept-password-ban-bad)암호 보호 구성과 함께 사용하여 알려진 약한 암호와 해당 변형 및 조직과 관련한 약한 용어를 검색하고 차단합니다. Azure AD 암호 보호를 사용하면 변경된 암호가 강력한 암호가 됩니다.

## <a name="apply-app-data-protection-policies"></a>APP 데이터 보호 정책 적용

APP는 허용되는 앱과 조직의 데이터에 대해 수행할 수 있는 작업을 정의합니다. APP에서 사용할 수 있는 선택을 통해 조직은 특정 요구에 맞게 보호를 조정할 수 있습니다. 일부 경우에는 완전한 시나리오를 구현하는 데 어떤 정책 설정이 필요한지 명확하지 않을 수 있습니다. 조직에서 모바일 클라이언트 엔드포인트 강화의 우선 순위를 지정하는 데 도움을 주기 위해 Microsoft는 iOS 및 Android 모바일 앱 관리를 위한 APP 데이터 보호 프레임워크에 대한 분류를 도입했습니다.

APP 데이터 보호 프레임워크는 다음과 같은 세 가지 구성 수준으로 구성되며 각 수준은 이전 수준을 기반으로 합니다.

- **엔터프라이즈 기본 데이터 보호**(레벨 1)는 앱이 PIN 및 암호화로 보호되고 선택적 초기화 작업을 수행하도록 합니다. Android 디바이스의 경우, 이 수준은 Android 디바이스 증명의 유효성을 검사합니다. Exchange Online 사서함 정책에서 유사한 데이터 보호 제어 기능을 제공하고 IT 및 사용자 인구를 APP에 도입하는 엔트리 레벨 구성입니다.
- **엔터프라이즈 강화된 데이터 보호**(레벨 2)는 APP 데이터 누출 방지 메커니즘과 최소 OS 요구 사항을 도입합니다. 이 구성은 직장 또는 학교 데이터에 액세스하는 대부분의 모바일 사용자에게 적용됩니다.
- **엔터프라이즈 고급 데이터 보호**(레벨 3)는 고급 데이터 보호 메커니즘, 향상된 PIN 구성 및 APP 모바일 위협 방어를 도입합니다. 이 구성은 위험 수준이 높은 데이터에 액세스하는 사용자에게 적합합니다.

각 구성 레벨 및 보호해야 하는 최소 앱에 대한 구체적인 권장 사항을 보려면 [앱 보호 정책을 사용하는 데이터 보호 프레임워크](/mem/intune/apps/app-protection-framework)를 검토하세요.

[ID](microsoft-365-policies-configurations.md)및 장치 액세스 구성에 설명된 원칙을 사용하여 기준 및 중요한 보호 계층은 수준 2 엔터프라이즈 향상된 데이터 보호 설정과 밀접하게 매핑됩니다. 높은 규제 대상 보호 계층은 수준 3 엔터프라이즈 높은 데이터 보호 설정에 밀접하게 매핑됩니다.

|보호 수준|앱 보호 정책|추가 정보|
|---|---|---|
|기준|[수준 2 향상된 데이터 보호](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|수준 2에 적용된 정책 설정에는 수준 1에 권장되는 모든 정책 설정이 포함되고 수준 1보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.|
|중요|[수준 2 향상된 데이터 보호](/mem/intune/apps/app-protection-framework#level-2-enterprise-enhanced-data-protection)|수준 2에 적용된 정책 설정에는 수준 1에 권장되는 모든 정책 설정이 포함되고 수준 1보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.|
|높은 규제|[수준 3 엔터프라이즈 높은 데이터 보호](/mem/intune/apps/app-protection-framework#level-3-enterprise-high-data-protection)|수준 3에 적용된 정책 설정에는 수준 1 및 2에 권장되는 모든 정책 설정이 포함되고, 수준 2보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.|
|

데이터 보호 프레임워크 설정을 사용하여 Microsoft Endpoint Manager 각 플랫폼(iOS 및 Android)에 대해 새 앱 보호 정책을 만들 수 있습니다.

1. 를 사용하여 앱 보호 정책을 만들고 배포하는 방법의 단계에 따라 정책을 [Microsoft Intune.](/mem/intune/apps/app-protection-policies)
2. [Intune의](https://github.com/microsoft/Intune-Config-Frameworks/tree/master/AppProtectionPolicies) PowerShell 스크립트를 사용하여 샘플 [Intune](https://github.com/microsoftgraph/powershell-intune-samples)앱 보호 정책 Configuration Framework JSON 템플릿을 가져올 수 있습니다.

## <a name="require-approved-apps-and-app-protection"></a>승인된 앱 및 APP 보호 필요

Intune에서 적용한 APP 보호 정책을 적용하려면 승인된 클라이언트 앱 및 APP 보호 정책에 설정된 조건을 요구하는 조건부 액세스 정책을 만들어야 합니다.

앱 보호 정책을 적용하려면 조건부 액세스를 통해 클라우드 앱 액세스에 대한 앱 보호 정책 필요에 설명된 정책 [집합이 필요합니다.](/azure/active-directory/conditional-access/app-protection-based-conditional-access) 이러한 정책은 각각 이 권장 ID 및 액세스 구성 정책 집합에 포함되어 있습니다.

승인된 앱 및 앱 보호가 필요한 조건부 액세스 정책을 만들려면 시나리오 [1: Microsoft 365](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies)앱에 iOS 및 Android용 Outlook 허용하는 앱 보호 정책이 있는 승인된 앱이 필요하지만 OAuth 기능을 차단하는 시나리오 1: Microsoft 365에 대한 Azure AD 조건부 액세스 정책 구성"을 따르하세요. Exchange ActiveSync 클라이언트가 연결되지 Exchange Online.

   > [!NOTE]
   > 이 정책은 모바일 사용자가 해당 앱을 사용하여 모든 Office 끝점에 액세스할 수 있도록 합니다.

모바일 응용 Exchange Online 사용하도록 설정하는 경우 기본 인증을 활용하는 Exchange ActiveSync 클라이언트가 클라이언트에 연결하지 못하도록 차단 [ActiveSync](secure-email-recommended-policies.md#block-activesync-clients)클라이언트를 Exchange Online. 이 정책은 이 문서 맨 위에 있는 그림에 설명되지 않습니다. 전자 메일 보안에 대한 정책 권장 사항에 설명되어 있으며 [그림에 설명되어 있습니다.](secure-email-recommended-policies.md)

iOS 및 Android용 Edge가 필요한 조건부 액세스 정책을 만들려면 시나리오 [2:](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-2-browser-apps-require-approved-apps-with-app-protection-policies)브라우저 앱에 iOS 및 Android용 Edge를 허용하지만 다른 모바일 장치 웹 브라우저가 Microsoft 365 끝점에 연결하지는 차단하는 앱 보호 정책을 사용하여 승인된 앱이 필요합니다.에서 "2단계: Microsoft 365 Azure AD 조건부 액세스 정책 구성"을 따르십시오.

 이러한 정책은 승인된 클라이언트 앱 필요 및 앱 보호 정책 필요 [제어를](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) [활용합니다.](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy)

마지막으로 iOS 및 Android 장치에서 다른 클라이언트 앱에 대한 레거시 인증을 차단하면 이러한 클라이언트가 조건부 액세스 정책을 무시할 수 없습니다. 이 문서의 지침을 따라야 하는 경우 최신 인증을 지원하지 않는 클라이언트 차단을 이미 [구성한 것입니다.](#block-clients-that-dont-support-multi-factor)

<!---
With Conditional Access, organizations can restrict access to approved (modern authentication capable) iOS and Android client apps with Intune app protection policies applied to them. Several Conditional Access policies are required, with each policy targeting all potential users. Details on creating these policies can be found in [Require app protection policy for cloud app access with Conditional Access](/azure/active-directory/conditional-access/app-protection-based-conditional-access).

1. Follow "Step 1: Configure an Azure AD Conditional Access policy for Microsoft 365" in [Scenario 1: Microsoft 365 apps require approved apps with app protection policies](/azure/active-directory/conditional-access/app-protection-based-conditional-access#scenario-1-office-365-apps-require-approved-apps-with-app-protection-policies), which allows Outlook for iOS and Android, but blocks OAuth capable Exchange ActiveSync clients from connecting to Exchange Online.

   > [!NOTE]
   > This policy ensures mobile users can access all Office endpoints using the applicable apps.

2. If enabling mobile access to Exchange Online, implement [Block ActiveSync clients](secure-email-recommended-policies.md#block-activesync-clients), which prevents Exchange ActiveSync clients leveraging basic authentication from connecting to Exchange Online.

   The above policies leverage the grant controls [Require approved client app](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-approved-client-app) and [Require app protection policy](/azure/active-directory/conditional-access/concept-conditional-access-grant#require-app-protection-policy).

3. Disable legacy authentication for other client apps on iOS and Android devices. For more information, see [Block clients that don't support modern authentication](#block-clients-that-dont-support-modern-authentication).
-->

## <a name="define-device-compliance-policies"></a>장치 준수 정책 정의

장치 준수 정책은 장치가 준수로 결정하기 위해 충족해야 하는 요구 사항을 정의합니다. 관리 센터 내에서 Intune 장치 준수 정책을 Microsoft Endpoint Manager 있습니다.

각 PC, 휴대폰 또는 태블릿 플랫폼에 대한 정책을 만들어야 합니다.

- Android 장치 관리자
- Android Enterprise
- iOS/iPadOS
- macOS
- Windows 8.1 이상
- Windows 10 이상

장치 준수 정책을 만들하려면 관리자 자격 [증명으로 Microsoft Endpoint Manager](https://endpoint.microsoft.com) 관리 센터에 로그인한  다음 장치 준수 정책 \> **으로** \> **이동합니다.** **정책 만들기** 를 선택합니다.

장치 준수 정책을 배포하려면 사용자 그룹에 할당해야 합니다. 정책을 만들고 저장한 후 정책을 할당합니다. 관리 센터에서 정책을 선택하고 할당 **을 선택합니다.** 정책을 받을 그룹을 선택한 후 저장을 선택하여  해당 그룹 할당을 저장하고 정책을 배포합니다.

Intune에서 규정 준수 정책을 만드는 방법에 대한 단계별 지침은 Intune 설명서의 [Microsoft Intune](/mem/intune/protect/create-compliance-policy) 규정 준수 정책 만들기를 참조하세요.

### <a name="recommended-settings-for-ios"></a>iOS에 대한 권장 설정

iOS/iPadOS는 몇 가지 등록 시나리오를 지원합니다. 이 중 2개는 이 프레임워크의 일부로 설명됩니다.

- [개인 소유 장치에](/mem/intune/enrollment/ios-enroll) 대한 장치 등록 - 이러한 장치는 개인적으로 소유하며 업무 및 개인용 모두에 사용됩니다.
- [회사 소유 장치에](/mem/intune/enrollment/device-enrollment-program-enroll-ios) 대한 관리되는 자동화된 장치 등록 - 이러한 장치는 회사 소유의 장치로, 단일 사용자와 연결되고, 업무 전용으로 사용하며 개인적으로 사용되지 않습니다.

iOS/iPadOS 보안 구성 프레임워크는 여러 가지 고유한 구성 시나리오로 구성되어 개인 소유 및 감독 장치에 대한 지침을 제공합니다.

개인 소유 디바이스의 경우:

- 기본 보안(수준 1) - 사용자가 직장 또는 학교 데이터에 액세스하는 개인 장치에 대한 최소 보안 구성으로 이 구성을 권장합니다. 이 수행은 암호 정책, 장치 잠금 특성을 적용하고 특정 장치 기능(예: 인증되지 않은 인증서)을 해제하여 수행됩니다.
- 향상된 보안(수준 2) - 사용자가 중요한 정보 또는 기밀 정보에 액세스하는 장치에 대해 이 구성을 권장합니다. 이 구성은 데이터 공유 컨트롤을 제정합니다. 이 구성은 장치의 직장 또는 학교 데이터에 액세스하는 대부분의 모바일 사용자에게 적용할 수 있습니다.
- 높은 보안(수준 3) - Microsoft는 고유하게 높은 위험인 특정 사용자 또는 그룹이 사용하는 장치에 이 구성을 권장합니다(권한이 없는 공개로 인해 조직에 상당한 실질적인 손실을 일으키는 매우 중요한 데이터를 처리하는 사용자). 이 구성은 더 강력한 암호 정책을 제정하고, 특정 장치 기능을 사용하지 않도록 설정하며, 추가 데이터 전송 제한을 적용합니다.

감독되는 장치의 경우:

- 기본 보안(수준 1) - 사용자가 직장 또는 학교 데이터에 액세스하는 감독되는 장치에 대한 최소 보안 구성으로 이 구성을 권장합니다. 이 수행은 암호 정책, 장치 잠금 특성을 적용하고 특정 장치 기능(예: 인증되지 않은 인증서)을 해제하여 수행됩니다.
- 향상된 보안(수준 2) - 사용자가 중요한 정보 또는 기밀 정보에 액세스하는 장치에 대해 이 구성을 권장합니다. 이 구성은 데이터 공유 컨트롤을 제정하고 USB 장치에 대한 액세스를 차단합니다. 이 구성은 장치의 직장 또는 학교 데이터에 액세스하는 대부분의 모바일 사용자에게 적용할 수 있습니다.
- 높은 보안(수준 3) - Microsoft는 고유하게 높은 위험인 특정 사용자 또는 그룹이 사용하는 장치에 이 구성을 권장합니다(권한이 없는 공개로 인해 조직에 상당한 실질적인 손실을 일으키는 매우 중요한 데이터를 처리하는 사용자). 이 구성은 더 강력한 암호 정책을 제정하고, 특정 장치 기능을 사용하지 않도록 설정하고, 추가 데이터 전송 제한을 적용하며, Apple의 볼륨 구매 프로그램을 통해 앱을 설치해야 합니다.

[ID](microsoft-365-policies-configurations.md)및 장치 액세스 구성에 설명된 원칙을 사용하여 기준 및 중요한 보호 계층은 수준 2 강화 보안 설정과 밀접하게 매핑됩니다. 높은 규제 대상 보호 계층은 수준 3 높은 보안 설정에 밀접하게 매핑됩니다.

|보호 수준  |장치 정책 |추가 정보  |
|---------|---------|---------|
|기준     |향상된 보안(수준 2)         |수준 2에 적용된 정책 설정에는 수준 1에 권장되는 모든 정책 설정이 포함되고 수준 1보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.         |
|중요     |향상된 보안(수준 2)         |수준 2에 적용된 정책 설정에는 수준 1에 권장되는 모든 정책 설정이 포함되고 수준 1보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.         |
|높은 규제     |높은 보안(수준 3)         |수준 3에 적용된 정책 설정에는 수준 1 및 2에 권장되는 모든 정책 설정이 포함되고, 수준 2보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.         |

각 구성 수준에 대한 특정 장치 준수 및 장치 제한 권장 사항을 확인하려면 [iOS/iPadOS 보안 구성 프레임워크를 검토하세요.](/mem/intune/enrollment/ios-ipados-configuration-framework)

### <a name="recommended-settings-for-android"></a>Android에 대한 권장 설정

Android Enterprise 몇 가지 등록 시나리오를 지원합니다. 이 중 두 가지는 이 프레임워크의 일부로 설명됩니다.

- [Android Enterprise](/intune/android-work-profile-enroll) 프로필 - 이 등록 모델은 일반적으로 IT가 업무 데이터와 개인 데이터 간에 명확한 분리 경계를 제공하려는 개인 소유 장치에 사용됩니다. IT에서 제어하는 정책은 작업 데이터를 개인 프로필로 전송할 수 없습니다.
- [Android Enterprise 완전히](/intune/android-fully-managed-enroll) 관리되는 장치 - 이러한 디바이스는 회사 소유의 장치로, 단일 사용자와 연결되고, 업무 전용으로 사용하며 개인적으로 사용되지 않습니다.

Android Enterprise 보안 구성 프레임워크는 여러 가지 고유한 구성 시나리오로 구성되어 작업 프로필 및 완전히 관리되는 시나리오에 대한 지침을 제공합니다.

Android Enterprise 프로필 장치의 경우:

- 작업 프로필 보안 강화(수준 2) – 사용자가 직장 또는 학교 데이터에 액세스하는 개인 장치에 대한 최소 보안 구성으로 이 구성을 권장합니다. 이 구성은 암호 요구 사항을 도입하고, 작업 및 개인 데이터를 분리하며, Android 장치 인증의 유효성을 검사합니다.
- 작업 프로필 높은 보안(수준 3) - Microsoft는 고유하게 높은 위험인 특정 사용자 또는 그룹이 사용하는 장치에 이 구성을 권장합니다(권한이 없는 공개로 인해 조직에 상당한 중요한 자료 손실을 일으키는 매우 중요한 데이터를 처리하는 사용자). 이 구성은 모바일 위협 방어 또는 끝점용 Microsoft Defender를 도입하고, 최소 Android 버전을 설정하고, 보다 강력한 암호 정책을 제정하며, 작업 및 개인 분리를 추가로 제한합니다.

Android Enterprise 완전 관리형 디바이스의 경우:

- 완전히 관리되는 기본 보안(수준 1) - 엔터프라이즈 장치에 대한 최소 보안 구성으로 이 구성을 권장합니다. 이 구성은 직장 또는 학교 데이터에 액세스하는 대부분의 모바일 사용자에게 적용할 수 있습니다. 이 구성은 암호 요구 사항을 도입하고, 최소 Android 버전을 설정하고, 특정 장치 제한을 제정합니다.
- 완전히 관리되는 보안(수준 2) - 사용자가 중요한 정보 또는 기밀 정보에 액세스하는 장치에 대해 이 구성을 권장합니다. 이 구성은 더 강력한 암호 정책을 제정하고 사용자/계정 기능을 사용하지 않도록 합니다.
- 완전히 관리되는 높은 보안(수준 3) - Microsoft는 고유하게 높은 위험인 특정 사용자 또는 그룹이 사용하는 장치에 이 구성을 권장합니다(무단 공개로 인해 조직에 상당한 상당한 실질적인 손실을 일으키는 매우 중요한 데이터를 처리하는 사용자). 이 구성은 최소 Android 버전을 증가하고, 모바일 위협 방어 또는 끝점용 Microsoft Defender를 도입하고, 추가 장치 제한을 적용합니다.

[ID](microsoft-365-policies-configurations.md)및 장치 액세스 구성에 설명된 원칙을 사용하여 기준 및 중요한 보호 계층은 개인 소유 장치에 대한 수준 2 강화 보안 및 완전히 관리되는 장치에 대한 수준 2 향상된 보안 설정과 밀접하게 매핑됩니다. 높은 규제 대상 보호 계층은 수준 3 높은 보안 설정에 밀접하게 매핑됩니다.

Android Enterprise 프로필 장치의 경우:

|보호 수준  |장치 정책 |추가 정보  |
|---------|---------|---------|
|기준     |작업 프로필: 향상된 보안(수준 2)      |해당 없음         |
|중요     |작업 프로필: 향상된 보안(수준 2)         |해당 없음         |
|기준     |완전히 관리: 향상된 보안(수준 2)       |수준 2에 적용된 정책 설정에는 수준 1에 권장되는 모든 정책 설정이 포함되고 수준 1보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.         |
|중요     |완전히 관리: 향상된 보안(수준 2)         |수준 2에 적용된 정책 설정에는 수준 1에 권장되는 모든 정책 설정이 포함되고 수준 1보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.         |
|높은 규제     |높은 보안(수준 3)         |수준 3에 적용된 정책 설정에는 수준 1 및 2에 권장되는 모든 정책 설정이 포함되고, 수준 2보다 더 많은 컨트롤 및 보다 정교한 구성을 구현하기 위해 아래 정책 설정만 추가하거나 업데이트합니다.         |

각 구성 수준에 대한 특정 장치 준수 및 장치 제한 권장 사항을 확인하려면 Android Enterprise [보안 구성 프레임워크를 검토하세요.](/mem/intune/enrollment/android-configuration-framework)

### <a name="recommended-settings-for-windows-10-and-later"></a>Windows 10 이상에 대한 권장 설정

정책 만들기 프로세스의 **2단계:** 준수 설정에 Windows 10 이상으로 실행되는 PC에는 다음 설정을 권장합니다.

장치 상태 > Windows 상태 설명 서비스 평가 **규칙은** 다음 표를 참조하세요.

|속성|값|작업|
|---|---|---|
|BitLocker 필요|필요|선택|
|디바이스에서 보안 부팅을 사용하도록 설정해야 합니다.|필요|선택|
|코드 무결성 필요|필요|선택|
|

장치 **속성의 경우** IT 및 보안 정책에 따라 운영 체제 버전에 적절한 값을 지정합니다.

**Configuration Manager 규정 준수의** 경우 필요 를 **선택합니다.**

시스템 **보안에 대한 자세한** 내용은 다음 표를 참조합니다.

|유형|속성|값|작업|
|---|---|---|---|
|암호|모바일 장치의 잠금을 해제하려면 암호 필요|필요|선택|
||단순 암호|차단|선택|
||암호 유형|장치 기본값|선택|
||최소 암호 길이|6 |유형|
||암호가 필요하기 전 최대 비활성 시간(분)|15 |유형 <p> 이 설정은 Android 버전 4.0 이상 또는 KNOX 4.0 이상에서 지원됩니다. iOS 장치의 경우 iOS 8.0 이상에서 지원됩니다.|
||암호 만료(일)|41|유형|
||재사용을 방지하기 위한 이전 암호 수|5|유형|
||장치가 유휴 상태(모바일 및 홀로그램)에서 반환되는 경우 암호 필요|필요|추가 Windows 10 사용할 수 있습니다.|
|암호화|디바이스의 데이터 저장소 암호화|필요|선택|
|장치 보안|방화벽|필요|선택|
||바이러스 검사|필요|선택|
||스파이웨어 방지|필요|선택 <p> 이 설정을 사용하려면 Windows 보안 등록된 스파이웨어 방지 솔루션이 필요합니다.|
|Defender|Microsoft Defender 맬웨어 방지 프로그램|필요|선택|
||Microsoft Defender 맬웨어 방지 최소 버전||유형 <p> 데스크톱에서만 Windows 10 지원됩니다. 최신 버전에서는 버전이 5를 넘지 않습니다.|
||Microsoft Defender 맬웨어 방지 서명 최신|필요|선택|
||실시간 보호|필요|선택 <p> 데스크톱에서만 Windows 10 지원|
|

#### <a name="microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender

|유형|속성|값|작업|
|---|---|---|---|
|Microsoft Endpoint Manager 관리 센터의 끝점용 Microsoft Defender 규칙|[장치가 컴퓨터 위험 점수에 또는 그 미만이 되거나,](/mem/intune/protect/advanced-threat-protection-configure#create-and-assign-compliance-policy-to-set-device-risk-level)|보통|선택|
|

## <a name="require-compliant-pcs-but-not-compliant-phones-and-tablets"></a>호환 PC 필요(호환되지 않는 휴대폰 및 태블릿)

호환 PC를 요구하는 정책을 추가하기 전에 Intune에서 관리를 위해 장치를 등록해야 합니다. 디바이스가 의도한 사용자를 소유하고 있는지 확인하려면 Intune에 장치를 등록하기 전에 다단계 인증을 사용하는 것이 좋습니다.

규격 PC를 요구하려면:

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
2. Azure 서비스 목록에서 를 **Azure Active Directory.**
3. 관리 **목록에서** 보안 을 **선택한** 다음 조건부 **액세스 를 선택합니다.**
4. 새 **정책을 선택하고** 새 정책의 이름을 입력합니다.

5. 할당에서 사용자 및 **그룹을 선택하고** 정책을 적용할 사용자를 포함합니다.  조건부 액세스 제외 그룹도 제외합니다.

6. 할당에서 클라우드 앱 **또는 작업을 선택하세요.** 

7. 포함에서 **앱** 선택을 선택하고 > 를 선택한 다음 클라우드 앱 목록에서 원하는 **앱을** 선택합니다.  예를 들어 선택을 Office 365. 완료되면 **선택을** 선택합니다.

8. 호환되는 PC(하지만 호환되는 휴대폰 및 태블릿은 아미라)를 요구하려면 **할당에서** 장치 플랫폼에 대한 > **선택하세요.** 구성에 **대해 예를** **선택합니다.** Select **device platforms(장치 플랫폼** 선택)을 선택하고 **Yes(예)를** 선택하고 **Any device(모든** 장치)를 선택하고 Exclude select iOS and **Android(iOS** 및 Android 선택) **에서** Done(완료)을 **선택합니다.**

9. 액세스 **제어에서** 부여를 **선택 합니다.**

10. 액세스 **권한 부여를** 선택한 다음 장치가 규격으로 표시 **하도록 요구를 확인합니다.** 여러 컨트롤의 경우 선택한 모든 **컨트롤 필요를 선택합니다.** 완료되면 선택 **을 선택합니다.**

11. 정책 **사용에** **대해 을** 선택한 다음 만들기 를 **선택합니다.**

> [!NOTE]
> 이 정책을 사용하도록 설정하기 전에 장치가 규격으로 설정되어 있는지 확인합니다. 그렇지 않으면 잠겨 있을 수 있으며 사용자 계정이 조건부 액세스 제외 그룹에 추가될 때까지 이 정책을 변경할 수 없습니다.

## <a name="require-compliant-pcs-and-mobile-devices"></a>호환 PC 및 *모바일* 장치 필요

모든 장치에 대한 준수를 요구하려면:

1. [Azure Portal](https://portal.azure.com)로 이동한 다음 자격 증명을 사용하여 로그인합니다.
2. Azure 서비스 목록에서 를 **Azure Active Directory.**
3. 관리 **목록에서** 보안 을 **선택한** 다음 조건부 **액세스 를 선택합니다.**
4. 새 **정책을 선택하고** 새 정책의 이름을 입력합니다.

5. 할당에서 사용자 및 **그룹을 선택하고** 정책을 적용할 사용자를 포함합니다.  조건부 액세스 제외 그룹도 제외합니다.

6. 할당에서 클라우드 앱 **또는 작업을 선택하세요.** 

7. 포함에서 **앱** 선택을 선택하고 > 를 선택한 다음 클라우드 앱 목록에서 원하는 **앱을** 선택합니다.  예를 들어 선택을 Office 365. 완료되면 **선택을** 선택합니다.

8. 액세스 **제어에서** 부여를 **선택 합니다.**

9. 액세스 **권한 부여를** 선택한 다음 장치가 규격으로 표시 **하도록 요구를 확인합니다.** 여러 컨트롤의 경우 선택한 모든 **컨트롤 필요를 선택합니다.** 완료되면 선택 **을 선택합니다.**

10. 정책 **사용에** **대해 을** 선택한 다음 만들기 를 **선택합니다.**

> [!NOTE]
> 이 정책을 사용하도록 설정하기 전에 장치가 규격으로 설정되어 있는지 확인합니다. 그렇지 않으면 잠겨 있을 수 있으며 사용자 계정이 조건부 액세스 제외 그룹에 추가될 때까지 이 정책을 변경할 수 없습니다.

## <a name="next-step"></a>다음 단계

[![3단계: 게스트 및 외부 사용자에 대한 정책](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-3.png)](identity-access-policies-guest-access.md)

[게스트 및 외부 사용자에 대한 정책 권장 사항에 대해 자세히 알아보기](identity-access-policies-guest-access.md)
