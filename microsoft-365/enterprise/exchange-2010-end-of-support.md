---
title: Exchange 2010 지원 종료 로드맵
ms.author: dstrome
author: dstrome
manager: laurawi
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: e150e7b9-c432-4c8d-a0ae-c11847129a7d
f1.keywords:
- NOCSH
description: Exchange 2010의 지원이 종료됩니다. 이 계획 로드맵을 사용하여 Exchange Online 또는 최신 버전의 Exchange Server 준비합니다.
ms.openlocfilehash: bbc7fb83537621a47a866bf0ca129a38e21f055e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289130"
---
# <a name="exchange-2010-end-of-support-roadmap"></a>Exchange 2010 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Exchange Server 2010년 **10월 13일** 지원이 종료됩니다. Exchange 2010에서 Microsoft 365, Office 365 또는 Exchange 2016으로 마이그레이션을 아직 시작하지 않은 경우 이제 계획을 시작할 시간입니다.

## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

대부분의 Microsoft 제품에는 새로운 기능, 버그 수정, 보안 수정 등 지원 수명 주기가 있습니다. 이 수명 주기는 일반적으로 제품의 초기 릴리스부터 10년 동안 지속됩니다. 이 수명 주기의 끝을 제품의 지원 종료라고 합니다. Exchange 2010년 10월 13일 지원이 종료되어 Microsoft는 더 이상 다음을 제공하지 않습니다.

- 발생할 수 있는 문제에 대한 기술 지원
- 서버의 안정성과 사용 가능성에 영향을 줄 수 있는 문제에 대한 버그 수정
- 서버가 보안 위반에 취약해질 수 있는 취약점에 대한 보안 수정
- 표준 시간대 업데이트.

2010 Exchange 설치는 이 날짜 이후에도 계속 실행됩니다. 그러나 위에 나열된 변경 내용 때문에 가능한 한 빨리 Exchange 마이그레이션하는 것이 좋습니다.

지원 종료에 대한 자세한 내용은 [Resources to help you upgrade from Office servers and clients을 참조하십시오.](upgrade-from-office-2010-servers-and-products.md)

## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

이제 옵션을 탐색하고 마이그레이션 계획을 준비하는 것이 좋습니다. 다음을 수행할 수 있습니다.

- 전체 마이그레이션을 Microsoft 365. 컷오버, 최소 하이브리드 또는 전체 하이브리드 마이그레이션을 사용하여 사서함을 마이그레이션합니다. 그런 다음 서버와 Active Directory에 Exchange 프레미스 서버를 제거합니다.
- Exchange 2010 서버를 Exchange 2016으로 마이그레이션합니다.

> [!IMPORTANT]
> 조직에서 사서함을 Microsoft 365 마이그레이션하지만 온-프레미스 Active Directory에서 사용자 계정을 계속 관리하기 위해 DirSync 또는 Azure AD 커넥트 유지하려면 하나 이상의 Microsoft Exchange 서버를 온-프레미스에 유지해야 합니다. 모든 Exchange 제거하면 권한 원본이 Exchange Active Directory에 남아 Exchange Online 받는 사람을 변경할 수 없습니다. 변경해야 합니다. 이 시나리오에서는 다음 옵션을 사용할 수 있습니다.
>
>- *권장 사항:* 사서함을 Microsoft 365 2020년 10월 13일까지 서버를 업그레이드한 경우 Exchange 2010을 사용하여 사서함에 연결하고 Microsoft 365 마이그레이션합니다. 그런 다음 Exchange 2010을 Exchange 2016으로 마이그레이션하고 나머지 2010 서버를 Exchange 해제합니다.
>- 2020년 10월 13일까지 사서함 마이그레이션 및 사내 서버 업그레이드를 완료하지 않은 경우 2010년 10월 13일까지의 Exchange 2010 서버를 먼저 Exchange 업그레이드합니다. 그런 다음 Exchange 2016을 사용하여 사서함에 Microsoft 365 마이그레이션합니다.

> [!NOTE]
> 약간 더 복잡하지만, 201 Exchange 0년 2016으로 Exchange 프레미스 서버를 마이그레이션하는 동안 사서함을 Microsoft 365 마이그레이션할 수도 있습니다.

다음은 2010의 지원이 종료되는 것을 방지하기 위해 취할 수 있는 세 가지 Exchange Server 있습니다.

![Exchange Server 2010 업그레이드 경로](../media/exchange-2010-end-of-support/exchange-2010-end-of-support-options.png)

다음 섹션에서는 각 옵션을 보다 자세히 설명합니다.

## <a name="migrate-to-microsoft-365"></a>Microsoft 365로 마이그레이션

전자 메일을 Microsoft 365 마이그레이션하는 것은 2010 2010 배포를 중지하는 데 도움이 되는 가장 쉽고 Exchange 옵션입니다. 이전 기술로 Microsoft 365 다음을 비롯한 이전 기술에서 현재 기능으로 단일 홉을 만들 수 있습니다.

- 보존 정책, In-Place 및 소송 보존, eDiscovery 등의 규정 준수 기능
- Microsoft Teams.
- Power BI.
- 포커스가 있는 받은 편지함.
- MyAnalytics.

Microsoft 365 기능 및 환경을 먼저 사용할 수 있으므로 조직에서 바로 사용할 수 있습니다. 또한 다음에 대해 걱정할 필요가 없습니다.

- 하드웨어 구매 및 유지 관리
- 서버를 열과 식히기 위해 비용을 지불합니다.
- 보안, 제품 및 표준 시간대 수정을 최신으로 유지
- 규정 준수 요구 사항을 지원하기 위해 저장소 및 소프트웨어 유지 관리
- 새 버전의 업데이트로 Exchange. You're always on the latest version of Exchange in Microsoft 365.

### <a name="how-should-i-migrate-to-microsoft-365"></a>마이그레이션하려면 어떻게 Microsoft 365?

조직에 따라 몇 가지 옵션을 사용하여 조직에 Microsoft 365. 먼저 다음과 같은 몇 가지를 고려해야 합니다.

- 이동해야 하는 시트 또는 사서함의 수입니다.
- 마이그레이션을 지속할 기간입니다.
- 마이그레이션 중에는 사내 설치와 프레미스 설치 Microsoft 365 원활하게 통합해야 하는지 여부

이 표에는 마이그레이션 옵션과 사용할 방법을 결정하는 가장 중요한 요소가 표시됩니다.

<br>

****

|마이그레이션 옵션|조직 크기|기간|
|---|---|---|
|단독 마이그레이션|시트 수가 150명 미만|1주 이하|
|최소 하이브리드 마이그레이션|시트 수가 150명 미만|몇 주 이하|
|전체 하이브리드 마이그레이션|시트 수가 150명 이상인 경우|몇 주 이상|
|

다음 섹션에서는 이러한 메서드에 대한 개요를 제공합니다. 자세한 내용은 마이그레이션 경로 [결정 을 참조하세요.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27)

### <a name="cutover-migration"></a>단독 마이그레이션

단일 마이그레이션에서는 모든 사서함, 메일 그룹, 연락처 등에서 설정된 Office 365 시간으로 마이그레이션합니다. 완료되면 모든 서버의 Exchange 종료하고 단독 사용 Microsoft 365 합니다.

사서함이 많지 않은 소규모 조직에서는 마이그레이션을 빠르게 수행하고 Microsoft 365 방법의 복잡성을 처리하지 않는 소규모 조직에 매우 좋은 마이그레이션입니다. 그러나 1주일 이하에서 완료해야 합니다. 또한 사용자가 자신의 프로필을 다시 구성해야 Outlook 합니다. 컷오버 마이그레이션은 최대 2,000개 사서함을 마이그레이션할 수 있지만 최대 150개까지 사용하는 것이 좋습니다. 더 많은 마이그레이션을 시도할 경우 기한이 되기 전에 모든 사서함을 전송할 시간이 지났을 수 있으며 IT 지원 직원이 사용자의 사서함을 다시 구성하는 데 도움이 되는 요청이 과도하게 Outlook.

다음은 컷오버 마이그레이션에 대해 고려해야 할 사항입니다.

- Microsoft 365 TCP 포트 443을 통해 Exchange Outlook 서버에 연결해야 합니다.
- 모든 On-premises 사서함은 모든 Microsoft 365.
- 사용자의 사서함에 대한 읽기 권한이 있는 사내 관리자 계정이 필요합니다.
- Exchange 사용할 2010 허용 도메인은 Microsoft 365 확인된 도메인으로 추가해야 합니다.
- 마이그레이션을 시작할 때와 완료 단계를 시작할 Microsoft 365 사서함과 Microsoft 365 주기적으로 동기화합니다. 이렇게 하면 전자 메일이 전자 메일에 남아 있는 것을 걱정할 필요 없이 마이그레이션을 완료할 수 있습니다.
- 사용자는 해당 계정의 새 임시 Microsoft 365 받게 됩니다. 처음 사서함에 로그인할 때 해당 변경이 필요합니다.
- 마이그레이션하는 각 Microsoft 365 사서함에 대한 Exchange Online 라이선스가 필요합니다.
- 사용자는 각 장치에서 새 Outlook 프로필을 설정하고 전자 메일을 다시 다운로드해야 합니다. 다운로드할 전자 메일의 Outlook 다를 수 있습니다. 자세한 내용은 에서 오프라인으로 작업을 [Outlook.](https://support.microsoft.com/office/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

컷오버 마이그레이션에 대한 자세한 내용은 다음을 참조합니다.

- [컷오버 전자 메일 마이그레이션에 대해 알아야 할 것](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)
- [전자 메일로의 컷오버 마이그레이션을 Office 365](/Exchange/mailbox-migration/cutover-migration-to-office-365)

### <a name="minimal-hybrid-migration"></a>최소 하이브리드 마이그레이션

최소 하이브리드 또는 익스프레스 마이그레이션에서는 몇 주 내에 수백 개의 사서함을 Microsoft 365 이동하게 됩니다. 이 방법은 공유 약속이 있는 일정 정보와 같은 고급 하이브리드 마이그레이션 기능을 지원하지 않습니다.

최소 하이브리드 마이그레이션은 사서함을 마이그레이션하는 데 더 많은 시간을 Microsoft 365 몇 주 이내에 마이그레이션을 완료할 계획인 조직에 매우 도움이 됩니다. 복잡하지 않은 고급 전체 하이브리드  마이그레이션의 몇 가지 이점을 얻을 수 있습니다. 특정 시기에 마이그레이션할 사서함의 수와 사서함을 제어할 수 있습니다. Microsoft 365 사용자 이름과 암호로 사서함을 만들 수 있습니다. 또한, 컷오버 마이그레이션과 달리 사용자는 해당 프로필을 다시 Outlook 없습니다.

최소 하이브리드 마이그레이션에 대해 고려해야 할 사항은 다음과 같습니다.

- 프레미스 Active Directory 서버와 프레미스 Active Directory 서버 간에 일회성 디렉터리 동기화를 Microsoft 365.
- 사용자는 사서함과 동일한 사용자 이름과 암호를 Microsoft 365 사서함에 로그인할 수 있습니다.
- 마이그레이션하는 각 Microsoft 365 사서함에 대한 Exchange Online 라이선스가 필요합니다.
- 사용자는 대부분의 장치에서 새 Outlook 프로필을 설정할 필요가 없습니다. 그러나 일부 이전 Android 휴대폰에는 새 프로필이 필요할 수 있습니다. 사용자는 전자 메일을 다시 다운로드할 필요가 없습니다.

자세한 내용은 최소 하이브리드를 사용하여 사서함을 Exchange [마이그레이션을 Office 365.](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)

### <a name="full-hybrid"></a>전체 하이브리드

전체 하이브리드 마이그레이션에서는 수백, 최대 수만 개의 사서함이 있으며 일부 또는 모두를 사서함으로 Microsoft 365. 이러한 마이그레이션은 일반적으로 더 장기적이기 때문에 하이브리드 마이그레이션을 통해 다음을 할 수 있습니다.

- 프레미스 사용자에게 사용자에 대한 약속이 있는/약속 Microsoft 365 정보를 표시하는 경우도 마찬가지입니다.
- 전체 주소 목록을 참조하세요. 이 목록은 모든 전자 메일 주소 목록에 있는 받는 사람이 모두 포함된 Microsoft 365.
- 모든 Outlook Microsoft 365 모든 사용자에 대한 전체 받는 사람 속성을 볼 수 있습니다.
- TLS 및 인증서를 사용하여 Exchange 서버와 Office 365 전자 메일 통신을 보호합니다.
- 다음을 지원하여 Exchange 서버 간에 전송된 Microsoft 365 내부로 처리합니다.
  - 내부 메시지를 대상으로 하는 전송 및 규정 준수 에이전트가 적절히 평가하고 처리해야 합니다.
  - 스팸 방지 필터를 무시합니다.

전체 하이브리드 마이그레이션은 몇 개월 이상 하이브리드 구성을 유지해야 하는 조직에 가장 좋습니다. 이 섹션의 앞부분에 나와 있는 기능과 디렉터리 동기화, 보다 나은 통합 규정 준수 기능 및 온라인 사서함 이동을 사용하여 사서함을 이동하는 Microsoft 365 수 있습니다. Microsoft 365 조직의 확장이 됩니다.

전체 하이브리드 마이그레이션에 대해 고려해야 할 사항:

- 모든 조직에 적합하지는 않습니다. 전체 하이브리드 마이그레이션의 복잡성으로 인해 사서함이 수백 개 미만인 조직에서는 일반적으로 이러한 노력과 비용을 정당화하는 이점을 볼 수 없습니다. 이러한 경우에는 대신에 컷오버 또는 최소 하이브리드 마이그레이션을 고려하는 것이 좋습니다.
- Azure AD(Azure Active Directory)를 사용하여 디렉터리 동기화를 설정해야 커넥트 Active Directory 서버와 Microsoft 365.
- 사용자는 로컬 네트워크에 로그인할 때 사용하는 사용자 Microsoft 365 암호를 사용하여 자신의 Microsoft 365 사서함에 로그인할 수 있습니다. (이 기능을 사용하려면 암호 커넥트 및/또는 Active Directory Federation Services를 사용하는 Azure AD 계정이 필요합니다.
- 마이그레이션하는 Microsoft 365 사서함에 대한 Exchange Online 라이선스가 필요합니다.
- 사용자는 대부분의 장치에서 새 Outlook 프로필을 설정할 필요가 없습니다. 그러나 일부 이전 Android 휴대폰에는 새 프로필이 필요할 수 있습니다. 사용자는 전자 메일을 다시 다운로드할 필요가 없습니다.

> [!IMPORTANT]
> 조직에서 사서함을 Microsoft 365 마이그레이션하지만 온-프레미스 Active Directory에서 사용자 계정을 계속 관리하기 위해 DirSync 또는 Azure AD 커넥트 유지하려면 하나 이상의 Exchange 서버를 온-프레미스에 유지해야 합니다. 모든 Exchange 제거된 경우 해당 서버의 받는 사람을 Exchange 수 Exchange Online. 이는 권한 원본이 사내 Active Directory에 남아 있으며 변경 내용을 적용해야 하기 때문에입니다.

전체 하이브리드 마이그레이션이 적합한 경우 다음 유용한 리소스를 참조합니다.

- [Exchange 배포 도우미](/exchange/exchange-deployment-assistant)
- [Exchange Server 하이브리드 배포](/exchange/exchange-hybrid)
- [하이브리드 구성 마법사](/exchange/hybrid-configuration-wizard)
- [하이브리드 구성 마법사 FAQ](/exchange/hybrid-configuration-wizard-faqs)
- [하이브리드 배포 필수 구성 요소](/exchange/hybrid-deployment-prerequisites)

## <a name="upgrade-to-a-newer-version-of-exchange-server-on-premises"></a>최신 버전의 Exchange Server 업그레이드

모든 사용자 환경으로 완전히 마이그레이션하여 최고의 가치와 사용자 환경을 얻게 Microsoft 365. 그러나 일부 조직에서는 일부 Exchange 유지해야 한다는 것을 알고 있습니다. 이는 클라우드에서 충족할 수 없는 고유한 설정이나 요구 사항이 있기 때문에 데이터가 외외 데이터 센터에 저장되지 않을 수 있도록 하는 규정 요구 사항 또는 여전히 Active Directory를 사용하기 때문에 Exchange 사서함을 관리해야 하기 때문에 이러한 요구 사항일 수 있습니다. 어떤 경우든 Exchange 유지하면 Exchange 2010 환경이 Exchange 2013 또는 Exchange 2016 이상으로 업그레이드되도록 해야 합니다.

최상의 환경을 위해 남은 사내 환경을 2016년 8월로 업그레이드하는 Exchange 좋습니다. 2010에서 Exchange Server 2016으로 바로 이동하려는 경우 Exchange Server 2013을 Exchange Server 없습니다.

Exchange 2016에는 이전 릴리스의 모든 기능이 Exchange. 일부 기능은 Microsoft 365 사용 가능한 환경과 가장 Microsoft 365. 누락된 몇 가지 사항만 확인해 보아야 합니다.

<br>

****

|Exchange 릴리스|기능|
|---|---|
|**Exchange 2013**|간소화된 아키텍처에서는 서버 역할 수를 3개(사서함, 클라이언트 액세스, Edge 전송)로 줄입니다.|
||중요한 정보가 누출되는 문제를 방지하는 데 도움이 되는 DLP(데이터 손실 방지 정책)|
||향상된 Outlook Web App 환경|
|**Exchange 2016**|*2013 및 Exchange 기능*|
||사서함 및 Edge 전송으로의 추가 간소화된 서버 역할|
||향상된 DLP와 통합된 SharePoint|
||향상된 데이터베이스 탄력성|
||온라인 문서 공동 작업|
|

<br>

****

|고려 사항|추가 정보|
|---|---|
|지원 종료 날짜|Exchange 2010과 마찬가지로 각 Exchange 자체 지원 종료 날짜가 있습니다. <p> Exchange 2013년 4월 - 2023년 4월 <p> Exchange 2016년 10월 - 2025년 10월 <p> 지원 종료 날짜가 이르면 더 빨리 다른 마이그레이션을 수행해야 합니다. 2023년 4월이 생각보다 훨씬 더 가까워지고 있습니다.|
|2013 또는 Exchange 마이그레이션 경로|마이그레이션 경로는 Exchange 2010에서 최신 버전으로의 마이그레이션 경로는 2013 또는 Exchange 2016에 Exchange 동일합니다. <p> 기존 Exchange 2010 조직에 2013 또는 2016을 Exchange 설치합니다. <p> 서비스 및 기타 인프라를 2013 Exchange 2016으로 이동 <p> 사서함 및 공용 폴더를 Exchange 2013 또는 2016년 2010 서버의 나머지 Exchange 해제합니다.|
|버전 동시 사용|Exchange 2013 또는 Exchange 2016으로 마이그레이션할 때 기존 Exchange 2010 조직에 버전을 설치할 수 있습니다. 이렇게 하면 하나 이상의 Exchange 2013 또는 Exchange 서버를 설치하고 마이그레이션을 할 수 있습니다.|
|서버 하드웨어|서버 하드웨어 요구 사항은 2010년 Exchange 변경되었습니다. 하드웨어가 호환되는지 확인 각 버전에 대한 하드웨어 요구 사항에 대한 자세한 내용은 다음을에서 확인합니다. <p> [Exchange 2016 시스템 요구 사항](/Exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true) <p> [Exchange 2013 시스템 요구 사항](/Exchange/exchange-2013-system-requirements-exchange-2013-help) <p> 새로운 서버에서 Exchange 성능 및 저장소 용량이 크게 향상되어 동일한 수의 사서함을 지원하기 위해 더 적은 수의 서버가 필요할 수 있습니다.|
|운영 체제 버전|각 버전에 대해 지원되는 최소 운영 체제 버전은 다음입니다. <p> Exchange 2016 - Windows Server 2012 <p> Exchange 2013 - Windows Server 2008 R2 SP1 <p> 운영 체제 지원에 대한 자세한 내용은 지원 가능성 [매트릭스 Exchange 있습니다.](/exchange/plan-and-deploy/supportability-matrix)|
|Active Directory 포리스트 기능 수준|각 버전에 대해 지원되는 최소 Active Directory 포리스트 기능 수준은 다음입니다. <p> Exchange - Windows Server 2008 R2 SP1 <p> Exchange 2013 - Windows Server 2003 <p> 포리스트 기능 수준 지원에 대한 자세한 내용은 지원 가능성 [매트릭스 Exchange 있습니다.](/exchange/plan-and-deploy/supportability-matrix)|
|Office 클라이언트 버전|각 버전에 대해 Office 지원되는 최소 클라이언트 버전은 다음입니다. <p> Exchange 2016 - Office 2010(최신 업데이트 사용) <p> Exchange 2013 - Office 2007 SP3 <p> 클라이언트 지원에 대한 Office 자세한 내용은 Exchange [매트릭스를 참조하십시오.](/exchange/plan-and-deploy/supportability-matrix)|
|

다음 리소스를 사용하여 마이그레이션에 도움을 줄 수 있습니다.

- [Exchange 배포 도우미](/exchange/exchange-deployment-assistant)
- Exchange [2016,](/exchange/plan-and-deploy/active-directory/ad-schema-changes?view=exchserver-2016&preserve-view=true) [2013의](/Exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help) Active Directory schema changes
- Exchange [2016,](/exchange/plan-and-deploy/system-requirements?view=exchserver-2016&preserve-view=true) [2013에](/Exchange/exchange-2013-system-requirements-exchange-2013-help) 대한 시스템 요구 사항
- Exchange [2016,](/exchange/plan-and-deploy/prerequisites?view=exchserver-2016&preserve-view=true) [2013의](/Exchange/exchange-2013-prerequisites-exchange-2013-help) 선행 준비

## <a name="summary-of-options-for-office-2010-client-and-servers-and-windows-7"></a>Office 2010 클라이언트 및 서버 및 Windows 옵션 요약

Office 2010 클라이언트 및 서버와 Windows 7에 대한 업그레이드, 마이그레이션 및 클라우드 옵션으로 이동에 대한 시각적 요약은 [지원 종료 포스터](../downloads/Office2010Windows7EndOfSupport.pdf)를 참조하세요.

[![Office 2010 클라이언트 및 서버 및 Windows 포스터 지원 종료](../media/microsoft-365-overview/office2010-windows7-end-of-support.png)](../downloads/Office2010Windows7EndOfSupport.pdf)

이 한 페이지 포스터는 Office 2010 클라이언트 및 서버 제품 및 Windows 7의 지원 종료에 응답하기 위해 취할 수 있는 다양한 경로를 보여 주며 기본 설정 경로 및 옵션 지원은 강조 표시되어 Microsoft 365 Enterprise 있습니다.

이 [포스터를](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Office2010Windows7EndOfSupport.pdf) 다운로드하여 편지형, 법률형 또는 타블로이드(11 x 17) 형식으로 인쇄할 수도 있습니다.

## <a name="what-if-i-need-help"></a>도움이 필요한 경우 어떻게 하나요?

사용자 계정으로 마이그레이션하는 Microsoft 365 Microsoft FastTrack 서비스를 사용할 수 있습니다. FastTrack은 가능한 한 원활하게 마이그레이션할 수 있도록 모범 Microsoft 365, 도구 및 리소스를 제공합니다. 무엇보다 지원 엔지니어가 계획 및 디자인에서 마지막 사서함 마이그레이션에 대해 단계적 정보를 제공합니다. FastTrack에 대한 자세한 내용은 [Microsoft FastTrack을 참조합니다.](https://fasttrack.microsoft.com/)

Microsoft 365 마이그레이션하는 동안 문제가 발생하여 FastTrack을 사용하지 않는 경우 또는 최신 버전의 Exchange Server 마이그레이션하는 경우 사용할 수 있는 몇 가지 리소스는 다음과 같습니다.

- [기술 커뮤니티](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
- [고객 지원](https://support.microsoft.com/gp/support-options-for-business)

## <a name="related-articles"></a>관련 문서

[Office 2010 서버 및 클라이언트 업그레이드에 도움이 되는 리소스](upgrade-from-office-2010-servers-and-products.md)
