---
title: Microsoft 365 솔루션을 사용하여 계약 관리
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection:
- m365solution-managecontracts
- m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: Microsoft 365, 목록, SharePoint 및 SharePoint Syntex 솔루션으로 계약을 Microsoft Teams 방법을 Power Automate.
ms.openlocfilehash: 632a1cbe76c213c0bdb263bcb564fc7303c4780f
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59776239"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a>Microsoft 365 솔루션을 사용하여 계약 관리

이 문서에서는 조직의 구성 요소 및 구성 요소를 사용하여 조직에 SharePoint Syntex 관리 솔루션을 만드는 Microsoft 365. 또한 고유한 비즈니스 요구에 맞는 솔루션을 계획하고 만드는 데 도움이 되는 프레임워크를 제공합니다. 이 솔루션이 계약 관리에 대해 설명하는 경우에도 작업 또는 송장의 설명과 같은 다른 문서 관리 솔루션을 만들 수 있습니다.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWJUR0]

</br>

## <a name="identify-the-business-problem"></a>비즈니스 문제 식별

계약 관리 시스템을 계획하는 첫 번째 단계는 해결하려는 문제를 이해하는 것입니다. 이 솔루션의 경우 다음 네 가지 주요 문제를 해결해야 합니다.

- **계약을 식별합니다.** 조직은 송장, 계약서, 작업 설명 등의 많은 문서에서 작업합니다.  일부는 전자 메일을 통해 전송된 디지털 자산이고, 일부는 기존 메일을 통해 전송된 용지 자산입니다. 다른 모든 문서에서 모든 고객 계약을 식별한 다음 이와 같이 분류하는 방법이 필요합니다.

- **계약 승인 내역을 추적합니다.** 조직은 계약이 승인 또는 거부 찾은지 여부와 지급이 처리된지 여부를 안정적으로 찾을 수 있는 방법이 필요합니다. 

- **계약 승인을 관리하는 사이트입니다.** 조직에서는 필요한 모든 관련자가 계약을 쉽게 검토할 수 있는 공동 작업 사이트를 설정해야 합니다. 관련자는 필요한 경우 전체 계약을 검토할 수 있지만 주로 각 계약에서 몇 가지 주요 필드(예: 고객 이름, PO 번호 및 총 비용)를 보는 것이 중요합니다. 이해 관계자는 들어오는 계약을 쉽게 승인하거나 거부할 수 있습니다.

- **검토된 계약을 라우팅합니다.** 승인됨 및 거부된 계약은 특정 워크플로를 통해 라우팅해야 합니다. 승인된 계약은 결제 처리를 위해 타사 응용 프로그램으로 라우팅해야 합니다. 거부된 계약은 추가 검토를 위해 라우팅해야 합니다.

## <a name="overview-of-the-solution"></a>솔루션 개요

  ![목록, SharePoint Syntex, SharePoint 및 Teams 사용하는 솔루션 Power Automate.](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

이 계약 관리 솔루션 지침에는 다음과 같은 네 가지 구성 요소가 Microsoft 365.

- **Microsoft SharePoint Syntex**: 모델을 만들어 계약 파일을 식별하고 분류한 다음 계약 파일에서 적절한 데이터를 추출합니다.

- **Microsoft SharePoint 목록:** 최신 SharePoint 사용할 수 있는 서식을 사용하여 비즈니스에 친숙한 형식으로 계약을 제공합니다.

- **Microsoft Teams**: Teams 채널 및 관련 탭의 기능을 사용하여 관련자가 계약을 검토하고 관리할 수 있도록 합니다.

- **Power Automate:** 흐름을 사용하여 승인 프로세스를 통해 계약을 안내한 다음 타사 응용 프로그램에 지급을 안내합니다.

### <a name="how-it-all-works"></a>작동 방식

  ![문서를 업로드하고, 데이터를 추출하고, 이해 관계자에게 알리고, 계약을 승인하거나 거부하는 워크플로를 보여주는 솔루션 다이어그램입니다.](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. 문서가 문서 라이브러리에 SharePoint 업로드됩니다. 문서 SharePoint Syntex 이해 모델이 문서 라이브러리에 적용되었습니다. 각 파일을 검사하여 검색할 수 있는 "계약" 콘텐츠 형식과 일치하는지 확인할 수 있습니다. 일치하는 파일을 찾으면 해당 파일을 "계약"으로 분류하고 문서의 콘텐츠 형식을 업데이트합니다.

2. 또한 이 모델은 클라이언트, 계약자 및 수수료 금액과 같이 이해 관계자가 관심을 가지는 각 계약 파일에서 특정 데이터를 *끌어오기도 합니다.*

    다음 페이지는 모델이 식별하기 위해 교육된 계약의 예입니다.

      ![계약의 예입니다.](../media/content-understanding/contract.png)

3. Microsoft Teams 모든 이해 관계자는 문서 라이브러리의 모든 계약이 승인 또는 거부를 위해 표시되는 보안 Teams 채널의 구성원입니다. 이 Teams 사용하여 새 계약을 검토해야 하는 경우 모든 이해 관계자에게 알림을 제공합니다.

4. 이 Power Automate 사용하여 계약은 Teams 채널의 승인 프로세스를 통해 이동됩니다. 구성원이 계약을 승인하면 계약 상태가 승인됨으로 변경되고, 모든 구성원은 Teams 게시를 통해 알림을 하게 되고, 계약이 지급 준비가 됨을 보여 줄 품목이 만들어집니다. 이 프로세스를 확장하여 결제를 위해 타사 금융 응용 프로그램에 직접 쓸 수 있습니다.

5. 구성원이 계약을 거부하면 상태가 거부로 변경되고 모든 구성원은 해당 게시물을 통해 Teams 않습니다.

6. 이 솔루션의 최종 결과는 조직에 대한 자동화된 비즈니스 프로세스입니다. 직원은 문서의 승인 워크플로를 시작하고 Teams 사용자 지정 타일 보기를 쉽게 사용할 수 있습니다. 

     ![계약 탭](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a>라이선스 요구사항

이 솔루션은 Microsoft 365 Enterprise(E1, E3, E5, F3) 또는 비즈니스(기본, 표준 또는 Premium) 라이선스의 일부로 사용할 수 있는 다음 기능을 사용 합니다.

- Microsoft SharePoint Syntex
- Microsoft Teams
- Power Automate

### <a name="learn-how-to-use-sharepoint-syntex"></a>사용 방법을 SharePoint Syntex

새 SharePoint Syntex? AI를 사용하여 콘텐츠를 SharePoint Syntex 방법을 알아보겠습니다.

시작 [SharePoint Syntex](/learn/paths/syntex-get-started) 학습 경로에서는 문서 이해 및 양식 처리 모델을 사용하여 문서를 분류하고 텍스트를 추출하고 문서에 레이블을 지정하여 빠르고 쉬운 지식 관리를 하는 방법을 배울 수 있습니다.

## <a name="create-the-solution"></a>솔루션 만들기

다음 섹션에서는 계약 관리 솔루션을 구성하는 방법에 대해 자세히 설명합니다. 이 단계는 다음 세 단계로 나뉘어 있습니다.

- [1단계. 사용자 SharePoint Syntex 사용하여 계약 파일을 식별하고 데이터 추출](solution-manage-contracts-step1.md)
- [2단계. 이 Microsoft Teams 사용하여 계약 관리 채널 만들기](solution-manage-contracts-step2.md)
- [3단계. 이 Power Automate 사용하여 계약을 처리하기 위한 흐름 만들기](solution-manage-contracts-step3.md)
