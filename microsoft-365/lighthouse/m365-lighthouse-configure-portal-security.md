---
title: 포털 Microsoft 365 Lighthouse 구성
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 포털을 사용하는 MSP(관리 Microsoft 365 Lighthouse 공급자)의 경우 포털 보안을 구성하는 방법을 알아보고,
ms.openlocfilehash: fadff316b98b57960179214d3d895ecad6467a69
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152481"
---
# <a name="configure-microsoft-365-lighthouse-portal-security"></a>포털 Microsoft 365 Lighthouse 구성

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

관리 서비스 공급자(MSP)가 테넌트에 대한 액세스 권한을 위임한 경우 고객 데이터에 대한 액세스를 보호하는 것이 사이버 보안 우선 순위입니다. Microsoft 365 Lighthouse 및 선택적 기능이 모두 제공되어 Lighthouse 포털 보안을 구성할 수 있습니다.

## <a name="set-up-multifactor-authentication-mfa"></a>MFA(다단계 인증) 설정

블로그 게시물 [Your Pa$$word doesn't matter](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984):

> "암호는 중요하지 않지만 MFA는 중요하지 않습니다. 당사의 연구에 따르면 MFA를 사용하는 경우 계정이 손상될 가능성이 99.9%를 넘습니다."

사용자가 Lighthouse에 처음으로 액세스하는 경우 해당 Microsoft 365 계정이 아직 구성되지 않은 경우 MFA를 설정하라는 메시지가 표시됩니다. 사용자는 필수 MFA 설정 단계가 완료될 때까지 Lighthouse에 액세스할 수 없습니다. 인증 방법에 대한 자세한 내용은 다단계 인증에 Microsoft 365 로그인을 [참조합니다.](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)

## <a name="set-up-roles-to-manage-customer-tenants"></a>고객 테넌트 관리를 위한 역할 설정

Lighthouse의 고객 테넌트 데이터 및 설정에 대한 액세스는 CSP(클라우드 솔루션 공급자) 프로그램의 관리자 에이전트 및 헬프데스크 에이전트 역할로 제한됩니다.

[Azure AD -](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) 모든 그룹 페이지에서 보안 그룹 구성원 자격을 검토하여 파트너 테넌트에 관리자 에이전트 및 헬프데스크 에이전트 역할이 있는 사용자를 확인할 수 있습니다. 사용자에게 CSP 프로그램 역할 및 기타 사용 권한을 할당하는 방법에 대한 자세한 내용은 사용자에게 역할 및 사용 권한 [할당을 참조합니다.](/partner-center/permissions-overview) MSP의 경우 고객 테넌트에 대한 액세스 권한을 위임하지 않은 경우 고객 서비스 또는 구독을 관리할 수 있는 사용 권한 얻기 문서에서 액세스 권한을 얻는 방법을 [배워야 합니다.](/partner-center/customers-revoke-admin-privileges)

다음 표에는 다양한 Lighthouse 페이지와 관리자 에이전트 및 지원 센터 에이전트 역할에 대한 고객 테넌트 데이터 및 설정을 보고 이에 대한 권한을 나열합니다.<br><br>

| Lighthouse 페이지 | 관리자 에이전트 권한 | 헬프데스크 에이전트 권한 |
|--|--|--|
| 홈 | <ul><li> 모두 보기</li></ul> | <ul><li> 모두 보기</li></ul> |
| 테넌트 | <ul><li> 모두 보기</li><li>고객 연락처 및 웹 사이트 업데이트</li><li>배포 계획 보기 및 적용</li></ul> | <ul><li> 모두 보기</li><li>고객 연락처 및 웹 사이트 업데이트</li><li>배포 계획 보기</li></ul> |
| 사용자 | <ul><li> 모두 보기</li><li>암호 다시 설정</li><li>로그인 차단</li><li>MFA 설정</li></ul> | <ul><li> 모두 보기</li><li>암호 다시 설정</li><li>로그인 차단</li></ul> |
| 디바이스 | <ul><li> 모두 보기</li></ul> | <ul><li> 모두 보기</li></ul> |
| 위협 | <ul><li> 모두 보기</li><li>빠른 검사 실행</li><li>전체 검사 실행</li><li>장치 다시부팅</li><li>바이러스 백신 업데이트</li></ul> | <ul><li> 모두 보기</li></ul> |
| 기준 | <ul><li> 모두 보기</li></ul> | <ul><li> 모두 보기</li></ul> |
| 서비스 상태 | <ul><li>모두 보기*</li></ul> | <ul><li>모두 보기*</li></ul> |

> [!NOTE]
> 현재 표에 *로 표시된 작업을 수행하려면 **microsoft.office365.serviceHealth/allEntities/allTasks** 속성 집합이 있는 파트너 테넌트에서 Azure AD 역할도 필요합니다. Azure AD 역할 목록은 Azure AD 기본 [제공 역할을 참조하세요.](/azure/active-directory/roles/permissions-reference)

관리자 에이전트 역할과 관련된 광범위한 사용 권한이 있는 경우 파트너 테넌트 사용자를 관리자 에이전트와 헬프데스크 에이전트로 지정하는 경우 최소 권한 액세스의 원칙을 고수하는 것이 권장됩니다. [](/azure/active-directory/develop/secure-least-privileged-access) 이 작업을 하는 한 가지 방법은 필수 파트너 테넌트 사용자에게 헬프데스크 에이전트 역할을 할당하는 것입니다. 이를 통해 고객 데이터 및 설정을 볼 수 있지만 광범위하게 변경할 수 없습니다. 그런 다음 필요한 경우 Azure AD PIM(Privileged Identity Management)의 just-in-time 액세스 승인 기능을 사용하여 사용자에게 시간 범위 관리 에이전트 역할을 제공합니다.

## <a name="set-up-azure-ad-privileged-identity-management-pim"></a>Azure AD PRIVILEGED IDENTITY MANAGEMENT(PIM) 설정

MSP는 Azure AD PIM(Azure AD Privileged Identity Management 사용하여 보안 정보 또는 리소스에 액세스할 수 있는 사용자 수를 최소화할 수 있습니다. PIM은 악의적인 사용자가 리소스에 액세스하거나 권한이 부여된 사용자가 중요한 리소스에 부수적으로 영향을 줄 수 있는 기회를 줄입니다. 또한 MSP는 사용자에게 리소스에 대한 Just-In-Time 권한을 부여하고 지정된 사용자가 권한 있는 액세스로 수행되는 작업을 모니터링할 수 있습니다.

> [!NOTE]
> Azure AD PIM을 사용하려면 파트너 Azure AD Premium P2 라이선스가 필요합니다.

다음 단계에서는 Azure AD PIM을 사용하여 파트너 테넌트 사용자를 시간 범위가 정해진 관리 에이전트 역할로 승계합니다.

1. Create a group [for assigning roles in Azure Active Directory.](/azure/active-directory/roles/groups-create-eligible)

2. Azure [AD – 모든](https://portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups) 그룹으로 이동하여 관리 에이전트 그룹의 구성원으로 새 그룹을 추가합니다.

3. 권한이 부여된 액세스 그룹에 대해 적격 소유자 및 구성원 할당 문서에 설명된 바와 같이 새 그룹에 대한 권한 있는 [액세스를 설정하세요.](/azure/active-directory/privileged-identity-management/groups-assign-member-owner)

자세한 내용은 What [is Privileged Identity Management?](/azure/active-directory/privileged-identity-management/pim-configure)

## <a name="other-roles-and-permissions"></a>기타 역할 및 사용 권한

다음 표에는 파트너 테넌트 역할 및 관련 사용 권한이 나열됩니다.<br><br>

| 파트너 테넌트 역할 | 파트너 테넌트 내의 사용 권한 |
|--|--|
| 파트너 테넌트의 전역 관리자 | <ul><li>2016년 8월에 Lighthouse에 Microsoft 365 관리 센터.</li><li>첫 실행 경험 동안 파트너 계약 수정을 수락합니다.</li><li>테넌트 페이지에서 고객 테넌트 보기.\*</li><li>테넌트 활성화 및 비활성화\*</li><li>고객 연락처 및 웹 사이트를 업데이트합니다.\*</li><li>태그를 만들고, 업데이트하고, 삭제합니다.\*</li><li>고객 테넌트에서 태그를 할당하고 제거합니다.\*</li></ul> |
| 하나 이상의 파트너 테넌트 관리자<br> 다음 속성 집합을 사용하여 할당된 Azure AD 역할<br> **microsoft.office365.supportTickets/allEntities/allTasks**<br> (Azure AD 역할 목록은 Azure AD 기본 제공 [역할을 참조하세요.)](/azure/active-directory/roles/permissions-reference) | <ul><li>Lighthouse 서비스 요청을 생성합니다.</li></ul> |

> [!NOTE]
> 현재 표에 *로 표시된 작업을 수행하려면 전역 관리자가 관리자 에이전트 역할을 맡아야 합니다.

## <a name="related-content"></a>관련 콘텐츠

[개요](m365-lighthouse-overview.md) Microsoft 365 Lighthouse(문서)\
[등록을](m365-lighthouse-sign-up.md) Microsoft 365 Lighthouse(문서)\
[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)