---
title: 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션한 후 변경되는 것
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/11/2020
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
description: '요약: 독일 Microsoft 클라우드(도이치란드 Microsoft 클라우드)에서 새로운 독일 데이터 센터 지역의 Office 365 서비스로 전환하기 위해 변경된 내용을 이해합니다.'
ms.openlocfilehash: 74ad9a662d3ea7a68ef1f82961864eb4468f6098
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/06/2021
ms.locfileid: "51591783"
---
# <a name="what-will-change-after-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션한 후 변경되는 것

테넌트 마이그레이션은 관리자와 사용자에게 최소한의 영향을 미치기 위해 고안된 것입니다. 하지만, 각 작업과 관련하여 다음 사항에 유의 하세요.  다음 섹션을 검토하여 워크로드에 대한 마이그레이션 환경을 보다 잘 이해하세요.

다음은 독일 신규 독일 데이터 센터 지역의 Microsoft 클라우드와 Office 365 서비스 간의 주요 차이점입니다.

| Category | 독일 Microsoft 클라우드(도이칠란드 Microsoft 클라우드) | 신규 독일 데이터 센터 지역에서의 Office 365 서비스 |
|:-------|:-----|:-------|
| 하나의 Office 365 테넌트만으로도 구독 가능한 Microsoft 365 서비스 | 서비스 15개 | 29개 서비스 <br><br> 자세한 내용은 서로 다른 [Office 365](ms-cloud-germany-transition.md#serv-avail)클라우드 서비스 제품 간의 서비스 가용성이란?을 참조하세요. |
| 새로운 기능 | 새로운 기능은 사용할 수 없습니다. | Office 365 서비스와 일관된 새로운 기능을 사용할 수 있습니다. |
| 데이터 트러스티 | 예 | 아니요 |
| 글로벌 365 테넌트와 협업  | 아니요 | 예 |
| 고객 데이터 보존 | 고객 데이터는 독일 데이터 센터 내에만 저장됩니다. | Microsoft는 다음과 같은 고객 데이터를 독일 내에서만 저장합니다. <ul><li> Exchange Online 사서함 콘텐츠(전자 메일 본문, 일정 항목 및 전자 메일 첨부 파일 콘텐츠) </li><li> SharePoint Online 사이트 콘텐츠 및 해당 사이트에 저장된 파일 및 비즈니스용 OneDrive에 업로드된 파일 </li></ul> |
| 적용 약관  | [이 추가가 있는](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) 온라인 서비스 [약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) | [온라인 서비스 약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory

변경되지 않는 사항:

- 테넌트 ID(GUID) 및 사용자 지정 도메인이 있는 테넌트 초기 도메인(예: )은 마이그레이션 `contoso.onmicrosoft.de` 후에도 지속됩니다. 

- Office 365 서비스로 마이그레이션된 리소스에 대한 인증 요청은 Office 365 서비스 Azure 인증 서비스()에서 `login.microsoftonline.com` 부여됩니다. 마이그레이션 중에 Office 365 Germany에 남아 있는 리소스는 기존 독일 Azure 서비스()에 의해 `login.microsoftonline.de` 인증됩니다.

참고할 고려 사항:

- 관리되는 도메인 계정의 경우 초기 Azure AD(Active Directory) 테넌트의 복사가 완료된 후(Office 365 서비스 Azure AD 서비스로 Azure AD 마이그레이션의 첫 번째 단계), 암호 변경, SSPR(셀프 서비스 암호 재설정) 변경 및 관리자가 암호 재설정을 완료해야 합니다. Azure AD 테넌트가 Office 365 서비스로 마이그레이션되어 독일 서비스에서 암호 업데이트 요청이 성공하지 못합니다. 페더임 도메인 암호 재설정은 영향을 받지 않습니다. 이러한 암호는 On-premises 디렉터리에서 완료됩니다.

- Azure 로그인은 사용자가 액세스를 시도하는 포털에 표시됩니다. 감사 로그는 전환 후 Office 365 서비스 끝점에서만 사용할 수 있습니다. 마이그레이션이 완료되기 전에 도이치랜드 Microsoft 클라우드 포털에서 로그인 및 감사 로그를 저장해야 합니다.

- Office 365 서비스 포털을 통해 관리되는 조직(Active Directory Federation Services를 사용하지 않는)의 관리자가 암호 재설정, 암호 변경, 암호 재설정을 수행해야 합니다. 도이클란드 Microsoft 클라우드 포털에 액세스하는 사용자가 암호를 다시 설정하려고 하면 실패합니다.

- GDPR(일반 데이터 보호 규정) DSR(데이터 주체 요청)은 향후 요청을 위해 Office 365 서비스 Azure 관리 포털에서 실행됩니다. 도이클란드 Microsoft 클라우드에 있는 레거시 또는 비 고객 진단 데이터는 30일 또는 그 전에 삭제됩니다.

## <a name="subscriptions--licenses"></a>구독 & 라이선스

- 독일 Microsoft 클라우드의 Office 365 및 Dynamics 구독은 Azure AD 재배치가 있는 독일 지역으로 전환됩니다. 그런 다음 새 Office 365 서비스 구독을 반영하기 위해 조직이 업데이트됩니다. 간략한 구독 전송 프로세스 중에 구독에 대한 변경 내용이 차단됩니다.

- 테넌트가 Office 365 서비스로 전환될 때 독일 관련 구독 및 라이선스는 새로운 Office 365 서비스 제품으로 표준화됩니다. 전송된 독일 구독에 대해 해당 Office 365 서비스 구독을 구매합니다. 독일 라이선스가 있는 사용자에게는 Office 365 서비스 라이선스가 할당됩니다. 완료 시 레거시 독일 구독이 취소되고 현재 Office 365 서비스 테넌트에서 제거됩니다.

- 개별 워크로드를 마이그레이션한 후 새로운 Office 365 서비스 구독을 통해 Office 365 서비스(예: Microsoft Planner 및 Microsoft Flow)를 통해 추가 기능을 사용할 수 있습니다. 조직에 적합한 경우 테넌트 또는 라이선스 관리자는 새 서비스를 도입하기 위한 변경 관리를 계획할 때 새 서비스 계획을 사용하지 않도록 설정할 수 있습니다. 사용자의 라이선스에 할당된 서비스 계획을 사용하지 않도록 설정하는 방법에 대한 지침은 사용자 라이선스를 할당하는 동안 [Microsoft 365](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)서비스에 대한 액세스 사용 안 하도록 설정을 참조하세요.

## <a name="exchange-online"></a>Exchange Online

- 마이그레이션 후 레거시 독일 끝점에서 Office 365 서비스 끝점으로 Exchange 리소스 URL을 `outlook.office.de` `outlook.office365.com` 전환합니다. 사용자는 마이그레이션이 완료될 때까지 레거시 URL을 사용하여 마이그레이션된 사서함에 액세스할 수 있습니다. 고객은 Exchange 마이그레이션이 시작된 후 독일 환경의 사용 중지에 영향을 주지 않도록 최대한 빨리 사용자를 새 URL로 전환해야 합니다. Outlook 서비스의 Office 365 서비스 URL은 Exchange 마이그레이션이 시작된 후에만 사용할 수 있습니다.

- 사서함은 백end 프로세스로 마이그레이션됩니다. 조직의 사용자는 전환 중에 독일 Microsoft 클라우드 또는 독일 지역에 있을 수 있으며 동일한 Exchange 조직(동일한 전체 주소 목록에 있는)에 참여할 수 있습니다.

- 사서함이 Outlook Web App 없는 URL을 사용하여 서비스에 액세스하는 사용자에게는 추가 인증 프롬프트가 표시됩니다. 예를 들어 사용자의 사서함이 Office 365 서비스에 있으며 사용자의 Outlook Web App 연결에서 레거시 끝점을 사용하는 경우 사용자는 먼저 에 인증한 다음 에 를 `outlook.office.de` `login.microsoftonline.de` `login.microsoftonline.com` 인증합니다. 마이그레이션이 완료되면 사용자는 새 URL( ) 에 액세스할 수 있으며 예상되는 단일 로그인 요청만 `https://outlook.office365.com` 표시됩니다. 

## <a name="office-services"></a>Office Services

전환 전과 전환 중에 Office Online `office.de` 서비스에 액세스할 수 있습니다. 사용자의 사서함이 Office 365 서비스로 전환되면 사용자는 Office 365 서비스 URL 사용을 시작해야 합니다. 이후 워크로드가 Office 365 서비스로 마이그레이션되면 office 365 포털에서 office.com 인터페이스가 작동하기 시작됩니다.

Office에서 가장 최근에 사용한(MRU) 서비스는 마이그레이션이 아니라 도이클란드 Microsoft 클라우드에서 Office 365 전역 서비스로의 전환입니다. Office 365 전역 서비스 쪽의 MRU 링크만 포털에서 마이그레이션한 Office.com 표시됩니다. 도이치랜드 Microsoft 클라우드의 MRU 링크는 Office 365 전역 서비스의 MRU 링크로 표시되지 않습니다. Office 365 전역 서비스에서 테넌트 마이그레이션이 9단계에 도달한 후에만 MRU 링크에 액세스할 수 있습니다.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- 백 엔드 EOP(Exchange Online Protection) 기능은 새 독일 지역에 복사됩니다.
- Office 365 보안 및 준수 센터 사용자는 마이그레이션의 일부로 전역 URL을 사용하여 `https://protection.office.com` 전환해야 합니다.

## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

기존 비즈니스용 Skype Online 고객은 Microsoft 팀으로 이관 됩니다. 자세한 내용은 을 [https://aka.ms/SkypeToTeams-Home](/microsoftteams/upgrade-start-here) 참조하세요.

## <a name="office-365-video"></a>Office 365 비디오

Office 365 비디오는 2021년 3월 1일에 사용 중지되고, 새 독일 데이터 센터 지역으로의 SharePoint Online 마이그레이션이 완료된 후 Office 365 비디오가 지원되지 않습니다. Office 365 비디오의 콘텐츠는 SharePoint Online 마이그레이션의 일부로 마이그레이션됩니다. 그러나 Office 365 비디오의 비디오는 SharePoint 마이그레이션 후 Office 365 비디오 UI에서 재생되지 않습니다. [Office 365 비디오에서 Microsoft Stream(클래식)](/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)개요로의 마이그레이션 일정에 대해 자세히 알아보세요.

## <a name="next-step"></a>다음 단계

[마이그레이션 단계 작업 및 영향 이해](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>추가 정보

시작:

- [독일 Microsoft 클라우드에서 새 독일 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)

전환을 통해 이동:

- [문장 작업 및 영향 마이그레이션](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [장치,](ms-cloud-germany-transition-add-devices.md) [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS에](ms-cloud-germany-transition-add-adfs.md)대한 추가 정보.

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](/dynamics365/get-started/migrate-data-german-region)
- [Power BI 마이그레이션 프로그램 정보](/power-bi/admin/service-admin-migrate-data-germany)
- [Microsoft Teams 업그레이드 시작하기](/microsoftteams/upgrade-start-here)
