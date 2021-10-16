---
title: Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 끝점 데이터 손실 방지는 파일 활동의 모니터링 및 해당 파일에 대한 보호 작업을 끝점으로 확장합니다. 파일은 Microsoft 365 규정 준수 솔루션에서 확인할 수 있습니다. '
ms.openlocfilehash: 9d1577cff0cc06589c833a568af214c99059e829
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364534"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Microsoft 365 끝점 데이터 손실 방지 알아보기

Microsoft 365 DLP(데이터 손실 방지)를 사용하여 중요한 항목에 대해 수행 중인 작업을 모니터링하고 해당 항목이 의도치 않게 공유되는 것을 방지할 수 있습니다. DLP에 대한 자세한 내용은 [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)를 참조하세요.

**끝점 데이터 손실 방지**(끝점 DLP)는 DLP의 활동 모니터링 및 보호 기능을 Windows 10 디바이스에 물리적으로 저장된 중요한 항목으로 확장합니다. 장치가 Microsoft 365 규정 준수 솔루션에 등록된 경우 사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용할 수 있습니다.

> [!TIP]
> 이동식 저장소에 대한 디바이스 제어를 찾고 있는 경우 [엔드포인트용 Microsoft Defender 디바이스 제어 이동식 저장소 액세스 제어](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control)를 참조하세요.

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>모니터링 및 조치 가능한 끝점 활동

Microsoft 끝점 DLP를 사용하면 사용자가 Windows 10 디바이스에 물리적으로 저장된 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다.

|활동 |설명  | 감사 가능/제한 가능|
|---------|---------|---------|
|클라우드 서비스로 업로드 또는 허용되지 않은 브라우저에서 액세스    | 사용자가 항목을 제한된 서비스 도메인에 업로드하거나 브라우저를 통해 항목에 액세스하려는 경우 이를 감지합니다.  DLP에 허용되지 않는 브라우저로 나열되는 브라우저를 사용하는 경우에는 업로드 작업이 차단되고 사용자는 Edge Chromium을 사용하도록 리디렉션됩니다. Edge Chromium에서는 DLP 정책 구성을 기반으로 업로드 또는 액세스를 허용하거나 차단합니다.         |감사 및 통제|
|다른 앱으로 복사    |사용자가 보호되는 항목에서 정보를 복사한 후 다른 앱, 프로세스 또는 항목에 붙여넣기를 시도하는 경우 이를 감지합니다. 이 작업으로는 동일한 앱, 프로세스 또는 항목 내에서의 정보 복사 및 붙여넣기는 감지되지 않습니다.         | 감사 및 통제|
|USB 이동식 미디어에 복사 |사용자가 항목이나 정보를 이동식 미디어 또는 USB 장치에 복사하려고 할 때이를 감지합니다.         | 감사 및 통제|
|네트워크 공유 위치에 복사    |사용자가 항목을 네트워크 공유 또는 매핑된 네트워크 드라이브로 복사하려고 할 때 이를 감지합니다.         |감사 및 통제|
|문서 인쇄    |사용자가 보호된 항목을 로컬 또는 네트워크 프린터로 인쇄하려고 할 때 이를 감지합니다.| 감사 및 통제         |
|원격 세션에 복사|사용자가 원격 데스크톱 세션에 항목을 복사하려고 할 때 감지 |  감사 및 통제|
|Bluetooth 장치에 복사|사용자가 허용하지 않는 Bluetooth 앱(끝점 DLP 설정의 허용하지 않는 Bluetooth aps 목록에 정의된 경우)에 대한 복사를 시도하는 경우를 감지합니다.| 감사 및 통제|
|항목 만들기|사용자가 항목을 만들 때 이를 감지합니다.| 감사|
|항목 이름 바꾸기|사용자가 항목 이름을 바꿀 때 이를 감지합니다.| 감사|

## <a name="monitored-files"></a>모니터링된 파일

끝점 DLP는 다음 파일 형식의 모니터링을 지원합니다. DLP는 정책 일치가 없는 경우에도 이러한 파일 유형에 대한 작업을 감사합니다. 

- Word 파일
- PowerPoint 파일
- Excel 파일
- PDF 파일
- .csv 파일
- .tsv 파일
- .txt 파일
- RTF 파일
- c 파일
- 클래스 파일
- cpp 파일
- cs 파일
- h 파일
- java 파일
 
정책 일치의 데이터만 모니터링하려는 경우 끝점 DLP 전역 설정에서 **장치의 항상 감사 파일 활동** 을 해제할 수 있습니다.

> [!NOTE]
> **장치에 대한 파일 활동 항상 감사** 설정이 켜져 있으면 장치가 정책에 의해 대상이 지정되지 않더라도 Word, PowerPoint, Excel, PDF 및 .csv 파일의 작업이 항상 감사됩니다.

> [!TIP]
> 지원되는 모든 파일 형식에 대한 활동이 감사되도록 기본 정책과 함께 [사용자 지정 DLP 정책](create-test-tune-dlp-policy.md)을 만드면 됩니다.


끝점 DLP는 활동 기반의 Om MIME 유형을 모니터링하므로 파일 확장명이 변경되더라도 활동은 캡처됩니다.

## <a name="whats-different-in-endpoint-dlp"></a>끝점 DLP의 다양한 기능

끝점 DLP를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.

### <a name="enabling-device-management"></a>장치 관리 사용 설정

장치 관리는 장치에서 원격 분석 수집을 사용하도록 설정하고 원격 분석 수집을 끝점 DLP 및 [참가자 위험 관리](insider-risk-management.md)와 같은 Microsoft 365 규정 준수 솔루션으로 가져오는 기능입니다. DLP 정책에서 위치로 사용하려는 모든 장치를 등록해야 합니다.

> [!div class="mx-imgBorder"]
> ![장치 관리를 사용하도록 설정.](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

장치 관리 센터에서 다운로드한 스크립트를 통해 온보딩 및 오프보딩이 처리됩니다. 해당 센터는 각 배포 방법에 대한 사용자 지정 스크립트를 포함합니다.

- 로컬 스크립트(최대 10대의 컴퓨터)
- 그룹 정책
- System Center Configuration Manager(버전 1610 이상)
- 모바일 장치 관리/Microsoft Intune
- 비 영구적인 컴퓨터에 대한 VDI 온보딩 스크립트

> [!div class="mx-imgBorder"]
> ![장치 온보딩 페이지.](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 [Microsoft 365 끝점 DLP 시작하기](endpoint-dlp-getting-started.md)의 절차를 사용하여 장치를 등록하세요.

[엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)를 통해 장치를 온보딩한 경우, 해당 장치는 장치 목록에 자동으로 표시됩니다.

> [!div class="mx-imgBorder"]
> ![관리된 장치 목록.](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>끝점 DLP 데이터 확인하기

[DLP 경고 관리 대시보드](dlp-configure-view-alerts-policies.md)로 이동하여 끝점 장치에 적용되는 DLP 정책과 관련된 경고를 볼 수 있습니다.

> [!div class="mx-imgBorder"]
> ![경고 정보](../media/Alert-info-1.png)

동일한 대시보드에서 서식 있는 메타데이터와 관련된 이벤트 세부 정보를 볼 수도 있습니다.

> [!div class="mx-imgBorder"]
> ![이벤트 정보.](../media/Event-info-1.png)

장치가 등록되면 장치를 위치로 포함하는 모든 DLP 정책을 구성하고 배포하기 전에 감사 활동에 대한 정보가 활동 탐색기로 전달됩니다.

> [!div class="mx-imgBorder"]
> ![활동 탐색기의 끝점 DLP 이벤트.](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

끝점 DLP는 감사 활동에 대한 광범위한 정보를 수집합니다.

예를 들어 파일이 이동식 USB 미디어에 복사되는 경우 활동 세부 정보에 다음 특성이 표시됩니다.

- 활동 유형
- 클라이언트 IP
- 대상 파일 경로
- 타임스탬프 발생
- 파일 이름
- 사용자
- 파일 확장명
- 파일 크기
- 중요한 정보 유형(해당하는 경우)
- SHA1 값
- SHA256 값
- 이전 파일 이름
- 위치
- 상위
- 파일 경로
- 원본 위치 유형
- 플랫폼
- 장치 이름
- 대상 위치 유형
- 복사를 수행한 응용 프로그램
- 엔드포인트용 Microsoft Defender 장치 ID(해당하는 경우)
- 이동식 미디어 장치 제조업체
- 이동식 미디어 장치 모델
- 이동식 미디어 장치 일련 번호

> [!div class="mx-imgBorder"]
> ![USB 활동 특성에 복사.](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>다음 단계

이제 끝점 DLP에 대해 살펴보았으므로 다음 단계는 다음과 같습니다.

1. [Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기](endpoint-dlp-getting-started.md)
2. [Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기](endpoint-dlp-using.md)

## <a name="see-also"></a>참고 항목

- [Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기](endpoint-dlp-getting-started.md)
- [Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기](endpoint-dlp-using.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)
- [내부자 위험 관리](insider-risk-management.md)
