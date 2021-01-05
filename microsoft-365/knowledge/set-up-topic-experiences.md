---
title: Microsoft 365에서 항목 환경 설정
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
description: Microsoft 365에서 항목 환경을 설정하는 방법 학습
ms.openlocfilehash: d221f2932dc2ca9f562800b7b274e35e7f3d1db3
ms.sourcegitcommit: ae646779d84e993cf80b1207e76b856a21be5790
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/04/2021
ms.locfileid: "49749614"
---
# <a name="set-up-topic-experiences-in-microsoft-365"></a>Microsoft 365에서 항목 환경 설정

Microsoft 365 관리 센터를 사용하여 항목 환경을 설정하고 [구성할 수 있습니다.](topic-experiences-overview.md) 

환경에서 항목을 설정하고 구성하는 가장 좋은 방법을 계획하는 것이 중요합니다. 이 [문서의](plan-topic-experiences.md) 절차를 시작하기 전에 계획 항목 환경을 읽어 보아야 합니다.

Microsoft 365 관리 센터에 액세스하고 항목 환경을 설정하려면 전역 관리자 또는 SharePoint 관리자 되어야 합니다.

## <a name="video-demonstration"></a>동영상 데모

이 비디오에서는 Microsoft 365에서 항목 환경을 설정하는 프로세스를 보여줍니다.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topic-experiences"></a>주제 경험 설정

Microsoft 365에서 항목 환경을 설정하기 위해

1. Microsoft [365](https://admin.microsoft.com)관리 센터에서 설치를 **선택하고** 파일 및 콘텐츠 **섹션을** 시청합니다.
2. 파일 및 **콘텐츠 섹션에서** 사용자 **지식에 연결을 클릭합니다.**

    ![지식에 사람 연결](../media/admin-org-knowledge-options.png) 

3. 기술에 사용자 연결 **페이지에서**  시작을 클릭하여 설정 프로세스를 진행합니다.

    ![시작하기](../media/k-get-started.png) 

4. 지식 **네트워크에서 항목을** 찾을 수 있는 방법 선택 페이지에서 항목 검색을 구성합니다. **SharePoint** 항목 원본 선택 섹션에서 검색 중에 항목에 대한 원본으로 크롤링할 SharePoint 사이트를 선택합니다. 다음 중 선택:
    - **모든 사이트:** 조직의 모든 SharePoint 사이트 여기에는 현재 및 향후 사이트가 포함됩니다.
    - **선택한 사이트를 제외한** 모든 사이트: 제외할 사이트의 이름을 입력합니다.  검색에서 옵트아웃하려는 사이트 목록을 업로드할 수도 있습니다. 앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함됩니다. 
    - **선택한 사이트만**: 포함할 사이트의 이름을 입력합니다. 사이트 목록을 업로드할 수도 있습니다. 앞으로 만든 사이트는 항목 검색을 위한 원본으로 포함되지 않습니다.
    - **사이트 없음**: SharePoint 사이트를 포함하지 않습니다.

    ![항목을 찾는 방법 선택](../media/ksetup1.png) 
   
5. 이름 항목 **제외** 섹션에서 항목 검색에서 제외하려는 항목의 이름을 추가할 수 있습니다. 이 설정을 사용하여 중요한 정보가 항목으로 포함되지 않도록 합니다. 옵션은 다음과 같습니다.
    - **항목을 제외하지 않습니다.** 
    - **이름으로 항목 제외**

    ![제외 항목](../media/topics-excluded-by-name.png) 

    (지식 관리자는 검색 후 항목 센터의 항목을 제외할 수 있습니다.)

    #### <a name="how-to-exclude-topics-by-name"></a>이름으로 항목을 제외하는 방법    

    항목을 제외해야 하는 경우 이름으로 제외 항목을 선택한 후 .csv 템플릿을 다운로드하고 검색 결과에서 제외하려는 항목 목록으로 업데이트합니다.

    ![CSV 템플릿의 항목 제외](../media/exclude-topics-csv.png) 

    CSV 템플릿에서 제외할 항목에 대한 다음 정보를 입력합니다.

    - **이름:** 제외할 항목의 이름을 입력합니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.
        - 정확한 일치: 정확한 이름이나 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*
        - 부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.  예를 들어 *호는* 호 원, 마주치기 또는 교육 호와 같이 단어 호가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외하지 *않습니다.*
    - **약어(선택 사항)**: 약어를 제외하려는 경우 약어가 대명하는 단어를 입력합니다.
    - **MatchType-Exact/Partial**: 입력한 이름이 정확한지 부분 일치 *유형인지* *여부를* 입력합니다.

    .csv 파일을 완료하고 저장한 후 **찾아보기를** 선택하여 찾습니다.
    
    **다음** 을 선택합니다.

6. 항목을 **볼 수 있는 사람** 및 해당 항목을 볼 수 있는 위치 페이지에서 항목 표시를 구성합니다. 지식  네트워크 설정에서 항목을 볼 수 있는 사용자에서 강조 표시된 항목, 항목 카드, 검색의 항목 답변 및 항목 페이지와 같은 항목 세부 정보에 액세스할 수 있는 사용자 선택 다음을 선택할 수 있습니다.
    - **조직의 모든 사용자**
    - **선택한 사용자 또는 보안 그룹만**
    - **아무도 없어**

    ![항목을 볼 수 있는 사용자](../media/ksetup2.png)  

 > [!Note] 
 > 이 설정을 사용하면 조직의 모든 사용자를 선택할 수 있습니다. 그러나 항목에 항목 환경 라이선스가 할당된 사용자만 항목을 볼 수 있습니다.

7. 항목 관리에 **대한** 사용 권한 페이지에서 항목을 만들거나 편집하거나 관리할 수 있는 사용자들을 선택합니다. 항목을 **만들고 편집할 수** 있는 사용자 섹션에서 다음을 선택할 수 있습니다.
    - **조직의 모든 사용자**
    - **선택한 사용자 또는 보안 그룹만**
    - **아무도 없어**

    ![항목을 만들고 편집할 수 있는 항목 관리에 대한 사용 권한](../media/ksetup3.png) 

8. 항목 **관리를 할 수 있는 사용자 섹션에서** 다음을 선택할 수 있습니다.
    - **조직의 모든 사용자**
    - **선택한 사용자 또는 보안 그룹만**

    ![항목 관리에 대한 사용 권한](../media/km-setup-create-edit-topics.png) 

    **다음** 을 선택합니다.

9. 항목 센터 **만들기 페이지에서** 항목 페이지를 보고 항목을 관리할 수 있는 항목 센터 사이트를 만들 수 있습니다. 사이트 이름 **상자에** 항목 센터의 이름을 입력합니다. 필요한 경우 설명 상자에 간단한 설명을 입력할 **수** 있습니다. 

**다음** 을 선택합니다.

   ![기술 센터 만들기](../media/ksetup4.png)  

10. **검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다. 원하는 항목을 선택한 경우 **활성화** 를 선택합니다.

11. 기술 **자료 네트워크** 활성화 페이지가 표시되어 시스템에서 선택한 사이트가 항목에 대한 분석 및 기술 센터 사이트 만들기를 시작하게 됩니다. **완료** 를 선택합니다.

12. 기술에 대한 사용자 연결 **페이지로 돌아오게** 됩니다. 이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다. 

    ![적용된 설정](../media/ksetup7.png)    

## <a name="assign-licenses"></a>라이선스 할당

항목 환경을 구성한 후 항목 환경을 사용할 사용자에게 라이선스를 할당해야 합니다. 라이선스가 있는 사용자만 주요 항목, 항목 카드, 항목 페이지, 항목 센터 등의 항목에 대한 정보를 볼 수 있습니다. 

라이선스를 할당하려면 다음을 수행합니다.

1. Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.

2. 라이선스를 부여할 사용자를 선택하고 **제품 라이선스 관리** 를 클릭합니다.

3. **추가 할당** 을 선택합니다.

4. **라이선스에서** 항목 **환경을 선택합니다.**

5. 앱에서 **인덱스** 및 항목 환경이 포함된 **Graph Connectors** **검색이** 모두 선택되어 있는지 확인 합니다.

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 관리 센터의 SharePoint Syntex 라이선스](../media/topic-experiences-licenses.png)

6. **변경 사항 저장** 를 클릭합니다.

## <a name="manage-topic-experiences"></a>항목 환경 관리

항목 환경을 설정한 후 [Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)관리 센터에서 설치 중에 선택한 설정을 변경할 수 있습니다. 다음 참조를 참조합니다.

- [Microsoft 365에서 항목 검색 관리](topic-experiences-discovery.md)
- [Microsoft 365에서 항목 표시 관리](topic-experiences-knowledge-rules.md)
- [Microsoft 365에서 항목 사용 권한 관리](topic-experiences-user-permissions.md)
- [Microsoft 365에서 항목 센터의 이름 변경](topic-experiences-administration.md)

## <a name="see-also"></a>참고 항목

[항목 환경 개요](topic-experiences-overview.md)
