---
title: 에이전트 상태 문제 조사
description: mdatp 상태 명령을 실행하면 반환되는 값에 대해 자세히 알아보시고
keywords: mdatp 상태, 명령, 상태, 상태, 명령, 온보더링 상태
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f43905fe3487f44d3736e098c19964eaad3bf126
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60206974"
---
# <a name="investigate-agent-health-issues"></a>에이전트 상태 문제 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

다음 표에서는 명령을 실행할 때 반환되는 값과 해당 `mdatp health` 설명에 대한 정보를 제공합니다.

<br>

****

|값|설명|
|---|---|
|automatic_definition_update_enabled|True이면 자동 바이러스 백신 정의 업데이트가 사용하도록 설정되어 있습니다. 그렇지 않으면 false입니다.|
|cloud_automatic_sample_submission_consent|현재 샘플 제출 수준입니다. 다음 값 중 하나가 될 수 있습니다. <ul><li>**없음:** 의심스러운 샘플이 Microsoft에 제출하지 않습니다.</li><li>**금고:** PII(개인 식별 정보)를 포함하지 않는 의심스러운 샘플만 자동으로 제출됩니다. 이 설정의 기본값입니다.</li><li>**모두:** 의심스러운 모든 샘플이 Microsoft에 제출됩니다.</li></ul>|
|cloud_diagnostic_enabled|True이면 선택적 진단 데이터 수집을 사용하도록 설정하고, 그렇지 않으면 false입니다. Endpoint용 Defender 및 Microsoft Defender 바이러스 백신 및 Windows Microsoft 개인 정보 취급 방침을 [참조하세요.](https://go.microsoft.com/fwlink/?linkid=827576)|
|cloud_enabled|True이면 클라우드 제공 보호가 사용하도록 설정되어 있습니다. 그렇지 않으면 false입니다.|
|conflicting_applications|끝점용 Microsoft Defender와 충돌할 수 있는 응용 프로그램 목록입니다. 이 목록에는 호환성 문제를 일으키는 것으로 알려진 기타 보안 제품 및 기타 응용 프로그램이 포함되어 있지만 이에 국한되지 않습니다.|
|definitions_status|바이러스 백신 정의의 상태입니다.|
|definitions_updated|마지막 바이러스 백신 정의 업데이트의 날짜 및 시간입니다.|
|definitions_updated_minutes_ago|마지막 바이러스 백신 정의 업데이트 이후의 시간(분)입니다.|
|definitions_version|바이러스 백신 정의 버전입니다.|
|edr_client_version|장치에서 EDR 클라이언트의 버전입니다.|
|edr_configuration_version|EDR 버전입니다.|
|edr_device_tags|장치와 연결된 태그 목록입니다.|
|edr_group_ids|디바이스가 연결된 그룹 ID입니다.|
|edr_machine_id|디바이스에서 사용되는 장치 Microsoft Defender 보안 센터.|
|engine_version|바이러스 백신 엔진의 버전입니다.|
|healthy|True이면 제품이 정상이면 그렇지 않고 false입니다.|
|licensed|디바이스가 테넌트에 온보드된 경우 True, 그렇지 않으면 false입니다.|
|log_level|제품의 현재 로그 수준입니다.|
|machine_guid|바이러스 백신 구성 요소에서 사용하는 고유 컴퓨터 식별자입니다.|
|network_protection_status|네트워크 보호 구성 요소의 상태입니다(macOS만 해당). 다음 값 중 하나가 될 수 있습니다. <ul><li>**starting** - 네트워크 보호가 시작 중입니다.</li><li>**failed_to_start** - 오류로 인해 네트워크 보호를 시작할 수 없습니다.</li><li>**started** - 현재 장치에서 네트워크 보호가 실행되고 있습니다.</li><li>**restarting** - 네트워크 보호가 현재 다시 시작 중입니다.</li><li>**stopping** - 네트워크 보호가 중지됩니다.</li><li>**stopped** - 네트워크 보호가 실행되고 있지 않습니다.</li></ul>|
|org_id|장치가 온보드된 조직입니다. 장치가 아직 조직에 온보드되어 있지 않은 경우 사용할 수 없는 것으로 인쇄됩니다. 온보딩에 대한 자세한 내용은 [끝점용 Microsoft Defender에 온보딩을 참조하세요.](onboarding.md)|
|passive_mode_enabled|True이면 바이러스 백신 구성 요소가 수동 모드에서 실행됩니다. 그렇지 않으면 false입니다.|
|product_expiration|현재 제품 버전이 지원 종료에 도달한 날짜 및 시간입니다.|
|real_time_protection_available|True이면 실시간 보호 구성 요소가 정상이면 false입니다.|
|real_time_protection_enabled|True이면 실시간 바이러스 백신 보호가 사용하도록 설정되어 있습니다. 그렇지 않으면 false입니다.|
|real_time_protection_subsystem|실시간 보호를 위해 사용되는 하위입니다. 실시간 보호가 예상대로 작동되지 않는 경우 사용할 수 없는 것으로 인쇄됩니다.|
|release_ring|릴리스 링입니다. 자세한 내용은 [배포 링을 참조하세요.](deployment-rings.md)|
|
