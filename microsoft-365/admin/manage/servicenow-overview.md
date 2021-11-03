---
title: Microsoft 365 통합 지원 서비스Now 구성 개요
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow에 대한 범위가 지정한 인증된 응용 프로그램 설치 및 구성 가이드입니다.
ms.openlocfilehash: c5d0bf57eb037bd19b9666f9b3684249986d8f2e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661936"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-overview"></a>Microsoft 365 통합 지원 서비스Now 구성 개요

**Microsoft 365 통합을** 통해 서비스 Microsoft 365, 지원 및 서비스 상태와 ServiceNow 인스턴스를 통합할 수 있습니다. Microsoft의 알려진 문제 및 보고된 문제를 조사하고, 인시던트 문제를 해결하고, Microsoft 권장 솔루션을 사용하여 작업을 완료하고, 필요한 경우 Microsoft 휴먼 지원으로 에스컬레이터할 수 있습니다.

ServiceNow **Microsoft 365** 지원 통합 앱의 경우 servicenow 스토어로 [이동하세요.](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)

## <a name="key-features"></a>주요 기능

다음은 ServiceNow 인스턴스의 Microsoft 365 통합 앱과 함께 사용할 수 있는 주요 기능입니다.

- 서비스 상태 인시던트: 사용자 영향, 범위, 현재 상태 및 다음 예상 업데이트를 포함하여 알려진 Microsoft 서비스 상태 인시던트에 대한 정보입니다. 기계 학습을 사용하여 ServiceNow 인시던트는 간단한 설명 필드를 기반으로 Microsoft 서비스 상태 인시던트와 일치합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-1.png" alt-text="서비스 상태 인시던트 설명 필드입니다.":::

- 권장 해결 방법: 작업 및 인시던트에 대한 설명은 기계 학습을 통해 지원되는 Microsoft의 정확한 대상 솔루션 및 관련 문서를 권장하는 데 사용됩니다. 필요한 경우 Search를 사용하여 다른 솔루션을 찾을 수도 있습니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-description-field-2.png" alt-text="권장 솔루션 설명 필드입니다.":::

- Microsoft 서비스 요청: 문제를 Microsoft 지원 에이전트로 에스컬레이터하고 사례에 대한 상태 업데이트를 수신합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-service-request.png" lightbox="../../media/ServiceNow-guide/servicenow-overview-service-request.png" alt-text="서비스 요청 양식입니다.":::

## <a name="prerequisites"></a>필수 구성 요소

### <a name="permissions-requirements"></a>사용 권한 요구 사항

이 가이드를 계속 진행하려면 전체 프로세스 중에 환경에 대해 다음 사용 권한을 사용할 수 있도록 구성해야 합니다.

- Azure Active Directory (AAD) 응용 프로그램을 만들 수 있는 AAD 관리자

- ServiceNow 관리자

- Microsoft 365 테넌트 관리자

### <a name="configuration-highlights"></a>구성 주요

지원 **통합을 Microsoft 365:**

- 아웃바운드 및 Microsoft Azure Active Directory API AAD 인증을 위해 응용 프로그램을 AAD 등록합니다.

- 아웃바운드 및 인바운드 데이터 흐름에 AAD Microsoft 응용 프로그램을 사용하여 ServiceNow 엔터티를 만들 수 있습니다.

- 서비스 관리 포털을 통해 ServiceNow 인스턴스를 Microsoft Microsoft 365 통합합니다.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-overview-integration-diagram.png" alt-text="ServiceNow 통합 다이어그램.":::

### <a name="application-dependencies-in-your-servicenow-environments"></a>ServiceNow 환경의 응용 프로그램 종속성

필요한 사용 권한:

- oauth \_ 엔터티

- oauth \_ 엔터티 \_ 프로필

Microsoft 365 통합 앱을 설치하고 나면 두 개의 응용 프로그램 범위 간 액세스가 만들어집니다. 성공적으로 만들어지지 않은 경우 수동으로 만드시다.

## <a name="what-features-will-work-for-your-organization-based-on-your-configuration"></a>구성에 따라 조직에 어떤 기능이 작동하나요?

Microsoft 365 통합을 위한 구성을 설정하기 전에 다음 질문에 대한 답변을 검토하세요.

**질문 \# 1:** ServiceNow 환경에서 인바운드 웹 서비스 호출에 대해 기본 인증(ServiceNow 사용자 자격 증명으로 액세스)을 허용하나요?

**질문 \# 2:** 테넌트가 여러 개인 경우 서비스 지원 통합을 위해 ServiceNow 환경과 통합된 단일 테넌 Microsoft 365 계획입니까?

위의 질문에 대한 답변에 따라 다음 표에는 사용 가능한 기능과 지원 통합을 설정하는 Microsoft 365 설명되어 있습니다. 각 기능에 대한 설명은 Microsoft 365 [통합을 참조하세요.](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)

| 질문 \# 1 답변 | 질문 \# 2 답변 | 사용할 수 있는 기능은 무엇입니까? | 구성 단계 |
|---------------------|---------------------|-----------|----------------|
| 예                 | 예/아니요              | 서비스 상태 인시던트 권장 솔루션 Microsoft 서비스 요청 | [ServiceNow Microsoft 365 통합 지원 설정](servicenow-basic-authentication.md) |
| 아니요                  | 예                 | 서비스 상태 인시던트 권장 솔루션 Microsoft 서비스 요청 | [OAuth Microsoft 365 통합 지원 AAD 설정](servicenow-aad-oauth-token.md)                 |
| 아니요                  | 아니요                  | 서비스 상태 인시던트 권장 솔루션                           | [전용에 Microsoft 365 지원 통합 Insights 설정](servicenow-service-health-incidents-solutions-only.md)                    |
