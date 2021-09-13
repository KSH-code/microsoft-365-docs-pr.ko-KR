---
title: 공격 표면 감소 이벤트 보기
description: 사용자 지정 보기를 가져와 공격 표면 축소 이벤트를 볼 수 있습니다.
keywords: 이벤트 보기, exploit guard, 감사, 검토, 이벤트
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 6a4d548edb660838be9ea3d1a69749f23d3ac6c8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221908"
---
# <a name="view-attack-surface-reduction-events"></a>공격 표면 감소 이벤트 보기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)

이벤트 뷰어에서 공격 표면 감소 이벤트를 검토하여 작동되는 규칙 또는 설정을 모니터링합니다. 또한 설정이 너무 "시저"되거나 매일 워크플로에 영향을 미치는지 확인할 수 있습니다.

기능을 평가할 때 이벤트를 검토하는 것이 편리한 기능입니다. 기능 또는 설정에 대해 감사 모드를 사용하도록 설정한 다음 완전히 활성화된 경우 어떤 일이 일어나는지 검토할 수 있습니다.

이 문서에서는 모든 이벤트, 관련 기능 또는 설정을 나열하고 특정 이벤트에 대해 필터링하는 사용자 지정 보기를 만드는 방법에 대해 설명합니다.

E5 구독이 있는 경우 이벤트, 차단 및 경고에 대한 자세한 보고를 Windows 보안 [끝점용 Microsoft Defender를 사용하세요.](microsoft-defender-endpoint.md)

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>사용자 지정 보기를 사용하여 공격 표면 감소 기능 검토

이벤트 뷰어에서 Windows 사용자 지정 보기를 만들어 특정 기능 및 설정에 대한 이벤트만 볼 수 있습니다. 가장 쉬운 방법은 사용자 지정 보기를 XML 파일로 가져오는 것입니다. 이 페이지에서 직접 XML을 복사할 수 있습니다.

기능에 해당하는 이벤트 영역으로 수동으로 이동할 수도 있습니다.

### <a name="import-an-existing-xml-custom-view"></a>기존 XML 사용자 지정 보기 가져오기

1. 빈 .txt 파일을 만들고 파일 보기에 사용할 사용자 지정 보기의 XML을 .txt 복사합니다. 사용할 각 사용자 지정 보기에 대해 이 작업을 합니다. 파일 이름을 다음과 같이 바꿔야 합니다(형식을 .txt 변경해야 .xml.
    - 제어된 폴더 액세스 이벤트 사용자 지정 보기: *cfa-events.xml*
    - Exploit Protection 이벤트 사용자 지정 보기: *ep-events.xml*
    - 공격 표면 감소 이벤트 사용자 지정 *보기:asr-events.xml*
    - 네트워크/보호 이벤트 사용자 지정 *보기:np-events.xml*

2. 이벤트 **뷰어를** 시작 메뉴 이벤트 **뷰어를 열 수 있습니다.**

3. 작업 **사용자 지정** 보기 \> **가져오기...를 선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![Even 뷰어 창의 왼쪽에 있는 사용자 지정 보기 가져오기 강조 표시 애니메이션](images/events-import.gif)

4. 원하는 사용자 지정 보기에 대한 XML 파일을 추출한 위치로 이동하여 선택합니다.

5. **열기** 를 선택합니다.

6. 이 보기는 해당 기능과 관련된 이벤트만 표시하기 위해 필터를 지정하는 사용자 지정 보기를 만듭니다.

### <a name="copy-the-xml-directly"></a>XML 직접 복사

1. 이벤트 **뷰어를** 시작 메뉴 이벤트 뷰어 를 Windows **를 열 수 있습니다.**

2. 왼쪽 패널의 **동작에서** 사용자 지정 **보기 만들기...를 선택합니다.**

   > [!div class="mx-imgBorder"]
   > ![이벤트 뷰어 창에서 사용자 지정 보기 만들기 옵션을 강조 표시하는 애니메이션입니다.](images/events-create.gif)

3. XML 탭으로 이동하여 수동으로 쿼리 **편집을 선택합니다.** XML 옵션을 사용하는 경우 필터 탭을 사용하여  쿼리를 편집할 수 없는 경고가 표시됩니다. **예** 를 선택합니다.

4. 이벤트를 필터링할 기능에 대한 XML 코드를 XML 섹션에 붙여 넣습니다.

5. **확인** 을 선택합니다. 필터의 이름을 지정합니다. 이렇게 하면 해당 기능과 관련된 이벤트만 표시하기 위해 필터를 지정하는 사용자 지정 보기가 생성됩니다.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>공격 표면 감소 규칙 이벤트에 대한 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>제어된 폴더 액세스 이벤트에 대한 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>Exploit Protection 이벤트용 XML

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>네트워크 보호 이벤트에 대한 XML

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>공격 표면 감소 이벤트 목록

모든 공격 표면 감소 이벤트는 **Microsoft** > 서비스 로그 > Windows 다음 표에 나열된 폴더 또는 공급자 아래에 있습니다.

이벤트 뷰어에서 다음 이벤트에 Windows 있습니다.

1. 시작 **메뉴를** 열고 이벤트 **뷰어 를 입력한** 다음 이벤트 **뷰어 결과를** 선택합니다.
2. **Microsoft >** > Windows 응용 프로그램 및 서비스 로그를 확장한 다음 아래 표의 **공급자/원본에** 나열된 폴더로 이동합니다.
3. 하위 항목을 두 번 클릭하여 이벤트를 볼 수 있습니다. 이벤트를 스크롤하여 원하는 이벤트를 찾으면 됩니다.

   ![이벤트 뷰어를 사용하여 표시하는 애니메이션](images/event-viewer.gif)

<br>

****

|기능|공급자/원본|이벤트 ID|설명|
|---|---|:---:|---|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|1|ACG 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|2|ACG 적용|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|3 |자식 프로세스 감사 허용 안 함|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|4 |자식 프로세스 블록 허용 안 함|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|5 |낮은 무결성 이미지 감사 차단|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|6 |낮은 무결성 이미지 블록 차단|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|7 |원격 이미지 감사 차단|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|8 |원격 이미지 블록 차단|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|9 |win32k 시스템 호출 감사 사용 안 함|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|10 |Win32k 시스템 호출 블록 사용 안 함|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|11 |코드 무결성 가드 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|12 |코드 무결성 가드 블록|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|13|EAF 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|14 |EAF 적용|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|15 |EAF+ 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|16 |EAF+ 적용|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|17 |IAF 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|18 |IAF 적용|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|19|ROP StackPivot 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|20|ROP StackPivot 적용|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)| 21|ROP CallerCheck 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|22|ROP CallerCheck 적용|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|23|ROP SimExec 감사|
|악용 방지|Security-Mitigations(커널 모드/사용자 모드)|24|ROP SimExec 적용|
|악용 방지|WER-진단|5 |CFG 블록|
|악용 방지|Win32K(작동)|260|신뢰할 수 없는 글꼴|
|네트워크 보호|Windows Defender(작동)|5007|설정이 변경될 때의 이벤트|
|네트워크 보호|Windows Defender(작동)|1125|감사 모드에서 네트워크 보호가 발생하면 이벤트|
|네트워크 보호|Windows Defender(작동)|1126|차단 모드에서 네트워크 보호가 발생하면 이벤트|
|제어된 폴더 액세스|Windows Defender(작동)|5007|설정이 변경될 때의 이벤트|
|제어된 폴더 액세스|Windows Defender(작동)|1124|감사된 제어된 폴더 액세스 이벤트|
|제어된 폴더 액세스|Windows Defender(작동)|1123|차단된 제어된 폴더 액세스 이벤트|
|제어된 폴더 액세스|Windows Defender(작동)|1127|차단된 제어된 폴더 액세스 섹터 쓰기 차단 이벤트|
|제어된 폴더 액세스|Windows Defender(작동)|1128|감사된 제어된 폴더 액세스 섹터 쓰기 차단 이벤트|
|공격 표면 감소|Windows Defender(작동)|5007|설정이 변경될 때의 이벤트|
|공격 표면 감소|Windows Defender(작동)|1122|감사 모드에서 규칙이 발생하면 이벤트|
|공격 표면 감소|Windows Defender(작동)|1121|차단 모드에서 규칙이 발생하면 이벤트|
|
