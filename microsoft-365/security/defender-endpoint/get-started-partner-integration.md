---
title: 엔드포인트용 Microsoft Defender 파트너 자격
ms.reviewer: ''
description: 끝점용 Microsoft Defender와 솔루션을 통합하고 파트너가 하기 위한 단계 및 요구 사항에 대해 자세히 알아보십시오.
keywords: 파트너, 통합, 솔루션 유효성 검사, 인증, 요구 사항, 구성원, misa, 응용 프로그램 포털
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 59f59ac097cf2c2be3116f67abb4316d17a9ef97
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60556367"
---
# <a name="become-a-microsoft-defender-for-endpoint-partner"></a>엔드포인트용 Microsoft Defender 파트너 자격

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Endpoint 솔루션 파트너가 되기 위해 다음 단계를 수행하고 완료해야 합니다.

## <a name="step-1-subscribe-to-a-microsoft-defender-for-endpoint-developer-license"></a>1단계: 끝점 개발자용 Microsoft Defender 라이선스 구독

[끝점 개발자용 Microsoft Defender 라이선스를 구독합니다.](https://winatpregistration-prd.trafficmanager.net/Developer/UserAgreement?Length=9) Subscribing을 사용하면 최대 10대의 장치가 있는 끝점용 Microsoft Defender 테넌트를 사용하여 끝점용 Microsoft Defender와 통합되는 솔루션을 개발할 수 있습니다.

## <a name="step-2-fulfill-the-solution-validation-and-certification-requirements"></a>2단계: 솔루션 유효성 검사 및 인증 요구 사항 이행

기술 파트너가 통합이 작동하는지 인증하는 가장 좋은 방법은 공동 고객이 제안된 통합 디자인을 승인할 수 있도록 [](https://securitycenter.microsoft.com/interoperability/partners) 하는 것입니다(고객이 Microsoft Defender 보안 센터 파트너 응용 프로그램 페이지에서 파트너 추천 옵션을 사용할 수 있습니다) 끝점용 Microsoft Defender 팀으로 테스트 및 강연을 합니다. 

Microsoft Defender for Endpoint 팀이 통합을 검토하고 승인하면 Microsoft 지능형 보안 협회에서 파트너로 포함될 수 있습니다.

## <a name="step-3-become-a--microsoft-intelligent-security-association-member"></a>3단계: Microsoft Intelligent Security Association 구성원 되기

[Microsoft Intelligent Security Association는](https://www.microsoft.com/security/partnerships/intelligent-security-association) Microsoft 보안 파트너를 위한 프로그램으로, 보안 제품을 강화하고 Microsoft 보안 제품에 대한 통합의 고객 검색 기능을 개선하는 데 도움을 줄 수 있습니다.

## <a name="step-4-get-listed-in-the-microsoft-defender-for-endpoint-partner-application-portal"></a>4단계: 끝점 파트너 응용 프로그램 포털용 Microsoft Defender에 나열

끝점용 Microsoft Defender는 Microsoft Defender for Endpoint [](partner-applications.md) 관리 포털에 포함된 제품 내 파트너 페이지를 사용하여 타사 응용 프로그램 검색 및 통합을 지원합니다.

회사를 제품 내 파트너 페이지에 파트너로 나열하려면 다음 정보를 제공해야 합니다.

1. SVG(정사각형 로고).
2. 발표할 제품의 이름입니다.
3. 15 단어 제품 설명을 제공합니다.
4. 고객을 위한 방문 페이지로 연결하여 고객에게 충분한 정보를 포함할 통합 또는 블로그 게시물을 완료합니다. Microsoft Defender for Endpoint 제품 이름을 포함한 모든 보도 자료는 마케팅 및 엔지니어링 팀에서 검토해야 합니다. 검토 프로세스가 완료될 때까지 10일 이상 기다릴 수 있습니다.
5. 다중 테넌트 Azure AD 접근 방법을 사용하는 경우 응용 프로그램의 사용을 추적하려면 Azure AD 응용 프로그램 이름이 필요합니다.
6. Microsoft Defender에서 User-Agent API 또는 보안 API의 끝점 공용 집합에 대해 호출한 각 API에 Graph 필드를 포함합니다. 이는 통계 목적, 문제 해결 및 파트너 인식에 사용됩니다. 또한 이 단계는 MISA(Microsoft Intelligent Security Association)의 멤버 자격에 대한 요구 사항입니다.

   다음 단계를 따릅니다.

   - 각 HTTP User-Agent 헤더의 User-Agent 필드를 아래 형식으로 설정하십시오.

     ```http
     MdePartner-{CompanyName}-{ProductName}/{Version}
     ```

     예를 들어 User-Agent:

     ```http
     MdePartner-Contoso-ContosoCognito/1.0.0
     ```

   - 자세한 내용은 [RFC 2616 섹션-14.43을 참조하세요.](https://tools.ietf.org/html/rfc2616#section-14.43)

Endpoint용 Microsoft Defender와의 파트너 관계는 상호 고객이 방어를 더욱 간소화, 통합 및 오케스트레이션하는 데 도움이 됩니다. 사용자가 최신 위협을 함께 방지하고 대응하여 고객 및 자산을 효과적으로 보호하는 공통의 목표를 달성하기 위해 Microsoft Defender 파트너가 되기로 선택해 기쁘습니다.

## <a name="related-topics"></a>관련 항목

- [기술 파트너 기회](partner-integration.md)
