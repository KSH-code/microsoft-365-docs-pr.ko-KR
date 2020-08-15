---
title: 이중 바이트 문자 집합 릴리스 노트(미리 보기)를 위한 Microsoft 365 규정 준수 지원
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 더블 바이트 문자 집합에 대한 지원을 위한 릴리스 노트
ms.openlocfilehash: 13bac873f2ba18bc166451ea73ec0d569fb30f68
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695269"
---
# <a name="support-for-double-byte-character-set-release-notes-preview"></a>더블 바이트 문자 집합 릴리스 노트(미리보기)를 지원

 Microsoft 365 Information Protection은 이제 다음에 대해 미리보기 더블 바이트 문자 집합 언어를 지원합니다.

- 중국어(간체)
- 중국어(번체)
- 한국어
- 일본어

이 미리 보기는 상용 클라우드에서만 실행되며 롤아웃은 다음으로 제한됩니다.

- 일본
- 한국
- 중국
- 홍콩
- 마카오
- 대만

이 지원은 중요한 정보 유형 및 키워드 사전에서 사용할 수 있으며 데이터 손실 방지, 통신 규정 준수, Exchange 온라인, SharePoint 온라인, OneDrive for Business 및 Teams 솔루션에 반영됩니다.

## <a name="known-issues"></a>알려진 문제

- 전자 메일에 첨부된 텍스트 파일이 BOM(바이트 순서 표시)이 없는 UTF-8 형식인 경우, 통신 준수 정책에서 전자 메일이 탐지되지 않습니다.

- 정책 조건에 대해 "메시지에는 다음 단어가 포함되어 있습니다"라는 문장을 입력하면 통신 규정 준수 정책이 값을 검색할 수 없습니다. 정책에 지정된 텍스트가 단어로 작성되면 검색이 가능하지만, 문장 중간에 작성되면 검색되지 않습니다.

- 사전을 유형 정보로 지정하는 통신 준수 정책은 팀 개인 대화 및 채널 대화를 탐지하지 않습니다.

- 이 단계에서는 통신 규정 준수에 대해 다음 조건이 지원되지 않습니다(향후 이러한 문제를 해결할 계획임). 
  - "메세지에 다음 단어가 포함되어 있습니다."
  - "메세지에 다음 단어가 없습니다."
  - "첨부에는 이러한 단어가 포함되어 있습니다."
  - "첨부에는 이러한 단어가 포함되어 있습니다."

대신 메시지 및 첨부 파일 간의 패턴을 탐지할 키워드 사전이 있는 사용자 정의 SIT(중요한 정보 유형)을 만들고 이 사용자 정의 SIT를 통신 규정 준수 정책 조건으로 사용하는 것이 좋습니다.
