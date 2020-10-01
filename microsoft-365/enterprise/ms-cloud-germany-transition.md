---
title: Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 09/30/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: '요약: 독일 Microsoft 클라우드(도이칠란드 Microsoft 클라우드)에서 Office 365 서비스 독일 신규 데이터 센터 지역으로의 마이그레이션 이해 '
ms.openlocfilehash: a77dc43c4c30992d2e50aad94878f9269573db52
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327120"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션

> [!NOTE]
> 이 문서는 적격 Microsoft Cloud 독일 고객 에게만 적용 됩니다.

Microsoft는 2018 년 8 월에 전체 Microsoft 클라우드-Azure, Office 365, Dynamics 365 및 파워 플랫폼을 사용 하 여 고객의 디지털 변환을 보다 효율적으로 수행할 수 있도록 독일의 새 클라우드 지역에서 제공 합니다. 2019년 8월, 독일의 신규 클라우드 지역 출범을 발표합니다.   Azure, Office 365, Dynamics 365 및 파워 플랫폼의 가용성을 알린 이후로 제공 되었습니다.

새 지역은 독일어 고객이 보다 큰 유연성, 최신 지능형 클라우드 서비스 및 Microsoft 365 서비스 클라우드 네트워크에 대 한 전체 연결 및 독일 내의 고객 데이터 상주에 대 한 완전 한 연결성을 제공 하도록 디자인 되었습니다.

## <a name="how-to-migrate-to-the-new-german-regions"></a>새 독일어 지역으로 마이그레이션하는 방법

기존 Microsoft 클라우드 독일 고객은 이제 Office 365, Dynamics 365 고객 계약 및 파워 플랫폼 고객의 마이그레이션을 시작할 수 있습니다. 첫 번째 단계는 Microsoft 주도 신규 독일 데이터 센터 지역으로의 [마이그레이션에 동의](https://aka.ms/office365germanymoveoptin)하는 것입니다. 

Microsoft 기반 방법을 사용 하는 조직의 경우 마이그레이션은 초기 2021에 시작 되 고 2021 년 10 월 29 일에 완료 됩니다. 마이그레이션이 되면 핵심 고객 데이터 및 구독정보는 신규 독일 지역으로 이전됩니다. 

이 문서에서는 마이그레이션의 Microsoft 기반 접근 방식에 대 한 개요를 제공 하 고, 마이그레이션 중에 사용자 및 관리자의 경험을 명확 하 게 설명 하 고, 사용 하는 작업 부하를 기반으로 고객에 게 필요한 작업을 소개 합니다.

Microsoft 주도 방식에 동의하면 다음 서비스도 함께 마이그레이션됩니다.

- Azure Active Directory (Azure AD)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- 비즈니스용 OneDrive

- 비즈니스용 Skype Online\*\*
- Office 365 그룹
- Dynamics 365/전원 플랫폼\*\*\*

\*\*Microsoft Cloud 독일에서 독일어 데이터 센터 지역으로 마이그레이션하는 동안, 기존 비즈니스용 Skype Online 고객은 Microsoft 팀으로 전환 됩니다. 자세한 내용은 [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)를 참조하세요.

\*\*\*이러한 서비스에 대 한 마이그레이션의 필수 구성 요소 및 영향은 [Dynamics 365 고객 계약](https://aka.ms/d365ceoptin) 문서에 설명 되어 있습니다.

Office 365 비디오가 2021년 3월 1일에 사용 중지됩니다. Office 365 테넌트를 새 독일어 데이터 센터 영역으로 마이그레이션하도록 선택하면 SharePoint Online 마이그레이션이 완료된 후에 Office 365 비디오가 지원되지 않습니다. 자세한 내용을 보려면 [여기](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline) 를 클릭 하세요.

## <a name="how-is-the-migration-organized"></a>마이그레이션 구성 방법

이 그림은 새로운 독일어 데이터 센터로 마이그레이션의 Office 365 및 Dynamics 365의 다양 한 구성 요소를 나타냅니다.

![새 독일 데이터 센터로 마이그레이션의 Office 365 및 Dynamics 365의 구성 요소](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

마이그레이션은 [마이그레이션을 옵트인](https://aka.ms/office365germanymoveoptin)할 때 모두 시작 되는 단계로 실행 됩니다. 대부분의 마이그레이션 단계는 최소 고객 상호 작용을 사용 하 여 백 엔드 서비스 작업으로 실행 되며, 한 단계 후에 한 단계로 실행 됩니다. 추가 고객-led 작업 및 전체 마이그레이션 상태에 대 한 시작은 마이그레이션 프로세스 동안 Microsoft 365 관리 센터의 메시지 센터를 통해 전달 됩니다. 작업 예에는 고객 관리 DNS 업데이트, Exchange hybrid customers에 대 한 하이브리드 설치 재구성 또는 Azure migration이 포함 될 수 있습니다.

옵트인이 수행 될 때 마이그레이션이 즉시 시작 되지 않습니다. 조직이 나중에 마이그레이션을 위해 예약 된 테 넌 트 목록에 추가 됩니다. 작업이 완료 되 면 성공적인 마이그레이션 및 사용을 보장 하기 위해 작업 전 단계를 지금 시작할 수 있습니다.

테 넌 트 마이그레이션을 시작 하기 1 주 전에 메시지 센터 서비스에 모든 필수 구성 요소가 완료 되어야 함을 알리는 최종 경고가 표시 됩니다.

마이그레이션이 Azure AD 테 넌 트를 sovereign 클라우드에 전라남도 Azure AD 서비스에서 EU 지역에 있는 Azure AD의 Office 365 services 인스턴스로 이동 합니다.

다음 단계는 사용자의 테 넌 트&#39;s/독일 관련 제품에서의 구독 및 라이선스 마이그레이션입니다.

고객 Azure 마이그레이션을 포함 하 여 모든 단계가 완료 되 면 테 넌 트가 Office 365 services 서비스에 마무리 되 고 마이그레이션이 완료 된 것으로 표시 됩니다. 그러면 메시지 센터에 대 한 최종 업데이트가 사용자에 게 제공 됩니다. 이 테 넌 트는 이제 완전 한 글로벌 Office 365 조직이 아닙니다.

메시지 센터 게시물이 있는 마이그레이션 진행 상황에 대 한 알림이 제공 됩니다. 이 게시물은 특정 중요 시점에서 발생 하며, 프로세스 요구 사항에 따라 고객이 수행 하는 중요 한 정보 뿐만 아니라 단계의 진행 지침을 제공 합니다. 메시지 센터 알림은 다음 중요 시점에서 제공 됩니다.

- 마이그레이션 시작 (Azure AD 마이그레이션이 시작 되기 전까지 영업일 중 5 일)
- Azure AD 마이그레이션 완료
- 구독 및 라이선스 마이그레이션 완료
- SharePoint 마이그레이션 완료
- Exchange 마이그레이션 완료
- 비즈니스용 Skype 완료
- Dynamics complete
- Power BI 완료
- 서비스의 최종 가공선 완료

## <a name="moving-to-the-new-german-regions"></a>신규 독일 지역으로 이전 

기존 Microsoft Cloud 전라남도 (Microsoft 클라우드 독일) 고객은 이제 Office 365, Dynamics 365 고객 계약 및 파워 플랫폼 고객의 마이그레이션을 시작할 수 있습니다. 첫 번째 단계는 Microsoft 주도 신규 독일 데이터 센터 지역으로의 [마이그레이션에 동의](https://aka.ms/office365germanymoveoptin)하는 것입니다.  구독을 갱신할 때 Microsoft 지원 마이그레이션을 자동으로 옵트인 합니다. Microsoft는 고객 테 넌 트 관리자에 게 전자 메일과 Microsoft 365 관리 센터의 메시지 센터에서이 문제가 발생 한 경우이를 알려 줍니다. 그러나 지금 프로세스를 시작 하려는 경우 현재 Microsoft 365 관리 센터에서 직접 [옵트인](https://aka.ms/office365germanymoveoptin) 할 수 있습니다. 마이그레이션은 초기 2021에 시작 하 고 2021 년 10 월 29 일에 완료 될 예정입니다. 

마이그레이션이 되면 핵심 고객 데이터 및 구독정보는 신규 독일 지역으로 이전됩니다. 

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Office 365 서비스 신규 독일 데이터 센터 지역으로의 마이그레이션을 준비하는 방법 

첫 번째 단계는 Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 구독 및 데이터를 마이그레이션할 수 있는 권한이 있도록 Microsoft에 알리는 것입니다. [옵트인 프로세스](https://aka.ms/office365germanymoveoptin) 에서 지침을 참조 하 고 다음 사항을 확인 하세요.

- 모든 마이그레이션 고객은 새로운 독일어 데이터 센터 지역을 포함 하는 Office 365 서비스 [office 365 url 및 IP 주소](urls-and-ip-address-ranges.md)에 대 한 연결을 확인 해야 합니다. Inaction에서 서비스 및 클라이언트 오류가 발생할 수 있습니다.
- 독일어 지역으로 마이그레이션한 후에는 Office 365 플랫폼 서비스 설명을 검토 하 여 조직에서 사용할 수 있는 기능 및 서비스를 파악 해야 합니다.
- 평가판 구독은 마이그레이션되지 않으며 유료 구독의 마이그레이션도 차단 됩니다. 마이그레이션을 시작 하기 전에 모든 평가판을 취소 하거나 유료 구독으로 변환 해야 합니다.

## <a name="where-do-i-go-from-here"></a>여기서는 어디에서 이동 하나요?

다음에 대 한 faq (질문과 대답) 섹션을 검토 하십시오.

## <a name="frequently-asked-questions"></a>FAQ

### <a name="is-migration-required"></a>마이그레이션이 필수인가요? 

Microsoft는 Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역에 추가 비용 없이 office 365 서비스에 Office 365 테 넌 트 마이그레이션을 제공 합니다. 새 독일어 데이터 센터 지역으로 마이그레이션하기 위해 옵트인 하는 것이 좋지만 Microsoft 클라우드 독일 지역에는 계속 해 서 필요한 보안 업데이트를 제공 하 게 됩니다.

새 독일어 데이터 센터 지역의 Office 365 서비스:

- 경쟁력 있는 가격의 [Azure](https://azure.microsoft.com/pricing/calculator/),[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 고객 참여](https://dynamics.microsoft.com/pricing/) 및 [Power BI](https://powerbi.microsoft.com/pricing/)를 제공 합니다.
- 는 Microsoft&#39;s 전역 네트워크에 연결 되며 수백 개의 네트워크에 지 사이트, 피어 링 위치 및 송신 지점을 제공 하 여 세계 어디에서 든 견고한 사용자 환경을 제공 합니다.
- 독일 내 지역 고객 데이터 보관 요구사항을 충족하는데 도움을 줍니다. 
- 최신 버전의 서비스와 Office 365의 Microsoft 팀 및 다중 Geo를 비롯 하 여 새로운 기능을 갖춘 모든 기능의 글로벌 클라우드를 제공 합니다. [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) 및 [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability)의 지역별 상품을 비교하세요. 
- 고객의 준법 및 규정 요구 사항을 충족 할 수 있도록 모든 기능, 엔터프라이즈급 보안 및 종합 기능을 제공 합니다.
- 기존 온라인 서비스 계약을 통해 사용 가능합니다. 

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>여러 Office 365 클라우드 서비스 간에 사용할 수 있는 서비스는 무엇인가요?

Microsoft Cloud 독일 cloud 서비스 제공에서는 다음과 같은 15 가지 서비스를 사용할 수 있습니다. Microsoft 클라우드 독일에 새 서비스를 추가 하 고 있지 않습니다.

1. Exchange Online
2. 고객 Lockbox (Exchange Online)
3. 그룹 (모던 그룹)
4. Delve 프로필
5. Exchange Online Protection
6. ATP (Advanced Threat Protection)
7. Advanced eDiscovery
8. 고급 데이터 관리
9. SharePoint Online
10. 고객 Lockbox (SharePoint Online)
11. 비즈니스용 OneDrive
12. 비즈니스용 Skype Online
13. Word Online, Excel Online, PowerPoint, OneNote, Visio Online
14. Office 365 Pro Plus
15. Outlook Mobile

현재 새로운 독일 데이터 센터 영역에서 Office 365 서비스의 일부로 29개의 서비스를 사용할 수 있습니다. 계속해서 글로벌 Office 365 서비스와 일관된 새로운 기능과 서비스가 제공될 것입니다. 

1. Exchange Online
2. Exchange Online에 대 한 고객 Lockbox
3. Microsoft 365 그룹
4. Delve 프로필
5. MyAnalytics
6. Workplace Analytics
7. Exchange Online Protection
8. ATP (Advanced Threat Protection)
9. Advanced eDiscovery
10. 고급 보안 관리
11. 정보 권한 관리
12. 고급 데이터 관리
13. SharePoint Online
14. SharePoint Online에 대 한 고객 Lockbox
15. 비즈니스용 OneDrive
16. Microsoft Stream
17. 비즈니스용 Skype (마이그레이션 중에 Microsoft 팀으로 마이그레이션 예정)
18. 클라우드 PBX
19. PSTN 회의
20. PSTN 통화
21. Microsoft Teams
22. 관리 보고서/사용 현황 보고서
23. Word Online, Excel Online, PowerPoint, OneNote 및 Visio Online
24. Planner
25. Sway
26. Microsoft 365 앱
27. Outlook Mobile
28. EMS (Enterprise Mobility + Security) E3 (Azure AD Premium P1, Intune 및 권한 관리 서비스)
29. Yammer Online

### <a name="when-will-migration-happen"></a>언제 마이그레이션 되나요? 

**Azure**

Azure 고객만 있는 경우 오늘 Azure 리소스를 다른 지역으로 [마이그레이션하기](https://docs.microsoft.com/azure/germany/germany-migration-main) 시작할 수 있습니다. Azure에서 Office 365, Dynamics 365 또는 Power BI를 사용 하는 경우 다음 단계를 수행 하세요.

**Office 365**

지금 Microsoft 주도 마이그레이션에 [동의 합니다](https://aka.ms/office365germanymoveoptin).  마이그레이션을 시작할 준비가 되 면 Microsoft 365 관리 센터에서 메시지 센터를 통해 사용자에 게 알려줍니다.

**Dynamics 365 및 Power BI**

현재 [Dynamics 365 고객 계약](https://aka.ms/D365ceOptIn) 및 [Power BI](https://aka.ms/PBIOptIn) 에 대 한 Microsoft 기반 마이그레이션을 옵트인 합니다. 마이그레이션을 시작할 준비가 되면 Microsoft 365 관리 센터에서 메시지 센터를 통해 알려 드립니다. 

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>사용 하는 Office 365 서비스에 대 한 가격이 변경 됩니까?

예. Microsoft&#39;s 전역 클라우드 지역 (새 데이터 센터 영역 포함)의 가격은 일반적으로 낮습니다.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>구독 마이그레이션 중에는 조직 및 사용자에 게 어떤 Sku 및 라이선스가 적용 되나요?

Microsoft Cloud 독일 from Office 365 services로 마이그레이션하는 동안 독일 서비스 관련 Sku는 동일한 또는 유사한 SKU의 전역 버전으로 대체 됩니다. 대부분의 경우 Office 365 서비스의 SKU가 동일 하지만 독일의 SKU가 Office 365 서비스에서 더 이상 제공 되지 않는 몇 가지 대체가 있습니다. 마이그레이션이 완료 된 후 조직에 할당 된 SKU를 업데이트 하려면 판매자에 게 문의 하 여 할당 된 서비스를 추가 하거나 수정 합니다.

| Microsoft Cloud 독일-제품 SKU (DE) | Microsoft 클라우드 Global-WW (제품 SKU) |
| --- | --- |
| 고객 Lockbox \_ de-de (lockbox \_ ) | 고객 인증 키 저장소 (LOCKBOX) |
| Dynamics 365 Enterprise Edition-추가 데이터베이스 저장소 \_ DE (CRMSTORAGE \_ de) | Dynamics 365 Enterprise Edition-추가 데이터베이스 저장소 (CRMSTORAGE) |
| Dynamics 365 Enterprise Edition-추가 비프로덕션 인스턴스 \_ de (CRMTESTINSTANCE \_ de) | Dynamics 365 Enterprise Edition-추가 비프로덕션 인스턴스 (CRMTESTINSTANCE) |
| 고객 서비스 Enterprise Edition \_ de (DYN365 \_ enterprise \_ 고객 \_ 서비스 \_ de)에 대 한 Dynamics 365 | 고객 서비스 Enterprise Edition에 대 한 Dynamics 365 (DYN365 \_ enterprise \_ 고객 \_ 서비스) |
| 판매 Enterprise Edition \_ de (DYN365 \_ enterprise \_ Sales \_ de)에 대 한 Dynamics 365 | Sales Enterprise Edition에 대 한 Dynamics 365 ( \_ enterprise \_ SALES) DYN365 |
| Team Members Enterprise Edition \_ de (DYN365 \_ enterprise \_ Team \_ members \_ de)에 대 한 Dynamics 365 | Team Members Enterprise Edition에 대 한 Dynamics 365 ( \_ enterprise \_ 팀 구성원 DYN365 \_ ) |
| Dynamics 365 계획 1 Enterprise Edition \_ DE (DYN365 \_ enterprise \_ PLAN1 \_ de) | Dynamics 365 계획 1 Enterprise Edition (DYN365 \_ Enterprise \_ PLAN1) |
| ECAL 서비스 (EOA, EOP, DLP) \_ DE (ecal \_ services \_ de) | ECAL 서비스 (EOA, EOP, DLP) (ECAL \_ services) |
| Enterprise Mobility + Security E3 \_ de (EMS \_ de) | EMS (Enterprise Mobility + Security E3) |
| Exchange Online (계획 1) \_ DE (EXCHANGESTANDARD \_ de) | Exchange Online (계획 1) (EXCHANGESTANDARD) |
| Exchange Online (계획 2) \_ DE (EXCHANGEENTERPRISE \_ de) | Exchange Online (계획 2) (EXCHANGEENTERPRISE) |
| Exchange Online de에 대 한 exchange Online 아카이빙 \_ (EXCHANGEARCHIVE \_ ADDON \_ de) | Exchange Online에 대 한 exchange Online 보관 (EXCHANGEARCHIVE \_ ADDON) |
| Exchange Server \_ DE (EXCHANGEARCHIVE DE) 용 Exchange Online 보관 \_ | Exchange Server (EXCHANGEARCHIVE)에 대 한 exchange Online 보관 |
| Exchange Online Essentials \_ de (exchange \_ S \_ essentials \_ de) | Exchange Online Essentials (EXCHANGE \_ S \_ 필수) |
| \_EXCHANGEDESKLESS DE (Exchange Online Kiosk de \_ ) | EXCHANGEDESKLESS (Exchange Online Kiosk) |
| Exchange Online Protection \_ DE (EOP \_ 엔터프라이즈 \_ DE) | Exchange Online Protection (EOP \_ ENTERPRISE) |
| Microsoft 365 Business Standard (O365 \_ business \_ PREMIUM) | Microsoft 365 Business Standard (O365 \_ business \_ PREMIUM) |
| Microsoft Dynamics CRM Online 인스턴스 \_ DE (CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online 인스턴스 (CRMINSTANCE) |
| Office 365 A1 for 교직원 \_ de (STANDARDWOFFPACK \_ 교직원 \_ de) | 교직원 용 Office 365 A1 (STANDARDWOFFPACK \_ 교직원) |
| Office 365 A1 for 학생 \_ de (STANDARDWOFFPACK \_ STUDENT \_ de) | Office 365 A1 for 학생용 (STANDARDWOFFPACK \_ STUDENT) |
| Office 365 Advanced 준수 \_ de (EQUIVIO \_ ANALYTICS \_ de) | Microsoft 365 E5 준수 (정보 \_ 보호 \_ 규정 준수) |
| Office 365 Advanced Threat Protection (계획 1) \_ DE (ATP \_ ENTERPRISE \_ DE) | Office 365 Advanced Threat Protection (계획 1) (ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ de (O365 \_ business \_ essentials \_ de) | Microsoft 365 Business Basic (O365 \_ business \_ ESSENTIALS) |
| Office 365 Business Premium de \_ (O365 \_ business \_ premium \_ de) | Microsoft 365 Business Standard (O365 \_ business \_ PREMIUM) |
| Office 365 Business \_ de (O365 \_ business \_ de) | Microsoft 365 비즈니스용 앱 (O365 \_ 비즈니스) |
| Office 365 E1 \_ DE (STANDARDPACK \_ DE) | Office 365 E1 (STANDARDPACK) |
| ProPlus \_ de (ENTERPRISEPACKWITHOUTPROPLUS de)가 없는 Office 365 E3 \_ | ProPlus가 없는 Office 365 E3 (ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE (ENTERPRISEPACK \_ de) | Office 365 E3 (ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE (STANDARDPACK \_ de) | Office 365 Enterprise E1 (STANDARDPACK) |
| Office 365 Enterprise E3 \_ de (ENTERPRISEPACK \_ de) | Office 365 Enterprise E3 (ENTERPRISEPACK) |
| Office 365 추가 파일 저장 \_ de (SHAREPOINTSTORAGE \_ de) | Office 365 추가 파일 저장소 (SHAREPOINTSTORAGE) |
| Office 365 F1 \_ de (DESKLESSPACK \_ DE) | Office 365 F1 키 (DESKLESSPACK) |
| Office 365 ProPlus for 교직원 \_ (OFFICESUBSCRIPTION \_ 강사용 \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION \_ 강사용) |
| Office 365 ProPlus for 학생 \_ de (OFFICESUBSCRIPTION \_ 학생 \_ de) | Office 365 ProPlus for 학생용 (OFFICESUBSCRIPTION \_ 학생) |
| Office 365 ProPlus \_ de (OFFICESUBSCRIPTION \_ de) | Office 365 ProPlus (OFFICESUBSCRIPTION) |
| 비즈니스용 OneDrive (계획 1) \_ DE (WACONEDRIVESTANDARD \_ DE) | 비즈니스용 OneDrive (계획 1) (WACONEDRIVESTANDARD) |
| 비즈니스용 OneDrive (계획 2) \_ DE (WACONEDRIVEENTERPRISE \_ DE) | 비즈니스용 OneDrive (계획 2) (WACONEDRIVEENTERPRISE) |
| Power BI Pro for 교직원 \_ de (power \_ bi \_ pro \_ 교직원 \_ de-de) | Power BI Pro for 교직원 (POWER \_ bi \_ pro \_ 교직원) |
| Power BI Pro \_ de (power \_ bi \_ pro \_ de) | Power BI Pro (POWER \_ bi \_ pro) |
| Project Online Essentials \_ de (PROJECTESSENTIALS \_ de) | Project Online Essentials (PROJECTESSENTIALS) |
| Project Online Premium \_ de (PROJECTPREMIUM \_ de) | Project Online Premium (PROJECTPREMIUM) |
| Project Online Professional \_ de (PROJECTPROFESSIONAL \_ de) | Project Online Professional (PROJECTPROFESSIONAL) |
| 프로젝트 계획 3 \_ de-de (PROJECTPROFESSIONAL \_ de) | 프로젝트 계획 3 (PROJECTPROFESSIONAL) |
| Office 365 E4 \_ de (ENTERPRISEWITHSCAL \_ DE) | Office 365 E3 (ENTERPRISEPACK) |
| SharePoint Online (계획 1) \_ DE (SHAREPOINTSTANDARD \_ de) | SharePoint Online (계획 1) (SHAREPOINTSTANDARD) |
| SharePoint Online (계획 2) \_ DE (SHAREPOINTENTERPRISE \_ de) | SharePoint Online (계획 2) (SHAREPOINTENTERPRISE) |
| 비즈니스용 Skype Online (요금제 1) \_ DE (MCOIMP \_ de) | Office 365 E1 (STANDARDPACK) |
| 비즈니스용 Skype Online (요금제 1) \_ DE (MCOIMP \_ de) | 비즈니스용 Skype Online (요금제 1) (MCOIMP) |
| 비즈니스용 Skype Online (요금제 2) \_ DE (MCOSTANDARD \_ DE) | 비즈니스용 Skype Online (요금제 2) (MCOSTANDARD) |
| 비즈니스용 Skype Plus CAL \_ de (MCOPLUSCAL \_ de) | 비즈니스용 Skype 플러스 CAL (MCOPLUSCAL) |
| 교직원 용 Visio Online 계획 1 \_ (VISIOONLINE \_ PLAN1 \_ fac \_ DE) | 교직원 용 Visio Online 계획 1 (VISIOONLINE \_ PLAN1 \_ fac) |
| Visio Online 계획 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio Online 계획 1 (VISIOONLINE \_ PLAN1) |
| 교직원 용 Visio Online 계획 2 \_ (VISIOCLIENT \_ 강사용 \_ de) | 교직원 용 Visio Online 계획 2 (VISIOCLIENT \_ 강사용) |
| Visio Online 계획 2 \_ de (VISIOCLIENT \_ de) | Visio Online 계획 2 (VISIOCLIENT) |
| Visio 계획 1 \_ DE (VISIOONLINE \_ PLAN1 \_ DE) | Visio 계획 1 (VISIOONLINE \_ PLAN1) |
| Visio 요금제 2 \_ de (VISIOCLIENT \_ de) | Visio 계획 2 (VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>신규 지역으로 마이그레이션 할 때 도움이 필요하거나 문의 사항이 있으면 어떻게 해야 하나요? 

궁금한 점이 있으면 문의처 또는 파트너에 게 문의할 수 있습니다.

- Azure의 경우 Azure 포털에서 [새 지원 요청을](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) 제출하세요. 
- Office 365의 경우 &quot; &quot; [Microsoft 365 관리 센터](https://portal.office.de/)의 링크를 사용 하 여 질문을 제출할 수 있습니다.
- Dynamics 365 고객 계약 및 Power BI 고객 뿐 아니라 Office 365도 사용 하는 경우 &quot; &quot; [Microsoft 365 관리 센터](https://portal.office.de/)의 링크 필요 여부에 따라 질문을 제출할 수 있습니다. Dynamics 365 고객 참여 지원은 [여기](https://docs.microsoft.com/dynamics365/get-started/support/)를 이용하세요.  Power BI 지원은 [여기](https://powerbi.microsoft.com/support/)를 이용하세요. 

## <a name="more-information"></a>추가 정보

새 독일어 데이터 센터 지역으로 마이그레이션하는 방법에 대 한 자세한 정보가 제공 됩니다. 체크 인하고 현재 상태로 유지할 수 있도록이 페이지에 책갈피를 선택 합니다.

- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](https://aka.ms/office365germanymoveoptin)
- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Office 365 URL 및 IP 주소 범위](https://aka.ms/o365endpoints)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
