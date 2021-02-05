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
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114240"
---
# <a name="enable-microsoft-365-usage-analytics"></a>Microsoft 365 사용 현황 분석을 사용하도록 설정

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)를 참조하세요.

::: moniker-end

Microsoft 365 미국 정부 커뮤니티에서는 Microsoft 365 사용 현황 분석을 아직 사용할 수 없습니다.
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>Microsoft 365 사용 현황 분석을 사용하도록 설정하는 단계

Microsoft 365 사용 현황 분석을 시작하려면 먼저 Microsoft 365 관리 센터에서 데이터를 사용할 수 있도록 설정한 다음 Power BI에서 템플릿 앱을 시작해야 합니다.
  
### <a name="get-power-bi"></a>Power BI 가져오기

Power BI가 아직 없는 경우 [Power BI Pro에 등록할 수 있습니다.](https://go.microsoft.com/fwlink/p/?linkid=845347) 무료 **평가판에** 등록하거나 지금  구입하여 Power BI Pro를 다운로드하세요.
  
  
**제품** 을 확장하여 Power BI 버전을 구매할 수도 있습니다. 

> [!NOTE]
> 템플릿 앱을 설치, 사용자 지정 및 배포하려면 Power BI Pro 라이선스가 필요합니다. 자세한 내용은 사전 [준비를 참조하세요.](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

데이터를 공유하려면 사용자와 데이터를 공유하는 사용자 모두 Power BI Pro 라이선스가 필요하거나, 콘텐츠가 Power BI Premium 서비스의 작업 영역이 [되거나,](https://docs.microsoft.com/power-bi/service-premium-what-is) 
  
### <a name="enable-the-template-app"></a>템플릿 앱 사용

템플릿 앱을 사용하도록 설정하려면 전역 **관리자로 설정해야 합니다.**
  
자세한 [내용은 관리자 역할에](../add-users/about-admin-roles.md) 대해 참조하세요. 
  
1. 관리 센터에서 **보고서** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">사용 현황</a> 페이지를 참조하세요. 
    
2. 사용 **페이지에서** **Microsoft 365** 사용 현황 분석 카드를 찾고 **시작을 선택합니다.**
    
3. 보고서 패널이 열리면 **Power BI에 대한 Microsoft 365** 사용 현황 분석에서 데이터를 사용할 수 있도록 **설정하여 저장합니다.** \>  
  
데이터 수집 프로세스는 테넌트의 크기에 따라 2~48시간이면 완료됩니다. 데이터 수집이 완료되면 **Power BI로** 이동 단추를 사용할 수 있습니다(더 이상 회색 아미기). 
    
### <a name="start-the-template-app"></a>템플릿 앱 시작

템플릿 앱을 시작하기 위해 전역 **관리자,** 보고서 읽기 **프로그램,** **Exchange** 관리자, 비즈니스용 **Skype** 관리자 또는 **SharePoint 관리자 중 하나 이상이면 됩니다.** 
  
1. 테넌트 ID를 복사하고 **Power BI로 이동을 선택합니다.**
    
2.  Power BI로 이동하면 로그인합니다. 그런 **다음 탐색** -> **메뉴에서 앱을** 다운로드합니다.    
  
3. 앱 **탭에서** 검색 상자에 Microsoft 365를 입력한 다음 **Microsoft 365** 사용 현황 분석을 \> **지금 다운로드합니다.**

    [![지금 사용 선택](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  앱이 설치되면 타일을 선택하여 열습니다.

5.  샘플 **데이터가 있는** 앱을 보기 위해 탐색 앱을 선택합니다. **Connect를** 선택하면 앱을 조직의 데이터에 연결합니다.

6.  **Connect를** 선택하고 **Microsoft 365** 사용 현황 분석 화면에 연결 화면에서 복사한 테넌트 ID(대시 없이)를 입력하고(1단계) 다음을 **선택합니다.**
    
7. 다음 화면에서 인증 방법으로 로그인하여  **OAuth2를** \> **선택합니다.** 다른 인증 방법을 선택하면 템플릿 앱에 대한 연결이 실패합니다.
    
    ![인증 방법으로 Microsoft 계정 선택](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. 템플릿 앱이 인스턴스화된 후 Microsoft 365 사용 현황 분석 대시보드는 웹의 Power BI에서 사용할 수 있습니다. 대시보드의 초기 로드에는 2~30분 정도 걸립니다.
  
테넌트 수준 집계는 옵트인 후 모든 보고서에서 사용할 수 있습니다. 사용자 수준 세부 정보는 옵트인 후 다음 달 **5일 전후에만 사용할 수 있습니다.** 이는 사용자 활동의 모든 보고서에 영향을 줍니다(이러한 보고서를 보고 사용하는 방법에 대한 팁은 [Microsoft 365](navigate-and-utilize-reports.md) 사용 현황 분석의 보고서 탐색 및 활용 참조).
    
## <a name="make-the-collected-data-anonymous"></a>수집된 데이터를 익명으로 설정

모든 보고서에 대해 수집되는 데이터를 익명으로 만들려면 글로벌 관리자여야 합니다. 이렇게 하면 보고서 및 템플릿 앱의 사용자, 그룹 및 사이트 이름과 같은 식별 가능한 정보가 숨겨지게 됩니다.
  
1. 관리 센터에서  설정 구성 설정으로 이동한 다음 서비스 탭에서 보고서를 \>  **선택합니다.** 
    
2. 보고서를 **선택한** 다음 익명 식별자를 **표시하려면 선택합니다.** 이 설정은 템플릿 앱뿐만 아니라 사용 현황 보고서에도 모두 적용됩니다.
  
3. **변경 내용 저장** 을 선택합니다.
