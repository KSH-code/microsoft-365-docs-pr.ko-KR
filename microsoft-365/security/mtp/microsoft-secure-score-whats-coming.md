---
title: Microsoft 보안 점수가 어떻게 제공 됩니까?
description: Microsoft 365 보안 센터의 Microsoft 보안 점수, 세부 정보를 계산 하는 방법 및 보안 관리자가 예상할 수 있는 사항에 대해 설명 합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 점수, 보안 센터, 개선 작업
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545937"
---
# <a name="whats-coming-in-microsoft-secure-score"></a>Microsoft 보안 점수가 어떻게 제공 됩니까?

Microsoft의 보안 [점수](microsoft-secure-score-new.md) 를 보안 환경을 보다 효율적으로 대표 하 고 유용성을 향상 시키기 위해 곧 몇 가지 사항을 변경 하 고 있습니다. 점수와 가능한 최대 점수가 변경 됩니다. 그러나 보안 환경을 변경 하는 것은 아닙니다.

최근 변경 내용에 대 한 자세한 내용은 [Microsoft 보안 점수의 새로운 기능](microsoft-secure-score-new.md#whats-new) 을 참조 하세요.

## <a name="june-2020"></a>2020 년 6 월

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 제거

* 공격 표면 축소 규칙 켜기

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a>Microsoft Defender Advanced Threat Protection에 대 한 개선 작업 추가

* 하위 프로세스를 만들지 못하도록 Adobe Reader 차단
* 랜 섬 웨어에 대 한 고급 보호 사용
* 모든 Office 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단
* Office 응용 프로그램에서 실행 가능한 콘텐츠를 만들지 못하도록 차단
* 다운로드 한 실행 가능한 콘텐츠를 실행 하는 JavaScript 또는 VBScript 차단
* 잠재적으로 난독 처리 된 스크립트의 실행 차단
* 전자 메일 클라이언트 및 webmail에서 실행 가능한 콘텐츠 차단
* Office 통신 응용 프로그램에서 하위 프로세스를 만들지 못하도록 차단
* 신뢰할 수 없으며 USB에서 실행 되는 서명 되지 않은 프로세스 차단
* WMI 이벤트 구독을 통해 지 속성 차단
* Office 응용 프로그램에서 다른 프로세스에 코드를 주입 하지 못하도록 차단
* 실행 파일이 전파, 연령 또는 신뢰할 수 있는 목록 조건을 충족 하지 않는 이상 실행 되지 않도록 차단
* PSExec 및 WMI 명령에서 시작 되는 프로세스 만들기 차단
* Windows 로컬 보안 기관 하위 시스템 (lsass.exe)에서 자격 증명 가로채기 차단
* Office 매크로에서 Win32 API 호출 차단
