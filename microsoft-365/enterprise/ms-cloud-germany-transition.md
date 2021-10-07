---
title: 독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션
ms.author: andyber
author: andybergen
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: '요약: 독일 Microsoft 클라우드(도이칠란드 Microsoft 클라우드)에서 Office 365 서비스 독일 신규 데이터 센터 지역으로의 마이그레이션 이해 '
ms.openlocfilehash: 837a92b5ca3950615919392921ce7c37efc9f4bd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195332"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>독일 Microsoft 클라우드에서 새 독일 Office 365 서비스로 마이그레이션

> [!NOTE]
> 이 문서는 적격 Microsoft 클라우드 도이클란드 고객에게만 적용됩니다.

2018년 8월 Microsoft는 고객의 디지털 변환을 더욱 잘 가능하게 하기 위해 독일의 새 클라우드 지역에서 완전한 Microsoft 클라우드인 Azure, Office 365, Dynamics 365 및 Power Platform을 제공하겠다는 의도를 발표했습니다. 2019년 8월, 독일의 신규 클라우드 지역 출범을 발표합니다.   이후 Azure, Office 365, Dynamics 365 및 Power Platform의 가용성을 발표했습니다.

새로운 지역은 독일 고객의 진화하는 요구를 보다 유연하게, 최신 지능형 클라우드 서비스, Microsoft 365 서비스 클라우드 네트워크 및 독일 내 고객 데이터 상주에 대한 완전한 연결로 처리하도록 디자인되었습니다.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>새 독일 데이터 센터 지역으로 마이그레이션하는 방법

이제 도이치클라드의 기존 Microsoft 클라우드 고객은 이제 사용자 Office 365, Dynamics 365 고객 참여 및 Power Platform 고객 마이그레이션을 시작할 수 있습니다. 첫 번째 단계는 Microsoft 주도 신규 독일 데이터 센터 지역으로의 [마이그레이션에 동의](./ms-cloud-germany-migration-opt-in.md)하는 것입니다. 

Microsoft 주도 방식에 옵트인(opt in)하는 조직의 경우 마이그레이션은 2021년 초에 시작될 예정이고 2021년 10월 29일까지 완료됩니다. 마이그레이션이 되면 핵심 고객 데이터 및 구독정보는 신규 독일 지역으로 이전됩니다. 

이 문서에서는 마이그레이션을 위한 Microsoft 주도 접근 방식, 마이그레이션 중 및 후에 사용자와 관리자를 위한 환경의 명확성, 활용하는 워크로드에 따라 고객에게 요구될 수 있는 작업에 대한 개요를 제공합니다.

Microsoft 주도 방식에 동의하면 다음 서비스도 함께 마이그레이션됩니다.

- Azure Active Directory(Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- 비즈니스용 OneDrive
- 비즈니스용 Skype 온라인\*\*
- Office 365 그룹
- Dynamics 365/Power Platform\*\*\*

\*\*독일 Microsoft 클라우드에서 독일 데이터 센터 지역으로 마이그레이션하는 동안 기존 비즈니스용 Skype Online 고객은 해당 지역으로 Microsoft Teams. 자세한 내용은 [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)를 참조하세요.

\*\*\*이러한 서비스에 대한 마이그레이션의 선행 요구 및 영향은 [Dynamics 365 고객 참여 문서에 설명되어](/dynamics365/get-started/migrate-data-german-region) 있습니다.

Office 365 비디오가 2021년 3월 1일에 사용 중지됩니다. Office 365 테넌트를 새 독일어 데이터 센터 영역으로 마이그레이션하도록 선택하면 SharePoint Online 마이그레이션이 완료된 후에 Office 365 비디오가 지원되지 않습니다. 자세한 내용은 도이클란드 [Microsoft 클라우드 타임라인을 참조하세요.](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>마이그레이션은 어떻게 구성하나요?

이 그림에서는 새로운 독일 데이터 센터로의 10개 마이그레이션 단계를 보여 주었다.

:::image type="content" alt-text="새 독일 데이터 센터로의 10단계 마이그레이션 단계" source="../media/ms-cloud-germany-migration-opt-in/migration-organization.png" lightbox="../media/ms-cloud-germany-migration-opt-in/migration-organization.png":::

마이그레이션에 옵트인(opt [in)할 때 이러한 단계가 시작됩니다.](./ms-cloud-germany-migration-opt-in.md) 대부분의 마이그레이션 단계는 최소한의 고객 상호 작용이 필요하며 백 엔드 서비스 작업으로 실행되고 한 단계 후에 실행됩니다. 추가 고객 주도 작업의 시작 및 전체 마이그레이션 상태는 마이그레이션 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank"></a> 프로세스 중에 Microsoft 365 관리 센터 메시지 센터를 통해 전달됩니다. 작업의 예로는 고객 관리 DNS 업데이트, 하이브리드 고객을 위한 하이브리드 설정 Exchange 또는 Azure 마이그레이션이 있습니다.

옵트인(opt in)이 발생하면 마이그레이션이 즉시 시작되지는 않습니다. 조직이 이후 마이그레이션을 위해 예약된 테넌트 목록에 추가됩니다. 완료 시 성공적인 마이그레이션 및 사용을 보장하기 위해 이러한 단계가 중요하기 때문에 작업 전 단계를 시작할 수 있습니다.

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)

테넌트 마이그레이션이 시작된 지 1주 전에 메시지 센터 서비스에서 모든 선행 작업을 완료해야 하다는 최종 경고가 표시됩니다.

마이그레이션은 주권 독일 Azure AD 서비스에서 EU 지역의 Azure AD의 Office 365 서비스 인스턴스로 Azure AD 테넌트가 이동됩니다.

다음 단계는 독일 특정 제품에서 글로벌 제품으로&#39;테넌트 구독 및 사용자 라이선스를 마이그레이션하는 것입니다.

고객 Azure 마이그레이션을 포함하여 모든 단계가 완료되면 테넌트가 Office 365 서비스 서비스에서 완료된 것으로 표시되어 마이그레이션이 완료된 것으로 표시됩니다. 이제 메시지 센터에 대한 최종 업데이트가 제공됩니다. 테넌트는 이제 조직에서 완전히 Office 365 있습니다.

메시지 센터 게시물을 통해 마이그레이션 진행률에 대한 알림을 수신합니다. 게시물은 특정 중요 시점에 진행될 뿐만 아니라 단계 진행에 대한 지침과 고객이 프로세스 요구 사항에 따라 행동할 수 있는 중요한 정보를 제공합니다. 메시지 센터 알림은 다음 중요 시점에 제공됩니다.

- 마이그레이션 시작(Azure AD 마이그레이션 시작 5일 전)
- Azure AD 마이그레이션 완료
- 구독 및 라이선스 마이그레이션 완료
- SharePoint 완료
- Exchange 완료
- 비즈니스용 Skype 완료
- Dynamics 완료
- Power BI 완료
- 최종 서비스 컷오버 완료

Azure AD를 전 세계 서비스로 최종 전환한 후 모든 클라이언트와 응용 프로그램이 올바른 끝점을 사용하기 위해 완전히 전환될 것으로 예상됩니다. 최종 컷오버 이후 30일간의 기간이 있습니다. 여기서 도이치란드 Microsoft 클라우드 서비스에서 Azure AD 토큰을 계속 얻을 수 있습니다. 30일 기간이 만료되면 클라이언트와 응용 프로그램은 더 이상 도이치랜드 Microsoft 클라우드의 Azure AD 끝점에 액세스할 수 없습니다. 이 시점부터 응용 프로그램 또는 사용자 액세스가 실패합니다. 이 시간 창이 닫히기 전에 모든 사용자 및 응용 프로그램이 올바른 끝점으로 마이그레이션되도록 해야 합니다. 

## <a name="moving-to-the-new-german-datacenter-regions"></a>새 독일 데이터 센터 지역으로 이동

이제 도이치클라드 기존 Microsoft 클라우드 고객은 이제 사용자 Office 365, Dynamics 365 고객 참여 및 Power Platform 서비스 마이그레이션을 시작할 수 있습니다. 첫 번째 단계는 Microsoft 주도 신규 독일 데이터 센터 지역으로의 [마이그레이션에 동의](./ms-cloud-germany-migration-opt-in.md)하는 것입니다.  구독을 갱신하면 Microsoft 지원 마이그레이션에 자동으로 옵트인(opt in)합니다. Microsoft는 이러한 경우 고객 테넌트 관리자에게 전자 메일과 메시지 센터에 Microsoft 365 관리 센터 알릴 것입니다. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank"></a> 그러나 지금 프로세스를 시작하고자 하는 경우 지금 바로 옵트인(opt <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">in)할 Microsoft 365 관리 센터</a> 있습니다. [](./ms-cloud-germany-migration-opt-in.md) 마이그레이션은 2021년 초에 시작될 예정이고 2021년 10월 29일까지 완료됩니다. 

마이그레이션의 결과로 핵심 고객 데이터 및 구독이 새로운 독일 데이터 센터 지역으로 이동됩니다.

> [!NOTE]
> 이 문서에는 서비스 마이그레이션에 대한 지침만 Office 365 포함되어 있습니다. 도이치클란드 Microsoft 클라우드에서 추가 Azure 워크로드를 실행하는 경우 Azure Germany에 대한 마이그레이션 지침을 [참조하세요.](/azure/germany/germany-migration-main)

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Office 365 서비스 신규 독일 데이터 센터 지역으로의 마이그레이션을 준비하는 방법 

첫 번째 단계는 독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 서비스로 구독 및 데이터를 Office 365 수 있도록 Microsoft에 알리는 것입니다. 지침은 [옵트인 프로세스를](./ms-cloud-germany-migration-opt-in.md) 참조하고 다음에 유의하세요.

- 모든 마이그레이션 고객은 새 독일 데이터 센터 지역을 Office 365 OFFICE 365 [및 IP](urls-and-ip-address-ranges.md)주소에 대한 연결을 확인해야 합니다. 비활성으로 인해 서비스 및 클라이언트 오류가 발생될 수 있습니다.
- 조직에서 변경 [](ms-cloud-germany-transition-add-pre-work.md) 내용을 알리고 준비할 수 있도록 작업 전 활동 목록을 검토합니다.
- 독일 지역으로 마이그레이션한 Office 365 조직에서 사용할 수 있는 기능 및 서비스를 이해하기 위해 플랫폼 서비스 설명을 검토해야 합니다.
- 평가판 구독은 마이그레이션되지 않습니다. 모든 유료 구독의 마이그레이션이 차단됩니다. 마이그레이션을 시작하기 전에 평가판을 취소하거나 유료 구독으로 전환해야 합니다.

## <a name="where-do-i-go-from-here"></a>여기에서 어디로 이동하나요?

다음 질문과 대답 섹션을 검토하세요.

## <a name="frequently-asked-questions"></a>FAQ

### <a name="is-migration-required"></a>마이그레이션이 필수인가요? 

Microsoft는 Office 365 독일 클라우드에서 독일 신규 데이터 센터 Office 365 서비스로 테넌트 마이그레이션을 추가 비용부분으로 제공했습니다. 이제 적격 Microsoft 클라우드 독일(독일 Microsoft 클라우드) 고객이 모두 마이그레이션되었습니다. 추가 고객은 자동화된 프로세스를 통해 마이그레이션되지 않습니다. 나머지 Microsoft 클라우드 독일 구독 및 테넌트는 서비스 폐쇄 활동의 일부로 2021년 9월에 비활성화 및 비활성화됩니다.

Microsoft는 서비스가 폐쇄될 때까지 필요한 보안 업데이트를 도이클랜드 지역에 계속 제공할 것입니다. 

Office 365 독일 데이터 센터 지역에 서비스를 제공합니다.

- 경쟁력 있는 가격의 [Azure](https://azure.microsoft.com/pricing/calculator/),[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 고객 참여](https://dynamics.microsoft.com/pricing/) 및 [Power BI](https://powerbi.microsoft.com/pricing/)를 제공 합니다.
- Microsoft&#39;글로벌 네트워크에 연결되어 수백 개의 네트워크 에지 사이트, 피어 위치 및 이스그 포인트를 통해 전 세계 어디서나 강력한 사용자 환경을 제공합니다.
- 독일 내 지역 고객 데이터 보관 요구사항을 충족하는데 도움을 줍니다. 
- 최신 버전의 서비스 및 새로운 기능(Microsoft Teams 및 Multi-Geo 포함)으로 모든 기능을 제공하는 글로벌 클라우드 서비스를 Office 365. [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) 및 [Dynamics 365](/dynamics365/get-started/availability)의 지역별 상품을 비교하세요. 
- 고객의 준법 및 규정 요구 사항을 충족 할 수 있도록 모든 기능, 엔터프라이즈급 보안 및 종합 기능을 제공 합니다.
- 기존 온라인 서비스 계약을 통해 사용 가능합니다. 

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>여러 Office 365 클라우드 서비스 간에 사용할 수 있는 서비스는 무엇인가요?
<h2 id="serv-avail"></h2>

다음 15개 서비스는 도이치클라드 Microsoft 클라우드 서비스 제품에서 사용할 수 있습니다. Microsoft 클라우드 도이클란드에 새 서비스를 추가하고 있지 않습니다.

1. Exchange Online
2. 고객 Lockbox (Exchange Online)
3. 그룹 (모던 그룹)
4. Delve 프로필
5. Exchange Online Protection
6. Office 365용 Defender
7. Advanced eDiscovery
8. 고급 데이터 관리
9. SharePoint Online
10. 고객 Lockbox (SharePoint Online)
11. 비즈니스용 OneDrive
12. 비즈니스용 Skype Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

현재 새 독일 데이터 센터 지역의 Office 365 서비스로 39개 서비스를 사용할 수 있습니다. 계속해서 글로벌 Office 365 서비스와 일관된 새로운 기능과 서비스가 제공될 것입니다. 

1. Exchange Online
2. 고객용 Lockbox Exchange Online
3. Microsoft 365 그룹
4. Delve 프로필
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. Office 365용 Defender
9. Advanced eDiscovery
10. 고급 보안 관리
11. Office 365에 대한 정보 보호 
12. 고급 데이터 관리
13. SharePoint Online
14. 온라인용 고객 SharePoint Lockbox
15. 비즈니스용 OneDrive
16. Microsoft Stream
17. 비즈니스용 Skype(마이그레이션 중에 Microsoft Teams 마이그레이션)
18. 클라우드 PBX
19. PSTN 회의
20. PSTN 통화
21. Microsoft Teams
22. 관리 보고서/사용 현황 보고서
23. 웹용 Office
24. Planner
25. Sway
26. Microsoft 365 앱
27. Outlook Mobile
28. Enterprise Mobility + Security(EMS) E3(Azure AD Premium P1, Intune 및 권한 관리 서비스)
29. Yammer Enterprise
30. Microsoft Forms
31. Power Automate 대한 Office 365
32. Power Virtual Agents 대한 Office 365
33. Power Apps 대한 Office 365
34. Microsoft Bookings
35. 할 일
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. 목록

### <a name="when-will-migration-happen"></a>언제 마이그레이션 되나요? 

**Azure**

Azure 고객만 있는 경우 현재 [](/azure/germany/germany-migration-main) Azure 리소스를 다른 지역으로 마이그레이션할 수 있습니다. 

Office 365, Dynamics 365 또는 Power BI Azure가 있는 경우 자체 지시 Azure 마이그레이션을 시작하기 전에 먼저 Office 365 서비스에 대한 마이그레이션 프로세스를 따라야 합니다. Azure AD 및 테넌트 조직과 함께 Azure 워크로드를 유지 관리하려면 테넌트 마이그레이션을 완료하기 전에 Azure 마이그레이션을 Office 365 합니다. 자세한 [내용은 도이치란드 Microsoft](ms-cloud-germany-transition-phases.md) 클라우드에서 마이그레이션에 대한 마이그레이션 단계 작업 및 영향을 참조합니다.

**Office 365, Dynamics 365 및 Power BI**

이제 적격 Microsoft 클라우드 독일(독일 Microsoft 클라우드) 고객이 모두 마이그레이션되었습니다. 추가 고객은 자동화된 프로세스를 통해 마이그레이션되지 않습니다. 나머지 Microsoft 클라우드 독일 구독 및 테넌트는 서비스 폐쇄 활동의 일부로 2021년 9월에 비활성화 및 비활성화됩니다.

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>사용하는 Office 365 서비스에 대한 가격이 변경하나요?

예. Microsoft&#39;전역 클라우드 지역(새 데이터 센터 지역 포함)의 가격은 일반적으로 낮습니다.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>구독 마이그레이션 중에 조직 및 사용자에게 어떤 SKUS 및 라이선스가 적용될까요?

독일 Microsoft 클라우드에서 Office 365 서비스로 마이그레이션하는 동안 독일 서비스 관련 SKU는 동일하거나 유사한 SKU의 전역 버전으로 대체됩니다. 대부분의 경우 Office 365 서비스의 SKU는 동일합니다. 그러나 독일의 SKU가 Office 365 서비스에서 더 이상 사용할 수 없는 대체는 거의 없습니다. 마이그레이션이 완료된 후 조직에 할당된 SKU를 업데이트하려면 판매자에 문의하여 할당된 서비스를 추가하거나 수정합니다.

| 도이치클란드 Microsoft 클라우드 - 제품 SKU(DE) | Microsoft Cloud Global - WW(제품 SKU) |
| --- | --- |
| 고객 Lockbox \_ DE(LOCKBOX \_ DE) | 고객 Lockbox(LOCKBOX) |
| Dynamics 365 Enterprise Edition - 추가 데이터베이스 Storage \_ DE(CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition - 추가 데이터베이스 Storage(CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - 추가 비 프로덕션 인스턴스 \_ DE(CRMTESTINSTANCE \_ DE) | Dynamics 365 Enterprise Edition - 추가 비 프로덕션 인스턴스(CRMTESTINSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 for Customer Service Enterprise Edition(DYN365 \_ ENTERPRISE \_ CUSTOMER \_ SERVICE) |
| Dynamics 365 for Sales Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE SALES \_ \_ DE) | Dynamics 365 for Sales Enterprise Edition(DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 for Team Members Enterprise Edition(DYN365 \_ ENTERPRISE \_ 팀 \_ 구성원) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 계획 1 Enterprise Edition(DYN365 \_ ENTERPRISE \_ PLAN1) |
| \_ECAL Services (EOA, EOP, DLP) DE(ECAL \_ SERVICES \_ DE) | ECAL Services (EOA, EOP, DLP)(ECAL \_ SERVICES) |
| \_Enterprise Mobility + Security E3 DE(EMS \_ DE) | Enterprise Mobility + Security E3(EMS) |
| \_Exchange Online(계획 1) DE (EXCHANGESTANDARD \_ DE) | Exchange Online(계획 1)(EXCHANGESTANDARD) |
| \_Exchange Online(계획 2) DE (EXCHANGEENTERPRISE \_ DE) | Exchange Online(계획 2)(EXCHANGEENTERPRISE) |
| \_Exchange Online용 Exchange Online Archiving DE (EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online용 Exchange Online Archiving(EXCHANGEARCHIVE \_ ADDON) |
| \_Exchange Server용 Exchange Online Archiving DE (EXCHANGEARCHIVE \_ DE) | Exchange Server용 Exchange Online Archiving(EXCHANGEARCHIVE) |
| \_Exchange Online Essentials DE(EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials(EXCHANGE S \_ \_ ESSENTIALS) |
| \_Exchange Online Kiosk DE(EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk(EXCHANGEDESKLESS) |
| \_Exchange Online Protection DE(EOP \_ ENTERPRISE \_ DE) | Exchange Online Protection(EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard(O365 BUSINESS \_ \_ PREMIUM) | Microsoft 365 Business Standard(O365 BUSINESS \_ \_ PREMIUM) |
| Microsoft Dynamics CRM Online 인스턴스 \_ DE(CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online 인스턴스(CRMINSTANCE) |
| Office 365 A1 \_ DE(STANDARDWOFFPACK \_ FACULTY \_ DE) | Office 365 A1(STANDARDWOFFPACK \_ FACULTY) |
| Office 365 A1 \_ DE(STANDARDWOFFPACK \_ STUDENT \_ DE) | Office 365 A1(STANDARDWOFFPACK \_ STUDENT) |
| \_Office 365 Advanced Compliance DE (EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 Compliance(정보 \_ 보호 \_ 규정 준수) |
|Microsoft Defender for Office 365 (Plan 1) \_ DE (ATP \_ ENTERPRISE \_ DE) |Microsoft Defender for Office 365(계획 1)(ATP \_ ENTERPRISE) |
| \_Office 365 Business Essentials DE (O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic(O365 BUSINESS \_ \_ ESSENTIALS) |
| \_Office 365 Business Premium DE(O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard(O365 BUSINESS \_ \_ PREMIUM) |
| \_Office 365 Business DE(O365 \_ BUSINESS \_ DE) | 비즈니스용 Microsoft 365 앱(O365 \_ BUSINESS) |
| \_Office 365 E1 DE(STANDARDPACK \_ DE) | Office 365 E1(STANDARDPACK) |
| Office 365 E3 DE가 없는 \_ 경우(ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | Office 365 E3 없는 경우(ENTERPRISEPACKWITHOUTPROPLUS) |
| \_Office 365 E3 DE(ENTERPRISEPACK \_ DE) | Office 365 E3(ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE(STANDARDPACK \_ DE) | Office 365 Enterprise E1(STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE(ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3(ENTERPRISEPACK) |
| \_Office 365 Extra File Storage DE(SHAREPOINTSTORAGE \_ DE) | Office 365 Extra File Storage(SHAREPOINTSTORAGE) |
| \_Office 365 F1 DE(DESKLESSPACK \_ DE) | Office 365 F1(DESKLESSPACK) |
| Office 365 ProPlus \_ DE(OFFICESUBSCRIPTION \_ FACULTY \_ DE) | Office 365 ProPlus(OFFICESUBSCRIPTION \_ FACULTY) |
| Office 365 ProPlus \_ DE(OFFICESUBSCRIPTION \_ STUDENT \_ DE) | Office 365 ProPlus(OFFICESUBSCRIPTION \_ STUDENT) |
| \_Office 365 ProPlus DE (OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus(OFFICESUBSCRIPTION) |
| \_비즈니스용 OneDrive(요금제 1) DE (WACONEDRIVESTANDARD \_ DE) | 비즈니스용 OneDrive(요금제 1)(WACONEDRIVESTANDARD) |
| \_비즈니스용 OneDrive(요금제 2) DE (WACONEDRIVEENTERPRISE \_ DE) | 비즈니스용 OneDrive(요금제 2)(WACONEDRIVEENTERPRISE) |
| Power BI Pro \_ DE(POWER \_ BI PRO \_ \_ FACULTY \_ DE) | Power BI Pro(POWER \_ BI \_ PRO \_ FACULTY) |
| \_Power BI Pro DE(POWER \_ BI \_ PRO \_ DE) | Power BI Pro(POWER BI \_ \_ PRO) |
| \_Project Online Essentials DE (PROJECTESSENTIALS \_ DE) | Project Online Essentials(PROJECTESSENTIALS) |
| \_Project Online Premium DE (PROJECTPREMIUM \_ DE) | Project Online Premium(PROJECTPREMIUM) |
| \_Project Online Professional DE(PROJECTPROFESSIONAL \_ DE) | Project Online Professional(PROJECTPROFESSIONAL) |
| \_Project 플랜 3 DE(PROJECTPROFESSIONAL \_ DE) | Project 플랜 3(PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE(ENTERPRISEWITHSCAL \_ DE) | Office 365 E3(ENTERPRISEPACK) |
| \_SharePoint Online(계획 1) DE(SHAREPOINTSTANDARD \_ DE) | SharePoint Online(계획 1)(SHAREPOINTSTANDARD) |
| \_SharePoint Online(계획 2) DE (SHAREPOINTENTERPRISE \_ DE) | SharePoint Online(계획 2)(SHAREPOINTENTERPRISE) |
| 비즈니스용 Skype Online(계획 1) \_ DE(MCOIMP \_ DE) | Office 365 E1(STANDARDPACK) |
| 비즈니스용 Skype Online(계획 1) \_ DE(MCOIMP \_ DE) | 비즈니스용 Skype 온라인(계획 1)(MCOIMP) |
| 비즈니스용 Skype Online (Plan 2) \_ DE (MCOSTANDARD \_ DE) | 비즈니스용 Skype 온라인(계획 2)(MCOSTANDARD) |
| 비즈니스용 Skype Plus CAL \_ DE(MCOPLUSCAL \_ DE) | 비즈니스용 Skype Plus CAL(MCOPLUSCAL) |
| Visio 교직원용 온라인 계획 \_ 1(VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | Visio 교직원용 온라인 계획 1(VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio 온라인 계획 1 \_ DE(VISIOONLINE \_ PLAN1 \_ DE) | Visio 온라인 계획 1(VISIOONLINE \_ PLAN1) |
| Visio 교직원용 온라인 계획 2 \_ DE(VISIOCLIENT \_ FACULTY \_ DE) | Visio 교직원용 온라인 계획 2(VISIOCLIENT \_ FACULTY) |
| Visio 온라인 계획 2 \_ DE(VISIOCLIENT \_ DE) | Visio 온라인 계획 2(VISIOCLIENT) |
| \_Visio 플랜 1 DE(VISIOONLINE \_ PLAN1 \_ DE) | Visio 플랜 1(VISIOONLINE \_ PLAN1) |
| \_Visio 플랜 2 DE(VISIOCLIENT \_ DE) | Visio 플랜 2(VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>신규 지역으로 마이그레이션 할 때 도움이 필요하거나 문의 사항이 있으면 어떻게 해야 하나요? 

질문이 있는 경우 다음을 문의하거나 파트너에게 문의할 수 있습니다.

- Azure의 경우 Azure 포털에서 [새 지원 요청을](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) 제출하세요. 
- 자세한 Office 365 의 도움이 필요하세요? 링크를 사용하여 질문을 &quot; &quot; 제출할 [Microsoft 365 관리 센터.](https://portal.office.de/)
- Dynamics 365 고객 참여 및 Power BI 고객인 경우 Office 365 도움이 필요하세요? 링크를 사용하여 질문을 제출할 &quot; &quot; 수 [Microsoft 365 관리 센터.](https://portal.office.de/) Dynamics 365 고객 참여 지원은 [여기](/dynamics365/get-started/support/)를 이용하세요.  Power BI 지원은 [여기](https://powerbi.microsoft.com/support/)를 이용하세요. 

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>고객에게는 도이치랜드 Microsoft 클라우드와 함께 글로벌 Microsoft 클라우드에 M365 테넌트가 이미 있습니다. 마이그레이션의 일부로 이러한 두 테넌트가 하나의 테넌트에 병합될 수 있나요?

아니요. 테넌트 병합 기능이 없는 경우 모든 테넌트에 고유한 네임스페이스 및 고유 ID가 있는 경우 테넌트는 별개의 고유한 상태로 유지됩니다. Microsoft는 원하는 경우 Microsoft 클라우드 도이치랜드 테넌트를 글로벌 클라우드로 마이그레이션하거나 고객이 이를 취소하고 취소할 수 있습니다.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>마이그레이션의 일부로 대부분의 최종 사용자가 수행해야 하는 작업은 무엇입니까?
마이그레이션은 최종 사용자/고객에게 최소한의 영향을 미치기 위해 고안된 것입니다.
- 응용 Office 사용 가능한 최신 버전을 실행 중인지 확인 
- 마이그레이션을 사용하는 비즈니스용 Skype 마이그레이션의 일부로 Teams 전환할 예정이기 때문에 장치에 앱을 다운로드하여 [설치해야 Teams](/deployoffice/teams-install) 있습니다.
- 최종 사용자는 마이그레이션이 완료되면 Office 응용 프로그램에서 로그아웃하고 다시 로그인해야 할 수 있습니다. 
- OneDrive 동기화 클라이언트를 실행하는 고객은 OneDrive 동기화 클라이언트가 전역 Azure Active Directory 서비스에 로그인할 수 있도록 자신의 Azure Active Directory 로그아웃해야 합니다.
- 마이그레이션이 완료되면 새 전역 URL에 유의해야 합니다Outlook 웹 액세스(예: outlook.office365.com). SharePoint 온라인 클라이언트는 기존 URL을 사용하여 MCD 네임스페이스에 계속 연결합니다(예: contoso.sharepoint.de).


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>마이그레이션의 영향을 받는 고객은 Azure Active Directory 있나요? 

모든 고객 Office 365 Microsoft Azure Active Directory 서비스 운영에 필요한 중요한 서비스 구성 요소를 인증하고 저장하는 데 필요한 구성 요소에 의존합니다. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>마이그레이션의 영향은 Azure Active Directory 무엇입니까?

초기 Azure Active Directory 초기 마이그레이션은 고객 환경에 영향을 끼치지 않습니다. 최종 마이그레이션 단계 후 고객 테넌트에 대한 모든 서비스가 전역 서비스에 완전히 있습니다. 이 최종 단계가 Azure Active Directory 도이치랜드의 Azure Active Directory 서비스는 더 이상 권한 부여 요청을 수락하거나 Office 서비스에 대한 액세스 토큰을 제공할 수 없습니다.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>서비스 URL 및 IP 주소에 대한 네트워크 Office 365 의미는 [무엇입니까?](./urls-and-ip-address-ranges.md)

이 문서에서는 올바른 고객 환경을 보장하기 위해 전역 서비스의 적절한 기능에 필요한 URL 및 IP 주소에 대해 설명합니다. 비교적 드문 경우지만 일부 고객은 트래픽 흐름을 최소화하고 Microsoft 클라우드 도이클라드 서비스 IP 범위의 일부로만 서비스에 대한 액세스를 제한하는 방식으로 네트워크 경계 보안을 구성하려고 합니다.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>메일이 계속 흐르게 Exchange Online DNS 변경 내용을 관리하는 방법

Microsoft에서 관리하는 IP 범위 및 DNS 영역은 전역 서비스로 마이그레이션하는 동안 및 마이그레이션의 일부로 전환됩니다. 

사용자 지정 도메인 MX 레코드와 같은 고객 관리 DNS 영역은 고객의 책임입니다. 그러나 이 마이그레이션을 간소화하기 위해 고객은 MX 레코드가 Office 365 영역의 Office 365 office.de 서비스 끝점을 지점으로 지정하고 Microsoft는 이 서비스 끝점의 마이그레이션을 자동으로 관리합니다.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>사용자에 대한 DNS 변경 내용을 관리하는 비즈니스용 Skype? 
 
모든 Skype 비즈니스용 고객으로 전환할 Microsoft Teams. 고객 Skype DNS 영역으로 마이그레이션할 필요는 Teams. 고객은 마이그레이션 후 모든 기능을 Teams 즉시 로그인할 수 있습니다.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>마이그레이션 Outlook iOS 및 Android용 버전이 작동하나요? 

예. 모든 고객은 iOS 및 Android 클라이언트용 업데이트를 포함하여 사용 가능한 최신 버전의 Office 클라이언트를 Outlook 것이 좋습니다. Office 365 전역 서비스로의 마이그레이션이 완료된 후 모든 Office 클라이언트가 로그아웃했다가 다시 로그인하여 전역 서비스에서 새 Azure Active Directory 액세스 토큰을 얻어야 합니다. 



## <a name="next-step"></a>다음 단계

[마이그레이션에 대해 옵트인](ms-cloud-germany-migration-opt-in.md)

## <a name="more-information"></a>추가 정보

시작:

- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)
- [마이그레이션 중의 고객 환경](ms-cloud-germany-transition-experience.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 마이그레이션 프로그램 정보](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)
