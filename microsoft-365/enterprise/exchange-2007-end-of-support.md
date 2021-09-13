---
title: Exchange 2007 지원 종료 로드맵
ms.author: dstrome
author: dstrome
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
ms.assetid: c3024358-326b-404e-9fe6-b618e54d977d
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 2007년 지원 종료 Exchange Server 옵션에 대해 알아보고 Microsoft 365, Office 365 또는 2016으로의 마이그레이션 계획을 Exchange 있습니다.
ms.openlocfilehash: d7e8f50118dab6fcb618273f5c28497c80d4a549
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218565"
---
# <a name="exchange-2007-end-of-support-roadmap"></a>Exchange 2007 지원 종료 로드맵

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

Exchange Server 2007년 4월에 지원이 종료됩니다. Exchange 2007에서 Microsoft 365, Office 365 또는 Exchange 2016으로 마이그레이션을 시작하지 않은 경우 이제 계획을 시작할 시간입니다.
  
## <a name="what-does-end-of-support-mean"></a>지원 *종료는 무엇을 의미하나요?*

Exchange Server Microsoft는 거의 모든 Microsoft 제품과 마찬가지로 새로운 기능, 버그 수정, 보안 수정 등 지원 수명 주기를 제공합니다. 이 수명 주기는 일반적으로 제품의 초기 릴리스부터 10년 동안 지속됩니다. 이 수명 주기의 끝을 제품의 지원 종료라고 합니다. 2007 Exchange 2017년 4월 11일 지원이 종료된 이후 Microsoft는 더 이상 다음을 제공하지 않습니다.
  
- 발생할 수 있는 문제에 대한 기술 지원
    
- 서버의 안정성과 사용 가능성에 영향을 줄 수 있는 문제에 대한 버그 수정
    
- 서버가 보안 위반에 취약해질 수 있는 취약점에 대한 보안 수정
    
- 표준 시간대 업데이트.
    
2007 Exchange 설치는 지원 종료 날짜 이후에도 계속 실행됩니다. 하지만 새 업데이트나 지원이 없는 경우 최대한 빨리 Exchange 마이그레이션하는 것이 좋습니다.
  
지원 종료에 Office 2007 서버에 대한 자세한 내용은 Plan [your upgrade from Office 2007 servers and products을 참조하십시오.](upgrade-from-office-2007-servers-and-products.md)
  
## <a name="what-are-my-options"></a>내 옵션은 무엇입니까?

다음을 수행할 수 있습니다.
  
- 전환, Microsoft 365 또는 하이브리드 마이그레이션을 사용하여 마이그레이션합니다.
    
- Exchange 2007 서버를 Exchange 서버의 최신 버전으로 마이그레이션합니다.
    
다음 섹션에서는 각 옵션을 보다 자세히 설명합니다.
  
### <a name="migrate-to-microsoft-365"></a>Microsoft 365로 마이그레이션

2007 2007 배포를 Microsoft 365 가장 쉽고 가장 간단한 옵션으로 전자 메일을 Exchange 있습니다. 마이그레이션을 Microsoft 365 10년 된 기술에서 다음과 같은 최첨단 기능으로 단일 홉을 만들 수 있습니다.
  
- 보존 정책, In-Place 및 소송 보존, eDiscovery 등의 규정 준수 기능
    
- Microsoft 365 그룹
    
- 중요 받은 편지함
    
- MyAnalytics
    
- 전자 메일, 일정, 연락처에 프로그래밍식 액세스용 REST API
    
Microsoft 365 기능 및 환경을 먼저 사용할 수 있으므로 사용자와 함께 바로 사용할 수 있습니다. 또한 다음에 대해 걱정할 필요가 없습니다.
  
- 하드웨어 구매 및 유지 관리
    
- 서버를 열과 식히기 위해 비용을 지불합니다.
    
- 보안, 제품 및 표준 시간대 수정을 최신으로 유지
    
- 규정 준수 요구 사항을 지원하기 위해 저장소 및 소프트웨어 유지 관리
    
- 새 버전의 업데이트로 Exchange. 이 Microsoft 365 항상 최신 버전의 Exchange.
    
#### <a name="how-should-i-migrate-to-microsoft-365"></a>마이그레이션하려면 어떻게 Microsoft 365?

몇 가지 마이그레이션 옵션이 있습니다. 다음과 같은 몇 가지를 고려해야 합니다.

- 이동해야 하는 시트 또는 사서함의 수입니다.
- 마이그레이션을 지속할 기간입니다.
- 마이그레이션 중에는 사내 설치와 프레미스 설치 Microsoft 365 원활하게 통합해야 하는지 여부

이 표에는 마이그레이션 옵션과 사용할 방법을 결정하는 가장 중요한 요소가 표시됩니다.
  

|**마이그레이션 옵션**|**조직 크기**|**기간**|
|:-----|:-----|:-----|
|단독형 마이그레이션  <br/> |시트 수가 150명 미만  <br/> |1주 이하  <br/> |
|미리 구성된 마이그레이션  <br/> |시트 수가 150명 이상인 경우  <br/> |몇 주  <br/> |
|전체 하이브리드 마이그레이션  <br/> |수 십만 명  <br/> |몇 개월 이상  <br/> |
   
다음 섹션에서는 이러한 방법에 대한 개요를 제공합니다. 자세한 내용은 마이그레이션 경로 [결정 을 참조합니다.](https://support.office.com/article/Decide-on-a-migration-path-0d4f2396-9cef-43b8-9bd6-306d01df1e27) 
  
#### <a name="cutover-migration"></a>단독형 마이그레이션

단일 마이그레이션에서는 모든 사서함, 메일 그룹, 연락처 등에서 미리 Microsoft 365 및 시간으로 마이그레이션합니다. 마이그레이션이 완료된 후 서버에 대한 Exchange 종료하고 단독으로 Microsoft 365 시작해야 합니다.
  
사서함이 많지 않은 소규모 조직에서는 마이그레이션을 빠르게 수행하고 Microsoft 365 방법의 일부를 처리하고 싶지 않은 소규모 조직에 매우 좋은 마이그레이션입니다. 하지만 1주일이 지난 후 완료해야 하며, 사용자가 자신의 프로필을 다시 구성해야 Outlook 합니다. 컷오버 마이그레이션에서는 최대 2,000개 사서함을 처리할 수 있지만 최대 150개 사서함을 마이그레이션하는 데 사용하는 것이 좋습니다. 더 많은 마이그레이션을 시도할 경우 기한이 되기 전에 모든 사서함을 전송할 시간이 지났을 수 있으며 IT 지원 직원이 사용자의 사서함을 다시 구성하는 데 도움이 되는 요청이 과도하게 Outlook.
  
컷오버 마이그레이션을 고려하고 있는 경우 다음을 고려해야 합니다.
  
- Microsoft 365 TCP 포트 443을 통해 Exchange Outlook 서버에 연결해야 합니다.
    
- 모든 On-premises 사서함은 모든 Microsoft 365.
    
- 사용자의 사서함에 대한 읽기 권한이 있는 사내 관리자 계정이 필요합니다.
    
- Exchange 사용할 2007 허용 도메인은 Microsoft 365 확인된 도메인으로 추가해야 합니다.
    
- 마이그레이션을 시작하는 시간과 완료 단계를 시작할 Microsoft 365 사서함과 Microsoft 365 주기적으로 동기화됩니다. 이렇게 하면 전자 메일이 전자 메일에 남아 있는 것을 걱정할 필요 없이 마이그레이션을 완료할 수 있습니다.
    
- 사용자는 해당 계정의 새 임시 Microsoft 365 받게 됩니다. 사용자가 처음으로 사서함에 로그인할 때 암호를 변경해야 합니다.
    
- 마이그레이션하는 각 Microsoft 365 사서함에 대한 Exchange Online 라이선스가 필요합니다.
    
- 사용자는 각 장치에서 새 Outlook 프로필을 설정하고 전자 메일을 다시 다운로드해야 합니다. 다운로드할 전자 메일의 Outlook 다를 수 있습니다. 자세한 내용은 오프라인으로 유지할 메일의 수 [변경을 참조하세요.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
컷오버 마이그레이션에 대한 자세한 내용은 다음을 참조하세요.
  
- [컷오버 전자 메일 마이그레이션에 대해 알아야 할 것](https://support.office.com/article/What-you-need-to-know-about-a-cutover-email-migration-to-Office-365-961978ef-f434-472d-a811-1801733869da)
    
- [전자 메일의 컷오버 마이그레이션 수행](https://support.office.com/article/Perform-a-cutover-migration-of-email-to-Office-365-9496e93c-1e59-41a8-9bb3-6e8df0cd81b4)
    
#### <a name="staged-migration"></a>미리 구성된 마이그레이션

단계적 마이그레이션에서는 수백 또는 수천 개의 사서함을 Microsoft 365 마이그레이션을 완료하는 데 1주일 이상이 걸릴 수 있으며, 공유 약속이 있는/약속이 있는 일정 정보와 같은 고급 하이브리드 마이그레이션 기능이 필요하지 않습니다.
  
단계적 마이그레이션은 사서함을 마이그레이션하는 데 더 많은 시간을 Microsoft 365 몇 주 이내에 마이그레이션을 완료할 계획인 조직에 매우 도움이 됩니다. 사서함을 일괄적으로 마이그레이션할 수 있습니다. 특정 시기에 마이그레이션되는 사서함의 수와 사서함을 제어할 수 있습니다. 예를 들어 동일한 부서에 있는 사용자의 사서함을 일괄 처리하여 모두 동시에 이동하는지 확인하게 할 수 있습니다. 또는 마지막 일괄 처리가 될 때까지 임원 사서함을 남길 수 있습니다. 컷오버 마이그레이션과 함께 사용자는 해당 프로필을 다시 Outlook 합니다.
  
단계적 마이그레이션을 수행하려는 경우 다음을 고려해야 합니다.
  
- Microsoft 365 TCP 포트 443을 통해 Exchange Outlook 서버에 연결해야 합니다.
    
- 사용자의 사서함에 대한 읽기 권한이 있는 사내 관리자 계정이 필요합니다.
    
- Exchange 사용할 2007 허용 도메인은 Microsoft 365 확인된 도메인으로 추가해야 합니다.
    
- 일괄 마이그레이션할 각 사서함의 전체 이름과 전자 메일 주소를 사용하여 CSV 파일을 만들어야 합니다. 또한 마이그레이션할 각 사서함에 대해 새 암호를 포함하고 각 사용자에게 해당 암호를 보내야 합니다. 새 사서함에 처음 로그인할 때 암호를 변경하라는 Microsoft 365 표시됩니다.
    
- 마이그레이션 일괄 처리를 시작하는 시간과 완료 단계를 시작할 Microsoft 365 일괄 처리에 포함된 Microsoft 365 사서함과 Microsoft 365 주기적으로 동기화합니다. 이렇게 하면 전자 메일이 전자 메일에 남아 있는 것을 걱정할 필요 없이 마이그레이션을 완료할 수 있습니다.
    
- 마이그레이션하는 각 Microsoft 365 사서함에 대한 Exchange Online 라이선스가 필요합니다.
    
- 사용자는 각 장치에서 새 Outlook 프로필을 설정하고 전자 메일을 다시 다운로드해야 합니다. 다운로드할 전자 메일의 Outlook 다를 수 있습니다. 자세한 내용은 오프라인으로 유지할 메일의 수 [변경을 참조하세요.](https://support.office.com/article/Change-how-much-mail-to-keep-offline-f3a1251c-6dd5-4208-aef9-7c8c9522d633?ui=en-US&amp;rs=en-US&amp;ad=US&amp;fromAR=1)
    
단계적 마이그레이션에 대한 자세한 내용은 다음을 참조하세요.
  
- [단계적 전자 메일 마이그레이션에 대해 알아야 할 것](https://support.office.com/article/What-you-need-to-know-about-a-staged-email-migration-to-Office-365-7e2c82be-5f3d-4e36-bc6b-e5b4d411e207)
    
- [전자 메일의 단계적 마이그레이션 수행](https://support.office.com/article/Perform-a-staged-migration-of-email-to-Office-365-83bc0b69-de47-4cc4-a57d-47e478e4894e)
    
#### <a name="full-hybrid"></a>전체 하이브리드

전체 하이브리드 마이그레이션에서 조직에는 수백, 최대 수만 개의 사서함이 있으며 일부 또는 모두를 사서함으로 Microsoft 365. 이러한 마이그레이션은 일반적으로 더 장기적이기 때문에 하이브리드 마이그레이션을 통해 다음을 할 수 있습니다.
  
- 프레미스 사용자에게 사용자에 대한 약속이 있는/약속 Microsoft 365 정보를 표시하는 경우도 마찬가지입니다.
    
- 전체 주소 목록을 참조하세요. 이 목록은 모든 전자 메일 주소 목록에 있는 받는 사람이 모두 포함된 Microsoft 365.
    
- 모든 Outlook Microsoft 365 모든 사용자에 대한 전체 받는 사람 속성을 볼 수 있습니다.
    
- TLS 및 인증서를 사용하여 Exchange 서버와 Microsoft 365 전자 메일 통신을 보호합니다.
    
- 다음을 지원하여 Exchange 서버 간에 전송된 Microsoft 365 내부로 처리합니다.
    
  - 내부 메시지를 대상으로 하는 전송 및 규정 준수 에이전트가 적절히 평가하고 처리해야 합니다.
    
  - 스팸 방지 필터를 무시합니다.
    
전체 하이브리드 마이그레이션은 몇 개월 이상 하이브리드 구성을 유지해야 하는 조직에 가장 좋습니다. 이 섹션의 앞부분에 나와 있는 기능과 디렉터리 동기화, 보다 나은 통합 규정 준수 기능 및 온라인 사서함 이동을 사용하여 사서함을 Microsoft 365 기능을 사용할 수 있습니다. Microsoft 365 조직의 확장이 됩니다.
  
전체 하이브리드 마이그레이션을 고려하고 있는 경우 다음을 고려해야 합니다.
  
- 전체 하이브리드 마이그레이션은 모든 유형의 조직에 적합하지 않습니다. 전체 하이브리드 마이그레이션의 복잡성으로 인해 사서함이 수백 개 미만인 조직에서는 일반적으로 사서함을 설정하는 데 필요한 노력과 비용을 정당화하는 이점을 볼 수 없습니다. 조직과 같은 경우 대신에 컷오버 또는 단계적 마이그레이션을 고려하는 것이 좋습니다.
    
- "하이브리드 서버"로 사용하려면 Exchange 2013 서버를 하나 이상 Exchange 2007 조직에 배포해야 합니다. 이 서버는 Microsoft 365 2007 서버를 Exchange 통신합니다.
    
- Microsoft 365 TCP 포트 443을 통해 Outlook "하이브리드 서버"에 연결해야 합니다.
    
- Azure AD(Azure Active Directory)를 사용하여 디렉터리 동기화를 설정해야 커넥트 서버와 Microsoft 365.
    
- 사용자는 로컬 네트워크에 로그인할 때와 동일한 사용자 Microsoft 365 암호를 사용하여 자신의 Microsoft 365 사서함에 로그인할 수 있습니다. (이 기능을 사용하려면 암호 커넥트 및/또는 Active Directory Federation Services를 사용하는 Azure AD 계정이 필요합니다.)
    
- 마이그레이션하는 각 Microsoft 365 사서함에 대한 Exchange Online 라이선스가 필요합니다.
    
- 사용자는 대부분의 장치에서 새 Outlook 프로필을 설정할 필요가 없습니다. 그러나 일부 이전 Android 휴대폰에는 새 프로필이 필요할 수 있습니다. 사용자는 전자 메일을 다시 다운로드할 수 없습니다.
    
전체 하이브리드 마이그레이션이 적합한 경우 마이그레이션에 도움이 되는 다음 리소스를 참조합니다.
  
- [Exchange 배포 도우미](/exchange/exchange-deployment-assistant)
    
- [Exchange Server 하이브리드 배포](/exchange/exchange-hybrid)
    
- [하이브리드 구성 마법사](/exchange/hybrid-configuration-wizard)
    
- [하이브리드 구성 마법사 FAQ](/exchange/hybrid-configuration-wizard-faqs)
    
- [하이브리드 배포 필수 구성 요소](/exchange/hybrid-deployment-prerequisites)
    
### <a name="migrate-to-a-newer-version-of-exchange-server"></a>최신 버전의 2016으로 Exchange Server

사용자 환경으로 마이그레이션하여 최고의 가치와 사용자 환경을 얻을 수 Microsoft 365. 그러나 일부 조직에서는 전자 메일을 전자 메일을 사내에 보관해야 한다는 것을 알고 있습니다. 이는 데이터가 다른 국가 또는 유사한 데이터 센터에 저장되지 못하게 하는 규정 요구 사항 때문에일 수 있습니다. 전자 메일을 Exchange 2007 환경을 Exchange 2010, Exchange 2013 또는 Exchange 2016으로 마이그레이션할 수 있습니다.
  
마이그레이션할 수 없는 경우 Microsoft 365 2016으로 마이그레이션하는 Exchange 좋습니다. Exchange 2016에는 이전 릴리스의 모든 기능이 Exchange. 또한 일부 기능은 Microsoft 365 사용 가능한 환경과 가장 Microsoft 365. 누락된 몇 가지 사항만 확인해 보아야 합니다.
  
|**Exchange 릴리스**|**기능**|
|:-----|:-----|
|Exchange 2010  <br/> | Role-Based 액세스 제어(ACL이 없는 사용 권한)  <br/>  Outlook Web App 사서함 정책  <br/>  조직 간에 약속이 있는/약속이 있는 일정을 공유하고 일정을 위임하는 능력  <br/> |
|Exchange 2013  <br/> | *2010 및 Exchange 기능*  <br/>  서버 역할 수를 3개로 줄인 간소화된 아키텍처(사서함, 클라이언트 액세스, Edge 전송)  <br/>  중요한 정보가 누출되는 문제를 방지하는 데 도움이 되는 DLP(데이터 손실 방지 정책)  <br/>  향상된 Outlook Web App 환경  <br/> |
|Exchange 2016  <br/> | *2013 및 Exchange 기능*  <br/>  사서함 및 Edge 전송으로의 추가 간소화된 서버 역할  <br/>  향상된 DLP와 통합된 SharePoint  <br/>  향상된 데이터베이스 탄력성  <br/>  온라인 문서 공동 작업 |
   
#### <a name="which-version-should-i-migrate-to"></a>어떤 버전으로 마이그레이션해야 하나요?

처음에는 2016에서 2016으로 마이그레이션할 것으로 Exchange 좋습니다. 그런 다음 다음 정보를 사용하여 가정을 확인하거나 2016년 Exchange 배제합니다. 어떤 이유로 Exchange 2016으로 마이그레이션할 수 없는 경우 Exchange 2013과 같은 프로세스를 진행합니다.
  
|**고려 사항**|**추가 정보**|
|:-----|:-----|
|지원 종료 날짜  <br/> | Exchange 2007과 마찬가지로 각 Exchange 자체 지원 종료 날짜가 있습니다.  <br/> *Exchange 2010* - 2020년 1월  <br/> *Exchange 2013년 4월* -  <br/> *Exchange 2016년 10월* - 2025년 10월  <br/>  지원이 끝나면 더 빨리 다른 마이그레이션을 수행해야 합니다.<br/> |
|2010 및 Exchange 마이그레이션 경로입니다.  <br/> |다음은 2010 또는 Exchange 2013으로 마이그레이션하는 Exchange 단계입니다.  <br/> - Exchange 2010 또는 2013을 기존 Exchange 조직에 설치합니다. <br/>- 서비스 및 기타 인프라를 2010 Exchange 2013으로 이동<br/>- 사서함 및 공용 폴더를 Exchange 2010 또는 2013으로 이동합니다.<br/>- 2007 서버의 Exchange 해제합니다. |
|2016년 Exchange 마이그레이션 경로  <br/> |2016으로 마이그레이션하는 일반적인 단계는 Exchange 있습니다.  <br/> - Exchange 2013을 기존 Exchange 2007 조직에 설치합니다.<br/>- 2013으로 서비스 및 기타 인프라를 Exchange.<br/>- 사서함 및 공용 폴더를 Exchange 2013으로 이동합니다.<br/>- 2007 서버의 Exchange 해제합니다.<br/>- 기존 Exchange 2013 조직에 Exchange 설치합니다.<br/>- 사서함, 공용 폴더, 서비스 및 기타 인프라를 Exchange 2016으로 이동합니다(순서는 중요하지 않습니다). 2013 서버의 Exchange 해제합니다.<br/><br/> **참고:** 2013 Exchange 2016으로 Exchange 마이그레이션하는 것은 간단합니다. 두 버전은 하드웨어 요구 사항이 거의 동일하며 이러한 버전은 매우 호환됩니다. 따라서 Exchange 2013을 위해 구입한 서버를 다시 Exchange 2016을 설치할 수 있습니다. 온라인 사서함 이동의 경우 대부분의 사용자는 사서함이 서버에서 이동된 후 2016년 8월을 통해 다시 Exchange 않습니다.           |
|버전 동시 사용  <br/> | 마이그레이션할 때...  <br/> **Exchange 2016:** Exchange 2016은 Exchange 서버를 포함하는 조직에 설치할 수 없습니다. 먼저 Exchange 2010 또는 2013으로 마이그레이션해야 합니다(Exchange 2013에서는 Exchange 2007 서버를 모두 제거한 다음 Exchange 2016으로 마이그레이션하는 것이 좋습니다.  <br/> **Exchange 2010 또는 Exchange 2013:** 기존 Exchange 2010 또는 Exchange 2013을 Exchange 수 있습니다. 이렇게 하면 하나 이상의 2010 또는 Exchange 서버를 설치하고 마이그레이션을 수행할 수 있습니다.  <br/> |
|서버 하드웨어  <br/> | 서버 하드웨어 요구 사항은 2007년 Exchange 변경되었습니다. 하드웨어가 호환되는지 확인 자세한 내용은 다음을 참조하세요.  <br/> [Exchange 2016 시스템 요구 사항](/Exchange/plan-and-deploy/system-requirements) <br/> [Exchange 2013 시스템 요구 사항](/exchange/exchange-2013-system-requirements-exchange-2013-help) <br/> [Exchange 2010 시스템 요구 사항](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) <br/>  새 서버의 컴퓨팅 성능과 저장소 용량이 Exchange 크게 향상되어 동일한 수의 사서함을 지원하기 위해 더 적은 수의 서버가 필요할 수 있습니다.  <br/> |
|운영 체제 버전  <br/> | 각 버전에 대해 지원되는 최소 운영 체제 버전은 다음입니다.  <br/> **Exchange -** Windows Server 2012  <br/> **Exchange 2013** - Windows Server 2008 R2 SP1  <br/> **Exchange -** Windows Server 2008 SP2  <br/>  운영 체제 지원에 대한 자세한 내용은 Exchange [매트릭스를 참조하십시오.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Active Directory 포리스트 기능 수준  <br/> | 각 버전에 대해 지원되는 최소 Active Directory 포리스트 기능 수준은 다음입니다.  <br/> **Exchange 2016** Windows Server 2008 R2 SP1  <br/> **Exchange 2013** Windows Server 2003  <br/> **Exchange 2010** Windows Server 2003  <br/>  포리스트 기능 수준 지원에 대한 자세한 내용은 Exchange [매트릭스를 참조하십시오.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
|Office 클라이언트 버전  <br/> | 각 버전에 대해 Office 지원되는 최소 클라이언트 버전은 다음입니다.  <br/> **Exchange 2016** - Office 2010(최신 업데이트 사용)  <br/> **Exchange 2013** - Office 2007 SP3  <br/> **Exchange 2010** - Office 2003  <br/>  클라이언트 지원에 대한 Office 자세한 내용은 Exchange [매트릭스를 참조하십시오.](/Exchange/plan-and-deploy/supportability-matrix)  <br/> |
   
#### <a name="how-do-i-migrate"></a>마이그레이션 방법

전자 메일을 사내에 보관하기로 결정한 경우 다음 리소스를 사용하여 마이그레이션에 도움을 줄 수 있습니다.
  
- [Exchange 배포 도우미](/exchange/exchange-deployment-assistant)
    
- Exchange [2016,](/Exchange/plan-and-deploy/active-directory/ad-schema-changes) [2013,](/exchange/exchange-2013-active-directory-schema-changes-exchange-2013-help) [2010에](https://www.microsoft.com/download/en/details.aspx?displaylang=en&amp;id=5401) 대한 Active Directory schema changes
    
- Exchange, [2013,](/Exchange/plan-and-deploy/system-requirements) [2010에](/previous-versions/office/exchange-server-2010/aa996719(v=exchg.141)) 대한 시스템 요구 사항 [](/exchange/exchange-2013-system-requirements-exchange-2013-help)
    
- Exchange [2016,](/Exchange/plan-and-deploy/prerequisites) [2013, 2010의](/exchange/exchange-2013-prerequisites-exchange-2013-help)선행 준비 [](/previous-versions/office/exchange-server-2010/bb691354(v=exchg.141))
    
## <a name="get-help"></a>도움말 보기

사용자 계정으로 마이그레이션하는 Microsoft 365 Microsoft FastTrack 서비스를 사용할 수 있습니다. FastTrack 가능한 한 원활하게 마이그레이션할 수 있도록 모범 사례Microsoft 365 도구 및 리소스를 제공합니다. 무엇보다 지원 엔지니어는 계획 및 디자인부터 마지막 사서함 마이그레이션까지 마이그레이션을 진행하는 방법을 단계화합니다. 자세한 내용은 FastTrack [Microsoft](https://fasttrack.microsoft.com/)FastTrack.
  
Microsoft 365 마이그레이션하는 동안 문제가 발생하여 FastTrack 또는 최신 버전의 Exchange Server 마이그레이션을 사용하지 않는 경우 도움이 될 것입니다. 다음은 사용할 수 있는 몇 가지 리소스입니다.
  
- [기술 커뮤니티](https://social.technet.microsoft.com/Forums/office/home?category=exchangeserver)
    
- [고객 지원](https://support.microsoft.com/gp/support-options-for-business)
    
## <a name="related-topics"></a>관련 항목

[2007 서버 및 클라이언트를 업그레이드하는 Office 리소스](upgrade-from-office-2007-servers-and-products.md)