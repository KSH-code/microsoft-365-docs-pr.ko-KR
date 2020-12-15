---
title: Microsoft 365에서 항목 검색 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365에서 항목 검색을 관리하는 방법을 학습합니다.
ms.openlocfilehash: 035fb74f1989dc7ef5b7fcf8e9c6d59b63cf2b42
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667893"
---
# <a name="manage-topic-discovery-in-microsoft-365"></a>Microsoft 365에서 항목 검색 관리

[Microsoft 365](https://admin.microsoft.com)관리 센터에서 항목 검색 설정을 관리할 수 있습니다. 이러한 작업을 수행하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.

## <a name="to-access-topics-management-settings"></a>항목 관리 설정에 액세스하려면

1. Microsoft 365 관리 센터에서 설정, Org 설정을 **클릭합니다.**
2. 서비스 **탭에서** 기술 **네트워크를 클릭합니다.**

    ![지식에 사람 연결](../media/admin-org-knowledge-options-completed.png) 

3. 항목 검색 **탭을** 선택합니다. 각 설정에 대한 자세한 내용은 다음 섹션을 참조하세요.

    ![knowledge-network-settings](../media/knowledge-network-settings-topic-discovery.png) 

## <a name="select-sharepoint-topic-sources"></a>SharePoint 항목 원본 선택

항목에 대해 크롤링할 조직의 SharePoint 사이트를 변경할 수 있습니다.

특정 사이트 목록을 포함하거나 제외하려는 경우 다음 .csv 템플릿을 사용할 수 있습니다.

``` csv
Site name,URL
```

사이트 선택을 사용하여 사이트를 추가하는 경우 포함하거나 제외할 기존 사이트 목록에 사이트가 추가됩니다. .csv 파일을 업로드하면 기존 목록을 덮어 덮어 덮어니다. 이전에 특정 사이트를 포함하거나 제외한 경우 목록을 .csv 파일로 다운로드하고, 변경하고, 새 목록을 업로드합니다.

항목 검색을 위한 사이트를 선택

1. 항목 검색 **탭의** **SharePoint** 항목 원본 선택 아래에서 편집을 **선택합니다.**
2. **SharePoint** 항목 원본 선택 페이지에서 검색 중에 항목에 대한 원본으로 크롤링할 SharePoint 사이트를 선택합니다. 해당 활동은 다음과 같습니다.
    - **모든 사이트**: 테넌트의 모든 SharePoint 사이트 이렇게 하여 현재 및 향후 사이트를 캡처합니다.
    - **선택한 사이트를 제외한** 모든 사이트: 제외할 사이트의 이름을 입력합니다.  검색에서 옵트아웃하려는 사이트 목록을 업로드할 수도 있습니다. 앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함됩니다. 
    - **선택한 사이트만**: 포함할 사이트의 이름을 입력합니다. 사이트 목록을 업로드할 수도 있습니다. 앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함되지 않습니다.
    - **사이트 없음**: 항목은 SharePoint 콘텐츠로 자동으로 생성되거나 업데이트되지 않습니다. 기존 항목은 항목 센터에 남아 있습니다.

    ![SharePoint 항목 원본 사용자 인터페이스 스크린샷](../media/k-manage-select-topic-source.png)
   
3. **저장** 을 클릭합니다.

## <a name="exclude-topics-by-name"></a>이름으로 항목 제외

.csv 파일을 사용하여 목록을 업로드하여 검색에서 항목을 제외할 수 있습니다. 이전에 항목을 제외한 경우 .csv를 다운로드하고 변경한 후 다시 업로드할 수 있습니다.

1. 항목 검색 **탭의** **제외 항목 아래에서** 편집을 **선택합니다.**
2. 이름으로 **항목 제외를 클릭합니다.**
3. 목록을 만들어야 하는 경우 .csv 템플릿을 다운로드하고 제외할 항목을 추가합니다(아래 *.csv* 템플릿 작업 참조). 파일이 준비되면 찾아보기를 **클릭하고** 파일을 업로드합니다. 기존 목록이 있는 경우 목록이 포함된 .csv를 다운로드할 수 있습니다.
4. **저장** 을 클릭합니다.

    ![제외 항목 사용자 인터페이스 스크린샷](../media/km-manage-exclude-topics.png)

### <a name="working-with-the-csv-template"></a>.csv 템플릿 작업

아래 csv 템플릿을 복사할 수 있습니다.

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

CSV 템플릿에서 제외할 항목에 대한 다음 정보를 입력합니다.

- **이름:** 제외할 항목의 이름을 입력합니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.
    - 정확한 일치: 정확한 이름이나 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*
    - 부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.  예를 들어 *호는* 호 원, 마주치기 또는 교육 호와 같이 단어 호가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외하지 *않습니다.*
- **약어(선택 사항)**: 약어를 제외하려는 경우 약어가 대명하는 단어를 입력합니다.
- **MatchType-Exact/Partial**: 입력한 이름이 정확히 일치하는 형식인지 부분 일치 *형식인지* *여부를* 입력합니다.

    ![CSV 템플릿의 항목 제외](../media/exclude-topics-csv.png) 

## <a name="see-also"></a>참고 항목

[Microsoft 365에서 항목 표시 관리](topic-experiences-knowledge-rules.md)

[Microsoft 365에서 항목 사용 권한 관리](topic-experiences-user-permissions.md)

[Microsoft 365에서 항목 센터의 이름 변경](topic-experiences-administration.md)

