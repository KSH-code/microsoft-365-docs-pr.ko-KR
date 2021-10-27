---
title: 끝점 도메인에 대한 Microsoft Defender 조사
description: 조사 옵션을 사용하여 장치와 서버가 악성 도메인과 통신하고 있는지 볼 수 있습니다.
keywords: 도메인 조사, 도메인, 악성 도메인, 끝점에 대한 Microsoft Defender, 경고, URL
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 9f2514c0f43bd8a7f1ab5dade389c0a12f3c4e54
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587792"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>끝점 경고에 대한 Microsoft Defender와 연결된 도메인 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatedomain-abovefoldlink)

도메인을 조사하여 엔터프라이즈 네트워크의 장치와 서버가 알려진 악성 도메인과 통신하고 있는지 확인합니다.

검색 기능을 사용하여 또는 장치 타임라인에서 도메인 링크를 클릭하여 도메인을 **조사할 수 있습니다.**

URL 보기에서 다음 섹션의 정보를 볼 수 있습니다.

- URL 세부 정보, 연락처, 이름 서비스
- 이 URL과 관련된 알림 
- 조직의 URL
- URL이 있는 가장 최근에 관찰된 장치

## <a name="url-worldwide"></a>전 세계 URL

**URL Worldwide** 섹션에는 URL, Whois의 추가 세부 정보 링크, 관련된 오픈 인시던트 수 및 활성 경고 수가 나열됩니다.

## <a name="incident"></a>인시던트

**인시던트** 카드에는 지난 180일 동안의 인시던트에 있는 모든 활성 경고의 막대 차트가 표시됩니다.

## <a name="prevalence"></a>보전

**Prevalence** 카드는 지정된 기간 동안 조직 내의 URL 보전에 대한 세부 정보를 제공합니다.

기본 기간이 지난 30일이지만 카드 모서리에서 아래쪽을 가리는 화살표를 선택하여 범위를 사용자 지정할 수 있습니다. 사용 가능한 가장 짧은 범위는 지난 날의 보편적으로 사용 가능하고 가장 긴 범위는 지난 6개월 동안의 범위입니다.

## <a name="alerts"></a>경고

경고 **탭은** URL과 연결된 경고 목록을 제공합니다. 여기에 표시된 표는 경고 큐 화면에 표시되는 필터링된 버전의 경고로, 도메인과 관련된 경고, 심각도, 상태, 관련 인시던트, 분류, 조사 상태 등만 표시합니다.

알림 탭을 조정하여 열 머리더 위에 있는 작업  메뉴에서 열 사용자 지정을 선택하여 더 많은 정보를 표시하거나 더 적게 볼 수 있습니다. 동일한 메뉴에서 페이지당 항목을 선택하여 표시되는 항목 수를 **조정할** 수도 있습니다.

## <a name="observed-in-organization"></a>조직에서 관찰

조직에서 **관찰된 탭에서는** URL에서 관찰된 이벤트 및 관련 경고에 대한 연대기 보기를 제공합니다. 이 탭에는 시간 표시 막대 및 사용자 지정 가능한 테이블 목록 이벤트 세부 정보(예: 시간, 장치 및 진행된 일)에 대한 간략한 설명이 포함되어 있습니다. 

날짜를 표 헤더 위에 있는 텍스트 필드에 입력하여 다양한 기간의 이벤트를 볼 수 있습니다. 시간 표시 막대의 다른 영역을 선택하여 시간 범위를 사용자 지정할 수도 있습니다.

**도메인 조사:**

1. 검색 표시줄 **드롭다운** 메뉴에서 **URL을** 선택합니다.
2. 검색 필드에 **URL을 입력합니다.**
3. 검색 아이콘을 클릭하거나 Enter를 **클릭합니다.** URL에 대한 세부 정보가 표시됩니다. 참고: 검색 결과는 조직의 장치와의 통신에서 관찰된 URL에 한해 반환됩니다.
4. 검색 필터를 사용하여 검색 조건을 정의합니다. 타임라인 검색 상자를 사용하여 URL과 통신하는 것으로 관찰된 조직의 모든 장치, 통신과 연결된 파일 및 마지막으로 관찰된 날짜를 필터링할 수도 있습니다.
5. 장치 이름을 클릭하면 보고된 경고, 동작 및 이벤트를 계속 조사할 수 있는 디바이스 보기로 연결됩니다.

## <a name="related-topics"></a>관련 항목
- [엔드포인트용 Microsoft Defender 경고 큐 보기 및 구성](alerts-queue.md)
- [끝점 경고에 대한 Microsoft Defender 관리](manage-alerts.md)
- [끝점 경고에 대한 Microsoft Defender 조사](investigate-alerts.md)
- [끝점 경고에 대한 Microsoft Defender와 관련된 파일 조사](investigate-files.md)
- [Microsoft Defender for Endpoint Devices 목록에서 장치 조사](investigate-machines.md)
- [끝점 경고에 대한 Microsoft Defender와 연결된 IP 주소 조사](investigate-ip.md)
- [끝점용 Microsoft Defender에서 사용자 계정 조사](investigate-user.md)
