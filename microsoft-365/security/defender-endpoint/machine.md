---
title: 컴퓨터 리소스 유형
description: Microsoft Defender for Endpoint에서 컴퓨터 리소스 유형의 메서드 및 속성에 대해 자세히 알아보습니다.
keywords: api, 지원되는 api, get, machines
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 91ee0c6ec2e4c11b714dee586613b16fd22df278
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59357672"
---
# <a name="machine-resource-type"></a>컴퓨터 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>메서드

<br>

****

|방법|반환 형식|설명|
|---|---|---|
|[컴퓨터 목록](get-machines.md)|[machine collection(컴퓨터](machine.md) 컬렉션)|조의 [컴퓨터 엔터티](machine.md) 집합을 나열합니다.|
|[컴퓨터 얻기](get-machine-by-id.md)|[컴퓨터](machine.md)|ID를 [통해](machine.md) 컴퓨터 얻습니다.|
|[로그온한 사용자](get-machine-log-on-users.md)|[사용자](user.md) 컬렉션|컴퓨터에 로그온한 [User](user.md) 집합을 [얻습니다.](machine.md)|
|[관련 알림 표시](get-machine-related-alerts.md)|[경고](alerts.md) 컬렉션|에서 [발생된](alerts.md) 경고 엔터티 집합을 [얻습니다.](machine.md)|
|[설치된 소프트웨어 가져오기](get-installed-software.md)|[software collection(소프트웨어](software.md) 컬렉션)|특정 컴퓨터 ID와 관련된 설치된 소프트웨어 컬렉션을 검색합니다.|
|[발견된 취약성 가져오기](get-discovered-vulnerabilities.md)|[취약점](vulnerability.md) 수집|특정 컴퓨터 ID와 관련된 검색된 취약성 컬렉션을 검색합니다.|
|[보안 권장 사항 가져오기](get-security-recommendations.md)|[권장 컬렉션](recommendation.md)|특정 컴퓨터 ID와 관련된 보안 권장 사항 컬렉션을 검색합니다.|
|[컴퓨터 태그 추가 또는 제거](add-or-remove-machine-tags.md)|[컴퓨터](machine.md)|특정 컴퓨터의 태그를 추가하거나 제거합니다.|
|[IP별 컴퓨터 찾기](find-machines-by-ip.md)|[machine collection(컴퓨터](machine.md) 컬렉션)|IP로 볼 수 있는 컴퓨터를 찾아 찾습니다.|
|[태그별 컴퓨터 찾기](find-machines-by-tag.md)|[machine collection(컴퓨터](machine.md) 컬렉션)|태그로 컴퓨터를 [검색합니다.](machine-tags.md)|
|[누락된 KB 가져오기](get-missing-kbs-machine.md)|KB 컬렉션|컴퓨터 ID와 연결된 누락된 KB 목록 표시|
|[장치 값 설정](set-device-value.md)|[machine collection(컴퓨터](machine.md) 컬렉션)|디바이스의 [값을 설정합니다.](tvm-assign-device-value.md)|
|[컴퓨터 업데이트](update-machine-method.md)|[machine collection(컴퓨터](machine.md) 컬렉션)|컴퓨터의 업데이트 상태를 얻습니다.|
|

## <a name="properties"></a>속성

<br>

****

|속성|유형|설명|
|---|---|---|
|id|String|[컴퓨터](machine.md) ID입니다.|
|computerDnsName|String|[컴퓨터의](machine.md) 정식 이름입니다.|
|firstSeen|DateTimeOffset|Microsoft Defender for [](machine.md) Endpoint에서 컴퓨터가 관찰된 첫 번째 날짜 및 시간입니다.|
|lastSeen|DateTimeOffset|마지막으로 수신한 전체 장치 보고서의 시간 및 날짜입니다. 일반적으로 장치는 24시간마다 전체 보고서를 전송합니다.|
|osPlatform|문자열|운영 체제 플랫폼.|
|onboardingstatus|String|컴퓨터 온보드 상태입니다. 가능한 값은 "온보드" 및 "오프보더"입니다.|
|osProcessor|String|운영 체제 프로세서. 대신 osArchitecture 속성을 사용합니다.|
|버전|String|운영 체제 버전입니다.|
|osBuild|Nullable long|운영 체제 빌드 번호입니다.|
|lastIpAddress|문자열|컴퓨터의 로컬 NIC에 대한 마지막 [IP입니다.](machine.md)|
|lastExternalIpAddress|String|컴퓨터로 인터넷에 [](machine.md) 액세스한 마지막 IP입니다.|
|healthStatus|Enum|[컴퓨터](machine.md) 상태. 가능한 값은 "Active", "Inactive", "ImpairedCommunication", "NoSensorData", "NoSensorDataImpairedCommunication" 및 "Unknown"입니다.|
|rbacGroupName|문자열|컴퓨터 그룹 이름입니다.|
|rbacGroupId|String|컴퓨터 그룹 ID입니다.|
|riskScore|Nullable Enum|끝점에 대한 Microsoft Defender에서 평가한 위험 점수입니다. 가능한 값은 'None', 'Informational', 'Low', 'Medium' 및 'High'입니다.|
|aadDeviceId|Nullable 표현 Guid|AAD 장치 [ID(장치가](machine.md) AAD에 가입된 경우).|
|machineTags|문자열 컬렉션|컴퓨터 [태그](machine.md) 집합입니다.|
|exposureLevel|Nullable Enum|끝점용 Microsoft Defender에서 평가한 노출 수준입니다. 가능한 값은 'None', 'Low', 'Medium' 및 'High'입니다.|
|deviceValue|Nullable Enum|디바이스의 [값입니다.](tvm-assign-device-value.md) 가능한 값은 '보통', '낮음' 및 '높음'입니다.|
|ipAddresses|IpAddress 컬렉션|***IpAddress*** 개체 집합입니다. 컴퓨터 [API 보기를 참조합니다.](get-machines.md)|
|osArchitecture|문자열|운영 체제 아키텍처. 가능한 값은 "32비트", "64비트"입니다. osProcessor 대신 이 속성을 사용합니다.|
|
