---
title: Microsoft 365 연결 모니터링
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/4/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 53cdb60c-a6b2-4848-b3ff-e7b75dc3fd1f
description: 이 문서에서는 연결 연결을 모니터링하고 유지 관리하는 데 사용할 수 있는 도구와 기술을 Microsoft 365 있습니다.
ms.openlocfilehash: 783278ad69fbe47afd6ea85fdb70c8bb0057005c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173262"
---
# <a name="monitor-microsoft-365-connectivity"></a>Microsoft 365 연결 모니터링

배포한 Microsoft 365 아래 도구와 기술을 사용하여 Microsoft 365 연결을 유지할 수 있습니다. 공식적인 서비스 상태 및 [](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity) 연속성 지침과 느린 네트워크에서 Microsoft 365 모범 [사례를 이해해야 합니다.](https://support.office.com/article/fd16c8d2-4799-4c39-8fd7-045f06640166) 또한 비즈니스용 Microsoft 365 앱의 책갈피를 잡고 비즈니스용 Microsoft 365 - 관리자 도움말을 책갈피로 [설정해야 합니다.](https://support.office.com/article/17d3ff3f-3601-466e-b5a1-482b31cfb791) [](https://blogs.office.com/2015/03/13/administer-on-the-go-with-the-updated-office-365-admin-app/)
  
## <a name="monitoring-microsoft-365-connectivity"></a>연결 Microsoft 365 모니터링

|모니터링 유형 |설명 |
|:-----|:-----|
|**새 끝점에 대한 Microsoft 365** <br/> |If you're [Managing Microsoft 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a), you'll want to receive notifications when we publish new endpoints, you can subscribe to our RSS feed using your favorite RSS reader. 다음은 를 통해 [구독하는 Outlook](https://go.microsoft.com/fwlink/p/?LinkId=532416) RSS 피드 업데이트를 전자 메일로 [보낼 수 있는 방법입니다.](https://go.microsoft.com/fwlink/p/?LinkId=532417)  <br/> |
|**이 System Center 사용하여 모니터링 Microsoft 365** <br/> |Microsoft System Center 사용하는 경우 Microsoft System Center [Operations Manager](https://www.microsoft.com/download/details.aspx?id=103379) 관리 팩을 다운로드하여 현재 Microsoft 365 모니터링을 시작할 Microsoft 365 있습니다. 자세한 지침은 관리 팩 작업 가이드를 참조하세요. <br/> |
|**Azure ExpressRoute** 의 상태 모니터링 <br/> |Microsoft 365 Azure ExpressRoute를 사용하여 Microsoft 365 연결하는 경우 azure 리소스 상태의 문제 해결 시간 단축뿐만 아니라 Microsoft 365 서비스 상태 대시보드를 모두 [](https://azure.microsoft.com/blog/reduce-troubleshooting-time-with-azure-resource-health/) 사용하고 있는 것이 좋습니다. <br/> |
|**AD FS와 Azure Active Directory Connect Health 사용** <br/> |단일 응용 Sign-On AD FS를 사용하는 Microsoft 365 Azure AD 커넥트 Health를 사용하여 AD FS 인프라를 [모니터링할 수 있습니다.](/azure/active-directory/hybrid/how-to-connect-health-adfs)  <br/> |
|**프로그래밍식 모니터링 Microsoft 365** <br/> |Microsoft 365 [관리 API에 대한 지침을 참조하세요.](/office/office-365-management-api/office-365-management-apis-overview)  <br/> |

다음의 간단한 링크를 사용할 수 있습니다. [https://aka.ms/monitorconnectivity365]()
  
## <a name="related-topics"></a>관련 항목

[서비스 Microsoft 365 Enterprise 응용 프로그램 구성](configure-services-and-applications.md)
  
[조직에서 조직에 대한 Microsoft 365 Enterprise](get-your-organization-ready-for-office-365.md)
  
[Microsoft 365의 네트워크 계획 및 성능 조정](network-planning-and-performance.md)
  
[Microsoft 365 환경과의 통합](microsoft-365-integration.md)
  
[끝점 Microsoft 365 관리](managing-office-365-endpoints.md)
