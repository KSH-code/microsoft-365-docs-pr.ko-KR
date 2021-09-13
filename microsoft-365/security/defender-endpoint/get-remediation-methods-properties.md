---
title: 수정 작업 방법 및 속성
description: API 응답에는 테넌트에서 & 취약성 관리 수정 활동에 대한 위협이 포함되어 있습니다. 모든 재구성 활동, 수정 활동 하나만 또는 선택한 수정 작업에 대해 노출된 장치에 대한 정보를 요청할 수 있습니다.
keywords: api, 수정, 수정 api, get, 수정 작업, 수정 방법, 수정 속성,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0ca1bc84d5e8cf5498ed3dc19cba3928823796ff
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190982"
---
# <a name="remediation-activity-methods-and-properties"></a>수정 작업 방법 및 속성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

API 응답에는 [테넌트에서 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)위협 요소 수정   활동이 포함되어 있습니다.

## <a name="methods"></a>메서드

방법|데이터 형식|설명
:---|:---|:---
[모든 수정 작업 나열s](get-remediation-all-activities.md)|조사 컬렉션|모든 수정 활동에 대한 정보를 반환합니다.
[한 번의 수정 작업이 있는 노출된 장치 목록](get-remediation-exposed-devices-activities.md)|조사 엔터티|지정된 수정 활동에 대해 노출된 장치에 대한 정보를 반환합니다.
[ID로 수정 작업 1개 가져오기](get-remediation-one-activity.md)|조사 엔터티|지정한 수정 활동에 대한 정보를 반환합니다.

재구성 활동에 [대해 자세히 알아보시다.](tvm-remediation.md)

## <a name="properties"></a>속성

속성 ID|데이터 형식|설명
:---|:---|:---
category|문자열|재구성 활동 범주(소프트웨어/보안 구성)
completerEmail|String|누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.
completerId|문자열|누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.
completionMethod|String|재구성 활동은 "자동"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사용자가 "수동으로" 완료할 수 있습니다.
createdOn|날짜/시간|이 수정 활동이 만들어진 시간
설명|문자열|이 수정 활동에 대한 설명
dueOn|날짜/시간|이 수정 활동에 대한 작성자가 설정한 기한
fixedDevices||고정된 장치 수
id|String|이 수정 활동의 ID
nameId|문자열|관련 제품 이름
priority|String|이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)
productId|문자열|관련 제품 ID
productivityImpactRemediationType|문자열|사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다. 이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.
rbacGroupNames|String|관련 장치 그룹 이름
recommendedProgram|String|업그레이드할 권장 프로그램
recommendedVendor|String|업그레이드할 권장 공급업체
recommendedVersion|문자열|업데이트/업그레이드에 권장되는 버전
relatedComponent|문자열|이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)
requesterEmail|문자열|작성자 전자 메일 주소
requesterId|문자열|Creator 개체 ID
requesterNotes|String|이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)
scid|문자열|관련 보안 권장 정보의 SCID
status|String|재구성 활동 상태(활성/완료)
statusLastModifiedOn|날짜/시간|상태 필드가 업데이트된 날짜
targetDevices|Long|이 수정을 적용할 수 있는 노출된 장치 수
제목|String|이 수정 활동의 제목입니다.
type|문자열|수정 유형
vendorId|문자열|관련 공급업체 이름

## <a name="see-also"></a>참고 항목

- [ID로 수정 작업 1개 가져오기](get-remediation-one-activity.md)

- [모든 수정 작업 나열s](get-remediation-all-activities.md)

- [한 번의 수정 작업이 있는 노출된 장치 목록](get-remediation-exposed-devices-activities.md)

- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)

- [조직의 취약성](tvm-weaknesses.md)
