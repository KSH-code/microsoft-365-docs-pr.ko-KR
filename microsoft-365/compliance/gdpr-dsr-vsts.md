---
title: GDPR에 대한 Azure DevOps 데이터 주체 요청
keywords: Visual Studio Team Services, VSTS, Azure DevOpsS 설명서, 개인 정보, GDPR
localization_priority: Priority
audience: itpro
ms.prod: devops
ms.topic: article
ms.date: 06/11/2018
author: jitojo
ms.author: jominana
manager: douge
ms.collection: GDPR
ms.workload:
- multiple
ms.openlocfilehash: 91ab1c1e23b2f4f9aab5c4327c29ac6cea52d080
ms.sourcegitcommit: 0dde96d5864e5b16ea24cfb302930b041c7a8091
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "34431779"
---
# <a name="azure-devops-services-data-subject-requests-for-the-gdpr"></a>GDPR에 대한 Azure DevOps Services 데이터 주체 요청

유럽 연합 [GDPR(일반 데이터 보호 규정)](http://ec.europa.eu/justice/data-protection/reform/index_en.htm)은 사용자(규정에 *데이터 주체*로 알려짐)에게 *데이터 통제자*가 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 데이터 통제자 또는 단순히 *통제자*는 고용주 또는 다른 유형의 대리점 및 조직(데이터 통제자 또는 단순히 통제자로 지칭)이 수집한 개인 데이터를 관리할 수 있는 권한을 부여합니다. 개인 데이터는 GDPR에서는 보다 광범위하게 식별되었거나 식별 가능한 자연인과 관련된 모든 데이터로 정의됩니다. GDPR은 데이터 주체에게 개인 데이터에 대한 특정 권한을 부여합니다. 이러한 권한에는 개인 데이터 복사본 획득, 수정 요청, 처리 제한, 삭제 또는 다른 통제자에게 이동될 수 있도록 전자 형식으로 수신하는 권한이 포함됩니다. 데이터 주체가 통제자에게 개인 데이터에 대해 조치를 취할 것을 요구하는 공식적인 요청을 *데이터 주체 요청* 또는 DSR이라고 합니다.

GDPR 대한 일반적인 내용은 [Service Trust Portal의 GDPR 섹션](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)을 참조하세요.

이 가이드에서는 Microsoft 도구를 사용하여 인증(로그인)된 Azure DevOps Services(이전에는 Visual Studio Team Services로 알려짐) 세션 동안 수집된 개인 데이터를 내보내거나 삭제하는 방법을 설명합니다.

## <a name="additional-privacy-information"></a>추가 개인 정보 보호 정보

[Microsoft 개인정보 취급방침](https://privacy.microsoft.com/privacystatement), [OST(온라인 서비스 약관)](https://www.microsoft.com/licensing/product-licensing/products.aspx) 및 [Microsoft의 GDPR 약속](/legal/gdpr) 문서에 데이터 처리 방법이 설명되어 있습니다.

## <a name="personal-data-we-collect"></a>수집한 개인 데이터

Microsoft는 Azure DevOps Services를 작동하고 개선하기 위해 사용자의 데이터를 수집합니다. Azure DevOps Services는 두 가지 범주의 데이터, 즉, 고객 데이터 및 시스템 생성 로그를 수집합니다. 고객 데이터에는 Azure DevOps Services가 서비스를 운영하는 데 필요한 사용자를 식별할 수 있는 트랜잭션의 및 상호 작용 데이터가 포함되어 있습니다. 시스템 생성 로그에는 각 제품 영역 및 기능에 대해 집계된 서비스 사용 현황 데이터가 포함됩니다.

## <a name="delete-azure-devops-data"></a>Azure DevOps 데이터 삭제

연결된 Azure DevOps Services 고객 데이터를 삭제하고 시스템 생성 로그에서 찾은 개인 식별이 가능한 데이터를 익명화하는 첫 번째 단계는 AAD(Azure Active Directory) ID 계정 또는 MSA(Microsoft 계정)을 닫는 것입니다. VSTS는 엄격한 무결성, 추적 가능성 및 감사 규칙을 제공하는 레코드 시스템으로서 활용됩니다. 이러한 기존 의무는 GDPR에 대한 삭제 및 보존 의무에 영향을 미칩니다. ID 계정을 닫아도 Azure DevOps Services 조직의 개별 ID와 연결된 아티팩트 및 레코드는 수정되거나, 제거되거나, 변경되지 않습니다. 전체 Azure DevOps Services 조직이 삭제되면 해당 조직에서 발견된 개인 식별이 가능한 모든 관련된 데이터 및 시스템 생성 로그가 시스템에서 제거됩니다(필수 Azure DevOps Services 조직의 30일 일시 삭제 기간 후).

## <a name="export-azure-devops-data"></a>Azure DevOps 데이터 내보내기

통제자는 Azure DevOps 서비스에 로그인하는 데 사용한 ID 공급자(MSA 또는 AAD)에 따라, 두 가지 방법 중 하나로 데이터 주체에서 수집된 고객 데이터 및 시스템 생성 로그를 내보낼 수 있습니다.

- Azure 테넌트가 지원하는 계정(예를 들어, Azure 구독과 관련된 AAD 계정 또는 MSA 계정)을 사용하여 인증을 받는 사용자는 [GDPR에 대한 Azure 데이터 주체 요청](../compliance/gdpr-dsr-azure.md)의 지침을 따를 수 있습니다.

- MSA ID를 사용하여 인증을 받는 사용자는 이 [개인 정보 요청 사이트](https://www.microsoft.com/concern/privacyrequest-msa)를 사용하여 여러 Microsoft 서비스에서 MSA ID에 연결된 작업 데이터를 볼 수 있습니다. 이 시나리오에서는 사용자가 자신의 개인 데이터에 대한 통제자가 됩니다.

## <a name="export-or-delete-issues"></a>내보내기 또는 삭제 문제

AAD ID의 경우 Azure Portal에서 데이터를 내보내거나 삭제하는 동안 문제가 발생하면 Azure Portal **도움말 + 지원** 블레이드로 이동하여 **등록 관리** > **기타 보안 및 준수 요청** > **개인 정보 보호 블레이드 및 GDPR 요청**에서 새 티켓을 제출합니다.

MSA ID의 경우 개인 정보 요청 사이트에서 데이터를 내보낼 때 문제가 발생할 경우 [개인 정보 요청 사이트](https://www.microsoft.com/concern/privacyrequest-msa)에 로그인한 후 요청 웹 양식을 통해 Microsoft 개인 정보 보호 지원 팀에 대한 지원 요청을 제출합니다.

## <a name="learn-more"></a>자세한 정보

Microsoft는 예외없이, Azure DevOps Services 데이터를 안전하고 비공개로 유지할 것을 약속드립니다. [Azure DevOps Services 데이터 보호 개요](/vsts/articles/team-services-security-whitepaper?view=vsts) 백서를 참조하여 Microsoft가 사용자의 Azure DevOps Services 데이터를 보호하는 방법을 자세히 알아보세요.

## <a name="see-also"></a>참고 항목

- [일반적으로 사용할 수 있는 엔터프라이즈 소프트웨어 제품의 고객에 대한 Microsoft의 GDPR 약속](https://docs.microsoft.com/legal/gdpr)
- [Microsoft 보안 센터](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)
- [Service Trust portal](https://servicetrust.microsoft.com/ViewPage/GDPRGetStarted)
- [Microsoft 개인 정보 대시보드](https://account.microsoft.com/privacy)
- [Microsoft 개인 정보 응답 센터](https://aka.ms/userprivacysite)
- [GDPR에 대한 Azure 데이터 주체 요청](gdpr-dsr-azure.md)