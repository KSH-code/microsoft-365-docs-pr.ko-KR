---
title: 보존 레이블 개요
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 보존 레이블을 사용하여 조직 전체의 데이터를 관리하여 분류하고 해당 분류에 따라 보존 규칙을 시행하십시오. 보존 레이블을 사용하여 Microsoft 365용 레코드 관리 솔루션을 구현할 수도 있습니다.
ms.openlocfilehash: e41c71a1f8bc0175b179ecd760dac7098551bc91
ms.sourcegitcommit: 6b7eecad7162c065af80721204fbabdd2e31e42b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2020
ms.locfileid: "43065644"
---
# <a name="overview-of-retention-labels"></a>보존 레이블 개요

조직 전체에서 산업 규정 및 내부 정책을 준수하기 위해 다른 작업이 수행되어야 하는 다음과 같은 다른 형식의 콘텐츠가 있을 수 있습니다.
  
- 최소 기간 동안 **보존**해야 하는 세금 양식 
    
- 특정 기간에 도달할 때 **영구적으로 삭제**되어야 하는 보도 자료 
    
- **보존**되었다가 **영구적으로 삭제**되어야 하는 경쟁업체 연구 자료 
    
- 편집하거나 삭제할 수 없게 **기록으로 표시**해야 하는 취업 비자 
    
이러한 모든 경우에 Office 365에서 보존 레이블은 올바른 콘텐츠에 대해 올바른 작업을 수행하는 데 도움이 될 수 있습니다. 보존 레이블을 사용하여 거버넌스를 위해 조직의 데이터를 분류하고 해당 분류에 따라 보존 규칙을 적용할 수 있습니다.
  
보존 레이블을 사용하여 다음을 수행할 수 있습니다.
  
- **조직의 사용자가 웹용 Outlook, Outlook 2010 이상, OneDrive, SharePoint 및 Office 365 그룹에서 Outlook 콘텐츠에 보존 레이블을 수동으로 적용할 수 있게 합니다**. 사용자는 종종 자신이 사용하고 있는 콘텐츠의 형식을 가장 잘 알고 있기 때문에 콘텐츠를 분류하여 적절한 정책을 적용할 수 있습니다. 
    
- 콘텐츠에 다음이 포함된 경우처럼 특정 조건과 일치하는 경우 **콘텐츠에 보존 레이블을 자동으로 적용**합니다. 
    
    - 특정 중요한 정보 유형
    
    - 만든 쿼리와 일치하는 특정 키워드
    
    - 학습 가능한 분류자에 대한 패턴 일치
    
  콘텐츠에 자동으로 보존 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.
    
     - 사용자에게 모든 분류를 교육할 필요가 없습니다.
    
     - 모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.
    
   - 사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 그 대신 업무에 집중할 수 있습니다.

- 전자 메일 문서를 포함하는 **기록 관리를 Office 365에서 구현**합니다. 보존 레이블을 사용하여 콘텐츠를 기록으로 분류할 수 있습니다. 이 경우 레이블을 변경하거나 제거할 수 없으며 콘텐츠를 편집하거나 삭제할 수 없습니다. 

- SharePoint의 **문서 라이브러리, 폴더 또는 문서 집합에 기본 보존 레이블을 적용**하여 해당 위치에 도착하는 모든 문서가 기본 보존 레이블을 상속하도록 합니다.  
    
Microsoft 365 규정 준수 센터, Microsoft 365 보안 센터 또는 Office 365 보안 규정 준수 센터에서 보존 레이블을 생성합니다.

## <a name="how-retention-labels-work-with-retention-label-policies"></a>보존 레이블이 보존 레이블 정책에 작동하는 방식

콘텐츠를 분류할 수 있도록 조직의 사용자에게 보존 레이블을 제공하는 작업은 2단계 프로세스입니다. 먼저 보존 레이블을 만든 다음 선택한 위치에 게시합니다. 보존 레이블을 게시하면 보존 레이블 정책이 생성됩니다.
  
![레이블의 역할 및 작업 다이어그램](../media/4082bc7d-c04c-4b9a-8a26-7f12565d3311.png)
  
보존 레이블은 한 개 이상의 보존 레이블 정책에 포함되는 독립적인 재사용 가능한 구성 요소입니다. 보존 레이블 정책의 기본 목적은 보존 레이블 집합을 그룹화하고 해당 레이블을 표시할 위치를 지정하는 것입니다.
  
![레이블, 레이블 정책 및 위치 다이어그램](../media/eee42516-adf0-4664-b5ab-76727a9a3511.png)
  
1. 보존 레이블을 게시하면 보존 레이블 정책에 포함됩니다. 보존 라벨 이름은 변경할 수 없습니다. 즉, 라벨 이름을 만든 후에는 수정할 수 없습니다.


2. 하나의 보존 레이블이 여러 보존 레이블 정책에 포함될 수 있습니다.

3. 하나의 위치가 여러 보존 레이블 정책에 포함될 수도 있습니다.    
    
3. 보존 레이블 정책은 보존 레이블을 게시할 위치를 지정합니다.
    
## <a name="only-one-retention-label-at-a-time"></a>한 번에 하나의 보존 레이블만

전자 메일 또는 문서와 같은 콘텐츠에는 한 번에 하나씩 단일 보존 레이블만 할당될 수 있다는 점에 유의합니다.
  
- 최종 사용자가 수동으로 할당한 보존 레이블의 경우, 할당된 보존 레이블을 제거하거나 변경할 수 있습니다.
    
- 콘텐츠에 자동 적용 레이블이 할당된 경우 최종 사용자가 자동 적용 레이블을 수동 할당 보존 레이블로 바꿀 수 있습니다.
    
- 최종 사용자가 콘텐츠에 수동으로 보존 레이블을 할당한 경우 자동 적용 레이블로 수동 할당 보존 레이블을 대신할 수 없습니다.
    
- 자동 적용 레이블을 할당하는 여러 규칙이 있고 콘텐츠가 여러 규칙의 조건을 충족하는 경우 가장 오래된 규칙에 대한 보존 레이블이 할당됩니다.
    
수동으로 할당된 레이블은 명시적으로 할당되고, 자동 적용 레이블은 암시적으로 할당됩니다. 또한 명시적 보존 레이블은 암시적 레이블보다 우선합니다. 자세한 내용은 아래 섹션에서 [보존 원칙 또는 우선 순위](#the-principles-of-retention-or-what-takes-precedence)를 참조하세요.

이 섹션의 모든 정보는 보존 레이블에만 적용됩니다. 하나의 콘텐츠 항목에 보존 레이블 1개 외에 민감도 레이블이 1개만 적용될 수 있습니다.
  
## <a name="how-long-it-takes-for-retention-labels-to-take-effect"></a>보존 레이블이 적용되는 데 걸리는 시간

보존 레이블을 게시하거나 자동 적용할 경우 즉시 적용되지 않습니다.
  
1. 먼저 관리 센터에서 레이블 정책을 정책의 위치로 동기화해야 합니다.
    
2. 그런 다음 위치에는 게시된 보존 레이블을 최종 사용자에게 제공하거나 레이블을 콘텐츠에 자동 적용하기 위한 시간이 필요할 수 있습니다. 여기에 걸리는 시간은 보존 레이블의 위치와 유형에 따라 다릅니다.
    
### <a name="published-retention-labels"></a>게시된 보존 레이블

SharePoint 또는 OneDrive에 보존 레이블을 게시하면 해당 보존 레이블이 최종 사용자에 게 표시되기까지 하루가 걸릴 수 있습니다. 또한 보존 레이블을 Exchange에 게시하는 경우 해당 보존 레이블이 최종 사용자에게 표시되기까지 7일이 걸릴 수 있으며, 사서함에는 10MB 이상의 데이터가 포함되어야 합니다.
  
![수동 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b19f3a10-f625-45bf-9a53-dd14df02ae7c.png)
  
### <a name="auto-apply-retention-labels"></a>보존 레이블 작동 적용

특정 조건과 일치하는 콘텐츠에 보존 레이블을 자동으로 적용하는 경우 보존 레이블이 조건과 일치하는 모든 기존 콘텐츠에 적용되는 데 7일이 걸릴 수 있습니다.
  
![자동 적용 레이블이 적용되는 경우를 나타내는 다이어그램](../media/b8c00657-477a-4ade-b914-e643ef97a10d.png)
  
### <a name="how-to-check-on-the-status-of-retention-labels-published-to-exchange"></a>Exchange에 게시된 보존 레이블의 상태를 확인하는 방법

Exchange Online에서는 7일 간격으로 실행되는 프로세스를 통해 최종 사용자가 보존 레이블을 사용할 수 있게 됩니다. Powershell을 사용하여 이 프로세스가 마지막으로 실행된 시간 및 다시 실행될 시간을 확인할 수 있습니다.
  
1. [Exchange Online PowerShell에 연결합니다](https://go.microsoft.com/fwlink/?linkid=799773).
    
2. 다음 명령을 실행합니다.
    
   ```powershell
   $logProps = Export-MailboxDiagnosticLogs <user> -ExtendedProperties
   ```

   ```powershell
   $xmlprops = [xml]($logProps.MailboxLog)
   ```

   ```powershell
   $xmlprops.Properties.MailboxTable.Property | ? {$_.Name -like "ELC*"}
   ```

결과에서 `ELCLastSuccessTimeStamp`(UTC) 속성은 시스템에서 사서함을 마지막으로 처리한 시간을 보여 줍니다. 정책을 만든 이후로 이러한 처리가 발생하지 않은 경우 레이블은 표시되지 않습니다. 강제로 처리하려면 `Start-ManagedFolderAssistant -Identity <user>`를 실행합니다.
    
웹용 Outlook에 레이블이 나타나야 하는데 나타나지 않으면 브라우저에서 캐시를 지워야 합니다(Ctrl + F5).
    
## <a name="retention-label-policies-and-locations"></a>보존 레이블 정책 및 위치

보존 레이블이 수행하는 작업에 따라, 다양한 유형의 보존 레이블을 여러 다른 위치에 게시할 수 있습니다.
  
|**보존 레이블...**|**레이블 정책을 적용할 수 있는 대상...**|
|:-----|:-----|
|최종 사용자에게 게시  <br/> |Exchange, SharePoint, OneDrive, Office 365 그룹  <br/> |
|중요한 정보 유형에 따라 자동으로 적용  <br/> |Exchange(모든 사서함만), SharePoint, OneDrive  <br/> |
|쿼리에 따라 자동 적용  <br/> |Exchange, SharePoint, OneDrive, Office 365 그룹  <br/> |
   
Exchange에서 자동 적용 보존 레이블(쿼리 및 중요한 정보 유형 모두에 대한)은 현재 사서함에 있는 모든 항목(미사용 데이터)이 아닌 새로 전송된 메시지(전송 중인 데이터)에만 적용됩니다. 또한 민감한 정보 유형에 대한 자동 적용 보존 레이블은 모든 사서함에만 적용되며 특정 사서함을 선택할 수 없습니다.
  
Exchange 공용 폴더 및 Skype는 레이블을 지원하지 않습니다.
  
## <a name="how-retention-labels-enforce-retention"></a>보존 레이블이 보존을 적용하는 방법

보존 레이블은 보존 정책이 할 수 있는 것과 같은 보존 작업을 적용할 수 있습니다. 보존 레이블을 사용하여 정교한 콘텐츠 계획(또는 파일 계획)을 구현할 수 있습니다. 보존 작업이 작동하는 방법에 대한 자세한 내용은 [보존 정책 개요](retention-policies.md)를 참조하세요.
  
또한 보존 레이블에는 보존 정책이 아니라 보존 레이블에서만 사용할 수 있는 2가지 보존 옵션이 있습니다. 보존 레이블을 사용하면 다음과 같은 작업을 수행할 수 있습니다.
  
- SharePoint 및 OneDrive 문서가 삭제되기 전에 검토될 수 있도록 보존 기간이 끝나면 처리 검토를 트리거합니다. 자세한 내용은 [처리 검토 개요](disposition-reviews.md)를 참조하세요.
    
- 보존 기간은 콘텐츠 사용 기간이나 마지막으로 수정되었을 때가 아니라 콘텐츠에 레이블이 지정될 때 시작됩니다. 해당 옵션은 SharePoint 사이트 및 OneDrive 계정의 콘텐츠에만 적용됨을 유의하세요. Exchange 전자 메일의 경우 보존 기간은 사용자가 선택한 옵션에 상관없이 항상 메시지를 보냈거나 받은 날짜를 기준으로 합니다.
    
![레이블 관련 옵션이 있는 보존 설정](../media/c49118c9-6279-4661-94db-deffa76e27ac.png)
  
## <a name="where-published-retention-labels-can-appear-to-end-users"></a>게시된 보존 레이블이 최종 사용자에게 표시될 수 있는 위치

최종 사용자가 콘텐츠에 보존 레이블을 할당하면 해당 레이블을 다음에 게시할 수 있습니다.
  
- 웹용 Outlook
    
- Outlook 2010 이상
    
- OneDrive
    
- SharePoint
    
- Office 365 그룹(웹용 Outlook의 그룹 사이트 및 그룹 사서함)
    
아래 섹션에서는 다양한 앱에서 레이블이 조직의 사용자에게 표시되는 방식을 설명합니다.
  
### <a name="outlook-on-the-web"></a>웹용 Outlook

웹용 Outlook에서 항목에 레이블을 지정하려면 마우스 오른쪽 단추로 항목 \> **정책 할당**을 클릭하고 \> 보존 레이블을 선택합니다. 
  
![웹용 Outlook의 정책 할당 메뉴](../media/146a23cf-e478-4595-b2e8-f707fc4e6ea3.png)
  
해당 보존 레이블이 적용된 후에는 항목 맨 위에서 해당 보존 레이블과 수행되는 작업을 볼 수 있습니다. 전자 메일 분류되고 연결된 보존 기간이 있으면 전자 메일이 만료될 시기를 한눈에 알 수 있습니다.
  
![웹용 Outlook에서 전자 메일에 할당된 레이블](../media/16f6c91b-5eab-4574-9d13-6d12be00a783.png)
  
폴더에 보존 레이블을 적용할 수도 있습니다. 이러한 경우 다음을 수행됩니다.
  
- 보존 레이블이 명시적으로 적용된 항목을 **제외**하고 폴더의 모든 항목에는 자동으로 같은 보존 레이블이 지정됩니다. 명시적으로 레이블이 지정된 항목은 기존 보존 레이블이 유지됩니다. 자세한 내용은 아래에서 보존 원칙에 대한 섹션을 참조하세요. 
    
- 폴더의 기본 보존 레이블을 변경하거나 제거하는 경우 명시적 보존 레이블이 지정된 항목을 **제외**하고 폴더의 모든 항목에 대해서도 보존 레이블이 변경되거나 제거됩니다. 
    
- 기본 보존 레이블이 있는 항목을 한 폴더에서 다른 기본 보존 레이블이 있는 다른 폴더로 이동하면 항목에 새 기본 보존 레이블이 지정됩니다.
    
- 기본 보존 레이블이 있는 항목을 한 폴더에서 기본 보존 레이블이 없는 다른 폴더로 이동하면 이전의 기본 보존 레이블이 제거됩니다.
    
### <a name="outlook-2010-and-later"></a>Outlook 2010 이상

Outlook 데스크톱 클라이언트에서 항목에 레이블을 지정하려면 해당 항목을 선택합니다. 리본 메뉴의 **홈** 탭에서 **정책 할당**을 클릭한 다음, 보존 레이블을 선택합니다. 
  
![정책 할당 단추](../media/30684dea-dd73-4e4a-9185-8e29f403b6ca.png)
  
항목을 마우스 오른쪽 단추로 클릭하고, 상황에 맞는 메뉴에서 **정책 할당**를 클릭한 다음, 보존 레이블을 선택할 수도 있습니다. 

보존 레이블이 적용된 후 항목 맨 위에서 해당 보존 레이블과 해당 레이블이 수행하는 작업을 볼 수 있습니다. 연결된 보존 기간이 있는 보존 레이블이 전자 메일에 적용된 경우, 해당 전자 메일이 만료되는 시간을 한눈에 알 수 있습니다.
  
폴더에 보존 레이블을 적용할 수도 있습니다. 이 내용은 웹용 Outlook에서와 마찬가지로 Outlook 2010 이상에서도 적용됩니다. 자세한 내용은 이전 섹션을 참조하세요.
  
### <a name="onedrive-and-sharepoint"></a>OneDrive 및 SharePoint

OneDrive 또는 SharePoint에서 문서(OneNote 파일 포함)에 레이블을 지정하려면 오른쪽 위 모서리에서 항목 \>을 선택하고 **세부 정보 창 열기**![정보 창 아이콘](../media/50b6d51b-92b4-4c5f-bb4b-4ca2d4aa3d04.png) \> **보존 레이블 적용**을 선택한 후 \> 보존 레이블을 선택합니다. 
  
폴더 또는 문서 집합에 보존 레이블을 적용할 수도 있으며, 문서 라이브러리에 대해 기본 보존 레이블을 설정할 수 있습니다. 자세한 내용은 아래 섹션을 참조하세요.
  
![SharePoint의 항목에 대해 레이블 목록 적용](../media/151cc83c-da57-45b0-9cd1-fd2f28a31083.png)
  
항목에 보존 레이블이 적용된 후에는 항목을 선택하면 세부 정보 창에서 해당 레이블을 볼 수 있습니다.
  
![세부 정보 창에 표시되는 적용된 레이블](../media/d06e585e-29f7-4c8c-afef-629c97268b8e.png)
  
**레이블** 열 또는 **기록 항목임** 열이 포함된 라이브러리의 보기를 만들 수도 있습니다. 이 경우 모든 항목에 할당된 보존 레이블과 기록에 해당하는 항목을 한눈에 확인할 수 있습니다. 그렇지만 **기록 항목임** 열을 기준으로는 보기를 필터링할 수 없습니다. 
  
![사용자 지정 보기에 표시된 레이블에 대한 라이브러리 열](../media/e3392627-c0a3-405e-bb57-55f27c34cfdd.png)
  
### <a name="office-365-groups"></a>Office 365 그룹

Office 365 그룹에 보존 레이블을 게시하면 웹용 Outlook의 그룹 사이트와 그룹 사서함에 보존 레이블에 나타납니다. 콘텐츠에 보존 레이블을 적용하는 환경은 전자 메일 및 문서에 대해 위에 표시된 환경과 동일합니다.

Office 365 그룹 콘텐츠를 보존하려면 Office 365 그룹 위치를 사용해야 합니다. Office 365 그룹이 Exchange 사서함을 보유하고 있더라도 전체 Exchange 위치를 포함하는 보존 정책이 Office 365 그룹 사서함의 콘텐츠를 포함하지는 않습니다.

또한 Exchange 위치를 사용하여 특정 그룹 사서함을 포함하거나 제외할 수 없습니다. 초기에 Exchange 위치가 선택될 그룹 사서함을 허용하더라도 보존 정책을 저장하려고 시도할 때 “RemoteGroupMailbox”가 Exchange 위치에 유효하지 않은 선택이라는 오류가 나타나게 됩니다.
  
## <a name="applying-a-retention-label-automatically-based-on-conditions"></a>조건에 따라 자동으로 보존 레이블 적용

보존 레이블의 가장 강력한 기능 중 하나는 특정 조건과 일치하는 콘텐츠에 자동으로 레이블을 적용하는 기능입니다. 이 경우 조직의 사용자는 레이블을 적용할 필요가 없습니다. Office 365에서 이 작업을 수행합니다.
  
![자동 적용 레이블의 역할 및 작업 다이어그램](../media/32f2f2fd-18a8-43fd-839d-72ad7a43e069.png)
  
자동 적용 보존 레이블은 다음과 같은 기능 때문에 강력합니다.
  
- 사용자에게 모든 분류를 교육할 필요가 없습니다.
    
- 모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.
    
- 사용자가 더 이상 데이터 거버넌스 정책을 알아야 할 필요가 없으며, 업무에 집중할 수 있습니다.
    
콘텐츠에 다음이 포함될 경우 콘텐츠에 자동으로 보존 레이블을 적용하도록 선택할 수 있습니다.
  
- [특정 중요한 정보 유형](#auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information)
    
- [만든 쿼리와 일치하는 특정 키워드](#auto-apply-labels-to-content-with-keywords-or-searchable-properties)

- [학습 가능한 분류자와 일치](#auto-apply-labels-to-content-by-using-trainable-classifiers)
    
![자동 적용 레이블에 대한 조건 페이지 선택](../media/classifier-pre-trained-apply-label-match-trainable-classifier.png)

구성한 조건과 일치하는 모든 콘텐츠에 자동 적용 보존 레이블을 적용하는 데 최대 7일이 걸릴 수 있습니다.
  
> [!TIP]
> SharePont에서 관리 속성을 사용하여 보존 레이블을 자동 적용하고 이벤트 중심 보존을 구현하는 방법에 대한 자세한 시나리오는 [보존 레이블로 SharePoint 문서의 수명 주기 관리](auto-apply-retention-labels-scenario.md)를 참조하세요.

### <a name="auto-apply-retention-labels-to-content-with-specific-types-of-sensitive-information"></a>특정 유형의 중요한 정보가 있는 콘텐츠에 보존 레이블 자동 적용

중요한 정보에 대한 자동 적용 보존 레이블을 만들면 DLP(데이터 손실 방지) 정책을 만들 때 같은 정책 템플릿 목록이 표시됩니다. 각 정책 템플릿은 특정 중요한 정보 유형을 찾도록 미리 구성되어 있습니다. 예를 들어, 여기에 표시된 템플릿은 미국 ITIN, SSN 및 여권 번호를 검색합니다. DLP에 대한 자세한 내용은 [데이터 손실 방지 정책 개요](data-loss-prevention-policies.md)를 참조하세요.
  
![중요한 정보 유형을 갖는 정책 템플릿](../media/dafd87d4-c7bb-439a-ac7b-193c018f98a5.png)
  
정책 템플릿을 선택한 후 임의 유형의 중요한 정보를 추가하거나 제거하고, 인스턴스 수 및 일치 정확도를 변경할 수 있습니다. 여기에 표시된 예제에서는 다음 경우에만 보존 레이블이 자동 적용됩니다.
  
- 콘텐츠에 이러한 세 가지 중요한 정보 유형 중 어느 하나의 1~9개 인스턴스가 포함되어 있습니다. **max** 값을 삭제하여 **any**로 변경할 수 있습니다.
    
- 검색된 중요한 정보 유형은 75 이상의 일치 정확도(또는 신뢰도)를 갖습니다. 많은 중요한 정보 유형은 여러 패턴으로 정의되고, 일치 정확도가 더 높은 패턴에서는 더 많은 증거(예: 키워드, 날짜 또는 주소)가 검색되어야 합니다. 일치 정확도가 더 낮은 패턴은 증거가 덜 요구합니다. 간단히 말해서 **min** 일치 정확도가 더 낮을수록 콘텐츠가 조건과 일치하기가 더 쉽습니다. 
    
이 옵션에 대한 자세한 내용은 [더 쉽게 또는 더 어렵게 일치하도록 규칙 조정](data-loss-prevention-policies.md#tuning-rules-to-make-them-easier-or-harder-to-match)을 참조하세요.
    
![중요한 정보 유형을 식별하기 위한 옵션](../media/de255881-f596-4c8d-8359-e974e3a0819a.png)
  
### <a name="auto-apply-labels-to-content-with-keywords-or-searchable-properties"></a>키워드 또는 검색 가능 속성이 있는 콘텐츠에 레이블 자동 적용

특정 조건을 충족하는 콘텐츠에 레이블을 자동으로 적용할 수 있습니다. 현재 사용 가능한 조건은 특정 단어, 구 또는 검색 가능 속성 값을 포함하는 콘텐츠에만 레이블을 적용하도록 지원합니다. AND, OR 및 NOT과 같은 검색 연산자를 사용하여 쿼리를 구체화할 수 있습니다.

쿼리 구문에 대한 자세한 내용은 다음을 참조하세요.

- [KQL(키워드 쿼리 언어) 구문 참조](https://docs.microsoft.com/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

쿼리 기반 레이블은 검색 인덱스를 사용하여 콘텐츠를 식별합니다. 유효한 검색 가능 속성에 대한 자세한 내용은 다음을 참조하세요.

- [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)
- [SharePoint Server에서 크롤링 및 관리 속성의 개요](https://docs.microsoft.com/SharePoint/technical-reference/crawled-and-managed-properties-overview)

예제 쿼리:

- Exchange
    - subject:"Quarterly Financials"
    - recipients:garthf<!--nolink-->@contoso.com
- SharePoint 및 비즈니스용 OneDrive
    - contenttype:contract
    - site:https<!--nolink-->://contoso.sharepoint.com/sites/teams/procurement AND contenttype:contract

![쿼리 편집기](../media/ac5b8e5e-7453-4ec7-905c-160df57298d3.png)


### <a name="auto-apply-labels-to-content-by-using-trainable-classifiers"></a>학습 가능한 분류자를 사용하여 콘텐츠에 레이블 자동 적용

학습 가능한 분류자 옵션을 선택할 때 기본 분류자 중 하나 또는 사용자 지정 분류자를 선택할 수 있습니다. 기본 분류자에는 **공격 언어**, **이력서**, **소스 코드**, **대상 희롱**, **비속어** 및 **위협**이 포함됩니다:

![학습 가능한 분류자 선택](../media/retention-label-classifers.png)

이 옵션을 사용하여 레이블을 자동으로 적용하려면 SharePoint Online 사이트 및 사서함에 10MB 이상의 데이터가 있어야 합니다.

학습 가능한 분류자에 대한 자세한 내용은 [학습 가능한 분류자 시작(미리 보기)](classifier-getting-started-with.md)를 참조하세요.

구성 예는 [분류자를 준비하고 기본 제공 분류자를 사용하는 방법](classifier-using-a-ready-to-use-classifier.md#how-to-prepare-for-and-use-a-built-in-classifier)을 참조하세요.

## <a name="applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set"></a>SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 콘텐츠에 기본 보존 레이블 적용

사용자가 개별 문서에 보존 레이블을 적용할 수 있도록 하는 것 외에, SharePoint 라이브러리, 폴더 또는 문서 집합의 모든 문서에 기본 보존 레이블이 적용되도록 해당 위치에 기본 보존 레이블을 적용할 수도 있습니다.
  
문서 라이브러리의 경우 이 작업은 문서 라이브러리의 **라이브러리 설정** 페이지에서 수행합니다. 기본 보존 레이블을 선택하는 경우 라이브러리의 기존 항목에 적용하도록 선택할 수도 있습니다. 
  
예를 들어 마케팅 자료에 대한 태그가 있고 특정 문서 라이브러리에 해당 유형의 콘텐츠만 포함된다는 것을 알 경우 마케팅 자료 태그를 해당 라이브러리의 모든 문서에 대한 기본 태그로 지정할 수 있습니다.
  
![라이브러리 설정 페이지의 레이블 적용 옵션](../media/0787d651-63dc-43b4-8768-716a5ecc64ec.png)
  
라이브러리, 폴더 또는 문서 집합의 기존 항목에 기본 보존 레이블을 적용하는 경우 다음 작업이 수행됩니다.
  
- 명시적으로 적용된 보존 레이블이 있는 항목(예: 레코드)의 경우를 **제외하고** 라이브러리, 폴더 또는 문서의 모든 항목에 자동으로 같은 보존 레이블이 적용됩니다. 명시적으로 레이블이 지정된 항목은 기존 레이블을 유지합니다. 자세한 내용은 [보존 원칙 또는 우선 순위](#the-principles-of-retention-or-what-takes-precedence)에 대한 아래 섹션을 참조하세요.
    
- 라이브러리, 폴더 또는 문서 집합의 기본 보존 레이블을 변경하거나 제거하는 경우 명시적 보존 레이블이 지정된 항목(예: 레코드)을 **제외하고** 라이브러리, 폴더 또는 문서 집합의 모든 항목에 대해서도 보존 레이블이 변경되거나 제거됩니다.
    
- 한 사이트 컬렉션, 라이브러리, 폴더 또는 문서 집합에서 기본 보존 레이블이 있는 항목을 다른 사이트 컬렉션, 라이브러리, 폴더 또는 다른 레이블이 있는 문서 집합으로 이동하면 새 위치에 다른 기본 보존 레이블이 있더라도 해당 항목은 기존의 기본 보존 레이블을 유지합니다. 항목을 이동하기 전에 레이블이 없으면 새 위치의 기본 보존 레이블을 사용합니다.

**레코드:** 라이브러리, 폴더 또는 문서 집합에 기본 레코드 레이블을 적용하면 해당 위치 내의 모든 개별 항목에 레코드 레이블이 적용됩니다. 새 항목을 레코드 레이블을 사용하여 위치로 이동하면 해당 항목에 레코드 레이블이 지정됩니다. 그러나 콘텐츠를 레코드로 선언하지 않는 레이블로 기본 보존 레이블을 변경하는 경우 해당 작업은 개별 항목에서 레코드 레이블을 제거하지 **않습니다**. 해당 항목은 레코드 레이블을 보존합니다. 사이트 모음 관리자는 레코드 항목의 보존 레이블을 명시적으로 제거하거나 변경할 수 있습니다.

콘텐츠를 레코드로 선언하는 보존 레이블에 대한 자세한 내용은 [레코드 개요](records.md)를 참조하세요.
    
## <a name="applying-a-retention-label-to-email-by-using-rules"></a>규칙을 사용하여 전자 메일에 보존 레이블 적용

Outlook 2010 이상에서는 보존 레이블 또는 보존 정책을 적용하는 규칙을 만들 수 있습니다.
  
예를 들어, 특정 메일 그룹에서 보내고 받은 모든 메시지에 특정 보존 레이블을 적용하는 규칙을 만들 수 있습니다.
  
규칙을 만들려면 마우스 오른쪽 단추로 항목 \> **규칙** \> **규칙 만들기** \> **고급 옵션** \> **규칙 마법사** \> **보존 정책 적용**을 클릭합니다.
  
![보존 정책을 적용하는 옵션이 포함된 규칙 마법사](../media/eeb2407c-15b6-4224-99cf-e0a00034d8ea.png)
  
## <a name="classifying-content-without-applying-any-actions"></a>작업을 적용하지 않고 콘텐츠 분류

보존 레이블을 만들 때 아래에 표시된 것처럼 보존이나 기타 작업을 설정하지 않고 그대로 만들 수 있습니다. 이 경우 작업을 적용하지 않고 보존 레이블을 단순히 텍스트 레이블로 사용할 수 있습니다.
  
예를 들어, 작업 없이 “나중에 검토”라는 보존 레이블을 만든 다음, 해당 보존 레이블을 중요한 정보 유형을 갖는 콘텐츠 또는 쿼리된 콘텐츠에 자동으로 적용할 수 있습니다.
  
![보존이 해제된 레이블 설정 페이지](../media/17ce863b-a823-426e-aaad-83718465f762.png)
  
## <a name="using-retention-labels-for-records-management"></a>기록 관리에 보존 레이블 사용
    
보존 레이블을 사용하여 콘텐츠를 레코드로 선언할 수 있습니다. 따라서 Office 365에서 일관된 단일 레코드 관리 전략을 구현할 수 있습니다. 자세한 내용은 [레코드 개요](records.md)를 참조하세요.
  
## <a name="using-a-retention-label-as-a-condition-in-a-dlp-policy"></a>보존 레이블을 DLP 정책의 조건으로 사용

보존 레이블은 콘텐츠에 보존 작업을 적용할 수 있습니다. 또한 보존 레이블을 DLP(데이터 손실 방지) 정책의 조건으로 사용할 수 있고, DLP 정책은 특정 레이블이 있는 콘텐츠에 대해 액세스 제한과 같은 기타 작업을 적용할 수 있습니다. 
  
자세한 내용은 [레이블을 DLP 정책의 조건으로 사용](data-loss-prevention-policies.md#using-a-label-as-a-condition-in-a-dlp-policy)을 참조하세요.
  
## <a name="monitor-retention-labels"></a>보존 레이블 모니터링

보존 레이블을 게시하거나 자동으로 적용한 후에 의도대로 콘텐츠에 적용되는지 확인할 수 있습니다. 보존 레이블을 모니터링하려면 다음을 사용할 수 있습니다.
  
- **레이블 활동 탐색기**. 이 탐색기(아래 그림 참조)를 사용하면 지난 30일 동안 SharePoint 및 비즈니스용 OneDrive에서 사용된 모든 콘텐츠를 빠르게 검색하고 해당 보존 레이블 활동을 볼 수 있습니다. 자세한 내용은 [문서에 대한 레이블 활동 보기](view-label-activity-for-documents.md)를 참조하세요.

- **레이블 분석** 페이지. Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터에서 빠르게 상단 레이블 및 레이블이 적용된 위치를 볼 수 있습니다. 특정 레이블이 포함된 모든 콘텐츠를 볼 수 있습니다. 자세한 내용은 [레이블 분석을 사용한 레이블 사용량 보기](label-analytics.md)를 참조하세요.
    
- **데이터 거버넌스 보고서**. 이러한 보고서를 사용하면 지난 90일 동안 Exchange, SharePoint 및 비즈니스용 OneDrive에서 사용된 모든 콘텐츠에 대한 보존 레이블 추세 및 활동을 빠르게 확인할 수 있습니다. 자세한 내용은 [데이터 거버넌스 보고서 보기](view-the-data-governance-reports.md)를 참조하세요.
    
![레이블 활동 탐색기](../media/671ca0cd-1457-40b4-9917-b663360afd95.png)
  
## <a name="using-content-search-to-find-all-content-with-a-specific-retention-label-applied-to-it"></a>콘텐츠 검색을 사용하여 특정 보존 레이블이 적용된 모든 콘텐츠 찾기

사용자가 콘텐츠에 보존 레이블을 할당하거나 레이블이 자동 적용된 후에 콘텐츠 검색을 사용하여 특정 보존 레이블로 분류된 모든 콘텐츠를 찾을 수 있습니다.
  
콘텐츠 검색을 만들 때 **준수 태그** 조건을 선택한 후 전체 레이블 이름 또는 레이블 이름 일부를 입력하고 와일드카드를 사용합니다. 자세한 내용은 [콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건](keyword-queries-and-search-conditions.md)을 참조하세요.
  
![준수 태그 조건](../media/82d6af16-59f8-462f-babb-c894b2917018.png)
  
## <a name="the-principles-of-retention-or-what-takes-precedence"></a>보존 원칙 또는 우선 순위

콘텐츠에 각기 다른 작업(보존, 삭제 또는 둘 다) 및 보존 기간을 지정하는 여러 보존 정책이 적용될 수 있습니다. 우선 순위는 어떨까요? 분명한 것은 가장 높은 수준에서 한 정책을 통해 보존되는 콘텐츠가 다른 정책에 의해 영구적으로 삭제될 수 없다는 것입니다.
  
![보존 원칙 다이어그램](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
보존 작업이 있는 여러 다른 레이블이 콘텐츠에 적용되는 방식을 이해하려면 다음과 같은 보존 원칙에 유의합니다.
  
1. **보존이 삭제보다 우선합니다.** 한 보존 정책은 3년 후에 Exchange 전자 메일을 삭제하도록 지정하지만 다른 보존 정책은 5년 동안 Exchange 전자 메일을 보존했다가 삭제하도록 지정하는 경우를 가정해보세요. 3년에 도달한 모든 콘텐츠는 삭제되고 사용자가 볼 수 없게 숨겨지지만, 5년에 도달할 때까지 복구 가능한 항목 폴더에 보존되었다가 영구적으로 삭제됩니다. 
    
2. **가장 긴 보존 기간이 우선합니다.** 콘텐츠에 여러 콘텐츠 보존 정책이 적용되는 경우 가장 긴 보존 기간이 끝날 때까지 보존됩니다. 
    
3. **명시적 포함이 암시적 포함보다 우선합니다.** 이것은 다음을 의미합니다. 
    
    1. 보존 설정이 포함된 보존 레이블이 사용자에 의해 수동으로 항목(예: Exchange 전자 메일 또는 OneDrive 문서)에 할당된 경우 해당 보존 레이블은 사이트 또는 사서함 수준에서 할당된 정책이나 문서 라이브러리에 의해 할당된 기본 보존 레이블보다 우선합니다. 예를 들어 명시적 보존 레이블에서 10년 동안 보존하라고 하지만, 사이트에 할당된 보존 정책에서 5년 동안만 보존하라고 한다면 보존 레이블이 우선합니다. 자동 적용 보존 레이블은 Office 365에 의해 자동으로 적용되므로 명시적이 아니라 암시적으로 간주됩니다.
    
    2. 보존 정책에 특정 사용자의 사서함 또는 OneDrive용 비즈니스 계정과 같은 특정 위치가 포함되는 경우 해당 정책이 모든 사용자의 사서함 또는 비즈니스용 OneDrive 계정에 적용되지만 해당 사용자의 사서함을 특별히 포함하지 않는 다른 보존 정책보다 우선합니다.
    
4. **가장 짧은 삭제 기간이 우선적으로 적용됩니다.** 마찬가지로 콘텐츠에 여러 콘텐츠 삭제 정책이 적용되는 경우(보존 없음) 가장 짧은 보존 기간이 끝나면 삭제됩니다. 
    
보존 원칙은 위에서 아래로 균형을 깨는 흐름처럼 작동한다는 점을 이해하도록 합니다. 모든 정책 또는 레이블에 의해 적용되는 규칙이 하나의 수준에서 동일한 경우 규칙이 적용되는 우선 순위를 결정하기 위해 흐름은 아래의 다음 수준으로 이동합니다.
  
마지막으로, 보존 정책 또는 레이블은 eDiscovery 보류 상태인 콘텐츠를 영구적으로 삭제할 수 없습니다. 보류가 해제되면 다시 위에 설명된 정리 프로세스가 해당 콘텐츠에 적용됩니다.

### <a name="precedence-for-auto-labeling-with-trainable-classifiers"></a>학습 가능한 분류 기준을 사용한 자동 레이블링 우선 순위

학습 가능한 분류 기준으로 구성된 모든 보존 레이블이 동시에 평가됩니다. 교육 가능한 분류 기준이 둘 이상인 항목이 감지되면 다음 기준을 사용하여 적용할 보존 레이블을 결정합니다.

1. 유지 전용 또는 유지 및 삭제용으로 구성된 보존 레이블은 삭제 전용으로 구성된 보존 레이블보다 우선 순위가 높습니다.

2. 보존 전용 또는 보존 및 삭제용으로 구성된 보존 레이블의 경우 가장 긴 보존 기간 동안 구성된 보존 레이블이 우선합니다.

3. 삭제 전용으로 구성된 보존 레이블의 경우 가장 짧은 기간 동안 구성된 보존 레이블이 우선합니다.

4. 동작과 기간이 같은 보존 레이블에는 유지되는 보존 레이블 선택이 포함됩니다.

## <a name="use-retention-labels-instead-of-these-features"></a>이러한 기능 대신 보존 레이블 사용

보존 레이블은 Exchange, SharePoint, OneDrive 및 Office 365 그룹을 포함하여 Office 365의 전체 조직 및 해당 콘텐츠에서 쉽게 사용할 수 있습니다. Office 365의 임의 위치에서 콘텐츠를 분류하거나 기록을 관리해야 하는 경우 보존 레이블을 사용하는 것이 좋습니다.
  
이전에 Office 365에서 콘텐츠를 분류하거나 레코드를 관리하는 데 사용된 다른 여러 기능이 있습니다. 이러한 기능은 아래에 나열되어 있습니다. 이러한 기능은 보존 레이블과 함께 계속해서 작동합니다. 보존 레이블 구현이 이전 기능과 다른 경우가 있기는 하지만, 보존 레이블이 발전하면서 앞으로 Office 365에서 레코드를 더 편리하게 관리할 수 있게 될 것입니다. 따라서 앞으로 데이터 거버넌스의 경우 이러한 기능 대신 보존 레이블을 사용하는 것이 좋습니다.
  
### <a name="exchange-online"></a>Exchange Online

- [보존 태그 및 보존 정책](https://go.microsoft.com/fwlink/?linkid=846125)[[MRM(메시징 기록 관리)라고도 함]](https://go.microsoft.com/fwlink/?linkid=846126)(삭제만 해당) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online 및 비즈니스용 OneDrive

- [ 현재 위치 기록 관리 구성](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a)(보존) 
    
- [기록 센터 소개](https://support.office.com/article/bae6ca5a-7b19-40e0-b433-e3613a747c2c) (보존) 
    
- [정보 관리 정책](intro-to-info-mgmt-policies.md)(삭제만 해당) 
    
## <a name="permissions"></a>권한

보존 레이블을 만드는 규정 준수 팀의 구성원은 보안 및 준수 센터에 대한 사용 권한이 필요합니다. 기본적으로 테넌트 관리자는 이 위치에 액세스할 수 있으며, 준수 관리자 및 기타 사용자에게 테넌트 관리를 위한 모든 권한을 부여하지는 않으면서, 보안 및 준수 센터에 대한 액세스 권한을 부여할 수 있습니다. 이렇게 하기 위해 보안 및 준수 센터의 **권한** 페이지로 이동한 후 **준수 관리자** 역할 그룹을 편집하고 해당 역할 그룹에 구성원을 추가하는 것이 좋습니다. 
  
자세한 내용은 [사용자에게 Office 365 보안 및 준수 센터에 대한 액세스 권한 부여](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)를 참조하세요.
  
이러한 정책은 보존 레이블 및 레이블 정책을 만들고 적용하는 데만 필요합니다. 정책 적용을 위해서는 콘텐츠에 액세스하지 않아도 됩니다.  
## <a name="find-the-powershell-cmdlets-for-labels"></a>레이블에 대한 PowerShell cmdlet 찾기

레이블 cmdlet을 사용하려면 다음 작업을 수행해야 합니다.
  
1. [Office 365 보안 및 준수 센터 PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)
    
2. 다음 Office 365 보안 및 준수 센터 cmdlet 사용:

  - [Get-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetag)

  - [New-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-compliancetag)

  - [Remove-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-compliancetag)

  - [Set-ComplianceTag](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-compliancetag)

  - [Enable-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/enable-compliancetagstorage)

  - [Get-ComplianceTagStorage](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-compliancetagstorage)

  - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)

  - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)

  - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)

  - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)

  - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)

  - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)

  - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)

  - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)
