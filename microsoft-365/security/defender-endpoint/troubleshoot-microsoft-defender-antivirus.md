---
title: Microsoft Defender 바이러스 백신 이벤트 코드 및 오류 코드
description: 이벤트 MICROSOFT DEFENDER 바이러스 백신 오류의 원인 및 해결 방법 찾아 보기
keywords: 이벤트, 오류 코드, siem, 로깅, 문제 해결, wef, Windows 이벤트 전달
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 2dda17d55dbe5e86b6d76e3a766a020c6e0bc3aa
ms.sourcegitcommit: f88a0ec621e7d9bc5f376eeaf70c8a9800711f88
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2021
ms.locfileid: "59356528"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>이벤트 로그 및 오류 코드를 검토하여 Microsoft Defender 바이러스 백신 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

이 항목에 문제가 Microsoft Defender 바이러스 백신 이 항목의 표를 검색하여 일치하는 문제 및 잠재적인 해결 방법을 찾을 수 있습니다.

표 목록에는 다음이 나열됩니다.

- [Microsoft Defender 바이러스 백신 이벤트 ID(Windows 10](#windows-defender-av-ids) 및 Windows Server 2016)
- [Microsoft Defender 바이러스 백신 오류 코드](#error-codes)
- [내부 Microsoft Defender 바이러스 백신 클라이언트 오류 코드(개발 및 테스트 중에 Microsoft에서 사용)](#internal-error-codes)

> [!TIP]
> Microsoft Defender for Endpoint 데모 웹 [사이트를](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 방문하여 demo.wd.microsoft.com 작동을 확인할 수 있습니다.
>
> - 클라우드 제공 보호
> - 빠른 학습(신속한 차단 포함)
> - 잠재적으로 원치 않는 응용 프로그램 차단

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Microsoft Defender 바이러스 백신 이벤트 ID

Microsoft Defender 바이러스 백신 로그에 이벤트 WINDOWS 기록합니다.

이벤트 로그를 직접 보거나 타사 SIEM(보안 정보 및 이벤트 관리) 도구가 있는 [](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) 경우 Microsoft Defender 바이러스 백신 클라이언트 이벤트 MICROSOFT DEFENDER 바이러스 백신 끝점에서 특정 이벤트 및 오류를 검토할 수도 있습니다.

이 섹션의 표에는 기본 Microsoft Defender 바이러스 백신 이벤트 MICROSOFT DEFENDER 바이러스 백신 나열되어 있으며 가능한 경우 오류를 수정하거나 해결하기 위한 권장 해결 방법을 제공합니다.

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>이벤트 Microsoft Defender 바이러스 백신 보기

1. 이벤트 **뷰어 를 열 수 있습니다.**
2. 콘솔 트리에서 **응용** 프로그램 및 서비스 **로그,** **Microsoft** 를 확장한 다음 를 Windows **를** Windows Defender.
3. 작동 을 두 **번 클릭합니다.**
4. 세부 정보 창에서 개별 이벤트 목록을 보고 이벤트를 찾을 수 있습니다.
5. 이벤트를 클릭하여 아래쪽 창의 일반 및 세부 정보 탭에서  이벤트에 대한 특정 세부 **정보를** 볼 수 있습니다.

<table>
<tr>
<th colspan="2" >이벤트 ID: 1000</th>
</tr>
<tr>
<td>
기호 이름:
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 검사가 시작된 경우 </b>
</td>
</tr>
<tr>
<td >
설명:
</td>
<td >
<dl>
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.<ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
</ul>
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.<ul>
<li>전체 검사</li>
<li>빠른 검사</li>
<li>고객 검사</li>
</ul>
</dt>
<dt>리소스 검사: &lt; 검사된 리소스(예: 파일/directories/BHO)입니다. &gt; </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1001</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 검사가 완료된 경우</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
<dl>
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.<ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
</ul>
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.<ul>
<li>전체 검사</li>
<li>빠른 검사</li>
<li>고객 검사</li>
</ul>
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>검사 시간: &lt; 검사 &gt; 기간입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1002</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 검사가 완료되기 전에 중지되었습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
<dl>
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.<ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
</ul>
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.<ul>
<li>전체 검사</li>
<li>빠른 검사</li>
<li>고객 검사</li>
</ul>
</dt>
<dt>사용자: &lt; 도메인 &gt; &amp; lt; 사용자 &gt; </dt>
<dt>검사 시간: &lt; 검사 &gt; 기간입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1003</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 검사가 일시 중지된 경우 </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
<dl>
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.<ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
</ul>
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.<ul>
<li>전체 검사</li>
<li>빠른 검사</li>
<li>고객 검사</li>
</ul>
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1004</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 검사가 다시 시작된 경우 </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
<dl>
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.<ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
</ul>
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.<ul>
<li>전체 검사</li>
<li>빠른 검사</li>
<li>고객 검사</li>
</ul>
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1005</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 검사가 실패했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
<dl>
<dt>검사 ID: &lt; 관련 검사의 ID &gt; 번호입니다.</dt> 
<dt> 검사 유형: &lt; 검사 &gt; 유형, 예를 들면 다음과 같습니다.<ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
</ul>
</dt>
<dt>검사 매개 변수: &lt; 검사 매개 &gt; 변수, 예를 들면 다음과 같습니다.<ul>
<li>전체 검사</li>
<li>빠른 검사</li>
<li>고객 검사</li>
</ul>
</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
바이러스 백신 클라이언트에서 오류가 발생하고 현재 검사가 중지되었습니다. 클라이언트 쪽 문제로 인해 검사가 실패할 수 있습니다. 이 이벤트 레코드에는 검사 ID, 검사 유형(Microsoft Defender 바이러스 백신, 스파이웨어 방지, 맬웨어 방지), 검사 매개 변수, 검색을 시작한 사용자, 오류 코드 및 오류 설명이 포함됩니다.
이 이벤트를 해결합니다.
<ol>
<li>검색을 다시 실행합니다.</li>
<li>같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>지원 사이트로 이동하여 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아야 합니다. <b></b></li>
<li><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1006</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진이 맬웨어 또는 사용자 원치 않는 기타 소프트웨어를 발견했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.<ul>
<li>알 수 없음</li>
<li>로컬 컴퓨터</li>
<li>네트워크 공유</li>
<li>인터넷</li>
<li>들어오는 트래픽</li>
<li>아웃보이스 트래픽</li>
</ul>
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:<ul>
<li>Heuristics</li>
<li>일반</li>
<li>구체적</li>
<li>동적 서명</li>
</ul>
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:<ul>
<li>사용자: 사용자가 시작한 경우</li>
<li>시스템: 시스템이 시작된 경우</li>
<li>실시간: 실시간 구성 요소가 시작되었습니다.</li>
<li>IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</li>
<li>NIS: 네트워크 검사 시스템</li>
<li>IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</li>
<li>ELAM(맬웨어 방지 조기 실행). 여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</li>
<li>원격 attestation</li>
</ul>AMSI(맬웨어 방지 검사 인터페이스). 제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.
UAC </dt> 
<dt>상태: &lt; 상태 &gt; </dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt>서명 버전의
<dt>프로세스: &lt; &gt; </dt>정의 버전 엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1007</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼은 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 이 머신을 보호하기 위해 작업을 수행했습니다. 자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>이름: &lt; 위협 이름 &gt; </dt>
<dt>ID: 위협 &lt; ID &gt; </dt> 
<dt> 심각도: &lt; 심각도, &gt; 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt> 작업: &lt; &gt; 작업, 예를 들면 다음과 같습니다.<ul>
<li>정리: 리소스가 정리된 경우</li>
<li>Quarantine: Resource was quarantined</li>
<li>제거: 리소스가 삭제되었습니다.</li>
<li>허용: 리소스가 실행/존재할 수 있습니다.</li>
<li>사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</li>
<li>작업 없음: 아무 작업도 수행하지 않습니다.</li>
<li>차단: 리소스가 실행되지 않습니다.</li>
</ul>
</dt>
<dt>상태: &lt; 상태 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진
<dt> &lt; 버전: &gt; </dt> Antimalware Engine 버전
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1008</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼이 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행하려고 했지만 작업이 실패했습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 또는 사용자 원치 않는 기타 소프트웨어에 대해 조치를 취할 때 오류가 발생했습니다. 자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>이름: &lt; 위협 이름 &gt; </dt>
<dt>ID: 위협 &lt; ID &gt; </dt> 
<dt> 심각도: &lt; 심각도, &gt; 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 동작: &lt; 동작 , 예를 들면 &gt; 다음과 같습니다.<ul>
<li>정리: 리소스가 정리된 경우</li>
<li>Quarantine: Resource was quarantined</li>
<li>제거: 리소스가 삭제되었습니다.</li>
<li>허용: 리소스가 실행/존재할 수 있습니다.</li>
<li>사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</li>
<li>작업 없음: 아무 작업도 수행하지 않습니다.</li>
<li>차단: 리소스가 실행되지 않습니다.</li>
</ul>
</dt>
<dt>오류 코드: &lt; 오류 코드 &gt; 위협 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>상태: &lt; 상태 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진
<dt> &lt; 버전: &gt; </dt> Antimalware Engine 버전
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1009</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼이 항목을 검지에서 복원했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 항목을 복원했습니다. 자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1010</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼에서 항목을 검지에서 복원할 수 없습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 항목을 복구하는 중 오류가 발생했습니다. 자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1011</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼에서 항목을 삭제했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 항목을 삭제했습니다.<br/>자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>서명 버전: &lt; 정의 버전 &gt; </dt>엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1012</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼에서 항목을 검지에서 삭제할 수 없습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 항목을 삭제하는 중 오류가 발생했습니다.
자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1013</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼에서 맬웨어 및 사용자 원치 않는 기타 소프트웨어 기록을 삭제했습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 맬웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 기록이 제거되었습니다.
<dl>Time: 이벤트가 발생한 시간(예: 기록이 
<dt>제거된 시간)입니다. 이 매개 변수는 위협 이벤트에서 사용되지 않습니다. 따라서 재구성 시간인지 감염 시간인지에 대한 혼동을 피할 수 있습니다. 이러한 경우 이러한</dt> 작업을 작업 시간 또는 검색 시간으로 특별히 호출합니다. 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1014</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
맬웨어 방지 플랫폼에서 맬웨어 및 사용자 원치 않는 기타 소프트웨어 기록을 삭제할 수 없습니다.
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 맬웨어 및 사용자 원치 않는 기타 소프트웨어의 기록을 제거하려고 하는 오류가 발생했습니다.
<dl>Time: 이벤트가 발생한 시간(예: 기록이 
<dt>제거된 시간)입니다. 이 매개 변수는 위협 이벤트에서 사용되지 않습니다. 따라서 재구성 시간인지 감염 시간인지에 대한 혼동을 피할 수 있습니다. 이러한 경우 이러한</dt> 작업을 작업 시간 또는 검색 시간으로 특별히 호출합니다. 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다. </dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1015</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼에서 의심스러운 동작을 감지했습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 의심스러운 동작을 감지했습니다.<br/>자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.
<ul>
<li>알 수 없음</li>
<li>로컬 컴퓨터</li>
<li>네트워크 공유</li>
<li>인터넷</li>
<li>들어오는 트래픽</li>
<li>아웃보이스 트래픽</li>
</ul>
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:<ul>
<li>Heuristics</li>
<li>일반</li>
<li>구체적</li>
<li>동적 서명</li>
</ul>
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:<ul>
<li>사용자: 사용자가 시작한 경우</li>
<li>시스템: 시스템이 시작된 경우</li>
<li>실시간: 실시간 구성 요소가 시작되었습니다.</li>
<li>IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</li>
<li>NIS: 네트워크 검사 시스템</li>
<li>IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</li>
<li>ELAM(맬웨어 방지 조기 실행). 여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</li>
<li>원격 attestation</li>
</ul>AMSI(맬웨어 방지 검사 인터페이스). 제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.
UAC </dt> 
<dt>상태: &lt; 상태 &gt; </dt>
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt>서명 ID의 프로세스: 심각도와
<dt>일치하는 열입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 &lt; &gt; 버전:</dt>Antimalware Engine 버전
<dt>화질 레이블:</dt>대상 파일 이름: 파일
<dt>이름 파일의 &lt; &gt; 이름입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1116</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼에서 맬웨어 또는 사용자 원치 않는 기타 소프트웨어를 검색했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 맬웨어 또는 사용자 원치 않는 기타 소프트웨어가 검색되었습니다.<br/>자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.
<ul>
<li>알 수 없음</li>
<li>로컬 컴퓨터</li>
<li>네트워크 공유</li>
<li>인터넷</li>
<li>들어오는 트래픽</li>
<li>아웃보이스 트래픽</li>
</ul>
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:<ul>
<li>Heuristics</li>
<li>일반</li>
<li>구체적</li>
<li>동적 서명</li>
</ul>
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:<ul>
<li>사용자: 사용자가 시작한 경우</li>
<li>시스템: 시스템이 시작된 경우</li>
<li>실시간: 실시간 구성 요소가 시작되었습니다.</li>
<li>IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</li>
<li>NIS: 네트워크 검사 시스템</li>
<li>IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</li>
<li>ELAM(맬웨어 방지 조기 실행). 여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</li>
<li>원격 attestation</li>
</ul>AMSI(맬웨어 방지 검사 인터페이스). 제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.
UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt>서명 버전의
<dt>프로세스: &lt; &gt; </dt>정의 버전 엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
필요한 작업은 없습니다. Microsoft Defender 바이러스 백신 일시 중단하고 이 위협에 대한 일상적인 조치를 취할 수 있습니다. 위협을 수동으로 제거하려면 Microsoft Defender 바이러스 백신 컴퓨터 <b>정리를 클릭합니다.</b>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1117</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼은 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 이 머신을 보호하기 위해 작업을 수행했습니다.<br/>자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.
<ul>
<li>알 수 없음</li>
<li>로컬 컴퓨터</li>
<li>네트워크 공유</li>
<li>인터넷</li>
<li>들어오는 트래픽</li>
<li>아웃보이스 트래픽</li>
</ul>
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:<ul>
<li>Heuristics</li>
<li>일반</li>
<li>구체적</li>
<li>동적 서명</li>
</ul>
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:<ul>
<li>사용자: 사용자가 시작한 경우</li>
<li>시스템: 시스템이 시작된 경우</li>
<li>실시간: 실시간 구성 요소가 시작되었습니다.</li>
<li>IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</li>
<li>NIS: 네트워크 검사 시스템</li>
<li>IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</li>
<li>ELAM(맬웨어 방지 조기 실행). 여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</li>
<li>원격 attestation</li>
</ul>AMSI(맬웨어 방지 검사 인터페이스). 제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.
UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt> 
<dt> 작업의 프로세스: &lt; 작업 , 예를 들면 다음과 &gt; 같습니다.<ul>
<li>정리: 리소스가 정리된 경우</li>
<li>Quarantine: Resource was quarantined</li>
<li>제거: 리소스가 삭제되었습니다.</li>
<li>허용: 리소스가 실행/존재할 수 있습니다.</li>
<li>사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</li>
<li>작업 없음: 아무 작업도 수행하지 않습니다.</li>
<li>차단: 리소스가 실행되지 않습니다.</li>
</ul>
</dt>
<dt>작업 상태: &lt; 추가 작업에 &gt; 대한 설명</dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: &lt; &gt; </dt> Antimalware Engine 버전 참고: Microsoft Defender 바이러스 백신, Microsoft Security Essentials, 악성 소프트웨어 제거 도구 또는 System Center Endpoint Protection 맬웨어를 검색할 때마다 맬웨어가 변경될 수 있는 다음과 같은 시스템 설정 및 서비스를 복원합니다.<ul>
<li>기본 Internet Explorer 또는 Microsoft Edge 설정</li>
<li>사용자 액세스 제어 설정</li>
<li>Chrome 설정</li>
<li>부팅 제어 데이터</li>
<li>Regedit 및 작업 관리자 레지스트리 설정</li>
<li>Windows 업데이트, Background Intelligent Transfer Service 및 원격 프로시저 호출 서비스</li>
<li>Windows 운영 체제 파일</li></ul>
위의 컨텍스트는 다음 클라이언트 및 서버 버전에 적용됩니다.
<table>
<tr>
<th>운영 체제</th>
<th>운영 체제 버전</th>
</tr>
<tr>
<td>
클라이언트 운영 체제
</td>
<td>
Windows Vista(서비스 팩 1 또는 서비스 팩 2), Windows 7 이상
</td>
</tr>
<tr>
<td>
서버 운영 체제
</td>
<td>
Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 및 Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
필요한 작업은 없습니다. Microsoft Defender 바이러스 백신 제거하거나 위협을 무단으로 제거했습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1118</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼이 맬웨어 또는 사용자 원치 않는 기타 소프트웨어로부터 시스템을 보호하기 위한 작업을 수행하려고 했지만 작업이 실패했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 또는 사용자 원치 않는 기타 소프트웨어에 대해 조치를 취할 때 중요하지 않은 오류가 발생했습니다.<br/>자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.
<ul>
<li>알 수 없음</li>
<li>로컬 컴퓨터</li>
<li>네트워크 공유</li>
<li>인터넷</li>
<li>들어오는 트래픽</li>
<li>아웃보이스 트래픽</li>
</ul>
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:<ul>
<li>Heuristics</li>
<li>일반</li>
<li>구체적</li>
<li>동적 서명</li>
</ul>
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:<ul>
<li>사용자: 사용자가 시작한 경우</li>
<li>시스템: 시스템이 시작된 경우</li>
<li>실시간: 실시간 구성 요소가 시작되었습니다.</li>
<li>IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</li>
<li>NIS: 네트워크 검사 시스템</li>
<li>IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</li>
<li>ELAM(맬웨어 방지 조기 실행). 여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</li>
<li>원격 attestation</li>
</ul>AMSI(맬웨어 방지 검사 인터페이스). 제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.
UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt> 
<dt> 작업의 프로세스: &lt; 작업 , 예를 들면 다음과 &gt; 같습니다.<ul>
<li>정리: 리소스가 정리된 경우</li>
<li>Quarantine: Resource was quarantined</li>
<li>제거: 리소스가 삭제되었습니다.</li>
<li>허용: 리소스가 실행/존재할 수 있습니다.</li>
<li>사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</li>
<li>작업 없음: 아무 작업도 수행하지 않습니다.</li>
<li>차단: 리소스가 실행되지 않습니다.</li>
</ul>
</dt>
<dt>작업 상태: &lt; 추가 작업에 &gt; 대한 설명</dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
필요한 작업은 없습니다. Microsoft Defender 바이러스 백신 수정과 관련된 작업을 완료하지 못했습니다. 이 오류는 심각한 오류는 아니며,
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1119</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼에서 맬웨어 또는 사용자 원치 않는 기타 소프트웨어에 대한 작업을 수행하려고 할 때 심각한 오류가 발생했습니다. 이벤트 메시지에 자세한 정보가 있습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 또는 사용자 원치 않는 기타 소프트웨어에 대해 조치를 취할 때 심각한 오류가 발생했습니다.<br/>자세한 내용은 다음 항목을 참조하세요.
<dl>
<dt>이름: &lt; 위협 &gt; 이름</dt>
<dt>ID: &lt; 위협 &gt; ID</dt> 
<dt> 심각도: &lt; &gt; 심각도, 예:<ul>
<li>낮음</li>
<li>보통</li>
<li>High</li>
<li>심각</li>
</ul>
</dt>
<dt>범주: &lt; 범주 설명 &gt; 입니다(예: 위협 또는 맬웨어 유형).</dt> 
<dt>경로: &lt; 파일 &gt; 경로</dt> 
<dt> 검색 원본: &lt; 검색 원본 , 예를 들면 다음과 &gt; 같습니다.
<ul>
<li>알 수 없음</li>
<li>로컬 컴퓨터</li>
<li>네트워크 공유</li>
<li>인터넷</li>
<li>들어오는 트래픽</li>
<li>아웃보이스 트래픽</li>
</ul>
</dt>
<dt>검색 유형: &lt; 검색 &gt; 유형, 예:<ul>
<li>Heuristics</li>
<li>일반</li>
<li>구체적</li>
<li>동적 서명</li>
</ul>
</dt>
<dt>검색 원본: &lt; 검색 &gt; 원본: 예:<ul>
<li>사용자: 사용자가 시작한 경우</li>
<li>시스템: 시스템이 시작된 경우</li>
<li>실시간: 실시간 구성 요소가 시작되었습니다.</li>
<li>IOAV: IE 다운로드 및 Outlook Express 첨부 파일 시작</li>
<li>NIS: 네트워크 검사 시스템</li>
<li>IEPROTECT: IE - IExtensionValidation; 이렇게 하여 악의적인 웹 페이지 컨트롤로부터 보호</li>
<li>ELAM(맬웨어 방지 조기 실행). 여기에는 부팅 시퀀스에서 검색된 맬웨어가 포함됩니다.</li>
<li>원격 attestation</li>
</ul>AMSI(맬웨어 방지 검사 인터페이스). 제3자도 호출할 수 있는 스크립트(PS, VBS)를 보호하는 데 주로 사용됩니다.
UAC </dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>프로세스 이름: &lt; PID &gt; </dt> 
<dt> 작업의 프로세스: &lt; 작업 , 예를 들면 다음과 &gt; 같습니다.<ul>
<li>정리: 리소스가 정리된 경우</li>
<li>Quarantine: Resource was quarantined</li>
<li>제거: 리소스가 삭제되었습니다.</li>
<li>허용: 리소스가 실행/존재할 수 있습니다.</li>
<li>사용자 정의: 사용자가 지정한 작업 목록에서 일반적으로 하나인 사용자 정의 작업</li>
<li>작업 없음: 아무 작업도 수행하지 않습니다.</li>
<li>차단: 리소스가 실행되지 않습니다.</li>
</ul>
</dt>
<dt>작업 상태: &lt; 추가 작업에 &gt; 대한 설명</dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: Antimalware Engine &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
Microsoft Defender 바이러스 백신 클라이언트에서 중요한 문제로 인해 이 오류가 발생했습니다. 끝점이 보호되지 않을 수 있습니다. 오류 설명을 검토한 다음 아래의 관련 <b>사용자 작업 단계를</b> 따릅니다.
<table>
<tr>
<th>작업</th>
<th>사용자 작업</th>
</tr>
<tr>
<td>
<b>제거</b>
</td>
<td>
정의를 업데이트한 다음 제거가 성공적이지 확인
</td>
</tr>
<tr>
<td>
<b>정리</b>
</td>
<td>
정의를 업데이트한 다음 수정이 성공적이지 확인
</td>
</tr>
<tr>
<td>
<b>Quarantine</b>
</td>
<td>
정의를 업데이트하고 사용자에게 필요한 리소스에 액세스할 수 있는 권한이 있는지 확인해야 합니다.
</td>
</tr>
<tr>
<td>
<b>허용</b>
</td>
<td>
사용자에게 필요한 리소스에 액세스할 수 있는 권한이 있는지 확인
</td>
</tr>
</table>

이 이벤트가 지속되는 경우:<ol>
<li>검색을 다시 실행합니다.</li>
<li>같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>지원 사이트로 이동하여 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아야 합니다. <b></b></li>
<li><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1120</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>Microsoft Defender 바이러스 백신 리소스에 대한 해시를 유인했습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 클라이언트가 정상 상태로 실행되고 있습니다.
<dl>
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 &gt; 버전</dt>
<dt>위협 리소스 경로: &lt; 경로 &gt; </dt>
<dt>해시: &lt; 해시 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>참고: 이 이벤트는 <b>ThreatFileHashLogging unsigned</b>정책을 설정한 경우만 기록됩니다.</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 1150</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼이 모니터링 플랫폼에 상태를 보고하는 경우 이 이벤트는 맬웨어 방지 플랫폼이 실행되고 있으며 정상 상태를 나타냅니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 클라이언트가 정상 상태로 실행되고 있습니다.
<dl>
<dt>플랫폼 버전: &lt; 현재 플랫폼 &gt; 버전</dt>
<dt>서명 버전: 정의 &lt; 버전 &gt; </dt>엔진 버전: Antimalware Engine
<dt> &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
필요한 작업은 없습니다. 클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다. 이 이벤트는 시간당 보고됩니다.
</td>
</tr>

<tr>
<th colspan="2">이벤트 ID: 1151</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>Endpoint Protection 상태 보고서(UTC의 시간)</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
바이러스 백신 클라이언트 상태 보고서.
<dl>
<dt>플랫폼 버전: &lt; 현재 플랫폼 &gt; </dt>버전 엔진
<dt>버전: &lt; &gt; </dt>Antimalware Engine 버전 네트워크 실시간 검사 엔진
<dt>버전: &lt; &gt; </dt>네트워크 실시간 검사 엔진 버전 바이러스 백신 서명
<dt>버전: &lt; 바이러스 &gt; </dt>백신 서명 버전 스파이웨어 방지 서명
<dt> &lt; &gt; 버전:</dt>스파이웨어 방지 서명 버전 네트워크 실시간 검사 서명
<dt>버전: 네트워크 실시간 &lt; 검사 &gt; </dt>서명 버전
<dt>RTP 상태: &lt; 실시간 보호 &gt; 상태(사용</dt>또는 사용 안 하게)
<dt>OA 상태: &lt; On Access state &gt; (Enabled or Disabled)</dt>
<dt>IOAV state: &lt; IE Downloads and Outlook Express Attachments state &gt; (Enabled or Disabled)</dt>
<dt>BM state: &lt; Behavior Monitoring state &gt; (Enabled or Disabled)</dt>Antivirus signature
<dt>age: Antivirus signature age &lt; &gt; (in days) </dt> 
<dt>Antispyware signature age: &lt; Antispyware signature age &gt; (in days)</dt>
<dt>Last quick scan age: Last quick scan &lt; age &gt; (in days)</dt>Last full
<dt>scan age: Last full scan age &lt; &gt; (in days)</dt>
<dt>Antivirus signature creation time: ? &lt; 바이러스 백신 &gt; 서명 생성 시간</dt>스파이웨어 방지 서명
<dt>생성 시간: ? &lt; 스파이웨어 방지 서명 생성 &gt; 시간</dt>
<dt>마지막 빠른 검사 시작 시간: ? &lt; 마지막 빠른 검사 &gt; 시작 시간</dt>
<dt>마지막 빠른 검사 종료 시간: ? &lt; 마지막 빠른 검사 &gt; </dt>종료 시간 마지막 빠른 검사 원본: 마지막 빠른 검사
<dt> &lt; &gt; 원본(0 = 검사가 실행되지 않았음, 1 = 사용자가 시작한, 2 =</dt>시스템 시작) 마지막 전체 검사 시작
<dt>시간: ? &lt; 마지막 전체 검사 &gt; 시작 시간</dt>
<dt>마지막 전체 검사 종료 시간: ? &lt; 마지막 전체 검사 &gt; </dt>종료 시간 마지막 전체 검사 원본: 마지막 전체 검사 원본(0 = 검사가
<dt> &lt; &gt; 실행되지 않았음, 1 = 사용자가 시작한, 2 =</dt>시스템 시작) 제품 상태: 내부 문제 
<dt> 해결
</dl>
</td>
</tr>

<tr>
<th colspan="2">이벤트 ID: 2000</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 정의가 성공적으로 업데이트되었습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
바이러스 백신 서명 버전이 업데이트되었습니다.
<dl>
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전 이전</dt>
<dt>서명 버전: 이전 서명 &lt; 버전 &gt; </dt>서명 
<dt> 유형: 서명 &lt; &gt; 유형, 예: <ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>업데이트 유형: &lt; 업데이트 &gt; 유형( 전체 또는 델타)입니다.</dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 버전 &gt; </dt>이전 엔진
<dt>버전: 이전 엔진 &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
필요한 작업은 없습니다. 클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다. 이 이벤트는 서명이 성공적으로 업데이트될 때 보고됩니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2001</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>보안 인텔리전스 업데이트가 실패했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 서명을 업데이트하는 중 오류가 발생했습니다.
<dl>
<dt>새 보안 인텔리전스 버전: &lt; 새 버전 &gt; 번호 이전</dt>
<dt>보안 인텔리전스 버전: &lt; 이전 &gt; 버전</dt>업데이트 
<dt> 원본: 업데이트 &lt; &gt; 원본, 예:
<ul>
<li>보안 인텔리전스 업데이트 폴더</li>
<li>내부 보안 인텔리전스 업데이트 서버</li>
<li>Microsoft Update Server</li>
<li>파일 공유</li>
<li>Microsoft 맬웨어 보호 센터(MMPC)</li>
</ul>
</dt>
<dt>업데이트 단계: &lt; 업데이트 &gt; 단계, 예를 들면 다음과 같습니다.
<ul>
<li>검색</li>
<li>다운로드</li>
<li>설치</li>
</ul>
</dt>
<dt>원본 경로: UNC(범용 명명 규칙)의 파일 공유 이름, WSUS(Windows Server Update Services)/Microsoft Update/ADL의 서버 이름입니다.</dt> 
<dt> 서명 유형: &lt; 서명 &gt; 유형, 예를 들면 다음과 같습니다. <ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>업데이트 유형: &lt; 업데이트 &gt; 유형( 전체 또는 델타)입니다.</dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 버전 &gt; </dt>이전
<dt> &lt; &gt; 엔진 버전: 이전 엔진</dt>버전 오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
정의를 업데이트하는 데 문제가 있는 경우 이 오류가 발생합니다.
이 이벤트를 해결합니다.
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">정의를 업데이트하고</a> 끝점에서 직접 다시 검사합니다.</li>
<li>이 오류에 대한 자세한 내용은 %Windir%\WindowsUpdate.log 파일의 항목을 검토합니다.</li>
<li><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2002</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진이 업데이트되었습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 엔진 버전이 업데이트되었습니다.
<dl>
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt>
<dt>이전 엔진 버전: 이전 엔진 &lt; 버전 &gt; </dt>엔진 유형: 엔진 유형, 맬웨어 방지 엔진 또는
<dt>네트워크 검사 시스템 &lt; &gt; 엔진.</dt> 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
필요한 작업은 없습니다. 클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다. 이 이벤트는 맬웨어 방지 엔진이 성공적으로 업데이트될 때 보고됩니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2003</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진 업데이트가 실패했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 엔진을 업데이트하는 동안 오류가 발생했습니다.
<dl>
<dt>새 엔진 버전:</dt>이전 엔진 버전: 이전
<dt>엔진 &lt; 버전 &gt; </dt>
<dt>엔진 유형: 엔진 &lt; &gt; 유형, 맬웨어 방지</dt> 엔진 또는 네트워크 검사 시스템 엔진. 
<dt>사용자: &lt; 도메인 &gt; \& lt; 사용자 &gt; </dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
클라이언트 Microsoft Defender 바이러스 백신 업데이트하지 못했습니다. 이 이벤트는 클라이언트가 자체 업데이트에 실패할 때 발생합니다. 이 이벤트는 일반적으로 업데이트 중에 네트워크 연결이 중단되어 발생하기 때문입니다.
이 이벤트를 해결합니다.
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">정의를 업데이트하고</a> 끝점에서 직접 다시 검사합니다.</li>
<li><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2004</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 정의를 로드하는 데 문제가 발생했습니다. 맬웨어 방지 엔진이 마지막으로 알려진 정의 집합을 로드하려고 합니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 로드하는 중 오류가 발생하여 알려진 서명 집합으로 되돌리려고 합니다.
<dl>
<dt>서명 시도:</dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>서명 버전: &lt; 정의 &gt; 버전</dt>
<dt>엔진 버전: &lt; 맬웨어 &gt; </dt> 방지 엔진 버전
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
Microsoft Defender 바이러스 백신 클라이언트가 최신 정의 파일을 다운로드하여 설치하려고 했지만 실패했습니다. 이 오류는 정의를 로드하는 동안 클라이언트에서 오류가 발생하거나 파일이 손상된 경우 발생할 수 있습니다. Microsoft Defender 바이러스 백신 정의 집합으로 되돌리려 합니다.
이 이벤트를 해결합니다.
<ol>
<li>컴퓨터를 다시 시작하고 다시 시도하십시오.</li>
<li>사이트 에서 최신 <a href="https://aka.ms/wdsi">정의를 Microsoft 보안 인텔리전스 다운로드합니다.</a>
참고: 사이트에서 다운로드한 정의 파일의 크기는 60MB를 초과할 수 있으며 정의를 업데이트하기 위한 장기 솔루션으로 사용되지 않습니다.
</li>
<li><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2005</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼이 최신이기 때문에 맬웨어 방지 엔진이 로드되지 못했습니다. 맬웨어 방지 플랫폼은 마지막으로 알려진 맬웨어 방지 엔진을 로드하고 업데이트를 시도합니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 플랫폼 버전이 지원되지 않는 경우 맬웨어 방지 엔진을 로드할 수 없습니다. Microsoft Defender 바이러스 백신 마지막으로 알려진 엔진으로 되돌아가면 플랫폼 업데이트가 시도됩니다.
<dl>
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 버전&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2006</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>플랫폼 업데이트가 실패했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 플랫폼을 업데이트하는 중 오류가 발생했습니다.
<dl>
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 &gt; 버전</dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2007</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>플랫폼이 곧 최신이 됩니다. 최신 보호를 유지하기 위해 최신 플랫폼을 다운로드합니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 맬웨어 방지 엔진의 이후 버전을 지원하려면 곧 최신 플랫폼 버전이 필요할 것입니다. 최신 Microsoft Defender 바이러스 백신 플랫폼을 다운로드하여 사용 가능한 최상의 보호 수준을 유지 관리합니다.
<dl>
<dt>현재 플랫폼 버전: &lt; 현재 플랫폼 버전&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2010</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진은 동적 서명 서비스를 사용하여 추가 정의를 얻습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 데 <i>도움이</i> 되는 추가 서명을 검색하는 데 동적 서명 서비스를 사용했습니다.
<dl>
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt> 
<dt> 서명 유형: 서명 &lt; &gt; 유형, 예: <ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt> 
<dt> 동적 서명 유형: 동적 서명 &lt; &gt; 유형, 예를 들면 다음과 같습니다.
<ul>
<li>버전</li>
<li>타임스탬프</li>
<li>제한 없음</li>
<li>기간</li>
</ul>
</dt>
<dt>지속성 경로: &lt; 경로 &gt; </dt>
<dt>동적 서명 버전: &lt; 버전 번호 &gt; </dt>동적 서명 컴파일
<dt>타임스탬프: &lt; 타임스탬프 &gt; </dt> 
<dt> 지속성 제한 유형: &lt; 지속성 제한 &gt; 유형, 예:
<ul>
<li>VDM 버전</li>
<li>타임스탬프</li>
<li>제한 없음</li>
</ul>
</dt>
<dt>지속성 제한: fastpath 서명의 지속성 제한.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2011</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>동적 서명 서비스가 기한이 지난 동적 정의를 삭제했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 <i>서명을</i> 삭제하기 위해 동적 서명 서비스를 사용했습니다.
<dl>
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt> 
<dt> 서명 유형: 서명 &lt; &gt; 유형, 예: <ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt> 
<dt> 동적 서명 유형: 동적 서명 &lt; &gt; 유형, 예를 들면 다음과 같습니다.
<ul>
<li>버전</li>
<li>타임스탬프</li>
<li>제한 없음</li>
<li>기간</li>
</ul>
</dt>
<dt>지속성 경로: &lt; 경로 &gt; </dt>
<dt>동적 서명 버전: &lt; 버전 번호 &gt; </dt>동적 서명 컴파일
<dt>타임스탬프: &lt; 타임스탬프 &gt; </dt>제거
<dt>이유:</dt> 
<dt> 지속성 제한 유형: 지속성 제한 &lt; &gt; 유형, 예:
<ul>
<li>VDM 버전</li>
<li>타임스탬프</li>
<li>제한 없음</li>
</ul>
</dt>
<dt>지속성 제한: fastpath 서명의 지속성 제한.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
필요한 작업은 없습니다. 클라이언트 Microsoft Defender 바이러스 백신 정상 상태입니다. 이 이벤트는 동적 서명 서비스가 기한이 지난 동적 정의를 성공적으로 삭제할 때 보고됩니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2012</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>동적 서명 서비스를 사용하려고 할 때 맬웨어 방지 엔진에서 오류가 발생했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 서명 서비스를 사용하려고 하는 중 오류가 <i>발생했습니다.</i>
<dl>
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt> 
<dt> 서명 유형: 서명 &lt; &gt; 유형, 예: <ul>
<li>바이러스 검사</li>
<li>스파이웨어 방지</li>
<li>맬웨어 방지</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>현재 엔진 버전: &lt; 현재 엔진 &gt; 버전</dt>오류 코드: 오류 코드 위협
<dt> &lt; &gt; 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt> 동적 서명 유형: &lt; 동적 서명 &gt; 유형, 예를 들면 다음과 같습니다.
<ul>
<li>버전</li>
<li>타임스탬프</li>
<li>제한 없음</li>
<li>기간</li>
</ul>
</dt>
<dt>지속성 경로: &lt; 경로 &gt; </dt>
<dt>동적 서명 버전: &lt; 버전 번호 &gt; </dt>동적 서명 컴파일
<dt>타임스탬프: &lt; 타임스탬프 &gt; </dt> 
<dt> 지속성 제한 유형: &lt; 지속성 제한 &gt; 유형, 예:
<ul>
<li>VDM 버전</li>
<li>타임스탬프</li>
<li>제한 없음</li>
</ul>
</dt>
<dt>지속성 제한: fastpath 서명의 지속성 제한.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
인터넷 연결 설정을 확인합니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2013</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>동적 서명 서비스가 모든 동적 정의를 삭제했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 서명을 모두 <i>삭제해야</i> 합니다.
<dl>
<dt>현재 서명 버전: &lt; 현재 서명 버전&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2020</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진이 클린 파일을 다운로드했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 파일을 다운로드했습니다.
<dl>
<dt>파일 이름: &lt; 파일 이름 &gt; 파일의 이름입니다.</dt> 
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt>
<dt>현재 엔진 버전: 현재 엔진 &lt; 버전 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2021</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진이 클린 파일을 다운로드하지 못했습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 파일을 다운로드하는 동안 오류가 발생했습니다.
<dl>
<dt>파일 이름: &lt; 파일 이름 &gt; 파일의 이름입니다.</dt> 
<dt>현재 서명 버전: &lt; 현재 서명 &gt; 버전</dt>
<dt>현재 엔진 버전: 현재 엔진 &lt; 버전 &gt; </dt>오류 코드: 오류 코드 위협 상태와 관련된 결과
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
인터넷 연결 설정을 확인합니다.
이 Microsoft Defender 바이러스 백신 동적 서명 서비스를 사용하여 특정 위협에 최신 정의를 다운로드할 때 오류가 발생했습니다. 이 오류는 네트워크 연결 문제로 인해 발생할 수 있습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2030</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진이 다운로드된 후 다음 시스템 다시 시작 시 오프라인으로 실행하도록 구성됩니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 다시 시작 시 실행될 오프라인 바이러스 백신을 다운로드하고 구성할 수 있습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2031</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진이 오프라인 검색을 다운로드하고 구성할 수 없습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 바이러스 백신을 다운로드하고 구성하는 동안 오류가 발생했습니다.
<dl>
<dt>오류 코드: &lt; 오류 코드 &gt; 위협 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2040</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>이 운영 체제 버전에 대한 맬웨어 방지 지원이 곧 종료됩니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
운영 체제에 대한 지원이 곧 만료됩니다. 지원 Microsoft Defender 바이러스 백신 운영 체제에서 데이터를 실행하는 것은 위협으로부터 보호하기에 적절한 솔루션이 아닙니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2041</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>이 운영 체제에 대한 맬웨어 방지 지원이 종료됩니다. 지원을 계속하려면 운영 체제를 업그레이드해야 합니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
운영 체제에 대한 지원이 만료되었습니다. 지원 Microsoft Defender 바이러스 백신 운영 체제에서 데이터를 실행하는 것은 위협으로부터 보호하기에 적절한 솔루션이 아닙니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 2042</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진은 더 이상 이 운영 체제를 지원하지하며 더 이상 맬웨어로부터 시스템을 보호하지 않습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
운영 체제에 대한 지원이 만료되었습니다. Microsoft Defender 바이러스 백신 운영 체제에서 더 이상 지원되지 않는 경우, 작동이 중지되어 맬웨어 위협으로부터 보호되지 않습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 3002</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>실시간 보호에 오류가 발생하여 오류가 발생했습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 Real-Time 보호 기능에 오류가 발생하여 오류가 발생했습니다.
<dl>
<dt>기능: &lt; &gt; 기능, 예를 들면 다음과 같습니다.
<ul>
<li>On Access</li>
<li>Internet Explorer 다운로드 및 Microsoft Outlook Express 첨부 파일</li>
<li>동작 모니터링</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>오류 코드: &lt; 오류 코드 &gt; 위협 상태와 관련된 결과 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt> 
<dt>이유: 실시간 Microsoft Defender 바이러스 백신 기능이 다시 시작된 이유입니다.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
시스템이 한 동안 보호되지 않을 수 있기 때문에 시스템을 다시 시작한 다음 전체 검색을 실행해야 합니다.
Microsoft Defender 바이러스 백신 서비스 중 하나를 시작하지 못했기 때문에 클라이언트의 실시간 보호 기능에 오류가 발생했습니다.
그 다음에 3007 이벤트 ID가 발생하면 오류가 일시적으로 발생하고 맬웨어 방지 클라이언트가 오류에서 복구됩니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 3007</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>오류로부터 실시간 보호를 복구했습니다. 이 오류가 표시되는 경우 전체 시스템 검색을 실행하는 것이 좋습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 실시간 보호가 기능을 다시 시작했습니다. 전체 시스템 검색을 실행하여 이 에이전트가 다운된 동안 누락된 항목을 검색하는 것이 좋습니다.
<dl>
<dt>기능: &lt; &gt; 기능, 예를 들면 다음과 같습니다.
<ul>
<li>On Access</li>
<li>IE 다운로드 및 Outlook Express 첨부 파일</li>
<li>동작 모니터링</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>이유: 실시간 Microsoft Defender 바이러스 백신 기능이 다시 시작된 이유입니다.</dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
실시간 보호 기능이 다시 시작됩니다. 이 이벤트가 다시 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원에 문의하세요.</a>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5000</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>실시간 보호가 사용됩니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 사용자 없이 설치될 수 있는 기타 소프트웨어에 대한 실시간 보호 검사가 사용되었습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5001</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>실시간 보호가 사용되지 않습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 사용자 없이 설치될 수 있는 기타 소프트웨어에 대한 실시간 보호 검사가 사용되지 않도록 설정되었습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5004</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>실시간 보호 구성이 변경되었습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 실시간 보호 기능 구성이 변경되었습니다.
<dl>
<dt>기능: &lt; &gt; 기능, 예를 들면 다음과 같습니다.
<ul>
<li>On Access</li>
<li>IE 다운로드 및 Outlook Express 첨부 파일</li>
<li>동작 모니터링</li>
<li>네트워크 검사 시스템</li>
</ul>
</dt>
<dt>구성: </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5007</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼 구성이 변경되었습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 구성이 변경되었습니다. 이 이벤트가 예기치 않은 이벤트인 경우 맬웨어의 결과일 수 있는 설정을 검토해야 합니다.
<dl>
<dt>이전 값: &lt; 이전 값 번호 &gt; 이전 바이러스 백신 구성 값입니다.</dt> 
<dt>새 값: &lt; 새 값 번호 &gt; 새 바이러스 백신 구성 값입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5008</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 엔진에서 오류가 발생하여 오류가 발생했습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 오류로 인해 엔진이 종료되었습니다.
<dl>
<dt>오류 유형: &lt; 오류 &gt; 유형, 예: 크래시 또는</dt>중단 예외
<dt>코드: 오류 &lt; 코드 &gt; </dt>
<dt>리소스: &lt; 리소스 &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
이 이벤트를 해결합니다.<ol>
<li>서비스를 다시 시작하십시오.<ul>
<li>맬웨어 방지, 바이러스 백신 및 스파이웨어의 경우 상승된 명령 프롬프트에 <b>net stop msmpsvc를</b>입력한 다음 <b>net start msmpsvc를</b> 입력하여 맬웨어 방지 엔진을 다시 시작합니다.</li>
<li>네트워크 <i></i>검사 시스템의 경우 승격된 명령 프롬프트에 <b>net start nissrv를</b>입력한 다음 <i></i> <b>net start nissrv를</b> 입력하여 네트워크 검사 시스템 엔진을 다시 NiSSRV.exe.
</li>
</ul>
</li>
<li>같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> 지원 사이트에 액세스하고 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아 Microsoft 기술 지원 에 <a href="https://go.microsoft.com/fwlink/?LinkId=215491">문의하세요.</a> <b></b></li>
</ol>
</td>
</tr>
<tr>
<td>
사용자 작업:
</td>
<td >
예기치 Microsoft Defender 바이러스 백신 때문에 클라이언트 엔진이 중지되었습니다.
이 이벤트를 해결합니다.
<ol>
<li>검색을 다시 실행합니다.</li>
<li>같은 방식으로 오류가 발생하면 <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a>지원 사이트로 이동하여 검색 상자에 오류 번호를 입력하여 오류 코드를 찾아야 합니다. <b></b></li>
<li><a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft 기술 지원</a>에 문의합니다.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5009</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검사가 사용하도록 설정되어 있습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 소프트웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검색이 활성화되었습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5010</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검사가 사용되지 않도록 설정되었습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 소프트웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 검색이 사용되지 않도록 설정되었습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5011</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>바이러스 검사가 사용하도록 설정되어 있습니다.</b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 검사가 사용하도록 설정되어 있습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5012</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>바이러스 검사가 사용되지 않습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 검사가 사용되지 않습니다.
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5100</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼이 곧 만료됩니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 유예 기간이 시작되고 곧 만료됩니다. 만료 후 이 프로그램은 바이러스, 스파이웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 보호를 사용하지 않도록 설정합니다.
<dl>
<dt>만료 이유: 만료 Microsoft Defender 바이러스 백신 이유입니다.</dt> 
<dt>만료 날짜: Microsoft Defender 바이러스 백신 날짜입니다.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">이벤트 ID: 5101</th>
</tr>
<tr><td>
기호 이름:
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
메시지:
</td>
<td >
<b>맬웨어 방지 플랫폼이 만료되었습니다. </b>
</td>
</tr>
<tr>
<td>
설명:
</td>
<td >
Microsoft Defender 바이러스 백신 유예 기간이 만료되었습니다. 바이러스, 스파이웨어 및 사용자 원치 않는 기타 소프트웨어에 대한 보호가 사용되지 않도록 설정됩니다.
<dl>
<dt>만료 이유:</dt>
<dt>만료 날짜: </dt>오류 코드: 오류 코드 위협 상태와 관련된 결과 
<dt> &lt; &gt; 코드입니다. 표준 HRESULT 값입니다.</dt> 
<dt>오류 설명: &lt; 오류 설명 &gt; 오류에 대한 설명입니다.</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Microsoft Defender 바이러스 백신 클라이언트 오류 코드 Microsoft Defender 바이러스 백신 문제가 발생하는 경우 일반적으로 문제를 해결하는 데 도움이 되는 오류 코드를 제공합니다. 대부분의 오류는 업데이트를 설치하는 데 문제가 발생했다는 의미입니다.
이 섹션에서는 클라이언트 오류와 관련한 Microsoft Defender 바이러스 백신 제공합니다.
- 오류 코드 오류에 대한 가능한 - 이유 - 지금 할 일에 대한 조언

다음 표의 정보를 사용하여 오류 코드 문제를 Microsoft Defender 바이러스 백신 수 있습니다.


<table>
<tr>
<th colspan="2">오류 코드: 0x80508007</th>
</tr>
<tr>
<td>메시지</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
가능한 이유
</td>
<td>
이 오류는 메모리가 부족할 수 있습니다.
</td>
</tr>
<tr>
<td>해결 방법</td>
<td>
<ol>
<li>장치에서 사용 가능한 메모리를 확인합니다.</li>
<li>장치에서 메모리를 비우기 위해 실행 중인 사용되지 않는 응용 프로그램을 닫습니다.</li>
<li>장치를 다시 시작하고 스캔을 다시 실행합니다.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x8050800C</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 보안 제품에 문제가 있을 수 있습니다.
</td>
</tr><tr><td>해결 방법</td><td>
<ol>
<li>정의를 업데이트합니다. 중 하나:<ol>
<li>업데이트 <b>탭의</b> 정의 업데이트 <b></b> 단추를 Microsoft Defender 바이러스 백신. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>또는
</li>
<li>사이트 에서 최신 <a href="https://aka.ms/wdsi">정의를 Microsoft 보안 인텔리전스 다운로드합니다.</a>
참고: 사이트에서 다운로드한 정의 파일의 크기는 60MB를 초과할 수 있으며 정의를 업데이트하기 위한 장기 솔루션으로 사용되지 않습니다.
</li>
</ol>
</li>
<li>전체 검색을 실행합니다.
</li>
<li>장치를 다시 시작하고 다시 시도합니다.</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508020</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 엔진 구성 오류가 있을 수 있습니다. 일반적으로 이는 엔진이 제대로 작동할 수 없는 입력 데이터와 관련이 있습니다.
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x805080211
</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 Microsoft Defender 바이러스 백신 수 없습니다.
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508022
</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 위협 제거를 완료하기 위해 재부팅이 필요하다는 메시지를 나타냅니다.
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 위협이 미디어에 더 이상 존재하지 않을 수도, 맬웨어가 장치 검색을 중지하고 있을 수 있다는 것을 나타냅니다.
</tr><tr><td>해결 방법
</td>
<td>
보안 <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft 보안 검사</a> 실행한 다음 보안 소프트웨어를 업데이트하고 다시 시도하세요.
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508024 </th></tr>
<tr>
<td>메시지</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 전체 시스템 검사가 필요한 것일 수 있습니다.
</td></tr>
<tr>
<td>해결 방법</td><td>
전체 시스템 검색을 실행합니다.
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508025
</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 위협 제거를 완료하는 데 수동 단계가 필요하다는 메시지를 나타냅니다.
</td></tr><tr><td>해결 방법</td><td>
Microsoft 맬웨어 보호 백과사전 에 설명된 수동 <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">수정 단계를 따릅니다.</a> 이벤트 기록에서 위협 관련 링크를 찾을 수 있습니다.<br/></td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508026
</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 컨테이너 유형 내에서 제거가 지원되지 않을 수 있습니다.
</td></tr><tr><td>해결 방법</td><td>
Microsoft Defender 바이러스 백신 내부에서 감지된 위협을 수정하지 못합니다. 검색된 리소스를 수동으로 제거하는 것입니다.
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508027
</th>
</tr><tr><td>메시지</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 낮음 및 중간 위협 제거가 사용하지 않도록 설정되어 있을 수 있습니다.
</td></tr><tr><td>해결 방법</td><td>
감지된 위협을 확인하고 필요한 경우 해결합니다.
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508029
</th>
</tr><tr><td>메시지</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 위협을 다시 검색해야 하다는 메시지를 나타냅니다.
</td></tr><tr><td>해결 방법</td><td>
전체 시스템 검색을 실행합니다.
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508030
</th>
</tr><tr><td>메시지</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 오프라인 검사가 필요를 나타냅니다.
</td></tr><tr><td>해결 방법</td><td>
오프라인으로 Microsoft Defender 바이러스 백신. 오프라인 문서 에서 이 작업을 하는 <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">방법에 대해 Microsoft Defender 바이러스 백신 있습니다.</a>
</td>
</tr>
<tr>
<th colspan="2">오류 코드: 0x80508031
</th>
</tr><tr><td>메시지</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>가능한 이유</td>
<td>
이 오류는 Microsoft Defender 바이러스 백신 플랫폼의 현재 버전을 지원하지 않는 새 버전의 플랫폼이 필요하다는 의미입니다.
</td></tr><tr><td>해결 방법</td><td>
이 경우 해당 Microsoft Defender 바이러스 백신 사용할 수 Windows 10. Windows 8 7과 Windows Vista의 Windows 를 사용할 <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection.</a><br/></td>
</tr>
</table>

<a id="internal-error-codes"></a>다음 오류 코드는 내부 테스트 중에 Microsoft Defender 바이러스 백신.

이러한 오류가 표시될 경우 정의를 [](manage-updates-baselines-microsoft-defender-antivirus.md) 업데이트하고 끝점에서 직접 다시 검사할 수 있습니다.


<table>
<tr>
<th colspan="3">내부 오류 코드</th>
</tr>
<tr>
<th><b>오류 코드</b></th>
<th>메시지 표시</th>
<th>가능한 오류 및 해결 이유</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
인터넷 연결을 확인한 다음 검사를 다시 실행합니다.
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E
</td>
<td rowspan="34">
내부 오류입니다. 원인은 명확히 정의되지 않았습니다.
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
내부 오류입니다. 맬웨어 제거가 성공하지 못하면 트리거될 수 있습니다.
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
내부 오류입니다. 검사가 완료되지 않을 때 트리거될 수 있습니다.
</td>
</tr>
</table>

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender 바이러스 백신 보호에 대한 보고](report-monitor-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
