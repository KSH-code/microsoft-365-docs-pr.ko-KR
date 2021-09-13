---
title: 끝점용 Microsoft Defender에서 사용자 계정 조사
description: 조사하는 동안 사용자 계정에서 잠재적으로 손상된 자격 증명을 조사하거나 관련 사용자 계정을 피벗합니다.
keywords: 조사, 계정, 사용자, 사용자 엔터티, 경고, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 73c16691dc56ad478912b85cb1b712bc7b1b44a8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189502"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 사용자 계정 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>사용자 계정 엔터티 조사

가장 활발한 경고(대시보드에 "위험 상태의 사용자"로 표시)가 있는 사용자 계정을 식별하고 잠재적으로 손상된 자격 증명의 사례를 조사하거나 경고 또는 장치를 조사할 때 관련 사용자 계정을 피벗하여 해당 사용자 계정이 있는 장치 간에 가능한 측면 이동을 식별합니다.

다음 보기에서 사용자 계정 정보를 찾을 수 있습니다.

- 대시보드
- 경고 큐
- 장치 세부 정보 페이지

이러한 보기에서는 사용자 계정에 대한 자세한 정보가 표시되는 사용자 계정 세부 정보 페이지로 이동하는 클릭 가능한 사용자 계정 링크를 사용할 수 있습니다.

사용자 계정 엔터티를 조사하면 다음이 표시됩니다.

- 사용자 계정 세부 정보, ID에 대한 Microsoft Defender 경고 및 로그온 장치, 역할, 로그온 유형 및 기타 세부 정보
- 인시던트 및 사용자 장치 개요
- 이 사용자와 관련된 알림
- 조직에서 관찰된(로그온한 장치)

![사용자 계정 엔터티 세부 정보 페이지의 이미지입니다.](images/atp-user-details-view.png)

### <a name="user-details"></a>사용자 세부 정보

왼쪽의 사용자 세부 정보 창에서는 관련된 공개 인시던트, 활성 경고, SAM 이름, SID, ID 알림용 Microsoft Defender 경고, 사용자가 로그온한 장치 수, 사용자가 처음 및 마지막으로 본 때, 역할 및 로그온 유형과 같은 사용자에 대한 정보를 제공합니다.  사용하도록 설정한 통합 기능에 따라 다른 세부 정보가 표시됩니다. 예를 들어 비즈니스용 Skype 사용하도록 설정하면 포털에서 사용자에게 연락할 수 있습니다. **Azure ATP 경고** 섹션에는 Id에 대한 Microsoft Defender 기능을 사용하도록 설정한 경우 Id에 대한 Microsoft Defender 페이지로 이동하는 링크가 포함되어 있으며 사용자와 관련된 알림이 있습니다. Microsoft Defender for Identity 페이지에서 경고에 대한 자세한 정보를 제공합니다.

> [!NOTE]
> 이 기능을 사용하려면 ID용 Microsoft Defender 및 Endpoint용 Defender에서 통합을 사용하도록 설정해야 합니다. Endpoint용 Defender에서 고급 기능에서 이 기능을 사용하도록 설정할 수 있습니다. 고급 기능을 사용하도록 설정하는 방법에 대한 자세한 내용은 고급 기능 [켜기 를 참조하세요.](advanced-features.md)

조직에서 개요, 경고 및 관찰된 탭은 사용자 계정에 대한 다양한 특성을 표시하는 서로 다른 탭입니다.

### <a name="overview"></a>개요

개요 **탭에는** 인시던트 세부 정보 및 사용자가 로그온한 장치 목록이 표시됩니다. 이러한 이벤트를 확장하여 각 장치에 대한 로그온 이벤트에 대한 세부 정보를 볼 수 있습니다.

### <a name="alerts"></a>경고

경고 **탭에서는** 사용자 계정과 연결된 경고 목록을 제공합니다. 이 목록은 경고 큐의 [](alerts-queue.md)필터링된 보기로, 사용자 컨텍스트가 선택된 사용자 계정, 마지막 활동이 검색된 날짜, 경고에 대한 간단한 설명, 경고와 연결된 장치, 경고의 심각도, 큐의 경고 상태 및 경고가 할당된 사용자를 보여 주며, 경고가 할당된 경고를 보여줍니다.

### <a name="observed-in-organization"></a>조직에서 관찰

**조직에서** 관찰 탭을 사용하면 이 사용자가 로그온한 것으로 관찰된 장치 목록, 이러한 각 장치에 대해 가장 자주 로그온한 사용자 계정 및 각 장치에서 관찰된 총 사용자 목록을 볼 수 있는 날짜 범위를 지정할 수 있습니다.

조직에서 관찰 표에서 항목을 선택하면 항목이 확장되고 장치에 대한 세부 정보가 표시됩니다. 항목 내의 링크를 직접 선택하면 해당 페이지로 전송됩니다.

## <a name="search-for-specific-user-accounts"></a>특정 사용자 계정 검색

1. 검색 **표시줄** **드롭다운** 메뉴에서 사용자를 선택합니다.
2. 검색 필드에 사용자 계정을 **입력합니다.**
3. 검색 아이콘을 클릭하거나 Enter를 **클릭합니다.**

쿼리 텍스트와 일치하는 사용자 목록이 표시됩니다. 사용자 계정의 도메인 및 이름, 사용자 계정이 마지막으로 확인된 경우 및 지난 30일 동안 로그온한 것으로 관찰된 총 장치 수가 표시됩니다.

다음 기간에 따라 결과를 필터링할 수 있습니다.

- 1일
- 3일
- 7일
- 30일
- 6개월

## <a name="related-topics"></a>관련 항목

- [엔드포인트용 Microsoft Defender 경고 큐 보기 및 구성](alerts-queue.md)
- [끝점 경고에 대한 Microsoft Defender 관리](manage-alerts.md)
- [끝점 경고에 대한 Microsoft Defender 조사](investigate-alerts.md)
- [끝점 경고에 대한 Defender와 관련된 파일 조사](investigate-files.md)
- [Endpoint 장치용 Defender 목록에서 장치 조사](investigate-machines.md)
- [끝점 경고에 대한 Defender와 연결된 IP 주소 조사](investigate-ip.md)
- [끝점 경고에 대한 Defender와 연결된 도메인 조사](investigate-domain.md)
