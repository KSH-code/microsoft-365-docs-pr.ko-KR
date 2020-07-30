---
title: Microsoft Threat Protection의 자동화 된 조사에 따라 수정 작업 수행
description: Microsoft Threat Protection의 자동화 된 조사를 따르는 업데이트 관리 작업에 대 한 개요를 확인 하세요.
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e0f76f6a232edeac350d08eeeb47188535ffe688
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502940"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 자동화 된 조사에 따라 수정 작업 수행

**적용 대상:**
- Microsoft 위협 방지


## <a name="remediation-actions"></a>수정 작업

Microsoft Threat Protection에 대 한 자동화 된 조사 중 및 후에는 악성 또는 의심 스러운 항목에 대 한 재구성 작업이 식별 됩니다. 일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다. 전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다. 자동화 된 조사 작업을 수행, 승인 또는 거부 한 후에 완료 됩니다.

다음 표에서는 현재 Microsoft Threat Protection에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다. 

|장치 (끝점) 재구성 작업  |전자 메일 수정 작업  |
|---------|---------|
|-수집 조사 패키지 <br/>-장치 격리 (이 작업을 실행 취소할 수 있음)<br/>-Offboard 컴퓨터 <br/>-릴리스 코드 실행 <br/>-격리에서 릴리스 <br/>-요청 샘플 <br/>-코드 실행 제한 (이 작업을 실행 취소할 수 있음) <br/>-바이러스 검사 실행 <br/>-중지 및 격리      |-블록 URL (시간 클릭)<br/>-소프트 삭제 전자 메일 메시지 또는 클러스터<br/>-격리 전자 메일<br/>-전자 메일 첨부 파일 격리<br/>-외부 메일 전달을 해제 합니다.          |

승인 보류 중 이거나 이미 완료 되었는지 여부에 관계 없이 수정 작업은 [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.

## <a name="remediation-actions-follow-automated-investigations"></a>재구성 작업의 자동화 된 조사 진행

자동화 조사가 완료 되면 관련된 모든 증명정보에 따라 결과가 도출되고 재구성 작업이 식별됩니다.   경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다. 도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. 

|의견    |영역    |결과|
|------|------|------|
|악성    |장치 (끝점)    |재구성 작업이 자동으로 실행 됩니다.|
|악성    |전자 메일 콘텐츠 (Url 또는 첨부 파일) | 승인 보류 중인 재구성 활동 |
|피싱    |장치 또는 전자 메일 콘텐츠 |승인 보류 중인 재구성 활동 |
|발견 된 위협 없음    |장치 또는 전자 메일 콘텐츠    |재구성 작업이 필요 하지 않습니다.|

[활동 센터에서 대기 중인 작업 검토](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요. 가양성 [/네거티브를 보고](mtp-autoir-report-false-positives-negatives.md)합니다.

## <a name="next-steps"></a>다음 단계

- [작업 승인 또는 거부](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [알림 센터에 대한 자세한 정보](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
