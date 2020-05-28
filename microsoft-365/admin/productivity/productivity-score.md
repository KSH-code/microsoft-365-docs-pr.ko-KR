---
title: Microsoft 생산성 점수
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 생산성 점수 개요
ms.openlocfilehash: 52a520e36c6b121984aef650ffba1867f4d3e8c9
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399185"
---
# <a name="microsoft-productivity-score-preview"></a>Microsoft 생산성 점수 (미리 보기)

생산성 점수 조직은 조직이 Microsoft 365를 사용 하는 방법 및 사용자가 지 원하는 기술 환경에 대 한 정보를 활용 하 여 작업 수행 방식을 변환할 수 있도록 합니다. 점수는 직원 및 기술 경험 측정과 조직의 성과를 반영 하 고 사용자와 같은 조직과 점수를 비교 합니다.

점수에는 다음이 포함 됩니다.

- **메트릭** -사용자가 Microsoft 365 제품을 사용 하 여 플랫폼 공동 작업, 통신 및 작업을 수행 하는 방법을 확인 하는 데 도움을 줍니다.
- 직원 생산성 및 만족도 개선을 위한 기회를 식별 하는 데 도움이 되는 데이터 **에 대 한 정보를** 소개 합니다.
- 조직의 사용자가 Microsoft 365 제품을 효율적으로 사용 하 여 모든 사용자가 최상의 작업을 수행할 수 있도록 하기 위해 수행할 수 있는 **권장 작업** 입니다.

Microsoft는 다음과 같은 두 가지 분야에서 데이터, 통찰력 및 권장 사항을 제공 합니다. 

- **직원 환경:** 여기서는 사용자가 콘텐츠를 공동으로 작업 하는 방법, Microsoft 365 제품을 사용 하 여 통신 하는 방법, 플랫폼 간에 Microsoft 365을 사용 하는지 여부를 측정 합니다. 

    사용자는 온라인으로 공동 작업을 하는 경우 시간을 절약 하기 때문에 이러한 정보를 제공 합니다. 모든 장치에서 자유롭게 작업할 수 있게 되 면 생산성과 만족도가 향상 됩니다. 융통성 있는 방식으로 통신할 수 있으면 보다 효율적이 고 양식의 관계가 향상 되며 조직이 보다 통합 됩니다. 증거는 [Forrester report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)를 참조 하십시오.

- **기술 환경:** 생산성은 안정성 및 안정적인 기술과 Microsoft 365을 효율적으로 사용 하는 방식에 따라 달라 집니다. Microsoft는 장치 설치 및 시작 시간에 대 한 정보를 제공 하 고 사용자에 게 조직에 대해 마이크로소프트 365 네트워크 연결 정보를 제공할 수 있도록 하는 끝점 분석을 제공 합니다.

끝점 분석에 대 한 자세한 내용은 [네트워크 연결 개요](https://docs.microsoft.com/office365/enterprise/office-365-networking-overview)를 참조 하세요.
  

## <a name="how-the-score-is-calculated"></a>점수가 계산 되는 방식

생산성 점수가 직원 및 기술 경험 범주의 조합 점수를 기반으로 합니다. 각 범주는 가중치에 따라 동일 하며 범주별로 총 100 포인트입니다. 생산성 점수에 사용할 수 있는 총 점수는 500입니다.

### <a name="score-categories"></a>점수 범주 

- 콘텐츠 공동 작업 (100 포인트)
- 통신 (100 지점)
- 모바일 기능 (100 지점)
- 끝점 분석 (100 포인트)
- 네트워크 연결 (100 포인트)
- **총 가능 = 500 포인트**
 
 각 범주에서 사용자가 Microsoft 365 제품을 사용 하 여 플랫폼 공동 작업, 통신 및 작업을 수행 하는 방법에 대 한 지표를 나타내는 주요 작업의 패턴을 식별 합니다. 여기서는 28 일 및 180 일 동안의 주요 활동 보기를 제공 합니다. 또한 점수 계산에 포함 되지 않는 지원 메트릭스를 제공 하지만 기본 동작과 드라이브 변경에 대해 수행할 수 있는 설정을 확인 하는 데 도움이 되는 것이 중요 합니다.

### <a name="products-included-in-productivity-score"></a>생산성 점수에 포함 된 제품 

생산성 점수에는 Exchange, SharePoint, OneDrive, 팀, Word, Excel, PowerPoint, OneNote, Outlook, Yammer 및 Skype의 데이터가 포함 됩니다.

점수는 매일 업데이트 되며 최근 28 일에서 완료 된 사용자 작업은 현재 날짜를 포함 하 여 180 일 이내에 반영 됩니다.


## <a name="pre-requisites"></a>필수 구성 요소 

직원 경험 데이터를 가져오려면 비즈니스용 Microsoft 365 for business 또는 Office 365이 필요 하며, 다중 테 넌 트 클라우드 서비스를 사용 해야 합니다. 테 넌 트에 대 한 끝점 분석 데이터를 가져오려면 구독에 Microsoft Intune을 추가 해야 합니다. Intune은 장치 및 앱을 관리 하 여 조직의 데이터를 보호 하는 데 도움이 됩니다.       Intune을 사용 하는 경우 Intune 환경 내에서 끝점 분석을 켤 수 있습니다. 자세한 내용은 Microsoft Intune을 참고 하세요. 

조직의 생산성 점수를 확인 하려면 다음 역할 중 하나가 있어야 합니다. 

- 전역 관리자 
- Exchange 관리자
- SharePoint 관리자 
- 비즈니스용 Skype 관리자 
- Teams 관리자 
- 전역 읽기 권한자 
- 보고서 구독자 

**Reports**  >  **생산성 점수가**보고 되 면 Microsoft 365 관리자 홈의 환경에 액세스할 수 있습니다.

## <a name="interpreting-productivity-score"></a>생산성 점수 해석 

생산성 점수 홈 페이지에는 각 범주에 대 한 주요 통찰력과 함께 총 점수 및 점수 기록이 표시 됩니다.

![생산성 점수 홈 페이지](../../media/pslanding.png)

**점수** 는 포인트 (분자)와 최대 가능한 점수 (분모)를 볼 수 있도록 포인트 단위 뿐만 아니라 백분율 값으로 표시 됩니다.

**피어 벤치 마크** 를 사용 하 여 사용자와 같은 조직과 점수를 비교할 수 있습니다. 직원 경험 범주의 경우 피어 벤치 마크 측정값은 유사한 조직 집합 내의 측정값 평균으로 계산 됩니다. 이 집합은 사용자의 사용이 허가 된 사용자, 라이선스 유형, 산업 및 Microsoft 365을 사용 하 여 tenure와 비슷한 수의 조직으로 구성 됩니다. 

끝점 분석 피어 벤치 마크에는 모든 테 넌 트에서 집계 된 중앙값을 기반으로 하는 장치 시작 성능 및 권장 소프트웨어 구성에 대 한 대상이 포함 됩니다.

네트워크 연결의 경우 권장 되는 벤치 마크는 80 포인트입니다.

**점수 분석** 섹션에서는 직원 및 기술 경력 분야의 벤치 마크에 대 한 생산성 성과를 분석 하 여 보여 줍니다.

점수 기록에서는 지난 6 개월 동안 각 범주의 점수가 변경 된 방식을 표시 합니다.

**직원 환경** 및 **기술 경력** 영역에는 해당 영역의 범주에 대 한 기본 정보가 포함 되어 있습니다. 각 범주를 클릭 하 여 세부 정보를 확인할 수 있습니다.

## <a name="category-details-pages"></a>범주 세부 정보 페이지

각 범주 세부 정보 페이지에는 기본 통찰력과 지원 메트릭 및 조직에서 변경을 수행 하기 위해 수행할 수 있는 관련 연구 및 작업이 표시 됩니다. 조사에서는 각 범주에 대 한 기본 정보를 통한 중요 성과 근거를 지원 합니다. 자세한 내용은 [Forrester report를 참조](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)하세요.

### <a name="content-collaboration-details"></a>콘텐츠 공동 작업 세부 정보

콘텐츠 공동 작업에 대 한 주요 이해는 온라인에서 만들고, 읽고, 공동 작업을 수행 (편집 및 공유) 하는 사용자 수입니다. 조사에서는 사용자가 온라인 파일을 사용 하 여 공동 작업을 수행 하는 경우 각 사용자가 평균적으로 100 분 또는 약 2 시간을 저장 하므로 이러한 조치는 중요 합니다.

콘텐츠 공동 작업은 Office 파일을 작성 하 고 공유 하는 한 명의 사용자로 정의 하 고, 하나 이상의 다른 사용자가 편집 합니다. 

독자: OneDrive 또는 SharePoint에서 온라인 파일을 액세스 하거나 다운로드 하는 사용자입니다.

**작성자:** 온라인 OneDrive 또는 SharePoint 파일을 생성, 수정, 업로드, 동기화, 체크 인, 복사 또는 이동 하는 사용자입니다.

협력자: OneDrive 또는 SharePoint를 사용 하 여 온라인 파일로 공동 작업 하는 사용자입니다. 두 사용자가 해당 사용자가 온라인 Word, Excel, PowerPoint, OneNote 또는 PDF 클라우드 문서를 만든 후 28 일 이내에 공동 작업을 수행 하는 경우

공동 작업용으로 고려 되는 파일 형식은 Word, Excel, PowerPoint, OneNote 및 PDF 파일입니다.

온라인 파일 공동 작업에는 빠르게 시작 되 고 최신 소프트웨어를 제공 하 고 Microsoft 365에 연결 되는 안정적인 장치가 필요 하기 때문에 조직의 장치에 대 한 정보 및 네트워크 연결에 대 한 자세한 내용은 시작 시간을 설명 합니다.

### <a name="communication-details"></a>통신 정보

통신에 대 한 주요 정보는 조직에서 전자 메일, 채팅 및 커뮤니티 게시물을 사용 하 여 정보를 교환 하는 빈도입니다. 이러한 통찰력은 사용자가 다양 한 실시간 통신 도구를 사용할 때 가장 효율적으로 사용할 수 있는 통신 모드를 선택할 수 있을 뿐만 아니라 여러 office 위치에서 관계를 개발 하는 데 도움이 되는 채팅 및 커뮤니티와 같은 도구를 제공 하기 때문에 중요 합니다.

### <a name="mobility-details"></a>모바일 기능 세부 정보

모바일 기능에 대 한 주요 이해는 파일에 액세스 하 고 여러 플랫폼에서 전자 메일 및 채팅을 사용 하는 사용자 수입니다. 영업 역할, 상급 관리자, 컨설턴트 및 사무실에서 작업을 수행 해야 하는 사용자는 업무를 진행 하기 위해 원하는 장치에서 어떤 위치에서 든 작업을 수행할 수 있어야 합니다. 이러한 작업 자가 향상 된 기능은 크게 영향을 받습니다. 

Microsoft는 데스크톱, 모바일 및 웹을 비롯 하 여 둘 이상의 플랫폼에서 적어도 한 대의 마이크로소프트 365 생산성 앱을 사용 하는 사용자의 백분율 및 절대 수를 측정 합니다. 측정 되는 생산성 앱은 Outlook, 팀, Word, Excel, PowerPoint, OneNote, Yammer 및 Skype입니다. 사용자에 게 측정 해야 하는 enterprise, Exchange, Yammer, Skype 또는 팀 라이선스에 대 한 Microsoft 365 앱이 있어야 합니다. 

## <a name="we-want-to-hear-from-you"></a>사용자의 의견을 듣고 싶습니다.

생산성 점수에 대 한 생각과 의견을 개선 하는 방법에 대 한 의견을 공유 하세요. 제품 내 **사용자 의견** 섹션을 사용 하거나 ProductivityScorePreview@service.microsoft.com의 생산성 점수 팀에 연락 합니다.