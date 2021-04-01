---
title: Microsoft 365 사용 현황 분석을 사용하도록 설정
f1.keywords:
- CSH
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
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: Power BI에서 Microsoft 365 사용 현황 분석 템플릿 앱을 사용하여 테넌트에 대한 데이터 수집을 시작하는 방법을 알아보십시오.
ms.openlocfilehash: 734712994d47fcb234ba988bb4d185d09f3267d0
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471060"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 사용 현황 분석을 사용하도록 설정

Microsoft 365 미국 정부 커뮤니티에서는 Microsoft 365 사용 현황 분석을 아직 사용할 수 없습니다.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Microsoft 365 사용 현황 분석을 사용 설정 단계

Microsoft 365 사용 현황 분석을 시작하려면 먼저 Microsoft 365 관리 센터에서 데이터를 사용할 수 있도록 설정한 다음 Power BI에서 템플릿 앱을 시작해야 합니다.
  
### <a name="get-power-bi"></a>Power BI 가져오기

Power BI가 아직 없는 경우 [Power BI Pro에 등록할 수 있습니다.](https://go.microsoft.com/fwlink/p/?linkid=845347) 무료 **평가판** 등록을 선택하거나  지금 구입을 선택하여 Power BI Pro를 다운로드합니다.
  
  
**제품** 을 확장하여 Power BI 버전을 구매할 수도 있습니다. 

> [!NOTE]
> 템플릿 앱을 설치, 사용자 지정 및 배포하려면 Power BI Pro 라이선스가 필요합니다. 자세한 내용은 [Prerequisites를 참조하세요.](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

데이터를 공유하려면 사용자와 데이터를 공유하는 사람이 모두 Power BI Pro 라이선스가 필요하거나 콘텐츠가 [Power BI Premium](/power-bi/service-premium-what-is)서비스의 작업 영역 에 있을 수 있습니다. 
  
### <a name="enable-the-template-app"></a>템플릿 앱 사용

템플릿 앱을 사용하도록 설정하려면 전역 관리자 **를 으로 설정해야 합니다.**
  
자세한 [내용은 관리자 역할](../add-users/about-admin-roles.md) 정보를 참조하세요. 
  
1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
    
2. 사용 **페이지에서** **Microsoft 365** 사용 현황 분석 카드를 찾고 시작 **을 선택합니다.**
    
3. 보고서 패널이 열리면 **Power BI에 대한 Microsoft 365** 사용 현황 분석을 사용할 수 있도록 설정 을 **저장으로** \> **설정하십시오.** 
  
데이터 수집 프로세스는 테넌트의 크기에 따라 2~48시간 만에 완료됩니다. 데이터 수집이 완료되면 **Power BI로** 이동 단추가 활성화됩니다(더 이상 회색 아 없음). 
    
### <a name="start-the-template-app"></a>템플릿 앱 시작

템플릿 앱을 시작하기 위해 전역 **관리자,** 보고서 읽기 권한자,  **Exchange** 관리자, 비즈니스용 **Skype** 관리자 또는 SharePoint 관리자 중 **하나일 수 있습니다.** 
  
1. 테넌트 ID를 복사하고 **Power BI로 이동을 선택합니다.**
    
2.  Power BI로 이동하면 로그인합니다. 그런 **다음 탐색** -> **메뉴에서 앱** 다운로드를 선택합니다.    
  
3. 앱 **탭의** 검색 상자에 Microsoft 365를 입력한 다음 **Microsoft 365** 사용 현황 분석 \> **지금 다운로드를 선택합니다.**

    [![지금 시작을 선택합니다.](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  앱이 설치되면 타일을 선택하여 열립니다.

5.  샘플 **데이터로** 앱을 보기 위해 앱 탐색을 선택합니다. 연결을 **선택하면** 앱을 조직의 데이터에 연결합니다.

6.  Microsoft  **365에 연결** 사용 현황 분석 화면에서 연결을 선택한 다음 1단계에서 복사한 테넌트 ID(대시 없이)를 입력하고 다음 을 **선택합니다.**
    
7. 다음 화면에서 인증 방법 **로그인으로 OAuth2를**  \> **선택합니다.** 다른 인증 방법을 선택하면 템플릿 앱에 대한 연결이 실패합니다.
    
    ![인증 방법으로 Microsoft 계정 선택](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. 템플릿 앱이 인스턴스화된 후 Microsoft 365 사용 현황 분석 대시보드는 웹의 Power BI에서 사용할 수 있습니다. 대시보드의 초기 로드에는 2~30분 정도 걸립니다.
  
테넌트 수준 집계는 옵트인 후 모든 보고서에서 사용할 수 있습니다. 사용자 수준 세부 정보는 옵트인 후 다음 달 **5일 전후에만 사용할 수 있습니다.** 이는 사용자 활동의 모든 보고서에 영향을 줍니다(이러한 보고서를 보고 사용하는 방법에 대한 팁은 [Microsoft 365](navigate-and-utilize-reports.md) 사용 현황 분석에서 보고서 탐색 및 활용 참조).
    
## <a name="make-the-collected-data-anonymous"></a>수집된 데이터를 익명으로 설정

모든 보고서에 대해 수집되는 데이터를 익명으로 만들려면 글로벌 관리자여야 합니다. 이렇게 하면 보고서 및 템플릿 앱에서 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보가 숨겨지게 됩니다.
  
1. 관리 센터에서 설정 구성  설정으로 \> **이동하고** 서비스 **탭에서** 보고서를 **선택합니다.**
    
2. 보고서를 **선택한** 다음 익명 식별자 **표시를 선택합니다.** 이 설정은 템플릿 앱뿐만 아니라 사용 현황 보고서에도 모두 적용됩니다.
  
3. **변경 내용 저장** 을 선택합니다.