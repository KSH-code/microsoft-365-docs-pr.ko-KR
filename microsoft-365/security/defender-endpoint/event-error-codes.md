---
title: 이벤트 뷰어를 사용하여 이벤트 및 오류 검토
description: Microsoft Defender for Endpoint Service에서 보고하는 모든 이벤트에 대한 설명 및 추가 문제 해결 단계(필요한 경우)를 얻습니다.
keywords: 문제 해결, 이벤트 뷰어, 로그 요약, 오류 코드, 실패, 끝점용 Microsoft Defender 서비스, 시작할 수 없습니다, 중단, 시작할 수 없습니다.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076620"
---
# <a name="review-events-and-errors-using-event-viewer"></a>이벤트 뷰어를 사용하여 이벤트 및 오류 검토

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- 이벤트 뷰어
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

개별 디바이스의 이벤트 뷰어에서 이벤트 [ID를](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) 검토할 수 있습니다.

예를 들어 장치가 장치 목록에 나타나지 않는 경우 장치에서 이벤트 ID를 찾아야 할 수 있습니다.  그런 다음 이 표를 사용하여 추가 문제 해결 단계를 결정할 수 있습니다.

**이벤트 뷰어를 열고 끝점용 Microsoft Defender 서비스 이벤트 로그를 찾습니다.**

1. Windows **메뉴에서** 시작을 클릭하고 이벤트 **뷰어를 입력한** 다음 **Enter를 클릭합니다.**

2. 로그 목록의 **로그** 요약에서 **Microsoft-Windows-SENSE/Operational이** 표시될 때까지 스크롤합니다. 항목을 두 번 클릭하여 로그를 니다.

   a.  응용 프로그램 및 서비스 로그   >  **Microsoft**  >  **Windows**  >  **SENSE를** 확장하고 작동을 클릭하여 로그에 액세스할 수도 **있습니다.**

   > [!NOTE]
   > SENSE는 끝점용 Microsoft Defender의 전원을 공급하는 동작 센서를 참조하는 데 사용되는 내부 이름입니다.

3. 서비스에서 기록한 이벤트가 로그에 표시됩니다. 서비스에서 기록하는 이벤트 목록은 다음 표를 참조하세요.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>이벤트 ID</th>
<th>메시지</th>
<th>설명</th>
<th>작업</th>
</tr>
<tr>
<td>1</td>
<td>끝점용 Microsoft Defender 서비스가 <code>variable</code> 시작되었습니다(버전).</td>
<td>시스템 시작, 종료 및 온보더링 중에 발생합니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>2 </td>
<td>끝점용 Microsoft Defender 서비스 종료.</td>
<td>디바이스가 종료되거나 오프보더될 때 발생합니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>3 </td>
<td>끝점용 Microsoft Defender 서비스를 시작하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>서비스가 시작되지 않습니다.</td>
<td>다른 메시지를 검토하여 가능한 원인 및 문제 해결 단계를 파악합니다.</td>
</tr>
<tr>
<td>4 </td>
<td>끝점용 Microsoft Defender 서비스가 에 서버에 <code>variable</code> 연결했습니다.</td>
<td>변수 = 끝점 처리 서버용 Defender의 URL입니다.<br>
이 URL은 방화벽 또는 네트워크 활동에 있는 URL과 일치합니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>5 </td>
<td>끝점용 Microsoft Defender 서비스가 의 서버에 연결하지 <code>variable</code> 못했습니다.</td>
<td>변수 = 끝점 처리 서버용 Defender의 URL입니다.<br>
서비스가 해당 URL의 외부 처리 서버에 연결하지 못했습니다.</td>
<td>URL에 대한 연결을 확인합니다. 프록시 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">및 인터넷 연결 구성을 참조합니다.</a></td>
</tr>
<tr>
<td>6 </td>
<td>Microsoft Defender for Endpoint Service가 온보딩되지 않은 경우 온보딩 매개 변수를 찾을 수 없습니다.</td>
<td>장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</td>
<td>서비스를 시작하기 전에 온보더링을 실행해야 합니다.<br>
온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>7 </td>
<td>Microsoft Defender for Endpoint Service에서 온보딩 매개 변수를 읽지 못했습니다. 실패: <code>variable</code> .</td>
<td>변수 = 자세한 오류 설명입니다. 장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</td>
<td>온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>8 </td>
<td>Microsoft Defender for Endpoint Service에서 구성을 정리하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td><b>온보드 중:</b> 서비스가 온보더링하는 동안 구성을 정리하지 못했습니다. 온보더링 프로세스가 계속됩니다. <br><br> <b>오프보더 중:</b> 서비스가 오프보더하는 동안 구성을 정리하지 못했습니다. 오프보더 프로세스가 완료 했지만 서비스가 계속 실행됩니다.
 </td>
<td><b>온보더링:</b> 필요한 작업은 없습니다. <br><br> <b>오프보더링:</b> 시스템을 다시 부트합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>9 </td>
<td>끝점용 Microsoft Defender 서비스가 시작 유형을 변경하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td><b>온보드 중:</b> 장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다. <br><br><b>오프보더 중:</b> 서비스 시작 유형을 변경하지 못했습니다. 오프보더 프로세스가 계속됩니다. </td>
<td>온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>10  </td>
<td>Microsoft Defender for Endpoint Service에서 온보딩 정보를 유지하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>장치가 올바르게 온보드되지 않았고 포털에 보고되지 않습니다.</td>
<td>온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>11 </td>
<td>Endpoint Service용 Defender의 온보딩 또는 다시 온보딩이 완료되었습니다.</td>
<td>장치가 올바르게 온보드되었습니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.<br>
디바이스가 포털에 표시될 때 몇 시간이 걸릴 수 있습니다.</td>
</tr>
<tr>
<td>12 </td>
<td>끝점용 Microsoft Defender가 기본 구성을 적용하지 못했습니다.</td>
<td>서비스가 기본 구성을 적용할 수 없습니다.</td>
<td>이 오류는 잠시 후에 해결해야 합니다.</td>
</tr>
<tr>
<td>13</td>
<td>끝점용 Microsoft Defender 장치 ID 계산: <code>variable</code> .</td>
<td>정상적인 작동 프로세스.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>15 </td>
<td>끝점용 Microsoft Defender는 URL로 명령 채널을 시작할 수 없습니다. <code>variable</code> .</td>
<td>변수 = 끝점 처리 서버용 Defender의 URL입니다.<br>
서비스가 해당 URL의 외부 처리 서버에 연결하지 못했습니다.</td>
<td>URL에 대한 연결을 확인합니다. 프록시 <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">및 인터넷 연결 구성을 참조합니다.</a></td>
</tr>
<tr>
<td>17 </td>
<td>끝점용 Microsoft Defender 서비스가 연결된 사용자 환경 및 원격 분석 서비스 위치를 변경하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>Windows 원격 분석 서비스에 오류가 발생했습니다.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a><br>
온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>18 </td>
<td>OOBE(Windows 시작)가 완료되었습니다.</td>
<td>Windows 업데이트 설치가 완료된 후에만 서비스가 시작됩니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE(Windows 시작)가 아직 완료되지 않았습니다.</td>
<td>Windows 업데이트 설치가 완료된 후에만 서비스가 시작됩니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.<br>
시스템을 다시 시작한 후에도 이 오류가 지속되면 모든 Windows 업데이트가 전체 설치가 되도록 합니다.</td>
</tr>
<tr>
<td>20</td>
<td>OOBE(Windows 시작)가 완료될 때까지 기다릴 수 없습니다. 오류 코드: <code>variable</code> .</td>
<td>내부 오류입니다.</td>
<td>시스템을 다시 시작한 후에도 이 오류가 지속되면 모든 Windows 업데이트가 전체 설치가 되도록 합니다.</td>
</tr>
<tr>
<td>25</td>
<td>Microsoft Defender for Endpoint Service가 레지스트리에서 상태를 다시 설정하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>장치가 올바르게 온보드되지 않았습니다.
포털에 보고됩니다. 그러나 서비스가 SCCM 또는 레지스트리에 등록된 것으로 나타나지 않을 수 있습니다.</td>
<td>온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>26</td>
<td>Microsoft Defender for Endpoint Service가 레지스트리에서 등록 상태를 설정하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>장치가 올바르게 온보드되지 않았습니다.<br>
포털에 보고됩니다. 그러나 서비스가 SCCM 또는 레지스트리에 등록된 것으로 나타나지 않을 수 있습니다.</td>
<td>온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>27</td>
<td>Microsoft Defender for Endpoint Service가 Microsoft Defender 바이러스 백신에서 SENSE 인식 모드를 사용하도록 설정하지 못했습니다. 온보더링 프로세스가 실패했습니다. 오류 코드: <code>variable</code> .</td>
<td>일반적으로 다른 실시간 맬웨어 방지 제품이 장치에서 제대로 실행되고 장치가 Endpoint용 Defender에 보고하는 경우 Microsoft Defender 바이러스 백신은 특별한 수동 상태가 됩니다.</td>
<td>온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a><br>
실시간 맬웨어 방지 보호가 제대로 실행되고 있는지 확인합니다.</td>
</tr>
<tr>
<td>28</td>
<td>Endpoint용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록에 실패했습니다. 오류 코드: <code>variable</code> .</td>
<td>Windows 원격 분석 서비스에 오류가 발생했습니다.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a><br>
온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>29</td>
<td>오프보더 매개 변수를 읽지 못했습니다. 오류 유형: %1, 오류 코드: %2, 설명: %3 </td>
<td>이 이벤트는 시스템에서 오프보더 매개 변수를&#39;수 있는 경우 발생합니다.</td>
<td>장치에 인터넷 액세스 권한이 있는지 확인한 다음 전체 오프보더 프로세스를 다시 실행합니다. 오프보더 패키지가 만료되지 않은지 확인</td>
</tr>
<tr>
<td>30</td>
<td>Microsoft Defender for Endpoint Service가 Microsoft Defender 바이러스 백신에서 SENSE 인식 모드를 사용하지 않도록 설정하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>일반적으로 다른 실시간 맬웨어 방지 제품이 장치에서 제대로 실행되고 장치가 Endpoint용 Defender에 보고하는 경우 Microsoft Defender 바이러스 백신은 특별한 수동 상태가 됩니다.</td>
<td>온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드 참조</a><br>
실시간 맬웨어 방지 보호가 제대로 실행되고 있는지 확인합니다.</td>
</tr>
<tr>
<td>31</td>
<td>Endpoint용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록이 실패했습니다. 오류 코드: <code>variable</code> .</td>
<td>온보더링하는 동안 Windows 원격 분석 서비스에 오류가 발생했습니다. 오프보더 프로세스가 계속됩니다.</td>
<td>Windows 원격 분석 서비스 에서 <a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">오류를 검사합니다.</a></td>
</tr>
<tr>
<td>32</td>
<td>Microsoft Defender for Endpoint Service가 오프보딩 프로세스 후 자체 중지를 요청하지 못했습니다. 오류 코드: %1</td>
<td>오프보더하는 동안 오류가 발생했습니다.</td>
<td>장치를 다시부팅합니다.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint Service에서 SENSE GUID를 유지하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>고유 식별자는 포털에 보고되는 각 장치를 나타내는 데 사용됩니다.<br>
식별자가 유지되지 않는 경우 동일한 장치가 포털에 두 번 나타날 수 있습니다.</td>
<td>장치에서 레지스트리 권한을 확인하여 서비스가 레지스트리를 업데이트할 수 있도록 합니다.</td>
</tr>
<tr>
<td>34</td>
<td>끝점용 Microsoft Defender 서비스가 연결된 사용자 환경 및 원격 분석 서비스에 대한 종속성으로 추가하지 못하여 온보딩 프로세스가 실패했습니다. 오류 코드: <code>variable</code> .</td>
<td>Windows 원격 분석 서비스에 오류가 발생했습니다.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">진단 데이터 서비스가 사용하도록 설정되어 있는지 확인합니다.</a><br>
온보딩 설정 및 스크립트가 제대로 배포되었는지 확인합니다. 구성 패키지를 다시 재배포해 보아야 합니다.<br>
<a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 장치 온보드를 참조합니다.</a></td>
</tr>
<tr>
<td>35</td>
<td>Microsoft Defender for Endpoint Service가 연결된 사용자 환경 및 원격 분석 서비스에 대한 종속성으로 자체적으로 제거하지 못했습니다. 오류 코드: <code>variable</code> .</td>
<td>오프보더 중 Windows 원격 분석 서비스에 오류가 발생했습니다. 오프보더 프로세스가 계속됩니다.
</td>
<td>Windows 진단 데이터 서비스에서 오류를 검사합니다.</td>
</tr>
<tr>
<td>36</td>
<td>끝점용 Microsoft Defender 연결된 사용자 환경 및 원격 분석 서비스 등록이 성공했습니다. 완료 코드: <code>variable</code> .</td>
<td>연결된 사용자 환경 및 원격 분석 서비스에 끝점에 대한 Defender 등록이 완료되었습니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>37</td>
<td>끝점용 Microsoft Defender A 모듈이 할당량 초과됩니다. 모듈: %1, 할당량: {%2} {%3}, 할당량 사용률: %4.</td>
<td>장치는 현재 24시간 창의 할당량에 거의 사용했습니다. 이제는 스로틀이 될 수 있습니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>38</td>
<td>네트워크 연결은 낮음으로 식별됩니다. 끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다. 데이터 통신 연결: %2, 인터넷 사용 가능: %3, 무료 네트워크 사용 가능: %4.</td>
<td>장치가 데이터 통신/유료 네트워크를 사용하고 있으며 서버에 자주 연결하지 않습니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>39</td>
<td>네트워크 연결은 정상으로 식별됩니다. 끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다. 데이터 통신 연결: %2, 인터넷 사용 가능: %3, 무료 네트워크 사용 가능: %4.</td>
<td>장치가 데이터 데이터 연결/유료 연결을 사용하지 않는 경우 평소처럼 서버에 연결합니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>40</td>
<td>배터리 상태는 낮음으로 식별됩니다. 끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다. 배터리 상태: %2.</td>
<td>디바이스의 배터리 잔량이 낮고 서버에 자주 연결하지 않습니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>41</td>
<td>배터리 상태는 정상으로 식별됩니다. 끝점용 Microsoft Defender는 %1분마다 서버에 연결합니다. 배터리 상태: %2.</td>
<td>디바이스의 배터리 수준이 낮지 않은 경우 평소처럼 서버에 연결합니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>42</td>
<td>끝점용 Microsoft Defender WDATP 구성 요소가 작업을 수행하지 못했습니다. 구성 요소: %1, 작업: %2, 예외 유형: %3, 예외 메시지: %4</td>
<td>내부 오류입니다. 서비스를 시작하지 못했습니다.</td>
<td>이 오류가 계속되면 지원에 문의합니다.</td>
</tr>
<tr>
<td>43</td>
<td>끝점용 Microsoft Defender WDATP 구성 요소가 작업을 수행하지 못했습니다. 구성 요소: %1, 작업: %2, 예외 유형: %3, 예외 오류: %4, 예외 메시지: %5</td>
<td>내부 오류입니다. 서비스를 시작하지 못했습니다.</td>
<td>이 오류가 계속되면 지원에 문의합니다.</td>
</tr>
<tr>
<td>44</td>
<td>끝점 서비스에 대한 Defender의 오프보딩이 완료되었습니다.</td>
<td>서비스가 오프보더된 경우</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>45</td>
<td>이벤트 추적 세션 [%1]을(를) 등록하고 시작하지 못했습니다. 오류 코드: %2</td>
<td>ETW 세션을 만드는 동안 서비스 시작 시 오류가 발생했습니다. 이로 인해 서비스 시작 오류가 발생했습니다.</td>
<td>이 오류가 계속되면 지원에 문의합니다.</td>
</tr>
<tr>
<td>46</td>
<td>리소스 부족으로 인해 이벤트 추적 세션 [%1]을(를) 등록하고 시작하지 못했습니다. 오류 코드: %2. 활성 이벤트 추적 세션이 너무 많기 때문에 이 가능성이 많을 수 있습니다. 서비스가 1분 후 다시 시도됩니다.</td>
<td>리소스 부족으로 인해 ETW 세션을 만드는 동안 서비스 시작 시 오류가 발생했습니다. 서비스가 시작되고 실행 중이지만 ETW 세션이 시작될 때까지 센서 이벤트를 보고하지 않습니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다. 서비스가 1분마다 세션을 시작하려고 시도합니다.</td>
</tr>
<tr>
<td>47</td>
<td>이벤트 추적 세션을 등록하고 시작했습니다. 이전 시도가 실패한 후에 복구됩니다.</td>
<td>이 이벤트는 ETW 세션을 성공적으로 시작한 후 이전 이벤트를 진행합니다.</td>
<td>정상 작동 알림 필요한 작업이 없습니다.</td>
</tr>
<tr>
<td>48</td>
<td>이벤트 추적 세션 [%2]에 공급자 [%1]을(를) 추가하지 못했습니다. 오류 코드: %3. 즉, 이 공급자의 이벤트가 보고되지 않습니다.</td>
<td>ETW 세션에 공급자를 추가하지 못했습니다. 따라서 공급자 이벤트가 보고되지 않습니다.</td>
<td>오류 코드를 검사합니다. 오류가 계속되면 고객 지원에 문의합니다.</td>
</tr>
</tr>
</tbody>
</table>

>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>관련 항목
- [Windows 10 장치 온보드](configure-endpoints.md)
- [장치 프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md)
- [끝점용 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
