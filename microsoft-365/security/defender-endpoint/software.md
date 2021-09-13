---
title: 소프트웨어 방법 및 속성
description: 최근 경고를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: f14da0e999a0ec38c9be7ef36e47b2c786e12e97
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220264"
---
# <a name="software-resource-type"></a>소프트웨어 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>메서드

방법 |반환 형식 |설명
:---|:---|:---
[소프트웨어 목록](get-software.md) | 소프트웨어 컬렉션 | 조직 소프트웨어 인벤토리를 나열합니다.
[ID별 소프트웨어 가져오기](get-software-by-id.md) | 소프트웨어 | 소프트웨어 ID로 특정 소프트웨어를 다운로드합니다.
[소프트웨어 버전 배포 목록](get-software-ver-distribution.md)| 배포 모음 | 소프트웨어 ID로 소프트웨어 버전 배포를 나열합니다.
[소프트웨어별 컴퓨터 목록](get-machines-by-software.md)| MachineRef 컬렉션 | 소프트웨어 ID와 연결된 장치 목록을 검색합니다.
[소프트웨어별 취약성 목록](get-vuln-by-software.md) | [취약성](vulnerability.md) 컬렉션 | 소프트웨어 ID와 관련된 취약점 목록을 검색합니다.
[누락된 KB 가져오기](get-missing-kbs-software.md) | KB 컬렉션 | 소프트웨어 ID와 연결된 누락된 KB 목록 다운로드

## <a name="properties"></a>속성

속성 |   유형   |   설명
:---|:---|:---
id | String | 소프트웨어 ID
이름 | 문자열 | 소프트웨어 이름
공급업체 | 문자열 | 소프트웨어 공급업체 이름
약점 | Long | 검색된 취약성 수
publicExploit | 부울 | 일부 취약성에 대한 공개 악용이 있습니다.
activeAlert | 부울 | 활성 경고가 이 소프트웨어와 연결됩니다.
exposedMachines | Long | 노출된 장치 수
impactScore | 실수 | 이 소프트웨어의 노출 점수 영향
