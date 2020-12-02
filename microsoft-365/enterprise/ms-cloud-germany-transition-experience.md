---
title: Office 365 서비스 신규 독일 데이터 센터 지역으로 마이그레이션 하는 동안 고객 경험
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
description: '요약: Microsoft 클라우드 독일 (Microsoft 클라우드 독일)에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 이동 하는 환경에 대해 설명 합니다.'
ms.openlocfilehash: a44fbe504a9a710856deeb3baf258feb124ce7ae
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551698"
---
# <a name="customer-experience-during-the-migration-to-office-365-services-in-the-new-german-datacenter-regions"></a>Office 365 서비스 신규 독일 데이터 센터 지역으로 마이그레이션 하는 동안 고객 경험

테 넌 트 마이그레이션은 관리자와 사용자에 게 최소한의 영향을 주도록 설계 되었습니다. 하지만, 각 작업과 관련하여 다음 사항에 유의 하세요.  작업에 대 한 마이그레이션 환경을 보다 잘 이해 하려면 다음 섹션을 검토 하세요.

다음은 새 독일어 데이터 센터 지역에서 Microsoft 클라우드 독일 및 Office 365 서비스 간의 주요 차이점입니다.

| 범주 | Microsoft Cloud 독일 (Microsoft 클라우드 독일) | 신규 독일 데이터 센터 지역에서의 Office 365 서비스 |
|:-------|:-----|:-------|
| 하나의 Office 365 테넌트만으로도 구독 가능한 Microsoft 365 서비스 | 서비스 15 개 | 29 서비스 <br><br> 자세한 내용은 [서로 다른 Office 365 클라우드 서비스 제품 간의 서비스 가용성](ms-cloud-germany-transition.md#serv-avail)을 참조 하세요. |
| 새로운 기능 | 새로운 기능은 제공하지 않습니다.  | 새로운 기능은 Office 365 서비스와 일관 되 게 사용할 수 있습니다. |
| 데이터 트러스티 | 예 | 아니요 |
| 글로벌 365 테넌트와 협업  | 아니요 | 예 |
| 고객 데이터 보존 | 고객 데이터는 독일어 데이터 센터 내에만 저장 됩니다. | Microsoft는 다음과 같은 고객 데이터를 독일 내부에 독점적으로 저장 합니다. <ul><li> Exchange Online 사서함 콘텐츠 (전자 메일 본문, 일정 항목 및 전자 메일 첨부 파일 콘텐츠) </li><li> SharePoint Online 사이트 콘텐츠 및 해당 사이트 내에 저장 된 파일 및 비즈니스용 OneDrive에 업로드 되는 파일 </li></ul> |
| 적용 약관  | 이 [보조](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=64) 를 포함 하는 [온라인 서비스 약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) | [온라인 서비스 약관](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=46) |
||||

## <a name="azure-active-directory"></a>Azure Active Directory Domain Services

변경 되지 않는 사항:

- 마이그레이션 후 테 넌 트 `contoso.onmicrosoft.de` ID (GUID)와 사용자 지정 도메인을 포함 하는 거주자 초기 도메인 (예:)이 유지 됩니다. 

- Office 365 services로 마이그레이션되는 리소스에 대 한 인증 요청은 Office 365 services Azure 인증 서비스 ()에 의해 부여 됩니다 `login.microsoftonline.com` . 마이그레이션 중에 여전히 Office 365 독일에 남아 있는 리소스는 기존 독일 Azure 서비스 ()에 의해 인증 됩니다 `login.microsoftonline.de` .

참고 사항:

- 관리 되는 도메인 계정의 경우 초기 Azure Active Directory (Azure ad) 테 넌 트를 복사한 후에 (azure ad 마이그레이션 Office 365 services Azure AD service로의 첫 번째 단계), 암호 변경, SSPR (셀프 서비스 암호 재설정) 변경 내용, 관리자가 Office 365 서비스 포털에서 암호를 다시 설정 해야 합니다. Azure AD 테 넌 트가 Office 365 서비스로 마이그레이션 되었으므로이 시점에는 독일 서비스에서 암호를 업데이트 하는 요청이 제대로 수행 되지 않습니다. 페더레이션 도메인 암호의 재설정은 온-프레미스 디렉터리에서 완료 되었기 때문에 영향을 받지 않습니다.

- Azure 로그인은 사용자가 액세스를 시도 하는 포털에 표시 됩니다. 감사 로그는 전환 후 Office 365 서비스 끝점 에서만 사용할 수 있습니다. 마이그레이션이 완료 될 때까지 마이그레이션하기 전에 Microsoft Cloud 독일 portal에서 로그인 및 감사 로그를 저장 해야 합니다.

- 암호 재설정, 암호 변경, 관리자가 관리 되는 조직 (Active Directory Federation Services를 사용 하지 않는 경우)에 대 한 암호 재설정은 Office 365 서비스 포털을 통해 수행 해야 합니다. 암호를 다시 설정 하기 위해 Microsoft Cloud 독일 portal에 액세스 하는 사용자의 시도는 실패 합니다.

- GDPR (일반 데이터 보호 규정) d e r i e r (데이터 주체 요청)은 향후 요청을 위해 Office 365 services Azure 관리 포털에서 실행 됩니다. Microsoft Cloud 독일에 상주 하는 모든 레거시 또는 고객이 진단 데이터는 30 일 또는 그 이전에 삭제 됩니다.

## <a name="subscriptions--licenses"></a>구독 & 라이선스

- Microsoft 클라우드 독일의 Office 365 및 Dynamics 구독은 Azure AD 재배치가 포함 된 독일어 지역으로 전환 됩니다. 그런 다음 새 Office 365 서비스 구독을 반영 하도록 조직이 업데이트 됩니다. 간단한 구독 전송 프로세스 중에는 구독의 변경 내용이 차단 됩니다.

- 테 넌 트가 Office 365 서비스로 전환 되 면 해당 독일 관련 구독 및 라이선스는 새로운 Office 365 서비스 제품으로 표준화 됩니다. 전송 된 독일 구독에 해당 하는 Office 365 서비스 구독을 구입 합니다. 독일 라이선스가 있는 사용자에 게 Office 365 서비스 라이선스가 할당 됩니다. 완료 되 면 레거시 독일 구독은 현재 Office 365 서비스 테 넌 트에서 취소 되 고 제거 됩니다.

- 개별 작업을 마이그레이션한 후에는 새 Office 365 서비스 구독으로 인해 Office 365 서비스 (예: Microsoft Planner 및 Microsoft Flow)를 통해 추가 기능을 사용할 수 있게 됩니다. 조직에 적합 한 경우 테 넌 트 또는 라이선스 관리자는 새 서비스를 도입 하기 위해 변경 관리를 계획할 때 새 서비스 계획을 사용 하지 않도록 설정할 수 있습니다. 사용자 라이선스에 할당 된 서비스 계획을 사용 하지 않도록 설정 하는 방법에 대 한 지침은 [사용자 라이선스를 할당 하는 동안 Microsoft 365 services에 대 한 액세스 사용 안 함을](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses)참조 하세요.

## <a name="exchange-online"></a>Exchange Online

- Exchange 리소스 Url은 마이그레이션 후 레거시 독일 끝점에서 `outlook.office.de` Office 365 서비스 끝점으로 전환 `outlook.office365.com` 됩니다. 사용자는 마이그레이션이 완료 될 때까지 레거시 URL을 사용 하 여 마이그레이션된 사서함에 액세스할 수 있습니다. 고객은 독일 환경의 만료 영향을 방지 하기 위해 Exchange 마이그레이션이 시작 된 후 가능한 한 빨리 사용자를 새 URL로 전환 해야 합니다. Outlook services에 대 한 Office 365 서비스 Url은 Exchange 마이그레이션이 시작 된 후에만 사용할 수 있습니다.

- 사서함은 백엔드 프로세스로 마이그레이션됩니다. 조직의 사용자는 전환 중에 Microsoft 클라우드 독일 또는 독일어 지역에 있을 수 있으며 같은 Exchange 조직의 일부인 동시에 동일한 전체 주소 목록에 있습니다.

- 사서함이 없는 URL을 사용 하 여 서비스에 액세스 하는 Outlook Web App 사용자에 게는 추가 인증 프롬프트가 표시 됩니다. 예를 들어 사용자의 사서함이 Office 365 서비스이 고 사용자의 Outlook Web App 연결이 레거시 끝점을 사용 하는 경우 `outlook.office.de` 에는 사용자가 먼저를 인증 한 `login.microsoftonline.de` 후로를 실행 합니다 `login.microsoftonline.com` . 마이그레이션이 완료 되 면 사용자가 새 URL ()에 액세스할 수 있으며, `https://outlook.office365.com` 예상 되는 단일 로그인 요청만 표시 됩니다. 

## <a name="office-services"></a>Office 서비스

Office Online 서비스는 전환 전후에 액세스할 수 `office.de` 있습니다. 사용자의 사서함이 Office 365 서비스로 전환 되 면 사용자는 Office 365 서비스 Url 사용을 시작 해야 합니다. 후속 작업을 통해 Office 365 서비스로 마이그레이션하는 경우 office.com 포털의 인터페이스가 작동 하기 시작 합니다.

## <a name="exchange-online-protection"></a>Exchange Online Protection

- 백 엔드 Exchange Online Protection (EOP) 기능은 새 독일 지역으로 복사 됩니다.
- Office 365 보안 및 준수 센터 사용자는 마이그레이션의 일부로 전역 Url을 사용 하도록 전환 해야 `https://protection.office.com` 합니다.

## <a name="skype-for-business-online"></a>비즈니스용 Skype Online

기존 비즈니스용 Skype Online 고객은 Microsoft 팀으로 이관 됩니다. 자세한 내용은를 참조 [https://aka.ms/SkypeToTeams-Home](https://aka.ms/SkypeToTeams-Home) 하세요.

## <a name="office-365-video"></a>Office 365 비디오

Office 365 비디오를 새 독일어 데이터 센터 지역으로 마이그레이션한 후에도 2021 및 Office 365 Video가 지원 되지 않습니다. Office 365 비디오의 콘텐츠는 SharePoint Online 마이그레이션 과정의 일부로 마이그레이션됩니다. 그러나 Office 365 비디오의 비디오는 SharePoint 마이그레이션 후에 Office 365 비디오 UI에서 재생 되지 않습니다. Office 365 비디오 전환의 마이그레이션 시간 표시줄에 대해 자세히 알아보세요 [(클래식) 개요를](https://docs.microsoft.com/stream/migrate-from-office-365#microsoft-cloud-deutschland-timeline)확인 하세요.

## <a name="next-step"></a>다음 단계

[마이그레이션 단계 작업 및 영향 이해](ms-cloud-germany-transition-phases.md)

## <a name="more-information"></a>추가 정보

시작 하기:

- [Microsoft Cloud 독일에서 새 독일어 데이터 센터 지역의 Office 365 서비스로 마이그레이션](ms-cloud-germany-transition.md)
- [Microsoft Cloud Deutschland 마이그레이션 지원](https://aka.ms/germanymigrateassist)
- [마이그레이션에 대해 옵트인하는 방법](ms-cloud-germany-migration-opt-in.md)

전환을 통해 이동 하는 경우:

- [마이그레이션 단계 작업 및 영향](ms-cloud-germany-transition-phases.md)
- [추가 사전 작업](ms-cloud-germany-transition-add-pre-work.md)
- [서비스](ms-cloud-germany-transition-add-general.md), [장치](ms-cloud-germany-transition-add-devices.md), [환경](ms-cloud-germany-transition-add-experience.md)및 [AD FS](ms-cloud-germany-transition-add-adfs.md)에 대 한 추가 정보

클라우드 앱:

- [Dynamics 365 마이그레이션 프로그램 정보](https://aka.ms/d365ceoptin)
- [Power BI 마이그레이션 프로그램 정보](https://aka.ms/pbioptin)
- [Microsoft Teams 업그레이드 시작하기](https://aka.ms/SkypeToTeams-Home)
