---
title: 감사 로그에서 공유 감사 사용
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.collection:
- M365-security-compliance
- SPO_Content
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: 관리자는 조직 외부의 사용자와 공유되는 리소스를 식별하기 위해 Microsoft 365 감사 로그에서 공유 감사를 사용하는 방법을 배울 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ff05b655617608332b4b838e07a6af55e8b4d010
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193174"
---
# <a name="use-sharing-auditing-in-the-audit-log"></a>감사 로그에서 공유 감사 사용

공유는 SharePoint Online 및 비즈니스용 OneDrive 주요 활동으로, 조직에서 널리 사용됩니다. 관리자는 감사 로그에서 공유 감사를 사용하여 조직에서 공유가 사용되는 방법을 확인할 수 있습니다. 
  
## <a name="the-sharepoint-sharing-schema"></a>공유 SharePoint 공유

공유 이벤트(공유 정책 및 공유 링크와 관련된 이벤트는 포함하지 않는)는 한 사용자가 다른 사용자에게 영향을 미치기 위한 작업을 수행하는 한 가지 기본 방법으로 파일 및 폴더 관련 이벤트와 다릅니다. 예를 들어 리소스 사용자 A가 사용자 B에게 파일에 대한 액세스 권한을 부여할 때 이 예에서 사용자 A는 행동하는 *사용자이자* 사용자 B는 대상 *사용자입니다.* 파일 SharePoint 실행 사용자의 동작은 파일 자체에만 영향을 미치게 됩니다. 사용자 A가 파일을 열면 **FileAccessed** 이벤트에 필요한 유일한 정보는 역할을 하는 사용자입니다. 이러한 차이를 해결하기 위해 공유 이벤트에 대한 자세한 정보를 캡처하는 SharePoint 공유 SharePoint 별도의 *schema가* 있습니다. 이렇게 하면 관리자가 리소스를 공유한 사용자와 리소스를 공유한 사용자를 쉽게 확인하게 됩니다. 
  
공유 Schema는 공유 이벤트와 관련된 감사 레코드에 다음 두 개의 추가 필드를 제공합니다. 
  
- **TargetUserOrGroupType:** 대상 사용자 또는 그룹이 구성원, 게스트, SharePointGroup, SecurityGroup 또는 Partner인지 여부를 식별합니다.

- **TargetUserOrGroupName:** 리소스가 공유된 대상 사용자 또는 그룹의 UPN 또는 이름을 저장합니다(이전 예제의 사용자 B). 

이러한 두 필드는 사용자, 작업 및 날짜와 같은 감사 로그 스마마의 다른  속성 외에도  누가  누구와 언제 어떤 리소스를 공유한 사용자에 대한 전체 스토리를 알려 *주어질 수 있습니다.* 
  
공유 스토리에 중요한 또 다른 schema 속성이 있습니다. 감사 로그 검색 결과를 내보낼 때 내보낼 CSV 파일의 **AuditData** 열에는 공유 이벤트에 대한 정보가 저장됩니다. 예를 들어 사용자가 다른 사용자와 사이트를 공유하는 경우 이 작업을 수행하기 위해 대상 사용자를 SharePoint 있습니다. **AuditData 열은** 이 정보를 캡처하여 관리자에게 컨텍스트를 제공합니다. **AuditData** 열의 정보를 구문 분석하는 방법에 대한 지침은 [2단계를](#step-2-use-the-powerquery-editor-to-format-the-exported-audit-log) 참조하세요.

## <a name="sharepoint-sharing-events"></a>SharePoint 공유 이벤트

공유는 사용자(작업하는 사용자)가 다른 사용자(대상 사용자)와 리소스를 공유하려는 경우 *정의됩니다.*  외부 사용자(조직 외부에 있으며 조직의 Azure Active Directory에 게스트 계정이 없는 사용자)와 리소스를 공유하는 데 관련된 감사 레코드는 감사 로그에 기록되는 다음 이벤트로 식별됩니다.

- **SharingInvitationCreated:** 조직의 사용자가 외부 사용자와 리소스(사이트)를 공유하려고 했습니다. 그러면 대상 사용자에게 외부 공유 초대가 전송됩니다. 이때 리소스에 대한 액세스 권한이 부여됩니다.

- **SharingInvitationAccepted:** 외부 사용자가 작업 사용자가 보낸 공유 초대를 수락하고 이제 리소스에 액세스할 수 있습니다.

- **AnonymousLinkCreated:** 리소스에 대해 익명 링크("모든 사용자" 링크)가 만들어집니다. 익명 링크를 만든 다음 복사할 수 있기 때문에 익명 링크가 있는 문서가 대상 사용자와 공유된 것으로 가정하는 것이 타당합니다.

- **AnonymousLinkUsed:** 이름에서 알 수 있는 것 처럼 이 이벤트는 리소스에 액세스하는 데 익명 링크를 사용할 때 기록됩니다. 

- **SecureLinkCreated:** 사용자가 특정 사용자와 리소스를 공유하기 위한 "특정 사용자 링크"를 만들었다고 합니다. 이 대상 사용자는 조직 외부의 사용자일 수 있습니다. 리소스가 공유되는 사람은 **AddedToSecureLink** 이벤트에 대한 감사 레코드에서 식별됩니다. 이 두 이벤트의 타임스탬프는 거의 동일합니다.

- **AddedToSecureLink:** 사용자가 특정 사용자 링크에 추가되었습니다. 이 **이벤트의 TargetUserOrGroupName** 필드를 사용하여 해당 특정 사용자 링크에 추가된 사용자를 식별합니다. 이 대상 사용자는 조직 외부의 사용자일 수 있습니다.

## <a name="sharing-auditing-work-flow"></a>감사 작업 흐름 공유
  
사용자(작업하는 사용자)가 다른 사용자(대상 사용자)와 리소스를 공유하려는 경우 SharePoint(또는 비즈니스용 OneDrive)는 먼저 대상 사용자의 전자 메일 주소가 조직의 디렉터리에 있는 사용자 계정과 이미 연결되어 있는지 확인합니다. 대상 사용자가 디렉터리에 있으며 해당 게스트 사용자 계정을 SharePoint 다음을 합니다.
  
-  적절한 SharePoint 그룹에 대상 사용자를 추가하여 리소스에 액세스할 수 있는 권한을 대상 사용자에게 즉시 할당하고 **AddedToGroup** 이벤트를 기록합니다. 
    
- 대상 사용자의 전자 메일 주소로 공유 알림을 전송합니다.
    
- **SharingSet 이벤트를 기록합니다.** 이 이벤트에는 감사 로그 검색 도구의 활동 선택기에서 공유 및 액세스 요청 활동 아래에 "공유 파일, 폴더 또는 사이트"라는 이름이 있습니다.  1단계의 [스크린샷을 참조하세요.](#step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file) 
    
대상 사용자에 대한 사용자 계정이 디렉터리에 없는 경우 다음 SharePoint 합니다. 
    
   - 리소스가 공유되는 방식에 따라 다음 이벤트 중 하나를 기록합니다.
   
      - **AnonymousLinkCreated**
   
      - **SecureLinkCreated**
   
      - **AddedToSecureLink** 

      - **SharingInvitationCreated(이** 이벤트는 공유 리소스가 사이트인 경우만 기록)
    
   - 대상 사용자가 초대의 링크를 클릭하여 전송된 공유 초대를 수락하면 SharePoint **SharingInvitationAccepted** 이벤트를 기록하고 리소스에 액세스하기 위한 대상 사용자 권한을 할당합니다. 대상 사용자가 익명 링크를 보내면 대상 사용자가 링크를 사용하여 리소스에 액세스한 후 **AnonymousLinkUsed** 이벤트가 기록됩니다. 보안 링크의 경우 외부 사용자가 링크를 사용하여 리소스에 액세스할 때 **FileAccessed** 이벤트가 기록됩니다.

초대를 수락하는 사용자의 ID 및 초대를 수락한 사용자의 ID 등 대상 사용자에 대한 추가 정보도 기록됩니다. 경우에 따라 이러한 사용자(또는 전자 메일 주소)가 다를 수 있습니다. 

## <a name="how-to-identify-resources-shared-with-external-users"></a>외부 사용자와 공유되는 리소스를 식별하는 방법

관리자의 일반적인 요구 사항은 조직 외부의 사용자와 공유된 모든 리소스 목록을 만드는 것입니다. 관리자가 공유 감사를 사용하여 Office 365 목록을 생성할 수 있습니다. 이 작업을 수행하는 방법은 다음과 같습니다.
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>1단계: 공유 이벤트 검색 및 CSV 파일로 결과 내보내기

첫 번째 단계는 감사 로그에서 공유 이벤트를 검색하는 것입니다. 감사 로그 검색에 대한 자세한 내용은 (필요한 사용 권한 포함) 감사 로그 [검색을 참조하세요.](search-the-audit-log-in-security-and-compliance.md)
  
1. <https://compliance.microsoft.com>으로 이동합니다.

2. 회사 또는 학교 계정을 사용하여 로그인합니다.

3. Microsoft 365 준수 센터의 왼쪽 창에서 **감사** 를 클릭합니다.

    **감사** 페이지가 표시됩니다.

4. **활동에서** 공유 **및** 액세스 요청 활동을 클릭하여 공유 관련 이벤트를 검색합니다. 

    ![활동에서 공유 및 액세스 요청 활동을 선택합니다.](../media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5. 날짜 및 시간 범위를 선택하여 해당 기간 내에 발생한 공유 이벤트를 찾을 수 있습니다. 

6. 검색을 **클릭하여** 검색을 실행합니다. 

7. 검색 실행이 완료되고 결과가 표시되면 결과 내보내기 **모든** 결과 \> **다운로드 를 클릭합니다.**

    내보내기 옵션을 선택하면 창 아래쪽에 CSV 파일을 열거나 저장하라는 메시지가 표시됩니다.

8. 다른  \> **파일로 저장을** 클릭하고 CSV 파일을 로컬 컴퓨터의 폴더에 저장합니다. 

### <a name="step-2-use-the-powerquery-editor-to-format-the-exported-audit-log"></a>2단계: PowerQuery 편집기를 사용하여 내보낼 감사 로그 형식 지정

다음 단계는 다중 속성 JSON 개체로 구성된 **AuditData** 열의 각 속성을 Excel 쿼리 편집기에서 JSON 변환 기능을 사용하여 자체 열로 분할하는 것입니다. 이렇게 하면 열을 필터링하여 공유와 관련된 레코드를 볼 수 있습니다.

단계별 지침을 보려면 [감사 로그 레코드 내보내기, 구성 및 보기](export-view-audit-log-records.md#step-2-format-the-exported-audit-log-using-the-power-query-editor)의 “2단계: 파워 쿼리 편집기를 사용하여 내보낸 감사 로그의 서식 지정”을 참조하세요.

### <a name="step-3-filter-the-csv-file-for-resources-shared-with-external-users"></a>3단계: 외부 사용자와 공유되는 리소스에 대해 CSV 파일 필터링

다음 단계는 이전에 SharePoint 공유 이벤트 섹션에서 설명한 다른 공유 관련 이벤트에 대해 CSV를 [필터링하는](#sharepoint-sharing-events) 것입니다. 또는 **TargetUserOrGroupType** 열을 필터링하여 이 속성 값이 Guest인 모든 레코드를 표시할 **수 있습니다.** 

이전 단계의 지침을 따라 PowerQuery 편집기를 사용하여 CSV 파일을 준비한 후 다음을 수행하십시오.
    
1. 2단계에서 Excel 파일을 열 수 있습니다. 

2. 홈 **탭에서** 정렬 **필터를 &** 클릭한 다음 필터 를 **클릭합니다.**
    
3. 작업 **열의** 정렬 & 필터 드롭다운  목록에서 모든 선택을 취소한 다음 다음 공유 관련 이벤트를 하나 이상 선택한 다음 확인을 **클릭합니다.**
 
   - **SharingInvitationCreated**
   
   - **AnonymousLinkCreated**
   
   - **SecureLinkCreated**
   
   - **AddedToSecureLink** 
    
    Excel 선택한 이벤트의 행이 표시됩니다.
    
4. **TargetUserOrGroupType** 열로 이동하여 선택합니다. 
    
5. 정렬 & **필터** 드롭다운 목록에서 모든 선택을 지운 다음 **TargetUserOrGroupType:Guest를** 선택하고 확인을 **클릭합니다.**
    
    이제 Excel 외부 사용자가 **TargetUserOrGroupType:Guest** 값으로 식별되어 이벤트 및 대상 사용자가 조직 외부에 있는 위치를 공유하기 위한 행이 표시됩니다. 
  
> [!TIP]
> 표시되는 감사 레코드의 경우 **ObjectId** 열은 대상 사용자와 공유된 리소스를 식별합니다. 예를 들면  `ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx` 입니다.
