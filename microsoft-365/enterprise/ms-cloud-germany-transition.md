---
title: 독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
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
ms.openlocfilehash: d807637e9d5469131d3124d1ef8b6b1f874e81a1
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145418"
---
# <a name="migration-from-microsoft-cloud-deutschland-to-office-365-services-in-the-new-german-datacenter-regions"></a>독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션

> [!NOTE]
> 이 문서는 적격 Microsoft 클라우드 도이클랜드 고객에게만 적용됩니다.

2018년 8월, Microsoft는 고객의 디지털 변환을 보다 잘 지원하기 위해 독일의 새 클라우드 지역에서 완전한 Microsoft 클라우드인 Azure, Office 365, Dynamics 365 및 Power Platform을 제공하겠다는 의도를 발표했습니다. 2019년 8월, 독일의 신규 클라우드 지역 출범을 발표합니다.   이후로 Azure, Office 365, Dynamics 365 및 Power Platform의 가용성을 발표했습니다.

새로운 지역은 더 유연한 최신 지능형 클라우드 서비스, Microsoft 365 서비스 클라우드 네트워크에 대한 완전한 연결 및 독일 내 고객 데이터 지역에 대한 독일 고객의 진화된 요구를 해결하도록 디자인되었습니다.

## <a name="how-to-migrate-to-the-new-german-datacenter-regions"></a>새 독일 데이터 센터 지역으로 마이그레이션하는 방법

이제 도이치란드 기존 Microsoft 클라우드 고객은 Office 365, Dynamics 365 Customer Engagement 및 Power Platform 고객 마이그레이션을 시작할 수 있습니다. 첫 번째 단계는 Microsoft 주도 신규 독일 데이터 센터 지역으로의 [마이그레이션에 동의](https://aka.ms/office365germanymoveoptin)하는 것입니다. 

Microsoft 주도 방식에 옵트인(opt in)한 조직의 경우 마이그레이션은 2021년 초에 시작될 예정이고 2021년 10월 29일까지 완료됩니다. 마이그레이션이 되면 핵심 고객 데이터 및 구독정보는 신규 독일 지역으로 이전됩니다. 

이 문서에서는 마이그레이션을 위한 Microsoft 주도 접근 방식의 개요, 마이그레이션 중 및 이후에 사용자와 관리자를 위한 환경의 명확성, 활용하는 워크로드를 기반으로 고객에게 요구될 수 있는 작업을 제공합니다.

Microsoft 주도 방식에 동의하면 다음 서비스도 함께 마이그레이션됩니다.

- Azure AD(Azure Active Directory)
- Exchange Online
- Exchange Online Protection
- SharePoint Online
- 비즈니스용 OneDrive

- 비즈니스용 Skype Online\*\*
- Office 365 그룹
- Dynamics 365 /Power Platform\*\*\*

\*\*독일 Microsoft 클라우드에서 독일 데이터 센터 지역으로 마이그레이션하는 동안 기존 비즈니스용 Skype Online 고객은 Microsoft Teams로 전환됩니다. 자세한 내용은 [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)를 참조하세요.

\*\*\*이러한 서비스에 대한 마이그레이션의 선행 요구 및 영향은 [Dynamics 365 고객 참여 문서에 설명되어](https://aka.ms/d365ceoptin) 있습니다.

Office 365 비디오가 2021년 3월 1일에 사용 중지됩니다. Office 365 테넌트를 새 독일어 데이터 센터 영역으로 마이그레이션하도록 선택하면 SharePoint Online 마이그레이션이 완료된 후에 Office 365 비디오가 지원되지 않습니다. 자세한 내용은 도이치란드 [Microsoft 클라우드 타임라인을 참조하세요.](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)

## <a name="how-is-the-migration-organized"></a>마이그레이션은 어떻게 구성하나요?

이 그림에서는 새로운 독일 데이터 센터로의 9단계 마이그레이션 단계를 보여 주었다.

![새 독일 데이터 센터로의 9단계 마이그레이션](../media/ms-cloud-germany-migration-opt-in/migration-organization.png)

마이그레이션을 옵트인(opt [in)할 때 이러한 단계가 시작됩니다.](https://aka.ms/office365germanymoveoptin) 대부분의 마이그레이션 단계는 최소한의 고객 상호 작용이 필요하며 백 엔드 서비스 작업으로 실행되고 한 단계 후에 실행됩니다. 추가 고객 주도 작업 및 전체 마이그레이션 상태의 시작은 마이그레이션 프로세스 중에 Microsoft 365 관리 센터의 메시지 센터를 통해 전달됩니다. 작업의 예로는 고객 관리 DNS 업데이트, Exchange 하이브리드 고객을 위한 하이브리드 설정 재구성 또는 Azure 마이그레이션이 있습니다.

옵트인이 발생하면 마이그레이션이 즉시 시작되지는 않습니다. 조직이 나중에 마이그레이션할 예정인 테넌트 목록에 추가됩니다. 완료 시 성공적인 마이그레이션 및 사용을 보장하기 위해 이러한 단계가 중요하기 때문에 작업 전 단계를 시작할 수 있습니다.

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)

테넌트 마이그레이션이 시작된 지 1주 전에 메시지 센터 서비스에서 모든 선행 작업을 완료해야 하다는 최종 경고가 표시됩니다.

마이그레이션은 Azure AD 테넌트가 주권 독일 Azure AD 서비스에서 EU 지역의 Azure AD의 Office 365 서비스 인스턴스로 이동됩니다.

다음 단계는 독일 특정 제품에서&#39;구독 및 사용자 라이선스에 대한 테넌트 마이그레이션입니다.

고객 Azure 마이그레이션을 비롯한 모든 단계가 완료되면 테넌트가 Office 365 서비스 서비스에서 완료된 후 마이그레이션이 완료된 것으로 표시됩니다. 이제 메시지 센터에 대한 최종 업데이트가 제공됩니다. 테넌트는 이제 완전 전역 Office 365 조직입니다.

메시지 센터 게시물을 통해 마이그레이션 진행률에 대한 알림을 수신합니다. 게시물은 특정 중요 시점에 진행될 것이고 단계 진행에 대한 지침과 고객이 프로세스 요구 사항에 따라 행동해야 하는 중요한 정보를 제공합니다. 메시지 센터 알림은 다음 중요 시점에 제공됩니다.

- 마이그레이션 시작(Azure AD 마이그레이션 시작 영업일 5일 전)
- Azure AD 마이그레이션 완료
- 구독 및 라이선스 마이그레이션 완료
- SharePoint 마이그레이션 완료
- Exchange 마이그레이션 완료
- 비즈니스용 Skype 완료
- Dynamics 완료
- Power BI 완료
- 최종 서비스 컷오버 완료

## <a name="moving-to-the-new-german-datacenter-regions"></a>새 독일 데이터 센터 지역으로 이동

이제 도이치란드 기존 Microsoft 클라우드 고객은 Office 365, Dynamics 365 Customer Engagement 및 Power Platform 서비스 마이그레이션을 시작할 수 있습니다. 첫 번째 단계는 Microsoft 주도 신규 독일 데이터 센터 지역으로의 [마이그레이션에 동의](https://aka.ms/office365germanymoveoptin)하는 것입니다.  구독을 갱신하면 Microsoft 지원 마이그레이션에 자동으로 옵트인(opt in)합니다. 이 경우 Microsoft는 고객 테넌트 관리자에게 전자 메일과 Microsoft 365 관리 센터의 메시지 센터에 이를 알릴 것입니다. 그러나 지금 프로세스를 시작하려면 지금 Microsoft 365 관리 센터에서 직접 옵트인(opt [in)할](https://aka.ms/office365germanymoveoptin) 수 있습니다. 마이그레이션은 2021년 초에 시작될 예정이고 2021년 10월 29일까지 완료됩니다. 

마이그레이션의 결과로 핵심 고객 데이터 및 구독이 새로운 독일 데이터 센터 지역으로 이동됩니다.

## <a name="how-to-prepare-for-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Office 365 서비스 신규 독일 데이터 센터 지역으로의 마이그레이션을 준비하는 방법 

첫 번째 단계는 독일의 신규 독일 데이터 센터 지역의 Office 365 서비스로 구독 및 데이터를 마이그레이션할 수 있는 권한이 있도록 Microsoft에 알리는 것입니다. 지침은 [옵트인](https://aka.ms/office365germanymoveoptin) 프로세스를 참조하고 다음에 유의하세요.

- 모든 마이그레이션 고객은 Office 365 Services Office [365 URL](urls-and-ip-address-ranges.md)및 IP 주소(새 독일 데이터 센터 지역 포함)에 대한 연결을 확인해야 합니다. 비활성으로 인해 서비스 및 클라이언트 오류가 발생될 수 있습니다.
- 조직이 변경에 [대해](ms-cloud-germany-transition-add-pre-work.md) 알리고 준비되도록 작업 전 활동 목록을 검토합니다.
- 독일 지역으로 마이그레이션한 후 조직에서 사용할 수 있는 기능 및 서비스를 이해하기 위해 Office 365 플랫폼 서비스 설명을 검토해야 합니다.
- 평가판 구독은 마이그레이션되지 않습니다. 모든 유료 구독의 마이그레이션이 차단됩니다. 마이그레이션을 시작하기 전에 평가판을 취소하거나 유료 구독으로 전환해야 합니다.

## <a name="where-do-i-go-from-here"></a>여기에서 어디로 이동하나요?

다음 질문과 대답 섹션을 검토합니다.

## <a name="frequently-asked-questions"></a>FAQ

### <a name="is-migration-required"></a>마이그레이션이 필수인가요? 

Microsoft는 독일 Microsoft 클라우드에서 Office 365 서비스로의 Office 365 테넌트 마이그레이션을 새로운 독일 데이터 센터 지역의 Office 365 서비스로 추가 비용부분으로 제공합니다. 독일 신규 데이터 센터 지역으로의 마이그레이션을 옵트인(opt in)하는 것이 많지만 독일 Microsoft 클라우드 지역에 필요한 보안 업데이트를 계속 제공합니다.

새 독일 데이터 센터 지역의 Office 365 서비스:

- 경쟁력 있는 가격의 [Azure](https://azure.microsoft.com/pricing/calculator/),[Office 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans), [Dynamics 365 고객 참여](https://dynamics.microsoft.com/pricing/) 및 [Power BI](https://powerbi.microsoft.com/pricing/)를 제공 합니다.
- Microsoft&#39;전역 네트워크에 연결하여 전 세계 어디서나 강력한 사용자 환경을 제공하기 위해 수백 개의 네트워크 에지 사이트, 피어링 위치 및 연결 지점을 제공합니다.
- 독일 내 지역 고객 데이터 보관 요구사항을 충족하는데 도움을 줍니다. 
- Microsoft Teams 및 Office 365의 Multi-Geo를 비롯한 최신 버전의 서비스와 새로운 기능을 통해 모든 기능을 제공하는 글로벌 클라우드 서비스를 제공합니다. [Azure](https://azure.microsoft.com/global-infrastructure/services/?products=all&amp;regions=germany-non-regional,germany-central,germany-north,germany-northeast,germany-west-central), [Office 365](o365-data-locations.md) 및 [Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/availability)의 지역별 상품을 비교하세요. 
- 고객의 준법 및 규정 요구 사항을 충족 할 수 있도록 모든 기능, 엔터프라이즈급 보안 및 종합 기능을 제공 합니다.
- 기존 온라인 서비스 계약을 통해 사용 가능합니다. 

### <a name="what-is-the-service-availability-between-the-different-office-365-cloud-service-offerings"></a>여러 Office 365 클라우드 서비스 간에 사용할 수 있는 서비스는 무엇인가요?
<h2 id="serv-avail"></h2>

다음 15개 서비스는 도이치란드 Microsoft 클라우드 서비스에서 사용할 수 있습니다. 도이치란드 Microsoft 클라우드에 새 서비스를 추가하고 있지 않습니다.

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

현재 새 독일 데이터 센터 지역에서 Office 365 서비스의 일부로 39개 서비스를 사용할 수 있습니다. 계속해서 글로벌 Office 365 서비스와 일관된 새로운 기능과 서비스가 제공될 것입니다. 

1. Exchange Online
2. Exchange Online용 고객 Lockbox
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
14. SharePoint Online용 고객 Lockbox
15. 비즈니스용 OneDrive
16. Microsoft Stream
17. 비즈니스용 Skype(마이그레이션 중에 Microsoft Teams로 마이그레이션)
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
28. EMS(Enterprise Mobility + Security) E3(Azure AD Premium P1, Intune 및 Rights Management Service)
29. Yammer Enterprise
30. Microsoft Forms
31. Office 365용 Power Automate
32. Office 365용 Power Virtual Agents
33. Office 365용 PowerApps
34. Microsoft Bookings
35. To-Do
36. Whiteboard
37. Microsoft StuffHub
38. Microsoft Kaizala Pro
39. 목록

### <a name="when-will-migration-happen"></a>언제 마이그레이션 되나요? 

**Azure**

Azure 고객만 있는 경우 현재 [](https://docs.microsoft.com/azure/germany/germany-migration-main) Azure 리소스를 다른 지역으로 마이그레이션할 수 있습니다. 

Office 365, Dynamics 365 또는 Power BI가 있는 Azure가 있는 경우 자체 지시 Azure 마이그레이션을 시작하기 전에 마이그레이션 프로세스를 따라 AzureAD를 성공적으로 마이그레이션해야 합니다. AzureAD 및 Office 365 조직과 함께 Azure 워크로드를 유지 관리하려면 서비스가 완료되기 전에 Azure 마이그레이션을 완료해야 합니다.

**Office 365**

지금 Microsoft 주도 마이그레이션에 [동의 합니다](https://aka.ms/office365germanymoveoptin).  마이그레이션을 시작할 준비가 되면 Microsoft 365 관리 센터의 메시지 센터를 통해 알려드릴 것입니다.

**Dynamics 365 및 Power BI**

[현재 Dynamics 365 Customer Engagement](https://aka.ms/D365ceOptIn) 및 Power BI에 대한 Microsoft 주도 마이그레이션에 옵트인(opt in)합니다. [](https://aka.ms/PBIOptIn) 마이그레이션을 시작할 준비가 되면 Microsoft 365 관리 센터에서 메시지 센터를 통해 알려 드립니다. 

### <a name="will-the-price-change-for-the-office-365-services-that-i-use"></a>사용하는 Office 365 서비스의 가격이 변경하나요?

예. Microsoft&#39;전역 클라우드 지역(새 데이터 센터 지역 포함)의 가격은 일반적으로 낮습니다.

### <a name="during-the-subscription-migration-what-skus-and-licenses-will-be-applied-to-my-organization-and-users"></a>구독 마이그레이션 중에 조직 및 사용자에게 어떤 SKUS 및 라이선스가 적용될까요?

독일 Microsoft 클라우드에서 Office 365 서비스로 마이그레이션하는 동안 독일 서비스 관련 SKU는 동일하거나 유사한 SKU의 전역 버전으로 대체됩니다. 대부분의 경우 Office 365 서비스의 SKU는 동일합니다. 그러나 독일의 SKU가 Office 365 서비스에서 더 이상 사용할 수 없는 대체는 거의 없습니다. 마이그레이션이 완료된 후 조직에 할당된 SKU를 업데이트하려면 판매자에 문의하여 할당된 서비스를 추가하거나 수정합니다.

| 도이치클란드 Microsoft 클라우드 - 제품 SKU(DE) | Microsoft 클라우드 전역 - WW(제품 SKU) |
| --- | --- |
| 고객 Lockbox \_ DE(LOCKBOX \_ DE) | 고객 Lockbox(LOCKBOX) |
| Dynamics 365 Enterprise Edition - 추가 데이터베이스 저장소 \_ DE(CRMSTORAGE \_ DE) | Dynamics 365 Enterprise Edition - 추가 데이터베이스 저장소(CRMSTORAGE) |
| Dynamics 365 Enterprise Edition - 추가 비 프로덕션 인스턴스 \_ DE(CRMRMRMSTANCE \_ DE) | Dynamics 365 Enterprise Edition - 추가 비 프로덕션 인스턴스(CRMRMSTANCE) |
| Dynamics 365 for Customer Service Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE CUSTOMER SERVICE \_ \_ \_ DE) | Dynamics 365 for Customer Service Enterprise Edition(DYN365 \_ ENTERPRISE \_ 고객 \_ 서비스) |
| Dynamics 365 for Sales Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE \_ SALES \_ DE) | Dynamics 365 for Sales Enterprise Edition(DYN365 \_ ENTERPRISE \_ SALES) |
| Dynamics 365 for Team Members Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE TEAM MEMBERS \_ \_ \_ DE) | Dynamics 365 for Team Members Enterprise Edition(DYN365 \_ ENTERPRISE \_ TEAM \_ MEMBERS) |
| Dynamics 365 Plan 1 Enterprise Edition \_ DE(DYN365 \_ ENTERPRISE \_ PLAN1 \_ DE) | Dynamics 365 Plan 1 Enterprise Edition(DYN365 \_ ENTERPRISE \_ PLAN1) |
| ECAL Services(EOA, EOP, DLP) \_ DE(ECAL \_ SERVICES \_ DE) | ECAL 서비스(EOA, EOP, DLP)(ECAL \_ 서비스) |
| Enterprise Mobility + Security E3 \_ DE(EMS \_ DE) | Enterprise Mobility + EMS(Security E3) |
| Exchange Online(계획 1) \_ DE(EXCHANGESTANDARD \_ DE) | Exchange Online(계획 1)(EXCHANGESTANDARD) |
| Exchange Online(계획 2) \_ DE(EXCHANGEENTERPRISE \_ DE) | Exchange Online(계획 2)(EXCHANGEENTERPRISE) |
| Exchange Online Archiving For Exchange Online \_ DE(EXCHANGEARCHIVE \_ ADDON \_ DE) | Exchange Online Archiving For Exchange Online(EXCHANGEARCHIVE \_ ADDON) |
| Exchange Online Archiving 대한 \_ Exchange Server(EXCHANGEARCHIVE \_ DE) | Exchange Online Archiving 대한 Exchange Server(EXCHANGEARCHIVE) |
| Exchange Online Essentials \_ DE(EXCHANGE \_ S \_ ESSENTIALS \_ DE) | Exchange Online Essentials(EXCHANGE \_ S \_ ESSENTIALS) |
| Exchange Online Kiosk \_ DE(EXCHANGEDESKLESS \_ DE) | Exchange Online Kiosk(EXCHANGEDESKLESS) |
| EOP ENTERPRISE DE(Exchange Online Protection \_ \_ \_ DE) | EOP ENTERPRISE(Exchange Online \_ Protection) |
| Microsoft 365 Business Standard(O365 \_ BUSINESS \_ PREMIUM) | Microsoft 365 Business Standard(O365 \_ BUSINESS \_ PREMIUM) |
| Microsoft Dynamics CRM Online \_ 인스턴스 DE(CRMINSTANCE \_ DE) | Microsoft Dynamics CRM Online 인스턴스(CRMINSTANCE) |
| 교직원용 Office 365 \_ A1(STANDARDWOFFPACK \_ FACULTY \_ DE) | 교직원용 Office 365 A1(STANDARDWOFFPACK \_ FACULTY) |
| 학생용 Office 365 \_ A1(STANDARDWOFFPACK \_ STUDENT \_ DE) | 학생용 Office 365 A1(STANDARDWOFFPACK \_ 학생) |
| Office 365 Advanced Compliance \_ DE(EQUIVIO \_ ANALYTICS \_ DE) | Microsoft 365 E5 규정 준수(INFORMATION \_ PROTECTION \_ COMPLIANCE) |
|Microsoft Defender for Office 365(계획 1) \_ DE(ATP \_ ENTERPRISE \_ DE) |Microsoft Defender for Office 365(계획 1)(ATP \_ ENTERPRISE) |
| Office 365 Business Essentials \_ DE(O365 \_ BUSINESS \_ ESSENTIALS \_ DE) | Microsoft 365 Business Basic(O365 \_ BUSINESS \_ ESSENTIALS) |
| Office 365 Business Premium \_ DE(O365 \_ BUSINESS \_ PREMIUM \_ DE) | Microsoft 365 Business Standard(O365 \_ BUSINESS \_ PREMIUM) |
| Office 365 Business \_ DE(O365 \_ BUSINESS \_ DE) | 비즈니스용 Microsoft 365 앱(O365 \_ BUSINESS) |
| Office 365 E1 \_ DE(STANDARDPACK \_ DE) | Office 365 E1(STANDARDPACK) |
| ProPlus DE가 없는 Office 365 \_ E3(ENTERPRISEPACKWITHOUTPROPLUS \_ DE) | ProPlus가 없는 Office 365 E3(ENTERPRISEPACKWITHOUTPROPLUS) |
| Office 365 E3 \_ DE(ENTERPRISEPACK \_ DE) | Office 365 E3(ENTERPRISEPACK) |
| Office 365 Enterprise E1 \_ DE(STANDARDPACK \_ DE) | Office 365 Enterprise E1(STANDARDPACK) |
| Office 365 Enterprise E3 \_ DE(ENTERPRISEPACK \_ DE) | Office 365 Enterprise E3(ENTERPRISEPACK) |
| Office 365 추가 파일 저장소 \_ DE(SHAREPOINTSTORAGE \_ DE) | Office 365 추가 파일 저장소(SHAREPOINTSTORAGE) |
| Office 365 F1 \_ DE(DESKLESSPACK \_ DE) | Office 365 F1(DESKLESSPACK) |
| 교직원용 Office 365 ProPlus \_ DE(OFFICESUBSCRIPTION \_ FACULTY \_ DE) | 교직원용 Office 365 ProPlus(OFFICESUBSCRIPTION \_ 교직원) |
| 학생용 Office 365 ProPlus \_ DE(OFFICESUBSCRIPTION \_ STUDENT \_ DE) | 학생용 Office 365 ProPlus(OFFICESUBSCRIPTION \_ STUDENT) |
| Office 365 ProPlus \_ DE(OFFICESUBSCRIPTION \_ DE) | Office 365 ProPlus(OFFICESUBSCRIPTION) |
| 비즈니스용 OneDrive(계획 1) \_ DE(WACONEDRIVESTANDARD \_ DE) | 비즈니스용 OneDrive(계획 1)(WACONEDRIVESTANDARD) |
| 비즈니스용 OneDrive(계획 2) \_ DE(WACONEDRIVEENTERPRISE \_ DE) | 비즈니스용 OneDrive(계획 2)(WACONEDRIVEENTERPRISE) |
| 교직원용 Power BI Pro \_ DE(POWER \_ BI \_ PRO \_ FACULTY \_ DE) | 교직원용 Power BI Pro(POWER \_ BI \_ PRO \_ FACULTY) |
| Power BI Pro \_ DE(POWER \_ BI \_ PRO \_ DE) | Power BI Pro(POWER \_ BI \_ PRO) |
| Project Online Essentials \_ DE(PROJECTESSENTIALS \_ DE) | Project Online Essentials(PROJECTESSENTIALS) |
| Project Online Premium \_ DE(PROJECTPREMIUM \_ DE) | Project Online Premium(PROJECTPREMIUM) |
| Project Online Professional \_ DE(PROJECTPROFESSIONAL \_ DE) | Project Online Professional(PROJECTPROFESSIONAL) |
| Project Plan 3 \_ DE(PROJECTPROFESSIONAL \_ DE) | Project Plan 3(PROJECTPROFESSIONAL) |
| Office 365 E4 \_ DE(ENTERPRISEWITHSCAL \_ DE) | Office 365 E3(ENTERPRISEPACK) |
| SharePoint Online(계획 1) \_ DE(SHAREPOINTSTANDARD \_ DE) | SharePoint Online(계획 1)(SHAREPOINTSTANDARD) |
| SharePoint Online(계획 2) \_ DE(SHAREPOINTENTERPRISE \_ DE) | SharePoint Online(계획 2)(SHAREPOINTENTERPRISE) |
| 비즈니스용 Skype Online(계획 1) \_ DE(MCOIMP \_ DE) | Office 365 E1(STANDARDPACK) |
| 비즈니스용 Skype Online(계획 1) \_ DE(MCOIMP \_ DE) | 비즈니스용 Skype Online(계획 1)(MCOIMP) |
| 비즈니스용 Skype Online(계획 2) \_ DE(MCOSTANDARD \_ DE) | 비즈니스용 Skype Online(계획 2)(MCOSTANDARD) |
| 비즈니스용 Skype Plus CAL \_ DE(MCOPLUSCAL \_ DE) | 비즈니스용 Skype Plus CAL(MCOPLUSCAL) |
| Visio Online Plan 1 for faculty \_ DE (VISIOONLINE \_ PLAN1 \_ FAC \_ DE) | 교직원용 Visio Online 계획 1(VISIOONLINE \_ PLAN1 \_ FAC) |
| Visio Online Plan 1 \_ DE(VISIOONLINE \_ PLAN1 \_ DE) | Visio Online 계획 1(VISIOONLINE \_ PLAN1) |
| Visio Online Plan 2 for faculty \_ DE(VISIOCLIENT \_ FACULTY \_ DE) | 교직원용 Visio Online 계획 2(VISIOCLIENT \_ FACULTY) |
| Visio Online Plan 2 \_ DE(VISIOCLIENT \_ DE) | Visio Online 계획 2(VISIOCLIENT) |
| Visio Plan 1 \_ DE(VISIOONLINE \_ PLAN1 \_ DE) | Visio Plan 1(VISIOONLINE \_ PLAN1) |
| Visio Plan 2 \_ DE(VISIOCLIENT \_ DE) | Visio Plan 2(VISIOCLIENT) |
|||

### <a name="how-do-i-get-help-from-microsoft-to-migrate-to-a-new-region-or-answer-support-questions"></a>신규 지역으로 마이그레이션 할 때 도움이 필요하거나 문의 사항이 있으면 어떻게 해야 하나요? 

질문이 있는 경우 문의처 또는 파트너에게 문의할 수 있습니다.

- Azure의 경우 Azure 포털에서 [새 지원 요청을](https://portal.microsoftazure.de/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest) 제출하세요. 
- Office 365의 경우 Microsoft 365 관리 센터의 도움이 &quot; 필요하세요? 링크를 사용하여 질문을 &quot; [제출할 수 있습니다.](https://portal.office.de/)
- Dynamics 365 고객 참여 및 Power BI 고객이고 Office 365도 있는 경우 &quot; Microsoft 365 관리 센터의 도움이 필요하세요? 링크를 사용하여 질문을 &quot; [제출할 수 있습니다.](https://portal.office.de/) Dynamics 365 고객 참여 지원은 [여기](https://docs.microsoft.com/dynamics365/get-started/support/)를 이용하세요.  Power BI 지원은 [여기](https://powerbi.microsoft.com/support/)를 이용하세요. 

### <a name="my-customer-already-has-a-m365-tenant-in-the-global-microsoft-cloud-in-addition-to-a-microsoft-cloud-deutschland-tenant-can-these-two-tenants-be-merged-into-one-as-part-of-the-migration"></a>고객에게는 도이클란드 Microsoft 클라우드 외에도 글로벌 Microsoft 클라우드에 M365 테넌트가 이미 있습니다. 마이그레이션의 일부로 이러한 두 테넌트가 하나의 테넌트에 병합될 수 있나요?

아니요. 테넌트 병합 기능이 없는 경우 모든 테넌트에 고유한 네임스페이스와 고유 ID가 있는 경우 테넌트는 별개의 고유한 상태로 유지됩니다. Microsoft는 원하는 경우 도이치란드 Microsoft 클라우드 테넌트가 글로벌 클라우드로 마이그레이션되거나 고객이 이를 취소하고 취소할 수 있습니다.


### <a name="what-actions-are-required-to-be-done-by-most-end-users-as-part-of-the-migration"></a>마이그레이션의 일부로 대부분의 최종 사용자가 수행해야 하는 작업은 무엇입니까?
마이그레이션은 최종 사용자/고객에게 최소한의 영향을 미치기 위해 고안된 것입니다.
- Office 응용 프로그램에서 사용 가능한 최신 버전을 실행 중인지 확인 
- 비즈니스용 Skype를 사용하는 고객은 마이그레이션의 일부로 Teams로 전환하며 디바이스에 [Teams를](https://docs.microsoft.com/deployoffice/teams-install) 다운로드하여 설치해야 할 수 있습니다.
- 최종 사용자는 마이그레이션이 완료되면 Office 응용 프로그램에서 로그아웃하고 다시 로그인해야 할 수 있습니다. 
- OneDrive 동기화 클라이언트를 실행하는 고객은 OneDrive 동기화 클라이언트가 전역 Azure Active Directory 서비스에 로그인할 수 있도록 해당 작업에서 로그아웃했다가 다시 로그인해야 합니다.
- 마이그레이션이 완료되면 새 전역 URL, 특히 Outlook Web Access(예: 웹 액세스 사용)에 outlook.office365.com. SharePoint Online 클라이언트는 기존 URL(예: contoso.sharepoint.de)을 사용하여 MCD 네임스페이스에 계속 연결합니다.


### <a name="which-customers-are-affected-by-the-azure-active-directory-migration"></a>Azure Active Directory 마이그레이션의 영향을 받는 고객은 무엇입니까? 

Office365의 모든 고객은 Azure Active Directory를 사용하여 Microsoft 호스팅 서비스 운영에 필요한 중요한 서비스 구성 요소를 인증하고 저장합니다. 


### <a name="what-are-the-impacts-of-the-azure-active-directory-migration"></a>Azure Active Directory 마이그레이션의 영향은 무엇입니까?

초기 단계에서 Azure Active Directory의 초기 마이그레이션은 고객 환경에 영향을 끼치지 않습니다. 최종 마이그레이션 단계 후 고객 테넌트에 대한 모든 서비스가 전역 서비스에 완전히 있습니다. 이 마지막 단계가 지난 후 도이치랜드 Microsoft 클라우드의 Azure Active Directory 서비스는 더 이상 권한 부여 요청을 수락하거나 Office 서비스에 액세스 토큰을 제공할 수 없습니다.


### <a name="what-does-it-mean-to-ensure-network-connectivity-to-office-365-services-urls-and-ip-addresses"></a>[Office 365](https://aka.ms/o365urls)서비스 URL 및 IP 주소에 대한 네트워크 연결을 보장하는 것은 무엇을 의미하나요?

이 문서에서는 올바른 고객 환경을 보장하기 위해 전역 서비스의 적절한 기능에 필요한 URL 및 IP 주소에 대해 설명합니다. 비교적 드문 경우지만 일부 고객은 트래픽 흐름을 최소화하고 도이치랜드 Microsoft 클라우드 서비스 IP 범위의 일부로만 서비스에 대한 액세스를 제한하는 방식으로 네트워크 경계 보안을 구성하려고 합니다.


### <a name="how-do-i-manage-the-dns-changes-for-exchange-online-so-mail-will-continue-to-flow"></a>메일이 계속 전송될 수 있도록 Exchange Online의 DNS 변경 내용을 관리하는 방법

Microsoft에서 관리하는 IP 범위 및 DNS 영역은 전역 서비스로 마이그레이션하는 동안 및 마이그레이션의 일부로 전환됩니다. 

사용자 지정 도메인 MX 레코드와 같은 고객 관리 DNS 영역은 고객의 책임입니다. 그러나 이 마이그레이션을 간소화하기 위해 고객은 MX 레코드가 office.de 영역의 Office 365 서비스 끝점을 지점으로 지정하고 Microsoft는 이 서비스 끝점의 마이그레이션을 자동으로 관리합니다.


### <a name="how-do-i-manage-the-dns-changes-for-skype-for-business"></a>비즈니스용 Skype의 DNS 변경 내용을 관리하는 방법 
 
모든 비즈니스용 Skype 고객은 Microsoft Teams로 전환됩니다. Teams로 마이그레이션할 때 고객 Skype DNS 영역의 전환은 필요하지 않습니다. 고객은 마이그레이션 후 모든 기능을 통해 즉시 Teams에 로그인할 수 있습니다.
 

### <a name="will-outlook-for-ios-and-android-work-after-the-migration"></a>마이그레이션 후 iOS 및 Android용 Outlook이 작동하나요? 

예. 모든 고객은 iOS 및 Android용 Outlook을 포함하여 사용 가능한 최신 버전의 Office 클라이언트를 실행합니다. Office 365 전역 서비스로의 마이그레이션이 완료된 후 모든 Office 클라이언트가 로그아웃했다가 다시 로그인하여 전역 서비스에서 새 Azure Active Directory 액세스 토큰을 얻어야 합니다. 



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
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경 및](ms-cloud-germany-transition-add-experience.md) [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
