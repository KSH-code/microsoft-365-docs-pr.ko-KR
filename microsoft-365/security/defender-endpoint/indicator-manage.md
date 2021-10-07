---
title: 지표 관리
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 파일 해시, IP 주소, URL 또는 도메인에 대한 표시기를 관리합니다.
keywords: import, indicator, list, ioc, csv, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8c35f6c399e7668883b5b276fffd56f162984669
ms.sourcegitcommit: f6cb10b1dc4b679b7890d059f7242870fc40b9f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2021
ms.locfileid: "60225023"
---
# <a name="manage-indicators"></a>지표 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

1. 탐색 창에서 **끝점 설정(규칙** 아래)를 \>  \>  **선택합니다.**

2. 관리할 엔터티 유형의 탭을 선택합니다.

3. 표시기 세부 정보를 업데이트하고  목록에서  엔터티를 제거하려면 저장 또는 삭제 단추를 클릭합니다.

## <a name="import-a-list-of-iocs"></a>IoC 목록 가져오기

표시기 특성, 수행되는 작업 및 기타 세부 정보를 정의하는 CSV 파일을 업로드할 수도 있습니다.

지원되는 열 특성을 알고자 샘플 CSV를 다운로드합니다.

1. 탐색 창에서 **끝점 설정(규칙** 아래)를 \>  \>  **선택합니다.**

2. 표시기를 가져올 엔터티 유형의 탭을 선택합니다.

3. 파일 **선택** \> **가져오기 를 선택합니다.**

4. 가져오기 **를 선택합니다.** 가져오고자 하는 모든 파일에 대해 이 작업을 합니다.

5. **완료** 를 선택합니다.

다음 표에는 지원되는 매개 변수가 표시됩니다.

매개 변수|유형|설명
:---|:---|:---
indicatorType|Enum|표시기 유형입니다. 가능한 값은 "FileSha1", "FileSha256", "IpAddress", "DomainName" 및 "Url"입니다. **필수**
indicatorValue|String|Indicator [엔터티의 ID입니다.](ti-indicator.md) **필수**
조치|Enum|표시기가 조직에서 검색되는 경우 수행되는 작업입니다. 가능한 값은 "Alert", "AlertAndBlock" 및 "Allowed"입니다. **필수**
title|String|표시기 경고 제목입니다. **필수**
description|String| 표시기 설명입니다. **필수**
expirationTime|DateTimeOffset|YYYY-MM-DDTHH:MM:SS.0Z 형식의 표시기 만료 시간입니다. **옵션**
심각도|Enum|표시기 심각도입니다. 가능한 값은 "정보", "낮음", "중간" 및 "높음"입니다. **선택**
recommendedActions|String|TI 표시기 경고 권장 작업. **옵션**
rbacGroupNames|String|콤보로 구분된 RBAC 그룹 이름 목록 표시기가 적용됩니다. **옵션**
category|문자열|경고 범주입니다. 예로는 실행 및 자격 증명 액세스가 있습니다. **선택**
mitretechniques|String|MITRE 기술 코드/id(콤보로 구분) 자세한 내용은 전략 [Enterprise 참조하세요.](https://attack.mitre.org/tactics/enterprise/) **선택 사항** MITRE 기술을 사용할 때 범주에 값을 추가하는 것이 좋습니다.
GenerateAlert|String|경고를 생성해야 하는지 여부입니다. 가능한 값은 True 또는 False입니다. **선택**



> [!NOTE]
> IP 주소에 Inter-Domain CIDR(Classless Inter-Domain Routing) 상용화는 지원되지 않습니다.
자세한 내용은 끝점용 Microsoft Defender 경고 범주가 [이제 MITRE ATT 및 CK에&참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)

## <a name="see-also"></a>참고 항목

- [지표 만들기](manage-indicators.md)
- [파일에 대한 지표 만들기](indicator-file.md)
- [IP 및 URL/도메인에 대한 지표 만들기](indicator-ip-domain.md)
- [인증서를 기반으로 표시기 만들기](indicator-certificates.md)
