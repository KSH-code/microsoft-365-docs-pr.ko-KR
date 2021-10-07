---
title: 검사에 대한 제외 Microsoft Defender 바이러스 백신 설정
description: 파일(지정된 프로세스에서 수정한 파일 포함) 및 폴더가 해당 폴더에서 검색되지 Microsoft Defender 바이러스 백신. PowerShell을 사용하여 제외의 유효성을 검사합니다.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.collection: M365-security-compliance
ms.openlocfilehash: e97f720a5004a61687cea6d62afe6fc32481f94f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213838"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>검사에 대한 제외 Microsoft Defender 바이러스 백신 유효성 검사

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

특정 파일, 폴더, 프로세스 및 프로세스에서 연 파일은 검사에서 제외할 Microsoft Defender 바이러스 백신 있습니다. 이러한 제외는 예약된 [검사,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)요구 [](run-scan-microsoft-defender-antivirus.md)시 검사 및 항상 실시간 보호 및 모니터링에 [적용됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md) 처리된 파일에 대한 제외는 실시간 보호에만 적용됩니다.

## <a name="configure-and-validate-exclusions"></a>제외 구성 및 유효성 검사

제외를 구성하고 유효성을 검사하기 위해 다음을 참조합니다.

- 파일 이름, 확장명 및 폴더 위치에 따라 제외를 [구성하고 유효성을 검사합니다.](configure-extension-file-exclusions-microsoft-defender-antivirus.md) 파일 확장명Microsoft Defender 바이러스 백신 이름 또는 위치에 따라 파일 검색에서 파일을 제외할 수 있습니다.

- 프로세스에서 연 파일에 대한 제외를 [구성하고 유효성을 검사합니다.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md) 특정 프로세스에서 연 검사에서 파일을 제외할 수 있습니다.

## <a name="recommendations-for-defining-exclusions"></a>권장 사항 정의하는 데 사용할 수 있는 예

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신 운영 체제 동작 및 일반적인 관리 파일(예: 엔터프라이즈 관리, 데이터베이스 관리 및 기타 엔터프라이즈 시나리오 및 상황에 사용되는 파일)을 기반으로 하는 많은 자동 제외가 포함됩니다.
>
> 제외를 정의하면 제외가 제공하는 보호가 Microsoft Defender 바이러스 백신. 제외 구현과 관련된 위험을 항상 평가해야 합니다. 또한 악의적이지 않다고 확신하는 파일만 제외해야 합니다.

제외를 정의할 때 다음에 유의해야 합니다.

- 제외는 기술적으로 보호 간격입니다. 제외를 정의할 때 모든 옵션을 고려하세요. 다른 옵션은 제외된 위치에 적절한 ACL(액세스 제어 목록)이 있는지 확인하거나 처음에 정책을 감사 모드로 설정하는 것만큼 간단할 수 있습니다.

- 제외를 주기적으로 검토합니다. 검토 프로세스의 일부로 완화를 다시 검토하고 다시 적용합니다.

- 예방적 노력으로 제외를 정의하는 것이 가장 이상적입니다. 예를 들어 향후 문제가 될 수 있는 것으로 생각하기 때문에 제외하지 말아야 합니다. 제외를 완화할 수 있는 성능 또는 응용 프로그램 호환성과 관련한 문제와 같은 특정 문제에만 제외를 사용하십시오.

- 제외 목록의 변경 내용을 검토하고 감사합니다. 보안 팀은 나중에 혼동을 방지하기 위해 특정 제외가 추가된 이유에 대한 컨텍스트를 보존해야 합니다. 보안 팀은 제외가 존재하는 이유에 대한 질문에 대한 구체적인 답변을 제공할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [Microsoft Defender 바이러스 백신 제외 Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [제외 정의 시 피해야 하는 일반적인 실수](common-exclusion-mistakes-microsoft-defender-antivirus.md)
