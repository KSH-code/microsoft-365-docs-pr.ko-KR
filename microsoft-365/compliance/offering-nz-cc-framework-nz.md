---
title: 새로운 뉴질랜드 정부 클라우드 컴퓨팅 보안 및 개인 정보 고려 사항
description: Microsoft NZ는 새로운 뉴질랜드 클라우드 컴퓨팅 프레임 워크에 게시 된 질문을 해결 합니다.
keywords: Microsoft 365, 규정 준수, 제안
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: cbf118d918dd5c3bc922fbea157fb56a709fad66
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065803"
---
# <a name="new-zealand-government-cloud-computing-security-and-privacy-considerations"></a>새로운 뉴질랜드 정부 클라우드 컴퓨팅 보안 및 개인 정보 고려 사항

## <a name="new-zealand-government-cloud-computing-security-and-privacy-overview"></a>새로운 뉴질랜드 정부 클라우드 컴퓨팅 보안 및 개인 정보 보호 개요

2015 년 10 월에 새로운 뉴질랜드 정부 endorsed은 공용 섹터 전체에서 정보 기술을 사용 하 여 "클라우드 최초" 정책을 reaffirmed 하는 수정 된 모든 정부 후 전략을가지고 있습니다. 수정 된 전략에는 NZ 정부 (GCIO)의 권위에 따라 개발 되 고 구현 된 "클라우드 컴퓨팅 위험 및 보증 프레임 워크"가 유지 됩니다.

정부에는 클라우드 서비스를 평가 하 고 채택할 때 모든 새 뉴질랜드 State 서비스 기관이이 프레임 워크 내에서 작동 하는 것으로 예상 됩니다. "클라우드 컴퓨팅에 대 한 요구 사항"은 정부의 클라우드 정책 내역에 대 한 개요와 함께 클라우드 서비스를 채택할 때 어떤 기관이 수행 해야 할 작업을 간략하게 설명 합니다.

NZ 정부 기관에서 잠재적 클라우드 솔루션에 대 한 일관성 있고 강력 하 게 주의을 수행 하도록 지원 하기 위해 GCIO는 "클라우드 컴퓨팅: 정보 보안 및 개인 정보 고려 사항" ("클라우드 컴퓨팅 ISPC")을 게시 했습니다. 이 문서에는 데이터 소유권, 개인 정보, 보안, 거 버 넌 스, 데이터 무결성, 가용성 및 사건 대응 및 관리에 초점을 맞춘 100 개 이상의 질문이 포함 되어 있습니다. "클라우드 컴퓨팅 IPSC"는 클라우드 서비스 공급자가 공식적인 준수를 시연 해야 하는 NZ 정부 표준을 정의 하지 않습니다. 그러나 문서에서 설정 된 많은 질문은 클라우드 서비스 공급자가 광범위 한 관련 표준을 준수 하는 방식을 이해 하는 것이 중요 합니다.

Microsoft 및 뉴질랜드 정부 클라우드 컴퓨팅 보안 및 개인 정보 보호 고려 사항

기관에서 Microsoft enterprise 클라우드 서비스의 분석과 평가를 수행 하는 데 도움을 주기 위해 microsoft cloud services가 인증 되는 표준에 연결 하 여 해당 엔터프라이즈 클라우드 서비스가 "클라우드 컴퓨팅 ISPC"에서 설정한 질문을 해결 하는 방법을 보여 주는 일련의 문서를 만들었습니다. 이러한 인증은 개인 정보 보호 및 보안 위험을 효과적으로 완화 하 고 데이터 소유권 관련 문제를 해결 하기 위해 클라우드 서비스가 디자인 되 고 구축 되 고 운영 된다는 것을 Microsoft가 제공 하는 방식에 따라 결정 됩니다.

Azure 보안 및 준수 청사진을 사용 하 여 NZ CC Framework 배포를 가속화 하는 방법을 알아봅니다. [NZ 참조 프레임 워크에 azure 응답 다운로드](https://gallery.technet.microsoft.com/Response-to-GCIO-Cloud-e117bbb9)

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 범위 내 클라우드 서비스

- [Azure 및 Azure Government](https://aka.ms/AzureCompliance)
- [Dynamics 365](https://aka.ms/d365-compliance-list)
- Intune
- 독립형 서비스 혹은 Office 365에 브랜딩된 플랜 또는 제품군에 포함된 형태로서의 Power BI 클라우드 서비스
- [Office 365](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- Exchange Online, SharePoint Online 및 비즈니스용 Skype Online Microsoft NZ는 GCIO 팀과 협력 하 여 Exchange Online에 대 한 참조 아키텍처를 개발 하 고 백서 [Office 365: seemail And Reference architecture](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) 에 설명 된 전자 메일을 통합 했습니다.

## <a name="frequently-asked-questions"></a>자주 묻는 질문

**프레임 워크를 적용할 사람**

GCIO 요구 사항이 적용 되는 조직 (공용 및 비공용 서비스 부서, 20 개의 학구 상태 보드 및 일곱 개의 Crown 엔터티)이 클라우드 서비스 사용을 결정할 때 프레임 워크를 따라야 합니다.

**해당 ICT 시스템의 인증 프로세스에서이 프레임 워크에 대 한 Microsoft의 응답을 에이전시에서 사용할 수 있나요?**

[새 뉴질랜드 정보 보안 설명서](https://go.microsoft.com/fwlink/p/?linkid=2099496)에서 해당 ICT 시스템의 인증 및 인정을 수행 하기 위해 에이전시가 필요한 경우에는 이러한 반응을 분석의 일부로 사용할 수 있습니다.

## <a name="resources"></a>리소스

- [Offshore hosted Office 생산성 서비스에 대 한 보안 요구 사항: Office 365에 대 한 준수 가이드](https://aka.ms/o365-gcio-conformance-guidance)
- [뉴질랜드 보안 및 개인 정보 요구 사항의 맥락에서 Microsoft Azure 준수](https://aka.ms/azurecompliancenewzealand)
- [NZ 정부 ICT 전략 2015](https://www.ict.govt.nz/strategy-and-action-plan/strategy/)
- [클라우드 컴퓨팅을 위한 NZ 정부 요구 사항](https://aka.ms/NZ-Cloud-Requirements)
- [클라우드 컴퓨팅: 정보 보안 및 개인 정보 보호 고려 사항 (ISPC)](https://www.digital.govt.nz/standards-and-guidance/technology-and-architecture/cloud-services/)
- [Microsoft 온라인 서비스 사용 약관](https://aka.ms/Online-Services-Terms)
- [Office 365: SEEMail 통합 및 참조 아키텍처](https://download.microsoft.com/download/8/5/9/859CDCEE-D293-47D8-9B6A-670B108B48E1/Microsoft_Office_365_white_paper_EN_US.pdf) (클라우드 서비스 채택에 대 한 추가 Microsoft NZ 지침)
- [Microsoft 보안 센터에 대한 규정 준수](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="microsoft-responses-to-cloud-computing-ipsc"></a>' Cloud 컴퓨팅 IPSC '에 대 한 Microsoft 응답

- [Azure](https://aka.ms/Azure-NZ-response)
- [Dynamics 365](https://aka.ms/d365-nz-response)
- [Intune](https://aka.ms/Intune-NZ-response)
- [Office 365](https://aka.ms/O365-NZ-Response)
- [Power BI](https://download.microsoft.com/download/5/1/7/51726B9B-2E76-49C4-9D4F-A36BF025CB93/Response-to-GCIO-105-questions-Power-BI.pdf)
