---
title: Identity 및 장치 액세스 구성-Microsoft 365 Enterprise
description: Microsoft 권장 사항 및 배포 하는 전자 메일 보안, 문서, 및 앱 정책 및 구성에 대 한 핵심 개념에 설명 합니다.
author: brendacarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/11/2018
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 74378da4206c3735cd949358c6cb34b314c82b97
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869740"
---
# <a name="identity-and-device-access-configurations"></a>ID 및 장치 액세스 구성

이 문서 시리즈에 권장 되는 환경 및 구성, 지정 된 조건부 액세스 정책 집합을 포함 하 여 구현 하 여 엔터프라이즈 이동성 + 보안 제품을 통해 클라우드 서비스에 대 한 보안 액세스를 구성 하는 방법에 설명 하 고 관련된 기능입니다. Azure AD 응용 프로그램 프록시를 사용 하 여 다른 SaaS 서비스 및 온-프레미스 응용 프로그램 게시 Office 365 서비스를 포함 한 Azure Active Directory와 통합 하는 모든 서비스에 대 한 액세스를 보호 하기 위해이 설명서를 사용할 수 있습니다. 

이러한 권장 사항 Microsoft 보안 점수도 [identity 점수 Azure AD에](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-secure-score) 맞는 하 고 조직에 대 한 이러한 점수 증가 합니다. 이러한 권장 사항 이러한 [identity 인프라를 보호 하려면 5 단계](https://docs.microsoft.com/en-us/azure/security/azure-ad-secure-steps)를 구현할 수도 도움이 됩니다. 

Microsoft의 고유한 환경 요구 사항 또는 복잡 한 일부 조직에서는 되었는지 이해 합니다. 이러한 조직 중 하나 경우 이러한 권장 사항을 사용 하 여 시작 지점으로 합니다. 그러나 설명 했 듯이 대부분의 조직에서는 이러한 권장 사항을 구현할 수 있습니다. 

## <a name="intended-audience"></a>의도 한 대상 그룹

이러한 권장 사항은 엔터프라이즈 설계자와 [Office 365](https://technet.microsoft.com/library/dn127064(v=office.14).aspx) 와 [Microsoft Enterprise 이동성 + 보안](http://microsoft.com/ems) 등을 포함 하는 Azure Active Directory (id)를 Microsoft에 이해 하는 IT 전문가 위한 Intune (장치 관리) 및 Azure 정보 보호 (데이터 보호).

### <a name="customer-environment"></a>고객 환경

권장 되는 정책에 적용할 수 있는 Microsoft 클라우드 내 완전히 작동 하는 엔터프라이즈 조직 하 고 하이브리드에 대 한 인프라를 사용 하는 고객 온-프레미스와 Microsoft 클라우드를 배포 합니다.

엔터프라이즈 이동성 + 보안 (EMS) E5 라이선스에만 사용할 수 있는 서비스에 의존 하는 다양 한 제공 된 권장 사항 권장 사항을 제시 전체 EMS E5 라이선스 기능이 가정 합니다.

엔터프라이즈 이동성 + 보안 E5 라이선스 없는 해당 조직에 대 한 최소 모든 계획에 포함 된 Azure AD 초기 보호 기능을 구현 하는 것이 좋습니다. [초기 계획 보호 이란](/azure/active-directory/active-directory-conditional-access-baseline-protection) Azure AD 라이브러리에는 문서에서 자세한 정보를 확인할 수 있습니다.

### <a name="caveats"></a>단점

조직에서 권장 되는 구성 이러한 분기 하는 정책을 적용 해야할 수도 있는 특정 권장 사항을 비롯 한 다른 또는 규정 준수 요구 사항에 따라 달라 집니다 수 있습니다. 이러한 구성에 사용 현황 컨트롤을 획기적인으로 제공 되지 않은 것이 좋습니다. 보안 및 생산성 간의 균형을 나타내는지 판단 되는 때문에 이러한 컨트롤을 좋습니다.  

다양 한 보호 조직의 요구 사항에 대 한 계정에 최고 했던, 우리가 모든 가능한 요구 사항에 대 한 또는 조직의 고유한 모든 측면에 대 한 계정 수 있습니다.

## <a name="three-tiers-of-protection"></a>보호의 세 계층

대부분의 조직은 보안 및 데이터 보호에 관한 구체적 요구 사항을 가지고 있습니다. 이러한 요구 사항은 산업 부문 및 조직 내의 직무 기능에 따라 달라집니다. 예를 들어 법무 부서 및 Office 365 관리자는 다른 업무 단위 사용자에게 필요하지 않은 자신의 메일 서신에 대한 추가 보안 및 정보 보호 제어가 필요할 수 있습니다.

각 업계에는 다음과 같은 특수 규정 자신의 세트가 있습니다. 대신 업계 세그먼트 또는 작업 함수 당 권장 사항을 제공 된 보안의 서로 다른 세 계층에 대 한 모든 가능한 보안 옵션 또는 추천의 목록을 제공 하 고 보호 적용 될 수 있는 사용자의 요구의 세분성에 따라 .

- **초기 계획 보호** -데이터를으로 id 및 데이터에 액세스 하는 장치를 보호 하는 최소 표준을 설정 하는 것이 좋습니다. 대부분의 조직에서는의 요구를 충족 하는 강력한 기본 보호 기능을 제공 하려면 이러한 초기 계획 권장 사항을 따를 수 있습니다.
- **중요 한 보호** -일부 고객은 더 높은 수준에서 보호 해야 하거나 더 높은 수준 보호를 모든 데이터를 필요로 하는 데이터의 하위 집합입니다. 모든 강화 된 보호를 적용할 수 있습니다 또는 Office 365 환경에서 특정 데이터를 설정 합니다. Id 및 비교 가능한 수준의 보안을 사용 하 여 중요 한 데이터에 액세스 하는 장치를 보호 하는 것이 좋습니다.  
- **매우 규제 된** -일부 조직에서는 매우 분류 되는 데이터, 영업 비밀 또는 규제 데이터의 양이 적습니다 있을 수 있습니다. Microsoft는 조직이 id 및 장치에 대 한 추가 보호를 포함 하 여 이러한 요구 사항을 충족 하는 기능을 제공 합니다.

![보안 원뿔형-모든 고객 > 콘텐츠이며 > 특정 고객을 대상입니다. 특정 응용 프로그램을 광범위 한 응용 프로그램](../images/M365-idquality-threetiers.png)

이 설명서에서는 id에 대 한 보호 하 고 각 보호 이러한 계층에 대 한 장치를 구현 하는 방법을 보여줍니다. 시작 지점으로이 지침을 사용 하 여 조직에 대 한 하 고 특정 조직 요구를 충족 하도록 정책을 조정 합니다.

데이터, id 및 장치 전반에 걸쳐 일관성 있는 수준의 보호를 사용 하 여 중요 한 것입니다. 예,이 지침을 구현 하는 경우 해야 비교 가능한 수준에서 데이터를 보호 합니다. 이러한 아키텍처 모델 어떤 기능을 비교할 수를 표시 합니다.

**Office 365에 대 한 id 및 장치 보호**<br/>
![포스터 (영문) "Id 및 장치에 대 한 보호 Office 365"에 대 한 축소판 그림](../images/O365_Identity_device_protection_thumb.png)<br/>
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [더 많은 언어](https://www.microsoft.com/download/details.aspx?id=55032)

**Office 365의 파일 보호 솔루션**<br/>
!["Office 365의에서 보호 솔루션 파일" 포스터 축소판 그림](../images/24be68b5-d852-4fdb-94ad-94491a19edd8.png)<br/>
[PDF](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.pdf) | [Visio](http://download.microsoft.com/download/7/8/9/789645A5-BD10-4541-BC33-F8D1EFF5E911/MSFT_cloud_architecture_O365%20file%20protection.vsdx)

## <a name="security-and-productivity-trade-offs"></a>보안과 생산성의 절충

보안 및 생산성 간의 장단점을 필요 모든 보안 전략을 구현 합니다. 각 의사 결정 보안, 기능 및 편리한 사용을 위해의 균형에 미치는 영향을 평가 하는 것이 좋습니다.

![보안 3 인조 보안, 기능 및 편리한 사용을 위해 균형 조정 합니다.](media/policies-configurations/security-triad.png)

제공 된 권장 사항은 다음 원칙을 기반으로 합니다.

- 보안 및 기능 요구 사항에 융통성 있게 청중을 알고 있어야 합니다.
- 적시에 보안 정책을 적용 하 고 의미 있는 내용 인지 확인 합니다.

## <a name="services-and-concepts-for-identity-and-device-access-protection"></a>서비스 및 id 및 장치에 대 한 개념에 대 한 액세스 보호

Microsoft 365 엔터프라이즈 대규모 조직에 대 한 설계 및 통합 하는 Office 365 Enterprise, Windows 10 엔터프라이즈 및 엔터프라이즈 이동성 + 보안 (EMS) 창의적이 고 작동 되도록 모든 사용자에 게 권한 부여를 함께, 안전 하 게 합니다.

이 섹션에서는 Microsoft 365 서비스 및 id 및 장치 액세스에 대 한 중요 한 기능에 대 한 개요를 제공 합니다.

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

Azure AD 관리 기능 id의 전체 제품군을 제공 합니다. 다음과 같은 기능을 사용 하는 액세스를 보호 하기 위한 권장 사항:

- **[셀프서비스 암호 재설정 (SSPR)](/azure/active-directory/authentication/concept-sspr-howitworks.md)** -사용자가 확인의 관리자가 제어할 수 있는 여러 인증 방법 제공 하 여 고객 지원 센터의 개입 없이 자신의 암호를 안전 하 게 다시 설정 하도록 합니다.
- **[다단계 인증 (MFA)](/azure/active-directory/authentication/concept-mfa-howitworks.md)** -MFA 확인 사용자 암호를 더한 Microsoft 인증자 app 또는 전화에서 알림 등의 두 폼을 제공 하는 사용자가 필요 합니다. MFA 크게 도난당된 id를이 될 수 있는 위험을 줄일 수 Office 365 환경에 액세스 하는 데 사용 됩니다.
- **[조건부 액세스](/azure/active-directory/conditional-access/overview.md)** -Azure AD 사용자 로그인의 조건을 평가 하 고 액세스를 허용 하기 위해 만든 조건부 액세스 정책을 사용 하 여 합니다. 등이 설명서에는 방법을 보여줍니다에 중요 한 데이터에 대 한 액세스에 대 한 장치 규정 준수를 필요로 하는 조건부 액세스 정책을 만듭니다. 이렇게 하면 도난당 한 id 가진 해커 중요 한 데이터에 액세스할 수 있는지 위험이 줄어듭니다. 또한 장치 상태 및 보안에 대 한 특정 요구를 충족 하기 때문에 장치에서 중요 한 데이터를 보호 합니다.
- **[Azure AD 그룹](/azure/active-directory/fundamentals/active-directory-manage-groups.md)** -조건부 액세스 규칙의 경우 Intune 사용한 장치 관리 및 파일 및 조직에서 사이트에도 사용 권한을 할당할 사용자 및/또는 Azure AD 그룹 수에 의존 합니다. 구현 하는 보호 수준에 해당 하는 Azure AD 그룹을 만들 하는 것이 좋습니다. 예 임원 대 한 직원에는 해커 가능성이 높은 값 대상이 됩니다. 따라서 이러한 직원 Azure AD 그룹에 할당 하 고 더 높은 수준의 액세스에 대 한 보호를 적용 하는 다른 정책과 조건부 액세스 정책에이 그룹에 할당 하는 것입니다.
- **[장치 등록](/azure/active-directory/devices/overview.md)** -장치 id를 제공 하려면 Azure AD에 장치를 등록 합니다. 이 id는 사용자가 로그인 하는 경우 장치를 인증 하 고 도메인에 가입 하거나 호환 Pc를 필요로 하는 조건부 액세스 규칙을 적용 하려면 사용 됩니다. 이 설명서에 대 한 도메인 가입 Windows 컴퓨터를 자동으로 등록 하려면 장치 등록을 사용 합니다. 장치 등록은 Intune 사용 하 여 장치를 관리 하기 위한 필수 구성 요소입니다. 
- **[Azure AD Id 보호](/azure/active-directory/identity-protection/overview)** — Azure AD Id 보호를 사용 하면 조직의 id가 영향을 미치는 잠재적 보안 문제를 검색 하 고 낮음, 보통 및 높은 로그인 위험 및 사용자 위험에 자동된 업데이트 관리 정책을 구성할 수 있습니다. 이 설명서에서는 다중 요소 인증에 대 한 조건부 액세스 정책을 적용 하려면이 위험 평가 합니다. 이 설명서에는 사용자가 자신의 계정에 대 한 높은 위험 수준 감지 되는 경우 암호를 변경 하도록 요구 하는 조건부 액세스 정책을 포함 됩니다.

### <a name="microsoft-intune"></a>Microsoft Intune

[Intune](https://docs.microsoft.com/intune/introduction-intune) 는 Microsoft의 클라우드 기반 모바일 장치 관리 서비스입니다. 이 설명서 Intune 사용한 Windows Pc의 장치 관리 권장 및 장치 규정 준수 정책 구성을 것을 권장 합니다. Intune 장치 규격이 및 조건부 액세스 정책을 적용 하는 경우를 사용 하 여 Azure AD를이 데이터를 전송 되는지 여부를 결정 합니다.

#### <a name="intune-app-protection"></a>Intune app 보호

[Intune app 보호](https://docs.microsoft.com/intune/app-protection-policy) 정책은 관리로 모바일 앱 함께 또는 따로 등록 장치에서에서 회사의 데이터를 보호 하기 위해 사용할 수 있습니다. Intune 보호 Office 365 정보 확인 직원 생산성, 및 방지 데이터가 손실 될 수 있습니다. 응용 프로그램 수준 정책을 구현 하 여 회사 리소스에 대 한 액세스를 제한할 수 있으며 IT 부서의 컨트롤 내에서 데이터를 유지할 수 있습니다.

이 설명서에서는 승인 된 응용 프로그램의 사용을 적용 하 고 비즈니스 데이터와 이러한 앱을 사용할 수 있는 방법을 결정 하는 권장된 정책을 만드는 방법을 보여줍니다.

### <a name="office-365"></a>Office 365

이 설명서에서는 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive를 포함 하 여 Office 365에 대 한 액세스를 보호 하기 위해 정책 집합을 구현 하는 방법을 보여줍니다. 이러한 정책은 구현, 외에 이러한 리소스를 사용 하 여 Office 365 테 넌 트에 대 한 보호 수준을 발생 하는 것이 좋습니다.

- [보안 향상된을 위해 Office 365 테 넌 트 구성](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355) -Office 365 테 넌 트에 대 한 초기 보안에 이러한 권장 사항을 적용 합니다.
- [Office 365 보안 로드맵: 우선순위 위쪽 처음 30 일, 90 일 동안 및 이상](https://support.office.com/article/Office-365-security-roadmap-Top-priorities-for-the-first-30-days-90-days-and-beyond-28c86a1c-e4dd-4aad-a2a6-c768a21cb352) -이러한 권장 사항에는 로깅, 데이터 관리 방식, 관리 액세스 및 위협 보호 합니다.
- [SharePoint Online 보안 사이트 및 파일](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files) -이 문서 집합 파일 및 초기 계획, 소문자를 구분 하 고 매우 기밀 보호에 대 한 적절 한 수준에서 사이트를 보호 하는 방법에 설명 합니다.

### <a name="windows-10-and-office-365-proplus"></a>Windows 10 및 Office 365 ProPlus

Windows 10 및 Office 365 ProPlus는 Pc에 대 한 권장된 클라이언트 환경입니다. Azure 온-프레미스 및 Azure AD 모두에 대 한 가능한 가장 자연 스러운 경험을 제공 하기 위한 것 처럼 Windows 10을 권장 합니다. 또한 Windows 10 Intune를 통해 관리할 수 있는 고급 보안 기능을 포함 합니다. Office 365 ProPlus는 최신 버전의 Office 응용 프로그램을 포함합니다. 이러한 길수록 보안은 강화 현대 인증과 요구 사항이 조건부 액세스에 대 한 사용 합니다. 또한 이러한 앱 향상 된 보안 및 규정 준수 도구를 포함 합니다.

## <a name="applying-these-capabilities-across-the-three-tiers-of-protection"></a>보호의 세 계층에서 이러한 기능을 적용합니다.

다음 표에서 이러한 기능을 사용 하 여 보호의 세 계층 간에 하기 위한 권장 사항 요약 합니다.

|보호 메커니즘|기준|중요|높은 규제|
|:-------------------|:-------|:--------|:---------------|
|**MFA 강제 적용**|중간 이상 로그인 위험에 대해|낮음 이상 로그인 위험에 대해|모든 새 세션에 대해|
|**암호 변경 강제 적용**|높은 위험 사용자의 경우|높은 위험 사용자의 경우|높은 위험 사용자의 경우|
|**Intune 응용 프로그램 보호 강제 적용**|예|예|예|
|**Intune 등록(COD)**|준수를 요구 하거나 도메인 PC에 참가 하지만 BYOD 전화/태블릿 허용|호환되거나 도메인에 가입된 장치 필요|호환되거나 도메인에 가입된 장치 필요|

## <a name="device-ownership"></a>장치 소유권

위의 표에서 개인 또는 가져올 자신만 장치는 인력 별 모바일 생산성을 사용 하도록 설정 (BYOD) 장치 소유 하 고 회사의 혼합을 지원 하기 위해 대부분의 조직에 대 한 추세를 반영 합니다. Intune App 보호 정책 Outlook 모바일 응용 프로그램 및 다른 Office 모바일 응용 프로그램, 회사 소유의 장치 및 BYOD 모두에서 로그 아웃 exfiltrating에서 전자 메일 보호 되 고 있는지 확인 합니다.  

회사 소유의 장치 것이 좋습니다 Intune에서 관리 하는 또는 추가 보호 및 제어를 적용 하려면 도메인에 가입 되어야 합니다.  데이터 우편물 종류에 따라 조직 하지 특정 사용자 모집단 또는 특정 앱에 대 한 BYOD를 허용 하도록 선택할 수 있습니다.

## <a name="next-steps"></a>다음 단계

[Id 및 장치 액세스 정책을 구현 하기 위한 필수 구성 요소 작업](identity-access-prerequisites.md)