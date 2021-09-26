---
title: 사용 현황 분석에서 Microsoft 365 사용자 지정
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9b76065f-29b9-4b89-8059-c5f9db9ddbf6
description: 브라우저 및 웹 응용 프로그램을 통해 보고서를 사용자 지정하는 Power BI Desktop.
ms.openlocfilehash: 7fbd31af1dc59cb8161e981bb27d0bac132be755
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59773934"
---
# <a name="customize-the-reports-in-microsoft-365-usage-analytics"></a>사용 현황 분석에서 Microsoft 365 사용자 지정

Microsoft 365 사용 현황 분석은 사용자가 Power BI 사용하는 방법에 대한 인사이트를 제공하는 대시보드를 Microsoft 365. 대시보드는 사용 현황 데이터와 상호 작용하는 시작점입니다. 보고서를 사용자 지정하여 더 개인화된 유용한 정보를 얻을 수 있습니다.

또한 Power BI Desktop을 통해 보고서를 다른 데이터 원본에 연결하여 추가로 사용자 지정하고 비즈니스에 대한 풍부한 통찰력을 얻을 수 있습니다.

## <a name="customizing-reports-in-the-browser"></a>브라우저에서 보고서 사용자 지정하기

다음 두 가지 예에서는 기존 시각적 개체를 수정하고 새롭게 만드는 방법을 보여 줍니다.

### <a name="modify-an-existing-visual"></a>기존 시각적 개체 수정

이 예에서는 정품  인증/라이선스 보고서 내에서 정품 인증 **탭을 수정하는 방법을 보여줍니다.**

1. 정품 **인증/라이선스 보고서에서** 정품 인증 **탭을** 선택합니다.

2. 페이지의 페이지 더하기  단추를 통해 맨 위에 있는 편집 단추를 선택하여 편집 ![ 모드를 Power BI.](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 단추.

    ![오른쪽 상단 탐색에서 보고서 편집을 클릭합니다.](../../media/e2c16663-1fbd-4d7f-887c-0cbb891d3b3d.png)

3. On the top right, choose **Duplicate this page**.

    ![이 페이지 복제를 선택합니다.](../../media/b2d18dcd-6b82-4ce7-ab79-1b24e3721309.png)

4. 오른쪽 아래에서 Android, iOS, Mac 등의 OS를 기반으로 정비하는 사용자 수를 표시하는 막대형 차트를 선택하십시오.

5. 오른쪽의  시각화 영역에서 시각적 개체에서 **Mac 개수를** 제거하려면 옆에 **있는 X를** 선택합니다.

    ![Mac 개수를 제거합니다.](../../media/ce3d8358-df57-4f64-bd25-ac5be7fc8713.png)

### <a name="create-a-new-visual"></a>새 시각적 개체 만들기

다음 예에서는 매월 사용자를 새로 정의하기 위해 새 시각적 개체를 만드는 방법을 보여 줍니다.

1. 왼쪽 검색 **창을** 사용하여 제품 사용 현황 보고서로 이동한 다음 Yammer **선택합니다.**

2. 편집 모드에서 더 많은 페이지 단추를 선택하여 편집 ![ 모드로 Power BI.](../../media/d8da3c19-3f2d-4bf6-811e-faa804f74770.png) 를 **편집합니다.**

3. At the bottom of the page, select the ![페이지 추가 단추의 Power BI.](../../media/d3b8c117-17d4-4f53-b078-8fefc2155b24.png) 새 페이지를 만들 수 있습니다.

4. 오른쪽의  시각화 영역에서 누적  막대형 차트(왼쪽에서 맨 위 행)를 선택하십시오.

    ![막대형 차트를 선택합니다.](../../media/214c3fed-6eae-43e6-83fb-708a2d74406e.png)

5. 해당 시각화의 오른쪽 아래를 선택하고 끌어서 더 크게 합니다.

6. 오른쪽의 **필드** 영역에서 일정 **테이블을 확장합니다.**

7. **시각화** 영역의 **축** 머리글 바로 아래에 있는 필드로 **MonthName** 을 끌어다 놓습니다.

    ![월 이름을 끌어 놓습니다.](../../media/bff99987-8c4b-4618-89fd-47df557b0ed7.png)

8. 오른쪽의 **필드** 영역에서 **TenantProductUsage** 테이블을 확장합니다.

9. **FirstTimeUsers** 를 **값** 머리글 바로 아래에 있는 필드 영역으로 끌어다 놓습니다.

10. **제품** 을 **시각적 수준 필터** 머리글 바로 아래에 있는 **필터** 영역으로 끌어다 놓습니다.

11. **필터 형식** 영역이 표시되면 **Yammer** 확인란을 선택합니다.

    ![선택 Yammer 선택합니다.](../../media/82e99730-0de9-42da-928a-76aab0c3e609.png)

12. 시각화 목록 바로 아래에 있는  Visualizaions의 서식 아이콘 서식 ![ 아이콘을 Power BI ](../../media/ee0602f3-3df5-4930-b862-db1d90ae4ae2.png) 선택합니다.

13. 제목을 확장하고 **제목 텍스트** 값을 **First-Time Yammer Users by Month**(월별 Yammer 최초 사용자)로 변경합니다.

14. **텍스트 크기** 값을 **12** 로 변경합니다.

15. 오른쪽 아래에 있는 페이지의 이름을 편집하여 새 페이지의 제목을 변경합니다.

16. 맨 위에 있는 읽기  보기를 클릭한 다음 저장을 클릭하여 보고서를 **저장합니다.**

## <a name="customizing-the-reports-in-power-bi-desktop"></a>Power BI Desktop에서 보고서 사용자 지정

대부분의 고객의 경우 Power BI Web에서 보고서 및 차트 시각적 개체를 수정하는 것만으로도 만족합니다. 그러나 일부 고객의 경우 자신의 비즈니스에 대한 더욱 풍부한 통찰력을 얻기 위해 이러한 데이터를 다른 데이터 원본과 연결하기를 원할 수 있습니다. 이 경우 Power BI Desktop을 사용하여 추가 보고서를 사용자 지정하고 만들 수 있습니다. [Power BI Desktop](https://go.microsoft.com/fwlink/p/?linkid=849797)은 무료로 다운로드할 수 있습니다.

### <a name="use-the-reporting-apis"></a>보고 API 사용

이러한 보고서의 전원을 공급하는 ODATA 보고 API에 직접 연결하여 시작할 Microsoft 365 있습니다.

1. **데이터 가져오기** \> **기타** \> **ODATA 피드** \> **연결** 로 이동합니다.

2. URL 창에 "https:// <i></i> \<tenantid\> reports.office.com/pbi/v1.0/"를 입력합니다.

    **참고:** 보고 API는 미리 보기에 있으며 프로덕션으로 들어갈 때까지 변경될 수 있습니다.

    ![데스크톱용 OData Power BI URL입니다.](../../media/c0ef967e-a454-4eba-bc8e-61e113170053.png)

3. 메시지가 Microsoft 365 인증할 사용자(조직 또는 학교) 관리자 자격 증명을 Microsoft 365 자격 증명을 입력합니다.

    채택 템플릿 앱 보고서에 액세스할 수 있는 사용자에 대한 자세한 내용은 [FAQ를](usage-analytics.md#faq) Microsoft 365 참조하세요.

4. 연결이 승인되면 연결할 수 있는 데이터 집합을 보여주는 탐색 창이 표시됩니다.

    모두를 선택하고 로드 **를 선택합니다.**

    그러면 데이터가 Power BI Desktop으로 다운로드됩니다. 이 파일을 저장한 다음 필요한 보고서를 만들 수 있습니다.

    ![보고 API에서 사용할 수 있는 ODATA 값입니다.](../../media/545b4d17-dbbd-4cfc-b75a-a8b27283d438.png)

### <a name="use-the-microsoft-365-usage-analytics-template"></a>사용 현황 Microsoft 365 템플릿 사용

또한 데이터 연결의 시작점으로 Power BI 사용 현황 분석 보고서에 해당하는 Microsoft 365 서식 파일을 사용할 수도 있습니다. pbit 파일을 사용하는 장점은 연결 문자열이 이미 설정되었다는 점입니다. 기본 스키마가 반환하고 추가적으로 빌드하는 데이터의 맨 위에 만들어진 모든 사용자 지정 측정을 활용할 수도 있습니다.

Microsoft 다운로드 센터에서 Power BI 다운로드할 [수 있습니다.](https://download.microsoft.com/download/7/8/2/782ba8a7-8d89-4958-a315-dab04c3b620c/Microsoft%20365%20Usage%20Analytics.pbit) Power BI 파일을 다운로드한 후 다음 단계에 따라 시작하세요.

1. pbit 파일을 엽니다.

2. 대화 상자에 테넌트 ID 값을 입력합니다.

    ![pbit 파일을 열 테넌트 ID를 입력합니다.](../../media/071ed0bf-8b9d-49c6-81fc-fd4c6cc85bd3.png)

3. 메시지가 표시될 때 관리자 자격 증명을 입력하여 Microsoft 365 인증합니다.

     사용 현황 분석 보고서에 액세스할 수 있는 Microsoft 365 정보를 제공합니다.

    권한이 부여되면 데이터가 Power BI 파일에서 새로 고쳐집니다.

    데이터를 로드하는 데 다소 시간이 걸릴 수 있으며 로드가 완료되면 파일을 .pbix 파일로 저장하고 계속하여 보고서를 사용자 지정하거나 추가 데이터 원본을 이 보고서로 가져올 수 있습니다.

4. [Power BI 시작](/power-bi/fundamentals/desktop-getting-started) 문서를 확인하여 보고서를 만들고, Power BI 서비스에 게시하고 조직과 공유하는 방법을 알아봅니다. 사용자 지정 및 공유를 위한 이 방법에 따라 작업을 수행하기 위해 Power BI 라이선스가 추가로 필요할 수 있습니다. 자세한 내용은 Power BI [라이선싱 참고 자료](https://go.microsoft.com/fwlink/p/?linkid=849803)를 참조하세요.
