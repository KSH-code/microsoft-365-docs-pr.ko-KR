---
title: Linux의 끝점용 Microsoft Defender의 새로운
description: Linux의 끝점용 Microsoft Defender에 대한 주요 변경 사항 목록입니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, linux, whatsnew, release
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: cc24857adacf3b6fbb787030136f5ebb53f00937
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60178350"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Linux의 끝점용 Microsoft Defender의 새로운

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1013998-30121062139980"></a>101.39.98 (30.121062.13998.0)

- 버그 수정을 & 성능 개선

## <a name="1013427-30121052134270"></a>101.34.27 (30.121052.13427.0)

- 버그 수정을 & 성능 개선

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0)

- 이 버전부터 명령줄 클라이언트를 통해 트리거된 요청 시 바이러스 백신 검사 중에 감지된 위협이 자동으로 수정됩니다. 사용자 인터페이스를 통해 트리거된 검사 중에 검색된 위협에는 여전히 수동 작업이 필요 합니다.
- `mdatp diagnostic real-time-protection-statistics` 이제 다음 두 가지 추가 스위치를 지원합니다.
  - `--sort`: 검색된 총 파일 수를 통해 출력의 내선 번호를 정렬합니다.
  - `--top N`: 상위 N 결과를 표시하고(또한 지정한 `--sort` 경우만 작동)
- 버그 수정을 & 성능 개선

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Linux의 끝점용 Microsoft Defender는 이제 미국 정부 고객을 위해 미리 보기에서 사용할 수 있습니다. 자세한 내용은 미국 정부 고객용 [끝점용 Microsoft Defender를 참조하세요.](gov.md)
- FUSE 파일 시스템과 함께 Linux에서 Endpoint용 Microsoft Defender를 OS 중단으로 이어지는 문제를 해결했습니다.
- 기타 버그 & 개선

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- 버그 수정을 & 성능 개선

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- 전체 탑재 지점이 바이러스 백신 제외 목록에 추가되는 상황에 대한 성능 향상. 이 버전 이전에는 탑재 지점에서 시작된 파일 활동이 제품에 의해 계속 처리되었습니다. 이 버전부터 제외된 탑재 지점에 대한 파일 활동이 억제되고 제품 성능이 향상됩니다.
- 마지막 명령줄 검사에 대한 정보를 볼 수 있는 새 옵션이 명령줄 도구에 추가되었습니다. 마지막 on-demand 검사에 대한 정보를 보기 위해 를 실행합니다. `mdatp health --details antivirus`
- 버그 수정에 & 성능 향상

## <a name="1011853"></a>101.18.53

- EDR Linux용 배포판을 이제 [일반적으로 사용할 수 있습니다.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- 사용자 지정 검사 중에 AV 제외를 무시하는 새 명령줄 스위치()가 `--ignore-exclusions` 추가되었습니다. `mdatp scan custom`
- 진단 로그를 다른 디렉터리에 저장할 수 있도록 하는 새 매개 변수()로 `mdatp diagnostic create` `--path [directory]` 확장
- 버그 수정을 & 성능 개선

## <a name="1011299"></a>101.12.99

- 버그 수정을 & 성능 개선

## <a name="1010476"></a>101.04.76

- 버그 수정

## <a name="1010348"></a>101.03.48

- 버그 수정

## <a name="1010255"></a>101.02.55

- 제품이 때때로 재부팅/업그레이드 후 시작되지 않는 문제를 해결했습니다.
- 제품 업그레이드에서 프록시 설정이 유지되지 않는 문제를 해결했습니다.

## <a name="1010075"></a>101.00.75

- , , , , , , , , , , 및 파일 시스템 유형에 대한 `ecryptfs` `fuse` `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` 지원이 추가되었습니다. `vfat`
- 명령줄 도구에 대한 새 [구문입니다.](linux-resources.md#configure-from-the-command-line)
- 버그 수정을 & 성능 개선

## <a name="1009070"></a>100.90.70

> [!WARNING]
> 설치된 패키지를 100.90.70 이전 제품 버전에서 업그레이드하는 경우 Red Hat 기반 및 SLES 배포에서 업데이트가 실패할 수 있습니다. 이는 파일 경로가 대대적인 변경된 것이기 때문에입니다. 임시 솔루션은 이전 패키지를 제거한 다음 새 패키지를 설치하는 것입니다. 이 문제는 최신 버전에 존재하지 않습니다.

- 바이러스 [백신 제외에서 와일드카드 지원](linux-exclusions.md#supported-exclusion-types)
- 명령줄 도구를 [통해](linux-support-perf.md) 성능 문제를 해결하는 `mdatp` 기능을 추가했습니다.
- 패키지 설치를 보다 강력하게 만들기 위한 개선된 기능
- 버그 수정을 & 성능 개선
