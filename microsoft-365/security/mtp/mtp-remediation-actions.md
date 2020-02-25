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
ms.openlocfilehash: 76a4fe678ce0106c7345dd3bdf504673733b63b6
ms.sourcegitcommit: 59b006f8e82d1772cae2029f278a59ae8a106736
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/25/2020
ms.locfileid: "42266054"
---
# <a name="remediation-actions-following-automated-investigations-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 자동화 된 조사에 따라 수정 작업 수행

**적용 대상:**
- Microsoft 위협 방지


## <a name="remediation-actions"></a>수정 작업

Microsoft Threat Protection에 대 한 자동화 된 조사 중 및 후에는 악성 또는 의심 스러운 항목에 대 한 재구성 작업이 식별 됩니다. 일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다. 전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다. 자동화 된 조사 작업을 수행, 승인 또는 거부 한 후에 완료 됩니다.

다음 표에서는 현재 Microsoft Threat Protection에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다. 

|장치 (끝점) 재구성 작업  |전자 메일 수정 작업  |
|---------|---------|
|파일 격리<br/>레지스트리 키 추가<br/>프로세스 중단 <br/>서비스 중지 <br/>드라이버 해제 <br/>예약된 작업 제거      |전자 메일 메시지 또는 클러스터의 일시 삭제<br/>차단 URL(클릭 시간)<br/>외부 메일 전달 해제          |

승인 보류 중 이거나 이미 완료 되었는지 여부에 관계 없이 수정 작업은 [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.

## <a name="verdicts-and-outcomes-following-automated-investigations"></a>자동화 된 조사 후 Verdicts 및 결과

자동화 조사가 완료 되면 관련된 모든 증명정보에 따라 결과가 도출되고 재구성 작업이 식별됩니다.   경우에 따라 수정 작업이 자동으로 수행 됩니다. 그 밖의 경우에는 재구성 작업이 승인을 기다립니다. 도출 가능한 의견과 결과는 다음 테이블에서 확인할 수 있습니다. 

|의견    |영역   |결과|
|------|------|------|
|악성  |장치 (끝점)    |재구성 작업이 자동으로 실행 됩니다.|
|악성  |전자 메일 콘텐츠 (Url 또는 첨부 파일) | 승인 보류 중인 재구성 활동 |
|피싱 |장치 또는 전자 메일 콘텐츠 |승인 보류 중인 재구성 활동 |
|정리  |장치 또는 전자 메일 콘텐츠   |재구성 작업이 필요 하지 않습니다.|

[활동 센터에서 대기 중인 작업 검토](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요. 가양성 [/네거티브를 보고](mtp-autoir-report-false-positives-negatives.md)합니다.

## <a name="next-steps"></a>다음 단계

- [작업 승인 또는 거부](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)

- [알림 센터에 대한 자세한 정보](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
