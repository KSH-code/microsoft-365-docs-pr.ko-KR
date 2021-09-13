---
title: Microsoft 365 사용 현황 분석을 사용하도록 설정
f1.keywords:
- CSH
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Microsoft 365 사용 현황 분석 템플릿 앱을 사용하여 테넌트에 대한 데이터 수집을 시작하는 방법을 Power BI.
ms.openlocfilehash: a05ea19915af96720c3aeaf4a4d01fbe879fbc27
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188931"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 사용 현황 분석을 사용하도록 설정

Microsoft 365 US 정부 커뮤니티 클라우드(GCC) 테넌트에서 Microsoft 365 Microsoft 365 사용 현황 분석을 사용하도록 설정하려면 커넥트 to [Microsoft 365 정부 커뮤니티 클라우드(GCC) 데이터를 참조하세요.](connect-to-gcc-data-with-usage-analytics.md)

## <a name="before-you-begin"></a>시작하기 전에

사용 현황 Microsoft 365 시작하려면 먼저 Microsoft 365 관리 센터 에서 데이터를 사용할 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank"></a>수 있도록 설정한 다음 Power BI.

## <a name="get-power-bi"></a>Power BI 가져오기

아직 등록하지 않은 Power BI 에 등록할 [Power BI Pro.](https://go.microsoft.com/fwlink/p/?linkid=845347) 무료 **평가판** 등록을 선택하거나  지금 구입을 선택하여 평가판을 Power BI Pro.


**제품** 을 확장하여 Power BI 버전을 구매할 수도 있습니다.

> [!NOTE]
> 템플릿 앱을 Power BI Pro 사용자 지정하고 배포하려면 라이선스가 필요합니다. 자세한 내용은 [Prerequisites를 참조하세요.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

데이터를 공유하려면 사용자와 데이터를 공유하는 사람이 모두 Power BI Pro 라이선스가 필요하거나 콘텐츠가 Power BI 프리미엄 서비스의 작업 Power BI [합니다.](/power-bi/service-premium-what-is)

## <a name="enable-the-template-app"></a>템플릿 앱 사용

템플릿 앱을 사용하도록 설정하려면 전역 관리자 **를 으로 설정해야 합니다.**

자세한 [내용은 관리자 역할](../add-users/about-admin-roles.md) 정보를 참조하세요.

1. 관리 센터에서 관리 센터  설정 \> **서비스** \> **탭으로** 이동합니다.

2. 서비스 **탭에서** 보고서를 **선택합니다.**

3. 보고서 패널이 열리면 보고서에 대한 사용 현황 분석을 사용할 Microsoft 365 보고서 데이터를 **Power BI** **저장으로** \> **설정하십시오.**

데이터 수집 프로세스는 테넌트의 크기에 따라 2~48시간 만에 완료됩니다. 데이터 **수집이 Power BI** 이동 단추가 활성화됩니다(더 이상 회색 아 없음).

## <a name="start-the-template-app"></a>템플릿 앱 시작

템플릿 앱을 시작하기 위해 전역 관리자, 보고서 읽기 프로그램 관리자, Exchange  **관리자,** 비즈니스용 Skype 관리자 또는 SharePoint **합니다.**

1. 테넌트 ID를 복사하고 으로 **이동을 Power BI.**

2. Power BI로 이동하면 로그인합니다. 그런 **다음 탐색** -> **메뉴에서 앱** 다운로드를 선택합니다.

3. 앱 **탭에서** 검색 Microsoft 365 입력한 다음 사용 현황 Microsoft 365  \> **지금 다운로드를 선택합니다.**

    [![지금 시작을 선택합니다.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. 앱이 설치되면 타일을 선택하여 열립니다.

5. 샘플 **데이터로** 앱을 보기 위해 앱 탐색을 선택합니다. 앱을 **커넥트** 데이터에 연결하기 위해 앱을 선택하십시오.

6. 커넥트 를 선택하여 커넥트 사용 현황 분석 Microsoft 365 선택한 다음 1단계에서 복사한 테넌트 ID(대시 **없이)를** 입력하고 다음 을 **선택합니다.**

7. 다음 화면에서 인증 방법 **로그인으로 OAuth2를**  \> **선택합니다.** 다른 인증 방법을 선택하면 템플릿 앱에 대한 연결이 실패합니다.

    ![인증 방법으로 Microsoft 계정을 선택하세요.](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. 템플릿 앱을 인스턴스화한 후 Microsoft 365 사용 현황 분석 대시보드를 웹의 Power BI 사용할 수 있습니다. 대시보드의 초기 로드에는 2~30분 정도 걸립니다.

테넌트 수준 집계는 옵트인 후 모든 보고서에서 사용할 수 있습니다. 사용자 수준 세부 정보는 옵트인 후 다음 달 **5일 전후에만 사용할 수 있습니다.** 이는 사용자 활동의 모든 보고서에 영향을 줍니다(이러한 보고서를 보고 [사용하는 방법에 대한](navigate-and-utilize-reports.md) 팁은 Microsoft 365 사용 현황 분석에서 보고서 탐색 및 활용 참조).

## <a name="make-the-collected-data-anonymous"></a>수집된 데이터를 익명으로 설정

보고서는 조직의 사용량 데이터에 대한 정보를 제공합니다. 기본적으로 보고서에는 사용자, 그룹 및 사이트의 식별 가능한 이름이 포함된 정보가 표시됩니다. Microsoft는 2021년 9월 1일부터 회사가 현지 개인 정보 보호법을 지원할 수 있도록 돕는 지속적인 노력의 일환으로 기본적으로 모든 보고서에 대해 사용자 정보를 숨기고 있습니다.
  
전역 관리자는 해당 테넌트에 대해 이 변경 내용을 되돌리고 조직의 개인정보처리방침에서 허용하는 경우 식별 가능한 사용자 정보를 표시할 수 있습니다. 이러한 결과는 Microsoft 365 관리 센터에서 다음 단계를 수행하여 달성할 수 있습니다.
  
1. 관리 센터에서 **설정** \> **조직 설정**\>**서비스** 로 이동합니다.

2. **보고서** 를 선택합니다. 
  
3. **모든 보고서에서 사용자, 그룹 및 사이트의 비식별화된 이름 표시** 를 선택 취소한 다음 변경 내용을 저장합니다.  
  
이러한 변경 내용을 적용하는 데 몇 분 정도 걸립니다. 식별 가능한 사용자 정보를 표시하는 것은 Microsoft 365 규정 준수 센터 감사 로그에 기록된 이벤트입니다.   

## <a name="related-content"></a>관련 콘텐츠

[사용 현황 분석(문서)\](usage-analytics.md)
[최신 버전의 사용 현황 분석](get-the-latest-version-of-usage-analytics.md) 다운로드(문서)\
[사용 현황 분석에서 보고서를 Microsoft 365](navigate-and-utilize-reports.md) 활용(문서)
