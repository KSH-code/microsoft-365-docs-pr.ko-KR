---
title: 점수 방법 및 속성
description: 장치 그룹당 조직의 노출 점수, 장치 보안 점수 및 노출 점수를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 점수, 노출 점수, 장치 보안 점수, 장치 그룹당 노출 점수
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 6cb0fdb8b2fec03c616b1c0607e4f8be6476b96e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191710"
---
# <a name="score-resource-type"></a>점수 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>메서드

방법|반환 형식|설명
:---|:---|:---
[노출 점수 가져오기](get-exposure-score.md)|[점수](score.md)|조직 노출 점수를 얻습니다.
[장치 보안 점수 가져오기](get-device-secure-score.md)|[점수](score.md)|조직 장치 보안 점수를 얻습니다.
[장치 그룹당 노출 점수 나열](get-machine-group-exposure-score.md)|[점수](score.md)|장치 그룹당 점수를 나열합니다.

## <a name="properties"></a>속성

속성|유형|설명
:---|:---|:---
점수|실수|현재 점수입니다.
시간|날짜/시간|이 API를 호출한 날짜 및 시간입니다.
RbacGroupName|String|장치 그룹 이름입니다.
RbacGroupId|String|장치 그룹 ID입니다.
