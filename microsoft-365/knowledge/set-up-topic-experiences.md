---
title: Microsoft Viva 항목 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Microsoft Viva 항목을 설정하는 방법 학습
ms.openlocfilehash: 629008e083d71e09632b05e21eaefb011d7d9ce2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929447"
---
# <a name="set-up-microsoft-viva-topics"></a>Microsoft Viva 항목 설정

Microsoft 365 관리 센터를 사용하여 항목을 설정하고 [구성할 수 있습니다.](topic-experiences-overview.md) 

환경에서 항목을 설정하고 구성하는 가장 좋은 방법을 계획하는 것이 중요합니다. 이 문서의 절차를 시작하기 전에 [Plan for Microsoft Viva Topics을](plan-topic-experiences.md) 읽어야 합니다.

Microsoft 365 관리 센터에 액세스하고 항목을 설정하려면 [Viva](https://www.microsoft.com/microsoft-viva/topics) 항목을 구독하고 전역 관리자 또는 SharePoint 관리자 되어야 합니다.

관리되는 장치가 필요하도록 [](/sharepoint/control-access-from-unmanaged-devices)SharePoint를 구성한 경우 관리되는 장치에서 항목을 설정해야 합니다.

## <a name="video-demonstration"></a>동영상 데모

이 비디오에서는 Microsoft 365에서 항목을 설정하는 프로세스를 보여줍니다.

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Li0E]  

<br>

## <a name="set-up-topics"></a>주제 설정

항목을 설정하기 위해

1. Microsoft [365 관리 센터에서](https://admin.microsoft.com)설치 를 선택한 다음 파일 및 **콘텐츠 섹션을** 니다. 
2. 파일 **및 콘텐츠 섹션에서** 기술에 **사용자 연결 을 클릭합니다.**

    ![지식에 사람 연결](../media/admin-org-knowledge-options.png) 

3. 기술에 사용자 연결 **페이지에서**  시작을 클릭하여 설정 프로세스를 진행합니다.

    ![시작](../media/k-get-started.png) 

4. **Viva 항목을 찾는 방법** 선택 페이지에서 항목 검색을 구성합니다. **SharePoint** 항목 원본 선택 섹션에서 검색 중에 항목에 대한 원본으로 크롤링할 SharePoint 사이트를 선택합니다. 다음 중 선택:
    - **모든 사이트:** 조직의 모든 SharePoint 사이트 여기에는 현재 및 향후 사이트가 포함됩니다.
    - **선택한 사이트를 제외한** 모든 사이트: 제외할 사이트의 이름을 입력합니다.  검색에서 옵트아웃하려는 사이트 목록을 업로드할 수도 있습니다. 향후 만들어진 사이트는 항목 검색을 위한 원본으로 포함됩니다. 
    - **선택한 사이트만:** 포함할 사이트의 이름을 입력합니다. 사이트 목록을 업로드할 수도 있습니다. 향후 만들어진 사이트는 항목 검색을 위한 원본으로 포함되지 않습니다.
    - **사이트 없음:** SharePoint 사이트를 포함하지 않습니다.

    ![항목을 찾는 방법 선택](../media/ksetup1.png) 
   
5. 이름 **항목 제외 섹션에서** 항목 검색에서 제외하려는 항목의 이름을 추가할 수 있습니다. 이 설정을 사용하여 중요한 정보가 항목으로 포함되지 않도록 합니다. 옵션은 다음과 같습니다.
    - **항목을 제외하지 않습니다.** 
    - **이름으로 항목 제외**

    ![제외 항목](../media/topics-excluded-by-name.png) 

    (기술 관리자는 검색 후 항목 센터의 항목을 제외할 수 있습니다.)

    #### <a name="how-to-exclude-topics-by-name"></a>이름으로 항목을 제외하는 방법    

    항목을 제외해야 하는 경우 이름으로 항목 제외를 선택한 후 .csv 템플릿을 다운로드하여 검색 결과에서 제외하려는 항목 목록으로 업데이트합니다.

    ![CSV 템플릿에서 항목 제외](../media/exclude-topics-csv.png) 

    CSV 서식 파일에서 제외하려는 항목에 대한 다음 정보를 입력합니다.

    - **이름:** 제외할 항목의 이름을 입력합니다. 이 작업은 다음 두 가지 방법으로 수행할 수 있습니다.
        - 정확한 일치: 정확한 이름 또는 약어(예: *Contoso* 또는 ATL)를 포함할 *수 있습니다.*
        - 부분 일치: 특정 단어가 있는 모든 항목을 제외할 수 있습니다.  예를 들어 *호는* 호 원, 4도분의 호, 교육 호 등 호 단어가 있는 모든 항목을 *제외합니다.*  아키텍처와 같이 텍스트가 단어의 일부로 포함된 항목은 제외되지 *않습니다.*
    - **Stands for (optional)**: If you want to exclude an acronym, type the words the acronym stands for.
    - **MatchType-Exact/Partial**: 입력한 이름이 정확히  일치 유형인지 또는 부분 일치 *유형인지 여부를* 입력합니다.

    .csv 파일을 완료하고 저장한 후 찾아보기를 선택하여 찾아서 선택합니다. 
    
    **다음** 을 선택합니다.

6. 항목을 **볼 수 있는** 사용자 및 항목을 볼 수 있는 위치 페이지에서 항목 표시를 구성합니다. 항목을 **볼** 수 있는 사용자 설정에서 강조 표시된 항목, 항목 카드, 검색의 항목 응답 및 항목 페이지와 같은 항목 세부 정보에 액세스할 수 있는 사용자 선택 다음을 선택할 수 있습니다.
    - **조직의 모든 사용자**
    - **선택한 사용자 또는 보안 그룹만**
    - **아무도 없어**

    ![항목을 볼 수 있는 사용자](../media/ksetup2.png)  

    > [!Note] 
    > 이 설정을 사용하면 조직의 사용자를 선택할 수 있는 반면, 항목에 할당된 항목 환경 라이선스가 있는 사용자만 항목을 볼 수 있습니다.

7. 항목 **관리에 대한** 사용 권한 페이지에서 항목을 만들거나 편집하거나 관리할 수 있는 인원을 선택합니다. 항목을 **만들고 편집할 수 있는 사용자 섹션에서** 다음을 선택할 수 있습니다.
    - **조직의 모든 사용자**
    - **선택한 사용자 또는 보안 그룹만**
    - **아무도 없어**

    ![항목을 만들고 편집할 수 있는 항목 관리에 대한 사용 권한](../media/ksetup3.png) 

8. 항목을 **관리할 수 있는 사용자 섹션에서** 다음을 선택할 수 있습니다.
    - **조직의 모든 사용자**
    - **선택한 사용자 또는 보안 그룹만**

    ![항목 관리에 대한 사용 권한](../media/km-setup-create-edit-topics.png) 

    **다음** 을 선택합니다.

9. 항목 **센터 만들기 페이지에서** 항목 페이지를 보고 항목을 관리할 수 있는 항목 센터 사이트를 만들 수 있습니다. 사이트 **이름 상자에** 항목 센터의 이름을 입력합니다. 필요한 경우 설명 상자에 간단한 설명을 입력할 **수** 있습니다. 

   **다음** 을 선택합니다.

   ![기술 센터 만들기](../media/ksetup4.png)  

10. **검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다. 원하는 항목을 선택한 경우 **활성화** 를 선택합니다.

11. **Viva 항목** 활성화 페이지가 표시되어 시스템에서 선택한 사이트에서 항목을 분석하고 항목 센터 사이트를 만들기 시작할 것 것 을 확인합니다. **완료** 를 선택합니다.

12. 기술에 사용자 연결 **페이지로 돌아오게** 됩니다. 이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다. 

    ![적용된 설정](../media/ksetup7.png)    

처음 항목 검색을 사용하도록 설정한 경우 제안된 모든 항목을 항목 관리 보기에 표시하는 데 최대 2주가 걸릴 수 있습니다. 콘텐츠에 대한 새 콘텐츠 또는 업데이트가 진행될 때 항목 검색이 계속됩니다. Viva 항목에서 새 정보를 평가할 때 조직에서 제안된 항목 수가 변동되는 것은 일반적입니다.

## <a name="assign-licenses"></a>라이선스 할당

항목 환경을 구성한 후 항목을 사용할 사용자에 대한 라이선스를 할당해야 합니다. 라이선스가 있는 사용자만 주요 항목, 항목 카드, 항목 페이지 및 항목 센터를 비롯한 항목에 대한 정보를 볼 수 있습니다. 

라이선스를 할당하려면 다음을 수행합니다.

1. Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.

2. 라이선스를 부여할 사용자를 선택하고 라이선스 및 **앱을 클릭합니다.**

3. **라이선스에서** **Viva 항목을 선택합니다.**

4. 앱에서 **그래프** 커넥터 **검색(Viva 항목)** 및 **Viva 항목을** 둘 다 선택해야 합니다.

   > [!div class="mx-imgBorder"]
   > ![Microsoft 365 관리 센터의 Microsoft Viva 항목 라이선스](../media/topic-experiences-licenses.png)

5. **변경 내용 저장** 을 클릭합니다.

## <a name="manage-topic-experiences"></a>항목 환경 관리

항목을 설정한 후 [Microsoft 365](https://admin.microsoft.com/AdminPortal#/featureexplorer/csi/KnowledgeManagement)관리 센터에서 설정하는 동안 선택한 설정을 변경할 수 있습니다. 다음 사항을 참조하세요.

- [Microsoft Viva 항목에서 항목 검색 관리](topic-experiences-discovery.md)
- [Microsoft Viva 항목에서 항목 표시 관리](topic-experiences-knowledge-rules.md)
- [Microsoft Viva 항목에서 항목 사용 권한 관리](topic-experiences-user-permissions.md)
- [Microsoft Viva 항목의 항목 센터 이름 변경](topic-experiences-administration.md)

## <a name="see-also"></a>참고 항목

[항목 환경 개요](topic-experiences-overview.md)
