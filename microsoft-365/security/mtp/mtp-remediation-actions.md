---
title: Microsoft Threat Protection의 자동화 된 조사 및 응답 기능의 수정 작업
description: Microsoft Threat Protection의 자동화된 조사 및 대응 기능에 대한 개요를 확인하세요.
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
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175951"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 자동화 된 조사 및 응답 기능의 수정 작업

**적용 대상:**
- Microsoft 위협 방지

Microsoft Threat Protection의 자동화 된 조사 및 응답 기능은 특정 수정 작업을 포함 합니다. 일부 유형의 재구성 작업은 끝점이 라고도 하는 장치에서 수행 됩니다. 전자 메일 콘텐츠에 대 한 기타 수정 작업을 수행 합니다.

다음 표에서는 현재 Microsoft Threat Protection에서 지원 되는 수정 작업을 요약 하 여 보여 줍니다. 

|끝점 수정 작업  |전자 메일 수정 작업  |
|---------|---------|
|파일 격리<br/>레지스트리 키 추가<br/>프로세스 중단 <br/>서비스 중지 <br/>레지스트리 키 추가 <br/>드라이버 해제 <br/>예약된 작업 제거      |전자 메일 메시지 또는 클러스터의 일시 삭제<br/>차단 URL(클릭 시간)<br/>외부 메일 전달 해제          |

승인 보류 중 이거나 이미 완료 되었는지 여부에 관계 없이 수정 작업은 [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)에서 볼 수 있습니다.

## <a name="next-steps"></a>다음 단계

- [자동화된 조사 및 대응과 관련된 조치 승인 또는 거부](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [알림 센터에 대한 자세한 정보](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
