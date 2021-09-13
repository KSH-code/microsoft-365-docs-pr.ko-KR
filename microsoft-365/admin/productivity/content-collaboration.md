---
title: Microsoft 생산성 점수 - 콘텐츠 공동 작업
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: 콘텐츠 공동 작업의 세부 정보 - 사람들은 생산성 점수를 경험합니다.
ms.openlocfilehash: fa4e84f0cf454e28cd773292f2a4065cb1252acf
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186907"
---
# <a name="content-collaboration--people-experiences"></a>콘텐츠 공동 작업 - 사람 환경

생산성 점수는 조직의 디지털 변환 여정에 대한 인사이트를 Microsoft 365 지원하는 기술 환경을 제공합니다. 조직의 점수는 사용자 및 기술 환경 측정값을 반영하며 사용자와 비슷한 조직의 벤치마크와 비교할 수 있습니다. 콘텐츠 공동 작업 범주는 사람들이 경험하는 측정의 일부입니다. 자세한 내용은 생산성 점수 개요를 [확인하고](productivity-score.md) Microsoft의 개인 정보 [취급 방침을 참조하세요.](https://privacy.microsoft.com/privacystatement)

## <a name="prerequisites"></a>필수 구성 요소

콘텐츠 공동 작업 인사이트를 시작하려면 조직의 사용자들이 다음에 대한 라이선스를 부여해야 합니다.

- 비즈니스용 OneDrive
- SharePoint
- Exchange Online

자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](../manage/assign-licenses-to-users.md)

 사용자가 지난 28일 동안 적어도 한 번 이상 위의 제품에서 활동한 후 인사이트를 볼 수 있습니다.

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>조직에서 콘텐츠 공동&#39;점수가 중요한 이유

디지털 변환의 주요 측면은 사람들이 파일에서 공동 작업하는 방식입니다. 콘텐츠의 Microsoft 365 모든 위치에서 다른 사용자와 콘텐츠에 액세스하고, 만들고, 수정하고, 공동 작업을 할 수 있습니다. 연구에 따르면 온라인 파일로 공동 작업을 할 때 각 사용자가 일주일에 평균 100분을 절약할 수 있습니다.

## <a name="how-we-calculate-the-content-collaboration-score"></a>콘텐츠 공동 작업 점수를 계산하는 방법

조직에서 콘텐츠 공동 작업의 주요 메트릭을 포함하는 기본 인사이트를 제공합니다. 그런 다음 아래 자세히 설명된 점수 프레임워크를 이러한 메트릭에 사용하여 조직의 점수를 계산합니다.

> [!NOTE]
> 2021년 4월 22일, 공동 작업자 메트릭 계산 방법을 변경했습니다. 이는 기본 [정보,](#primary-insight)파일 [](#number-of-files-collaborated-on)공동 작업 정보 및 콘텐츠 공동 작업 점수가 측정되는 방식에 영향을 미치게 됩니다. 이러한 변경으로 Microsoft 및 기타 타사 응용 프로그램의 비인적 에이전트(또는 봇)의 데이터 노이즈를 줄여 더 정확하고 실행 가능한 점수를 얻을 수 있습니다.

### <a name="primary-insight"></a>기본 인사이트

Microsoft OneDrive 및 비즈니스용 SharePoint 사용하여 여러 장치 및 응용 프로그램에서 개인 및 공유 콘텐츠를 Microsoft 365 쉽게 만들고, 읽고, 검색할 수 있습니다. 또한 사용자가 콘텐츠를 안전하게 공유하고 공동 작업할 수 있습니다. 기본 인사이트에는 사용자 및 개인 정보를 사용할 수 있는 비즈니스용 OneDrive SharePoint. 또한 콘텐츠 및 콘텐츠에 저장된 콘텐츠를 읽고 만들고 공동 작업하는 사용자 수에 대한 세부 비즈니스용 OneDrive SharePoint.

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="통신 공동 작업 점수의 기본 인사이트입니다.":::


이 정보에 대해 고려되는 유형에는 Word, Excel, PowerPoint, OneNote 및 PDF 파일이 포함됩니다.

1. **헤더:** 콘텐츠에 대해 공동 작업을 하는 사용자 또는 OneDrive SharePoint 수 있는 사용자 비율을 보여 줄 수 있습니다.
2. **본문:** 온라인에서 파일을 읽고 만드는 동작이 파일 공동 작업과 연결된 방식에 대한 자세한 정보를 제공합니다.
3. **시각화(현재 상태):**
    - 가로 막대는 지난 28일 동안 온라인 파일에서 독자, 작성자 또는 공동 작업자로  OneDrive 또는 SharePoint 파일을  통해 파일 공동 작업을 할 수 있는 사용자 비율을 나타내는 가로 막대입니다.

        다음과 같이 정의됩니다.</br>
        **독자:** 온라인 파일에 액세스하거나 다운로드하는 OneDrive SharePoint.</br>
        **작성자:** 온라인으로 파일을 만들거나 수정, 업로드, 동기화, 체크 인, 복사 또는 이동하는 OneDrive SharePoint.</br>
        **공동 작업자:** 온라인 파일을 사용하여 공동 작업하는 OneDrive SharePoint. 두 사용자가 28일 이내에 온라인 Office 앱 또는 PDF를 읽거나 편집하는 경우 공동 작업자입니다.

        > [!NOTE]
        > 시각화에서 고려되는 파일은 온라인 또는 Excel, PowerPoint, OneNote 또는 PDF 파일로 OneDrive SharePoint. 

    - 분수의 강조(숫자/분모)는 각 가로 막대로 표시된 백분율을 계산하는 데 사용됩니다.
    
      - **독자:**</br>
          - Numerator: 지난 28일 동안 OneDrive 또는 SharePoint 온라인 파일에 액세스하거나 다운로드하는 사용자 수입니다.</br>
          - 분모: 지난 28일 중 OneDrive 또는 SharePoint 동안 액세스한 사용자 수입니다.</br>
      - **작성자:**</br>
        - Numerator: 지난 28일 동안 OneDrive 또는 SharePoint 온라인 파일을 만들거나 수정, 업로드, 동기화, 체크 인, 복사 또는 이동하는 사용자 수입니다.</br>
        - 분노: 지난 28일 중 OneDrive 또는 SharePoint 대한 액세스 권한이 있는 사용자 수입니다. </br> 
      - **공동 작업자:**</br>
        - Numerator: 지난 28일 동안 OneDrive 또는 SharePoint 온라인 파일로 공동 작업을 한 사용자 수입니다.</br>
        - 분노: 지난 28일 중 OneDrive 또는 SharePoint 동안 액세스할 수 있는 사용자 수입니다.

    - 각 독자, 작성자 및 공동 작업자에 대한 피어 벤치마크 값도 백분율로 표시됩니다. 즉, 작성자 수의 값은 크리에이터스 또는 크리에이터스에 액세스할 수 있는 사용자 수의 백분율로 OneDrive SharePoint.
    
1. **리소스 링크:** 이 링크를 선택하여 동료 비디오 및 기타 관련 도움말 콘텐츠를 볼 수 있습니다.


#### <a name="trend-visualization-of-primary-insight"></a>추세 통찰력의 시각화

추세 시각화 차트는 지난 180일 동안의 독자, 작성자 및 공동 작업자를 위한 기본 인사이트 키 메트릭의 추세선입니다. 차트의 각 데이터 포인트는 지난 28일간의 활동 집계입니다. 각 작성자 데이터 지점은 x 축의 각 날짜에 대해 지난 28일 이내에 작성자로 태그가 지정된 모든 사용자 수를 제공합니다.

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="공동 작업 기본 인사이트를 위한 추세가 있는 차트입니다.":::

### <a name="scoring-framework"></a>점수 매기기 프레임워크

조직에 대한 콘텐츠 공동 작업 점수는 Word, Excel, PowerPoint, OneNote 또는 PDF와 같은 온라인 Office 파일을 일관되게 읽거나 만들거나 공동 작업하는지 또는 조직 또는 OneDrive(조직) 수준에서 측정 SharePoint.

점수는 개별 사용자 수준에서 제공되지 않습니다.

## <a name="explore-how-your-organization-collaborates"></a>조직에서 공동 작업하는 방법 살펴보기

또한 조직에서 콘텐츠 공동 작업을 하는 방법을 쉽게 알 수 있는 정보를 제공합니다. 이러한 추가 메트릭은 생산성 점수에 직접적인 영향을 주지 않지만 디지털 변환의 일부로 작업 계획을 작성하여 사람들이 작업하는 방법을 최적화하는 데 도움이 됩니다.

### <a name="creating-files-in-onedrive-or-sharepoint"></a>사용자 또는 OneDrive 파일 SharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="OneDrive 사용자 수를 보여 SharePoint.":::

1. **헤더:** Microsoft 365 Office 응용 프로그램에서 파일을 만드는 사용자 비율을 OneDrive SharePoint.
2. **본문:** 콘텐츠 생성 및 콘텐츠 생성의 가치에 대한 OneDrive SharePoint.
3. **시각화:** 시각화의 분석은 다음과 같이 Microsoft Office 앱을 사용하여 OneDrive SharePoint 정도를 나타냅니다.
      - **OneDrive:** 막대의 파랑(색) 부분과 막대의 분수는 다음과 같이 Office 응용 프로그램에서 콘텐츠를 만드는 OneDrive 비율입니다.
        - Numerator: 지난 28일 이내에 온라인 Office 파일을 만들거나 수정, 업로드, 동기화, 체크 인, 복사 또는 이동하는 OneDrive 수입니다.</br>
        - 분노: 지난 28일 OneDrive 또는 SharePoint 파일에 액세스하고 액세스할 수 있는 사용자 수입니다.
      - **SharePoint:** 막대의 파랑(색) 부분과 막대의 분수는 Office 응용 프로그램에서 활성 상태인 사용자 비율을 나타내며 다음 SharePoint.</br>
         - Numerator Office: 지난 28일 이내에 Microsoft Word, Excel, PowerPoint 또는 OneNote SharePoint 파일(Microsoft Word, Excel, PowerPoint 또는 OneNote 파일)을 만들거나 수정, 업로드, 동기화, 체크 인, 복사 또는 이동하는 사용자 수입니다.</br>
        - 분모: 지난 28일 동안 OneDrive 또는 SharePoint 액세스하고 Office 파일에 액세스한 사용자 수입니다.

4. **리소스 링크:** 도움말 콘텐츠를 확인하려면 이 링크를 선택합니다.

### <a name="use-of-attachments-in-email"></a>전자 메일에서 첨부 파일 사용

**전자 메일에서 첨부 파일 사용** 클라우드의 콘텐츠에 대한 링크가 아닌 전자 메일에 실제 파일을 첨부하는 사용자의 수를 이해하고 시간이 지날 때 이 수치의 감소를 모니터링합니다.

:::image type="content" source="../../media/emailattachments.png" alt-text="전자 메일 첨부 파일 사용":::

1. **헤더:** 온라인 파일에 저장되지 않은 전자 메일에서 첨부 파일을 사용하는 비율을 강조합니다.
2. **본문:** 공동 작업 및 보안 관점에서 온라인 파일에 대한 링크를 공유하는 값에 대한 정보를 제공합니다.
3. **시각화:** 시각화의 분석은 전자 메일에 콘텐츠를 첨부하는 사람이 서로 다른 모드(온라인 파일에 저장되지 않은 파일, 온라인 파일에 대한 링크)를 사용하는 범위를 나타냅니다.
      - **파일 첨부:** 막대의 파랑(색) 부분과 막대의 분수(숫자/분모)는 전자 메일에서 첨부 파일을 사용하는 비율을 나타내는 비율입니다.
        - Numerator: 지난 28일 이내에 온라인 파일에 저장되지 않은 파일을 전자 메일에 첨부한 사용자 수입니다.
        - 분노: 지난 28일 이내에 Exchange 및 OneDrive, SharePoint 또는 둘 다에 액세스할 수 있는 사용자 수입니다.
      - **온라인 파일에 대한 링크:** 막대의 파랑(색) 부분과 막대의 분수(숫자/분모)는 첨부 파일을 사용하고 전자 메일의 파일에 링크를 첨부하는 비율을 나타내고 있습니다.
        - Numerator: 지난 28일 이내에 온라인 파일에 링크를 첨부한 사용자 수입니다.
        - 분모: 지난 28일 이내에 Exchange 및 OneDrive, SharePoint 또는 둘 다에 액세스할 수 있는 사용자 수입니다.
4. **리소스 링크:** 도움말 콘텐츠를 확인하려면 이 링크를 선택합니다.

### <a name="sharing-of-online-files"></a>온라인 파일 공유

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="온라인에서 파일을 공유하는 사용자 수를 표시하는 차트입니다.":::

1. **헤더:** 외부에서 파일을 공유하는 사용자 또는 OneDrive SharePoint 사용자 비율을 강조합니다.
2. **본문:** 조직에서 파일 공유&#39; 변경하여 조직에 가장 적합한 공동 작업 수준을 설정할 수 있는 관리자에 대한 정보를 제공합니다.
3. **시각화:** 내부 또는 외부에서 파일을 공유하는 OneDrive SharePoint 수 있는 범위를 나타 내외부로 나타내야 합니다.
      - **외부:** 막대의 파랑(색) 부분과 막대의 분수(숫자/분모)는 OneDrive 또는 SharePoint 외부에서 파일을 공유하는 SharePoint 비율을 나타내고 있습니다.
        -  Numerator: 지난 28일 동안 외부에서 파일을 공유한 사용자 수입니다.
        - 분노: 지난 28일 동안 OneDrive 또는 SharePoint 또는 SharePoint 대한 액세스 권한이 있는 총 사용자 수입니다.
      - **내부적으로만:** 막대의 파랑(색) 부분과 막대의 분수(숫자/분모)는 OneDrive 또는 SharePoint 액세스할 수 있으며 내부적으로만 파일을 공유하는 SharePoint 비율을 나타내고 있습니다.
        - 숫자: 지난 28일 이내에만 내부적으로만 파일을 공유한 사용자 수입니다.
        - 분노: 지난 28일 동안 OneDrive 또는 SharePoint 또는 SharePoint 대한 액세스 권한이 있는 총 사용자 수입니다.
4. **리소스 링크:** 도움말 콘텐츠를 확인하려면 이 링크를 선택합니다.

### <a name="number-of-files-collaborated-on"></a>공동 작업한 파일 수

:::image type="content" source="../../media/intensityofcollab.png" alt-text="가장 많이 공동 작업한 파일 수를 보여주는 차트입니다.":::

1. **헤더:** 4개 이상의 파일로 공동 작업하는 사용자 또는 OneDrive SharePoint 사용자 비율을 강조합니다.
2. **본문:** 사용자가 보다 나은 공동 작업을 위해 온라인 파일을 활용하는 방법에 대한 정보를 제공합니다.
3. **시각화:** 공동 작업하는 파일 수에 따라 OneDrive SharePoint 사용자 배포를 보여 주며, 이 항목은 다음 4개 범주(각각에 대해 막대의 파란색 부분과 분수는 해당 범주에 속하는 OneDrive 또는 SharePoint 사용자 비율을 나타임)를 통해 표시됩니다.
      - **공동 작업 없음:**
        - Numerator: 지난 28일 동안 어떤 파일도 공동 작업하지 않은 사용자 수입니다.
        - 분노: 지난 28일 중 OneDrive 또는 SharePoint 대한 액세스 권한이 있는 총 사용자 수입니다.
      - **1-3개 파일에 대한 공동 작업:**
        - Numerator: 지난 28일 동안 1~3개 파일에 대한 공동 작업 사용자 수입니다.
        - 분모: 지난 28일 중 OneDrive 또는 SharePoint 대한 액세스 권한이 있는 총 사용자 수입니다.
      - **4-10개 파일에 대한 공동 작업:**
        - Numerator: 지난 28일 동안 4-10개 파일에 대한 공동 작업 사용자 수입니다.
        - 분모: 지난 28일 중 OneDrive 또는 SharePoint 대한 액세스 권한이 있는 총 사용자 수입니다.
      - **11개 이상의 파일에 대한 공동 작업:**
        - Numerator: 지난 28일 동안 11개 이상의 파일에 대해 공동 작업하는 사용자 수입니다.
        - 분모: 지난 28일 중 OneDrive 또는 SharePoint 대한 액세스 권한이 있는 총 사용자 수입니다.
        
4. **리소스 링크:** 도움말 콘텐츠를 확인하려면 이 링크를 선택합니다.

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>네트워크 성능 및 OneDrive 성능 SharePoint

:::image type="content" source="../../media/networkperfstrength.png" alt-text="네트워크 및 네트워크의 네트워크 OneDrive 보여 SharePoint.":::

1. **헤더:** 테스트된 모든 장치에서 네트워크 연결이 불량한 장치의 비율을 OneDrive SharePoint. 
2. **본문:** 네트워크 연결 성능이 공동 작업에서 중요한 이유에 대한 정보를 제공합니다. 
3. **시각화:** 네트워크 연결 성능 수준이 서로 다른 장치의 백분율을 OneDrive SharePoint.
      - **81-100(최상)**: 막대의 진한 녹색(색) 부분은 최상의 성능을 나타내는 장치의 백분율을 나타내고 있습니다.
      - **61-80:** 막대의 녹색(색) 부분은 네트워크 성능 점수가 60~80인 장치의 백분율을 나타내고 있습니다. 
      - **41-60:** 막대의 주황색(색) 부분은 네트워크 성능 점수가 40~60인 장치의 백분율을 나타내고 있습니다. 
      - **21-40:** 막대의 빨간색(색) 부분은 네트워크 성능 점수가 20~40인 장치의 백분율을 나타내고 있습니다. 
      - **0-20**: 막대의 진한 빨강(색) 부분은 최하위 네트워크 성능 점수가 0~20인 장치의 백분율을 나타내고 있습니다. 

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365 앱 상태 – 기술](apps-health.md) 환경(문서)\
[커뮤니케이션 - 사람](communication.md) 환경(문서)\
[모임 - 사람](meetings.md) 환경(문서)\
[모바일 기능 - 사람](mobility.md) 환경(문서)\
[생산성 점수에 대한](privacy.md) 개인 정보 보호 컨트롤(문서)\
[팀워크 - 사람](teamwork.md) 환경(문서)
