---
title: 끝점 응답 API에 대해 지원되는 Microsoft Defender
description: 특정 응답 관련 Microsoft Defender for Endpoint API 호출에 대해 자세히 알아보습니다.
keywords: 응답 api, 그래프 api, 지원되는 api, 배우, 알림, 장치, 사용자, 도메인, ip, 파일
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 096f169daee45630be4cdf4b14f8b74b2f439464
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159369"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>끝점 쿼리 API에 대해 지원되는 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-supported-response-apis-abovefoldlink)

실행할 수 있는 지원되는 응답 관련 API 호출과 필요한 요청 헤더, 호출의 예상 응답 등의 세부 정보를 제공합니다.

## <a name="in-this-section"></a>이 섹션의 내용

<br>

****

|항목|설명|
|---|---|
|조사 패키지 수집|이 API를 실행하여 장치에서 조사 패키지를 수집합니다.|
|디바이스 격리|이 API를 실행하여 네트워크에서 장치를 격리합니다.|
|장치 고지 안|장치를 분리에서 제거합니다.|
|코드 실행 제한|악성 프로세스를 중지하여 공격을 포함하기 위해 이 API를 실행합니다. 또한 장치를 잠그고 잠재적인 악성 프로그램이 실행되지 않도록 할 수도 있습니다.|
|코드 실행 제한 안|손상된 장치가 수정된 것이 확인된 후 응용 프로그램 제한 정책을 되돌리기 위해 이 정책을 실행합니다.|
|바이러스 백신 검사 실행|바이러스 백신 검색을 원격으로 시작하여 손상된 장치에 있을 수 있는 맬웨어를 식별하고 수정합니다.|
|파일을 중지하고 격리|이 호출을 실행하여 실행 중인 프로세스를 중지하고, 파일을 검지하고, 레지스트리 키와 같은 지속성도 삭제합니다.|
|샘플 요청|특정 장치에서 파일의 샘플을 요청하려면 이 호출을 실행합니다. 파일은 장치에서 수집되고 보안 저장소에 업로드됩니다.|
|파일 차단|잠재적으로 악의적인 파일 또는 의심되는 맬웨어를 금지하여 조직에서 공격이 추가로 전파되지 않도록 방지하려면 이 API를 실행합니다.|
|파일 차단 해제|조직에서 파일을 실행하도록 허용하는 Microsoft Defender 바이러스 백신.|
|패키지 SAS URI를 얻습니다.|이 API를 실행하여 조사 패키지 다운로드를 허용하는 URI를 얻습니다.|
|MachineAction 개체 Get|이 API를 실행하여 MachineAction 개체를 만듭니다.|
|MachineActions 컬렉션을 얻습니다.|MachineAction 컬렉션을 얻습니다.|
|FileActions 컬렉션 다운로드|이 API를 실행하여 FileActions 컬렉션을 다운로드합니다.|
|FileMachineAction 개체 다운로드|이 API를 실행하여 FileMachineAction 개체를 다운로드합니다.|
|FileMachineActions 컬렉션 다운로드|이 API를 실행하여 FileMachineAction 컬렉션을 다운로드합니다.|
|
