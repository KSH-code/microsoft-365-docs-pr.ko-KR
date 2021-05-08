---
title: 2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft Teams 솔루션을 사용하여 계약 관리 채널을 만드는 Microsoft 365 대해 자세히 알아보십시오.
ms.openlocfilehash: a97f6a77818fc53aa28a5924b97e3c7309d01e3a
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281319"
---
# <a name="step-2-use-microsoft-teams-to-create-your-contract-management-channel"></a>2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기

조직에서 계약 관리 솔루션을 설정하는 경우 관련자가 계약을 검토하고 관리할 수 있는 중앙 위치가 필요합니다. 이를 위해 Microsoft Teams 채널을 설정하고 Teams 채널의 기능을 사용하여 다음을 Teams 있습니다. [](https://docs.microsoft.com/microsoftteams/)

- **관련자가 조치가 필요한 모든 계약을 쉽게 볼 수 있는 위치를 만들 수 있습니다.** 예를 Teams 구성원이 승인이 필요한  모든 계약의 유용한 타일 보기를 볼 수 있는 계약 관리 채널에서 계약 탭을 만들 수 있습니다. 또한 각 "카드"에 중요한 데이터(예: *클라이언트,* 계약자 및 수수료 금액)가 나열될 수 있도록 보기를 *구성할 수 있습니다.*

     ![계약 탭](../media/content-understanding/tile-view.png)

- **구성원이 서로 상호 작용하고 중요한 이벤트를 볼 수 있는 위치가 있습니다.** 예를 들어 Teams 게시물 탭을  사용하여 대화를 진행하고, 업데이트를 받을 수 있으며, 작업(예: 계약을 거부하는 구성원)을 볼 수 있습니다. 어떤 일이 발생하면(예: 승인을 위해 제출된 새 계약) 게시물 탭을 사용하여 이를 발표할 뿐만 아니라 기록을 보관할 수도 있습니다.  또한 구성원이 알림을 구독하면 업데이트가 있는 경우 알림을 받을 수 있습니다. 

     ![게시물 탭.](../media/content-understanding/posts.png)</br> 

- **결제를 위해 제출할 수 있는 경우를 알 수 있는 승인된 계약을 구성원에게 볼 수 있는 위치가 있습니다.** 이 Teams 결제 채널을 만들어 <b></b> 결제로 제출해야 하는 모든 계약을 나열할 수 있습니다. 이 솔루션을 쉽게 확장하여 이 정보를 타사 금융 응용 프로그램(예: Dynamics CRM)에 직접 작성할 수 있습니다.

## <a name="attach-your-sharepoint-document-library-to-the-contracts-tab"></a>계약 탭에 SharePoint 문서 라이브러리 연결 

계약 관리  채널에서 계약 탭을 만든 후 문서 라이브러리에 SharePoint [연결해야 합니다.](https://support.microsoft.com/office/add-a-sharepoint-page-list-or-document-library-as-a-tab-in-teams-131edef1-455f-4c67-a8ce-efa2ebf25f0b) 첨부할 SharePoint 문서 라이브러리는 이전 섹션에서 SharePoint 문서 이해 모델을 적용한 라이브러리입니다.

문서 SharePoint 연결한 후 기본 목록 보기를 통해 분류된 계약을 볼 수 있습니다.

   ![목록 보기.](../media/content-understanding/list-view.png) 

## <a name="customize-your-contracts-tab-tile-view"></a>계약 탭 타일 보기 사용자 지정

타일 Teams 보기에서 계약을 볼 수 있도록 하는 동안 계약 카드에 표시하려는 계약 데이터를 보게 계약 데이터를 사용자 지정할 수 있습니다. 예를 들어 계약  탭의 경우 구성원은 계약 카드에서 클라이언트, 계약자 및 수수료 금액을 보는 것이 중요합니다. 이러한 필드는 모두 문서 라이브러리에 적용된 SharePoint Syntex 모델을 통해 각 계약에서 추출되었습니다. 또한 구성원이 승인 프로세스에서 계약의 위치를 쉽게 확인할 수 있도록 각 상태에 대해 타일 헤더 막대를 다른 색으로 변경할 수 있습니다. 예를 들어 승인된 모든 계약에는 파란색 헤더 표시줄이 있습니다.

   ![목록 보기.](../media/content-understanding/tile.png)

사용하는 사용자 지정 타일 보기를 사용하려면 현재 타일 보기의 서식을 지정하는 데 사용되는 JSON 파일을 변경해야 합니다. 파일에서 카드 보기를 만드는 데 사용되는 JSON 파일을 참조할 **ContractCard.js** 있습니다. 다음 섹션에서는 계약 카드에 있는 기능에 대한 코드의 특정 섹션을 볼 수 있습니다.

Teams 채널의 보기에 대한 JSON 코드를 보거나 변경하려면 Teams 채널에서 보기 드롭다운 메뉴를 선택한 다음 현재 보기 서식을 **선택합니다.**

   ![json 형식](../media/content-understanding/jason-format.png) 

## <a name="card-size-and-shape"></a>카드 크기 및 모양

참조 **zipContractCard.js** 파일에서 다운로드한 파일에서 다음 섹션에서 카드의 크기와 모양의 형식을 지정하는 방법에 대한 코드를 참조하세요.

```JSON
                  {
                    "elmType": "div",
                    "style": {
                      "background-color": "#f5f5f5",
                      "padding": "5px",
                      "width": "180px"
                    },
                    "children": [
                      {
                        "elmType": "img",
                        "attributes": {
                          "src": "@thumbnail.large"
                        },
                        "style": {
                          "width": "185px",
                          "height": "248px"
                        }
                      }
```


## <a name="contract-status"></a>계약 상태

다음 코드에서는 각 제목 카드의 상태를 정의할 수 있습니다. 각 상태 값(새 *상태,* 검토 중, 승인됨 및 거부됨)에는 각각 다른 색 코드가 표시됩니다.  다운로드한 **ContractCard.js** 파일에서 상태를 정의하는 섹션을 살펴 봐야 합니다.

```JSON
          {
            "elmType": "div",
            "children": [
              {
                "elmType": "div",
                "style": {
                  "color": "white",
                  "background-color": "=if([$Status] == 'New', '#00b7c3', if([$Status] == 'In review', '#ffaa44', if([$Status] == 'Approved', '#0078d4', if([$Status] == 'Rejected', '#d13438', '#8378de'))))",
                  "padding": "5px 15px",
                  "height": "auto",
                  "text-transform": "uppercase",
                  "font-size": "12.5px"
                },
                "txtContent": "[$Status]"
              }
```


## <a name="extracted-fields"></a>추출된 필드

각 계약 카드에는 각 계약에 대해 추출된 세 개의 필드(클라이언트,계약자 및 수수료 금액)가 *표시됩니다.* 또한 파일을 식별하는 데 사용된 SharePoint 파일을 분류한 시간/날짜도 표시해야 합니다. 

다운로드한 **ContractCard.js** 파일에서 다음 섹션에서는 이러한 각 섹션을 정의합니다.

### <a name="client"></a>클라이언트

이 섹션에서는 카드에 "Client"가 표시될 방법을 정의하고 특정 계약에 대한 값을 사용 합니다.

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
                      },
```

### <a name="contractor"></a>계약자

이 섹션에서는 카드에 "계약자"가 표시될 방법을 정의하고 특정 계약에 값을 사용 합니다.

```JSON
                      {
                        "elmType": "div",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px"
                        },
                        "txtContent": "Client"
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "16px",
                          "font-weight": "600"
                        },
                        "txtContent": "[$Client]"
},
```


### <a name="fee-amount"></a>수수료 금액

이 섹션에서는 카드에 "수수료 금액"이 표시되는 방법을 정의하고 특정 계약에 값을 사용 합니다.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Fee amount",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$FeeAmount]"
                      },
```



### <a name="classification-date"></a>분류 날짜

이 섹션에서는 카드에 "분류"가 표시될 방법을 정의하고 특정 계약에 대한 값을 사용하는 방법을 정의합니다.

```JSON
                      {
                        "elmType": "div",
                        "txtContent": "Classified",
                        "style": {
                          "color": "#767676",
                          "font-size": "12px",
                          "margin-bottom": "2px"
                        }
                      },
                      {
                        "elmType": "div",
                        "style": {
                          "margin-bottom": "12px",
                          "font-size": "14px"
                        },
                        "txtContent": "[$PrimeLastClassified]"
                      }
```

## <a name="next-step"></a>다음 단계

[3단계. 이 Power Automate 사용하여 계약 처리 흐름 만들기](solution-manage-contracts-step3.md)
