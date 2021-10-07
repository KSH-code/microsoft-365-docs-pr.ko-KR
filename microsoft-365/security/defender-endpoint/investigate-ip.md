---
title: 경고와 연결된 IP 주소 조사
description: 조사 옵션을 사용하여 장치와 외부 IP 주소 간의 통신을 검사합니다.
keywords: 조사, 조사, IP 주소, 경고, 끝점용 Microsoft Defender, 외부 IP
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 6ee90a1d39d873eb01eaf4c586b612bfe5a6fac8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192754"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>끝점 경고에 대한 Microsoft Defender와 연결된 IP 주소 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

장치와 외부 IP(인터넷 프로토콜) 주소 간의 통신을 검사합니다.

C2(명령 및 제어) 서버와 같은 의심스러우거나 알려진 악성 IP 주소와 통신한 조직의 모든 장치를 식별하면 잠재적인 위반 범위, 관련 파일 및 감염된 장치를 확인하는 데 도움이 됩니다.

IP 주소 보기의 다음 섹션에서 정보를 찾을 수 있습니다.

- 전 세계 IP
- 역방향 DNS 이름
- 이 IP와 관련된 알림
- 조직의 IP
- 보전

## <a name="ip-worldwide-and-reverse-dns-names"></a>IP Worldwide 및 Reverse DNS names(IP Worldwide 및 역방향 DNS 이름)

IP 주소 세부 정보 섹션에는 해당 ASN 및 역방향 DNS 이름과 같은 IP 주소의 특성이 표시됩니다.

## <a name="alerts-related-to-this-ip"></a>이 IP와 관련된 알림

이 IP와 관련된 알림 **섹션에서는 IP와** 연결된 경고 목록을 제공합니다.

## <a name="ip-in-organization"></a>조직의 IP

조직의 **IP 섹션에서는** 조직의 IP 주소 보전에 대한 세부 정보를 제공합니다.

## <a name="prevalence"></a>보전

**Prevalence 섹션에는** 이 IP 주소에 연결된 장치 수와 IP가 처음 및 마지막으로 확인된 때가 표시됩니다. 이 섹션의 결과는 기간에 따라 필터링할 수 있습니다. 기본 기간은 30일입니다.

## <a name="most-recent-observed-devices-with-ip"></a>IP가 있는 가장 최근에 관찰된 장치

IP가 **있는** 가장 최근에 관찰된 디바이스 섹션에서는 IP 주소에서 관찰된 이벤트 및 관련 경고에 대한 연도 보기를 제공합니다.

**외부 IP 조사:**

1. 검색 표시줄 **드롭다운** 메뉴에서 **IP를** 선택합니다.
2. 검색 필드에 IP 주소를 **입력합니다.**
3. 검색 아이콘을 클릭하거나 Enter를 **클릭합니다.**

등록 세부 정보(사용 가능한 경우), 역방향 IP(예: 도메인), 이 IP 주소와 통신한 조직의 장치 보류(선택 가능한 기간 동안) 및 이 IP 주소와 통신하는 것으로 관찰된 조직의 장치 등 IP 주소에 대한 세부 정보가 표시됩니다.

> [!NOTE]
> 검색 결과는 조직의 장치와 통신하는 것으로 관찰된 IP 주소에 한해 반환됩니다.

검색 필터를 사용하여 검색 조건을 정의합니다. 타임라인 검색 상자를 사용하여 IP 주소와 통신하는 것으로 관찰된 조직의 모든 장치, 통신과 연결된 파일 및 마지막으로 관찰된 날짜의 표시 결과를 필터링할 수도 있습니다.

장치 이름을 클릭하면 보고된 경고, 동작 및 이벤트를 계속 조사할 수 있는 디바이스 보기로 연결됩니다.

## <a name="related-topics"></a>관련 항목

- [엔드포인트용 Microsoft Defender 경고 큐 보기 및 구성](alerts-queue.md)
- [끝점 경고에 대한 Microsoft Defender 관리](manage-alerts.md)
- [끝점 경고에 대한 Microsoft Defender 조사](investigate-alerts.md)
- [끝점 경고에 대한 Microsoft Defender와 관련된 파일 조사](investigate-files.md)
- [Microsoft Defender for Endpoint Devices 목록에서 장치 조사](investigate-machines.md)
- [끝점 경고에 대한 Microsoft Defender와 연결된 도메인 조사](investigate-domain.md)
- [끝점용 Microsoft Defender에서 사용자 계정 조사](investigate-user.md)
