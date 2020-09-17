---
title: '지식 관리 네트워크 관리 (미리 보기) '
description: 지식 관리를 설정 하는 방법
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/01/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: None
ms.openlocfilehash: 3ca180dba82e677dbc0d9f112b713df14820ce61
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950775"
---
# <a name="manage-your-knowledge-management-network-preview"></a>지식 관리 네트워크 관리 (미리 보기)

> [!Note] 
> 이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.


[지식 관리를 설정한](set-up-knowledge-network.md)후에는 언제 든 지 관리자가 Microsoft 365 관리 센터를 통해 구성 설정을 조정할 수 있습니다.

예를 들어 다음 중 하나에 대 한 설정을 조정 해야 할 수 있습니다.
- 항목을 광산에 새 SharePoint 원본을 추가 합니다.
- 항목에 액세스할 사용자를 변경 합니다.
- 항목 센터에서 작업을 수행할 수 있는 권한이 있는 사용자를 변경 합니다.
- 주제 센터 이름 변경


## <a name="requirements"></a>요구 사항 
Microsoft 365 관리 센터에 액세스 하 고 조직의 기술 자료 작업을 관리 하려면 전역 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.


## <a name="to-access-knowledge-management-settings"></a>기술 항목 관리 설정에 액세스 하려면

1. Microsoft 365 관리 센터에서 **설치**를 선택 하 고 **조직의 기술 자료** 섹션을 확인 합니다.
2. **조직의 기술 자료** 섹션에서 **사용자에 게 자세한 정보 연결을**클릭 합니다.<br/>

    ![전문 지식을 사용자에 게 연결](../media/content-understanding/admin-org-knowledge-options.png) </br>

3. **사용자에 게 정보 연결** 페이지에서 **관리** 를 선택 하 여 **정보 네트워크 설정** 창을 엽니다.<br/>

    ![지식-네트워크-설정](../media/content-understanding/knowledge-network-settings.png) </br>

## <a name="change-how-the-knowledge-network-can-find-topics"></a>지식 네트워크에서 항목을 찾을 수 있는 방식 변경

SharePoint 항목 원본에 대 한 선택 사항을 업데이트 하려면 **항목 검색** 탭을 선택 합니다. 이 설정을 사용 하 여 테 넌 트에서 크롤링할 SharePoint 사이트를 선택 하 고 항목에 대 한 의견을 받을 수 있습니다.

1. **항목 검색** 탭의 **SharePoint 항목 소스 선택**에서 **편집**을 선택 합니다.
2. **Sharepoint 항목 원본 선택** 페이지에서 검색 중에 항목의 소스로 크롤링할 SharePoint 사이트를 선택 합니다. 여기에는 다음이 포함됩니다.</br>
    a. **모든 사이트**: 테 넌 트의 모든 SharePoint 사이트 현재 및 미래의 사이트를 캡처합니다.</br>
    b. **선택한 사이트를 제외한 모두 (모두**): 제외 하려는 사이트의 이름을 입력 합니다.  검색에서 옵트아웃 할 사이트의 목록을 업로드할 수도 있습니다. 앞으로 만들어진 사이트는 항목 검색의 원본으로 포함 됩니다. </br>
    c. **선택한 사이트만**: 포함 하려는 사이트의 이름을 입력 합니다. 사이트 목록을 업로드할 수도 있습니다. 앞에서 만든 사이트는 항목 검색의 원본으로 포함 되지 않습니다. </br>

    ![항목 검색 방법 선택](../media/content-understanding/k-manage-select-topic-source.png) </br>
   
    제외할 사이트가 여러 개 있는 경우 ( **모두, 선택한 사이트를 제외 하 고 모두**선택) 또는 포함 ( **선택한 사이트만**선택한 경우)을 선택 하 고 사이트 이름과 url을 사용 하 여 CSV 파일을 업로드 하도록 선택할 수 있습니다. CSV 서식 파일을 사용 하려는 경우에는 **사이트 서식 파일인 .Csv 다운로드** 를 선택할 수 있습니다.

3. **저장**을 선택합니다.

##  <a name="change-who-can-see-topics-in-your-organization"></a>조직의 항목을 볼 수 있는 사람 변경

조직에서 검색 결과의 검색 된 항목을 볼 수 있는 사용자를 업데이트 하 고 SharePoint 페이지와 같은 콘텐츠에서 항목을 강조 표시 하려면 **항목 검색** 탭을 선택 합니다.

1. **항목 검색** 탭의 **사용자가 정보 네트워크의 항목을 볼 수 있는 사람**아래에서 **편집**을 선택 합니다.
2. **정보 네트워크 페이지의 항목을 볼 수 있는 사용자** 는 강조 표시 된 항목, 항목 카드, 검색의 항목 대답 및 주제 페이지와 같은 항목 세부 정보에 액세스할 사용자를 선택 합니다. 다음을 선택할 수 있습니다.</br>
    a. **조직의 모든 사람**</br>
    b. **선택한 사용자 또는 보안 그룹만**</br>
    c. **아무도 없어**</br>

    ![항목을 볼 수 있는 사람](../media/content-understanding/k-manage-who-can-see-topics.png) </br> 
3. **저장**을 선택합니다.  
 
> [!Note] 
> 이 설정을 사용 하면 조직의 모든 사용자를 선택할 수 있지만, 기술 관리 라이선스가 할당 된 사용자만 항목을 볼 수 있습니다.

## <a name="change-who-has-permissions-to-do-tasks-on-the-topic-center"></a>항목 센터에서 작업을 수행할 수 있는 권한이 있는 사용자 변경

항목 센터 페이지에서 다음 작업을 수행할 수 있는 권한이 있는 사용자를 업데이트 하려면 **항목 사용 권한** 탭을 선택 합니다.

- 항목을 만들고 편집할 수 있는 사용자: 검색 하는 동안 발견 되지 않은 새 항목을 만들거나 기존 항목 페이지 세부 정보를 편집 합니다.
- 항목을 관리할 수 있는 사용자: 검색 된 항목 확인 또는 거부

항목을 만들고 편집할 수 있는 권한이 있는 사용자를 업데이트 하려면 다음을 수행 합니다.

1. **항목 권한** 탭의 **항목을 만들고 편집할 수 있는 사용자는 누구 입니까**?에서 **편집**을 선택 합니다.</br>
2. 주제를 **만들고 편집할 수 있는 사람** 페이지에서 다음을 선택할 수 있습니다.</br>
    a. **조직의 모든 사람**</br>
    b. **선택한 사용자 또는 보안 그룹만**</br>

    ![항목 만들기 및 편집](../media/content-understanding/k-manage-who-can-create-and-edit.png) </br> 

3. **저장**을 선택합니다.</br>

항목을 관리할 수 있는 권한이 있는 사용자를 업데이트 하려면 다음을 수행 합니다.

1. **항목 권한** 탭의 **항목을 관리할 수 있는 사용자**에서 **편집**을 선택 합니다.</br>
2. 주제를 **관리할 수 있는 사람** 페이지에서 다음을 선택할 수 있습니다.</br>
    a. **조직의 모든 사람**</br>
    b. **선택한 사용자 또는 보안 그룹**</br>

    ![항목 관리](../media/content-understanding/k-manage-who-can-manage-topics.png) </br> 

3. **저장**을 선택합니다.</br>


##  <a name="update-your-topic-center-name"></a>항목 센터 이름 업데이트

항목 센터의 이름을 업데이트 하려면 **항목 가운데** 탭을 선택 합니다. 

1. **항목 가운데** 탭의 **항목 센터 이름**에서 **편집**을 선택 합니다.
2. **항목 센터 이름 편집** 페이지의 **항목 센터 이름** 상자에 항목 센터의 새 이름을 입력 합니다.
3. **저장**을 선택합니다.

    ![항목 센터 이름 편집](../media/content-understanding/manage-topic-center-name.png) </br> 











## <a name="see-also"></a>참고 항목



  






