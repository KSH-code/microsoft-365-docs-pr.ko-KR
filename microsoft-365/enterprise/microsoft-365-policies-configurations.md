---
title: Id 및 장치 액세스 구성-Microsoft 365 for enterprise
description: 보안 전자 메일, 문서 및 앱 정책 및 구성을 배포 하기 위한 Microsoft 권장 사항 및 핵심 개념에 대해 설명 합니다.
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
ms.openlocfilehash: e76ed8869f2e3bc3198eeff6dc4fcec777d0ce26
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898167"
---
# <a name="identity-and-device-access-configurations"></a>ID 및 장치 액세스 구성

이 문서 시리즈에서는 규정 된 조건부 액세스 정책 및 관련 기능 집합을 비롯 하 여 권장 되는 환경 및 구성을 구현 하 여 EMS (Enterprise Mobility + Security) 제품을 통해 클라우드 서비스에 대 한 보안 액세스를 구성 하는 방법을 설명 합니다. EMS는 Microsoft 365의 핵심 구성 요소입니다. 이 지침을 사용 하 여 Microsoft 365 서비스, 기타 SaaS 서비스 및 Azure AD 응용 프로그램 프록시를 통해 게시 된 온-프레미스 응용 프로그램을 비롯 하 여 Azure Active Directory와 통합 되는 모든 서비스에 대 한 액세스를 보호할 수 있습니다. 

이러한 권장 사항은 Microsoft 보안 점수 및 [AZURE AD의 id 점수](https://docs.microsoft.com/azure/active-directory/fundamentals/identity-secure-score)와 맞추고 조직에 대해 이러한 점수가 증가 합니다. 이러한 권장 사항은 다음 [다섯 단계를](https://docs.microsoft.com/azure/security/azure-ad-secure-steps)구현 하 여 id 인프라를 보호 하는 데도 도움이 됩니다. 

Microsoft는 일부 조직이 고유한 환경 요구 사항이 나 복잡성을 갖는 것을 이해 하 고 있습니다. 이러한 조직 중 하나에 해당 하는 경우에는 이러한 권장 사항을 출발점으로 사용 합니다. 그러나 대부분의 조직은 이러한 권장 사항을 규정 된 대로 구현할 수 있습니다. 

## <a name="intended-audience"></a>대상 그룹

이러한 권장 사항은 [Office 365](https://docs.microsoft.com/microsoft-365/admin) 및 [microsoft Enterprise Mobility + Security](https://microsoft.com/ems)에 익숙하고, azure Active Directory (Identity), microsoft Intune (장치 관리) 및 azure Information protection (데이터 보호)을 포함 하는 엔터프라이즈 설계자 및 IT 전문가를 위한 것입니다.

### <a name="customer-environment"></a>고객 환경

권장 정책은 전적으로 Microsoft 클라우드 내에서 운영 하는 엔터프라이즈 조직이 나 하이브리드 인프라를 사용 하는 고객에 게 적용 됩니다 (온-프레미스와 Microsoft 클라우드 모두에 배포 됨).

제공 되는 추천 항목 대부분은 EMS (Enterprise Mobility + Security) E5 라이선스 에서만 사용할 수 있는 서비스를 사용 합니다. 권장 사항은 전체 EMS E5 라이선스 기능을 사용 하는 것입니다.

Enterprise Mobility + Security E5 라이선스가 없는 조직의 경우에는 모든 요금제에 포함 된 Azure AD 기본 보호 기능을 최소한 구현 하는 것이 좋습니다. 자세한 내용은 Azure AD 라이브러리의 [기준 보호 란](/azure/active-directory/active-directory-conditional-access-baseline-protection)문서에 나와 있습니다.

### <a name="caveats"></a>유의할

조직은 이러한 권장 구성에서 분기 하는 정책을 적용 해야 하는 특정 권장 사항을 비롯 하 여 규정 또는 기타 준수 요구 사항이 적용 될 수 있습니다. 이러한 구성은 지금까지 사용할 수 없었던 사용 제어를 권장합니다. 이러한 컨트롤은 보안과 생산성 간의 균형을 나타내는 것으로 생각 되므로 권장 합니다.  

다양 한 조직의 보호 요구 사항을 고려 하는 것이 가장 좋지만, 이러한 모든 요구 사항을 고려 하거나 조직의 모든 고유한 측면에 대해 설명할 수는 없습니다.

## <a name="three-tiers-of-protection"></a>3 계층의 보호

대부분의 조직은 보안 및 데이터 보호에 관한 구체적 요구 사항을 가지고 있습니다. 이러한 요구 사항은 산업 부문 및 조직 내의 직무 기능에 따라 달라집니다. 예를 들어 법률 부서 및 관리자가 다른 사업부 사용자에 게 필요 하지 않은 전자 메일 서신에 대 한 추가 보안 및 정보 보호 제어를 요구할 수 있습니다. 

또한 각 산업마다 자체의 전문화된 규정을 가지고 있습니다. 모든 가능한 보안 옵션 또는 업계 부문 별 권장 사항에 대 한 목록을 제공 하는 대신, 요구 사항의 세분성에 따라 적용할 수 있는 세 가지 보안 및 보호 계층에 대 한 권장 사항이 제공 됩니다.

- **기본 보호**: 데이터를 보호 하는 데 필요한 최소 표준과 데이터에 액세스 하는 id 및 장치를 설정 하는 것이 좋습니다. 이러한 기본 권장 사항을 따르면 많은 조직의 요구를 충족 하는 강력한 기본 보호 기능을 제공할 수 있습니다.
- **중요 보호**: 일부 고객에 게는 높은 수준으로 보호 해야 하는 데이터의 하위 집합이 있거나, 모든 데이터가 더 높은 수준으로 보호 되어야 할 수 있습니다. Microsoft 365 환경에서 모든 또는 특정 데이터 집합에 대해 향상 된 보호를 적용할 수 있습니다. 중요 데이터에 액세스하는 ID와 장치를 유사한 보안 수준으로 보호하는 것이 좋습니다.  
- **높은 규제**: 일부 조직에는 고도로 분류 되 고 영업 비밀이 구성 되거나 데이터를 규제 하는 소량의 데이터가 있을 수 있습니다. Microsoft는 ID와 장치에 대한 추가된 보호를 포함하여 조직이 이러한 요구 사항을 충족하는 데 도움이 되는 기능을 제공합니다.

![보안 원뿔형-일부 고객이 특정 고객을 > > 모든 고객입니다. 특정 응용 프로그램에 대 한 광범위 한 응용 프로그램](../media/M365-idquality-threetiers.png)

이 가이드에서는 이러한 각 보호 계층에 대 한 id 및 장치에 대 한 보호를 구현 하는 방법을 보여 줍니다. 이 가이드를 조직의 시작 지점으로 사용 하 고 조직의 특정 요구 사항에 맞게 정책을 조정 합니다.

데이터, ID 및 장치 전반에 걸쳐 일관된 보호 수준을 사용하는 것이 중요합니다. 예를 들어이 지침을 구현 하는 경우에는 비슷한 수준에서 데이터를 보호 해야 합니다. 

**Office 365 아키텍처 모델에 대 한 id 및 장치 보호** 를 통해 비교 가능한 기능을 확인할 수 있습니다.

![포스터 축소판 그림 "Office 365에 대 한 Id 및 장치 보호"](../media/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [더 많은 언어](https://www.microsoft.com/download/details.aspx?id=55032)

또한 Microsoft 365에 저장 된 정보를 보호 하기 위해 [데이터 개인 정보 보호 규정 솔루션 배포](../solutions/information-protection-deploy.md) 를 참조 하세요.

## <a name="security-and-productivity-trade-offs"></a>보안과 생산성의 절충

보안 전략을 구현 하려면 보안과 생산성 간의 절충을 수행 해야 합니다. 각 의사 결정이 보안, 기능 및 사용 편이성의 균형에 미치는 영향을 평가 하는 것이 좋습니다.

![보안 cia 균형 조정 보안, 기능 및 간편한 사용](../media/policies-configurations/security-triad.png)

제공 되는 권장 사항은 다음과 같은 원칙을 기반으로 합니다.

- 대상 그룹을 파악 하 고 보안 및 기능 요구 사항에 유연성을 갖습니다.
- 보안 정책을 적시에 적용 하 고 의미를 확인 합니다.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>Id 및 장치 액세스 보호에 대 한 서비스 및 개념

엔터프라이즈에 대 한 Microsoft 365는 대규모 조직을 위해 설계 되었으며 Office 365 Enterprise, Windows 10 Enterprise 및 EMS (Enterprise Mobility + Security)를 통합 하 여 모든 사용자가 창의적인 작업을 수행 하 고 안전 하 게 함께 작업할 수 있도록 합니다.

이 섹션에서는 id 및 장치 액세스에 중요 한 Microsoft 365 서비스 및 기능에 대 한 개요를 제공 합니다.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD는 id 관리 기능을 완벽 하 게 제공 합니다. 액세스 보안을 위해 다음과 같은 기능을 사용 하는 것이 좋습니다.

- **[SSPR (셀프 서비스 암호 다시 설정)](/azure/active-directory/authentication/concept-sspr-howitworks)**: 관리자가 제어할 수 있는 여러 인증 방법에 대 한 확인을 제공 하 여 사용자가 지원 없이 암호를 안전 하 게 다시 설정할 수 있습니다.

- **[Mfa (multi-factor authentication)](/azure/active-directory/authentication/concept-mfa-howitworks)**: mfa를 사용 하려면 사용자 암호와 Microsoft 인증자 앱 또는 전화 통화의 알림과 같은 두 가지 유형의 확인을 제공 해야 합니다. MFA는 도난당 한 id가 사용자 환경에 액세스 하는 데 사용할 수 있는 위험을 크게 줄여줍니다.

- **[조건부 액세스](/azure/active-directory/conditional-access/overview)**: Azure AD는 사용자 로그인의 조건을 평가 하 고 만든 조건부 액세스 정책을 사용 하 여 액세스를 허용 합니다. 예를 들어이 가이드에서는 중요 한 데이터에 액세스 하기 위한 장치 준수를 요구 하는 조건부 액세스 정책을 만드는 방법을 보여 줍니다. 이렇게 하면 해커가 도난당 한 id를 가진 해커가 중요 한 데이터에 액세스할 수 있는 위험을 크게 줄여줍니다. 또한 장치는 상태 및 보안에 대 한 특정 요구 사항을 충족 하기 때문에 장치에서 중요 한 데이터를 보호 합니다.

- **[AZURE ad 그룹](/azure/active-directory/fundamentals/active-directory-manage-groups)**: 조건부 액세스 규칙, Intune을 사용한 장치 관리 및 조직의 파일 및 사이트에 대 한 사용 권한도 사용자 및/또는 Azure AD 그룹에 대 한 할당을 사용 합니다. 구현 하려는 보호 수준에 해당 하는 Azure AD 그룹을 만드는 것이 좋습니다. 예를 들어 경영 직원이 해커의 가치 목표 보다 높은 것을 들 수 있습니다. 따라서 이러한 직원을 Azure AD 그룹에 할당 하 고이 그룹을 조건부 액세스 정책 및 액세스를 위해 더 높은 수준의 보호를 적용 하는 기타 정책에 할당 하는 것이 좋습니다.

- **[Device registration](/azure/active-directory/devices/overview)**: 디바이스를 Azure AD에 등록 하 여 장치에 id를 제공 합니다. 이 id는 사용자가 로그인 할 때 장치를 인증 하 고 도메인에 가입 되거나 준수 된 Pc가 필요한 조건부 액세스 규칙을 적용 하는 데 사용 됩니다. 이 지침에서는 장치 등록을 사용 하 여 도메인에 가입 된 Windows 컴퓨터를 자동으로 등록 합니다. Device registration은 Intune을 사용 하 여 장치를 관리 하기 위한 필수 구성 요소입니다. 

- **[AZURE Ad Id 보호](/azure/active-directory/identity-protection/overview)**: Azure Ad id 보호를 사용 하면 조직의 id에 영향을 미치는 잠재적인 취약점을 검색 하 고 자동화 된 수정 정책을 낮음, 중간 및 높음 로그인 위험 및 사용자 위험에 대해 구성할 수 있습니다. 이 지침은이 위험 평가에 의존 하 여 다단계 인증에 대 한 조건부 액세스 정책을 적용 합니다. 또한이 지침에는 해당 계정에 대해 높은 위험 활동이 검색 되는 경우 사용자가 암호를 변경 해야 하는 조건부 액세스 정책도 포함 되어 있습니다.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) 은 Microsoft의 클라우드 기반 모바일 장치 관리 서비스입니다. 이 지침은 Intune을 사용 하는 Windows Pc의 장치 관리를 권장 하며 장치 준수 정책 구성을 권장 합니다. Intune은 장치가 호환 되는지 여부를 확인 하 고, 조건부 액세스 정책을 적용할 때 사용할 Azure AD로이 데이터를 보냅니다.

#### <a name="intune-app-protection"></a>Intune 앱 보호

[Intune 앱 보호](https://docs.microsoft.com/intune/app-protection-policy) 정책을 사용 하 여 관리에 장치를 등록 하거나 사용 하지 않고 모바일 앱에서 조직의 데이터를 보호할 수 있습니다. Intune은 정보를 보호 하 고 직원의 생산성을 유지 하 고 데이터 손실을 방지 하는 데 도움이 됩니다. 응용 프로그램 수준 정책을 구현 하 여 회사 리소스에 대 한 액세스를 제한 하 고 IT 부서의 통제 내에서 데이터를 유지할 수 있습니다.

이 가이드에서는 승인 된 앱을 사용 하 고 비즈니스 데이터에서 이러한 앱을 사용 하는 방법을 결정 하기 위한 권장 정책을 만드는 방법을 설명 합니다.

### <a name="microsoft-365"></a>Microsoft 365

이 가이드에서는 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive를 포함 하 여 Office 365에 대 한 액세스를 보호 하기 위한 정책 집합을 구현 하는 방법을 설명 합니다. 이러한 정책을 구현 하는 것 외에도 다음 리소스를 사용 하 여 테 넌 트의 보호 수준을 올리는 것이 좋습니다.

- [보안 강화를 위해 테 넌 트 구성](https://docs.microsoft.com/microsoft-365/security/office-365-security/tenant-wide-setup-for-increased-security): 이러한 권장 사항은 테 넌 트의 기준 보안에 적용 됩니다.
- [Microsoft 365 보안 로드맵: 처음 30 일, 90 일 및 그 이상에 대 한 주요 우선 순위](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap): 이러한 권장 사항에는 로깅, 데이터 거 버 넌 스, 관리자 액세스, 위협 방지 등이 있습니다.


### <a name="windows-10-and-microsoft-365-apps-for-enterprise"></a>Windows 10 및 Microsoft Office 365 ProPlus

Pc 용 Windows 10 및 Microsoft 365 Apps for enterprise는 권장 되는 클라이언트 환경입니다. Azure는 온-프레미스 및 Azure AD 둘 다에 사용할 수 있는 원활한 환경을 제공 하도록 디자인 되었기 때문에 Windows 10을 사용 하는 것이 좋습니다. Windows 10에는 Intune을 통해 관리할 수 있는 고급 보안 기능도 포함 되어 있습니다. Microsoft 365 enterprise 용 앱에는 최신 버전의 Office 응용 프로그램이 포함 되어 있습니다. 이러한 기능은 더 안전 하 고 조건부 액세스에 대 한 요구 사항을 충족 하는 최신 인증을 사용 합니다. 이러한 앱에는 향상 된 보안 및 준수 도구도 포함 되어 있습니다.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>3 개의 보호 계층에 걸쳐 이러한 기능 적용

다음 표에는 세 가지 보호 계층에서 이러한 기능을 사용 하기 위한 권장 사항이 요약 되어 있습니다.

|보호 메커니즘|기준|중요|매우 엄격한 규제|
|:-------------------|:-------|:--------|:---------------|
|**MFA 강제 적용**|중간 이상 로그인 위험에 대해|낮음 이상 로그인 위험에 대해|모든 새 세션에 대해|
|**암호 변경 적용**|위험성이 높은 사용자|위험성이 높은 사용자|위험성이 높은 사용자|
|**Intune 응용 프로그램 보호 적용**|예|예|예|
|**Intune 등록 적용 (COD)**|호환 또는 도메인에 가입 된 PC가 필요 하지만 BYOD 전화/태블릿을 허용 합니다.|호환 되거나 도메인에 가입 된 장치 필요|호환 되거나 도메인에 가입 된 장치 필요|

## <a name="device-ownership"></a>장치 소유권

위의 표에는 회사 소유의 장치를 함께 지원 하 고 개인 또는 자체 장치 (BYODs)를 사용 하 여 직원 들 간에 모바일 생산성을 설정 하기 위한 여러 조직에 대 한 추세가 반영 되어 있습니다. Intune 앱 보호 정책은 회사 소유 장치 및 BYODs 모두에서 Outlook 모바일 앱 및 기타 Office 모바일 앱에서 exfiltrating 로부터 전자 메일이 보호 되도록 합니다.  

추가 보호 및 제어를 적용 하기 위해 Intune 또는 도메인에 가입 하 여 회사 소유의 장치를 관리 하는 것이 좋습니다. 데이터 민감도에 따라 조직에서 특정 사용자 인구 또는 특정 앱에 대해 BYODs를 허용 하지 않도록 선택할 수 있습니다.

## <a name="next-steps"></a>다음 단계

[Id 및 장치 액세스 정책을 구현 하기 위한 필수 작업](identity-access-prerequisites.md)
