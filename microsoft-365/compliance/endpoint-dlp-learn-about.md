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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 끝점 데이터 손실 방지는 파일 활동과 해당 파일에 대한 보호 작업의 모니터링을 끝점으로 확장합니다. 파일은 Microsoft 365 규정 준수 솔루션에서 확인할 수 있습니다. '
ms.openlocfilehash: 966e201acb8038d85f0d06c0800c9845fd79097e
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984932"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a>Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보

Microsoft 365 DLP(데이터 손실 방지)를 사용하여 중요하다고 판단한 항목에 대해 수행되는 작업을 모니터링하고 해당 항목이 의도치 않게 공유되는 것을 방지할 수 있습니다. DLP에 대한 자세한 내용은 [데이터 손실 방지 개요](data-loss-prevention-policies.md)를 참조하세요.

**끝점 데이터 손실 방지** (끝점 DLP)는 Windows 10 장치에 있는 중요한 항목으로 DLP의 활동 모니터링 및 보호 기능을 확장합니다. 장치가 Microsoft 365 규정 준수 솔루션에 등록되면, [활동 탐색기](data-classification-activity-explorer.md)에서 사용자가 중요한 항목으로 수행하는 작업에 대한 정보를 확인할 수 있으며 이러한 항목에 대해 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 보호 작업을 적용할 수 있습니다.

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>모니터링 및 조치를 취할 수 있는 끝점 활동

Microsoft 끝점 DLP를 사용하여 Windows 10을 실행하는 장치에서 사용자가 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다. 여기에는 다음과 같은 활동이 포함됩니다.


|항목에 대한 작업 |감사/통제  |
|---------|---------|
|생성    | 감사      |
|이름 변경    |  감사       |
|이동식 미디어에 복사 또는 생성     |     감사 및 통제|
|네트워크 공유에 복사(예: \\my-server\fileshare)   |     감사 및 통제    |
|인쇄 |    감사 및 통제       |
|Chromium Edge를 통해 클라우드에 복사    |   감사 및 통제        |
|허용되지 않는 앱 및 브라우저로 액세스    |  감사 및 통제       |

## <a name="whats-different-in-endpoint-dlp"></a>끝점 DLP의 다양한 기능

끝점 DLP를 살펴보기 전에 알아야 할 몇 가지 추가 개념이 있습니다.

### <a name="enabling-device-management"></a>장치 관리를 사용하도록 설정하기

장치 관리는 장치에서 원격 분석 수집을 사용하도록 설정하고 이를 끝점 DLP 및 [참가자 위험 관리](insider-risk-management.md)와 같은 Microsoft 365 규정 준수 솔루션으로 가져오는 기능입니다. DLP 정책에서 위치로 사용하려는 모든 장치를 등록해야 합니다.

> [!div class="mx-imgBorder"]
> ![장치 관리를 사용하도록 설정](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

온보딩 및 오프보딩은 장치 관리 센터에서 다운로드하는 스크립트를 통해 처리됩니다. 장치 관리 센터는 각 배포 방법에 대한 사용자 지정 스크립트를 포함하고 있습니다.

- 로컬 스크립트(최대 10대의 컴퓨터)
- 그룹 정책
- System Center Configuration Manager(버전 1610 이상)
- 모바일 장치 관리/Microsoft Intune
- 비 영구적인 컴퓨터에 대한 VDI 온보딩 스크립트

> [!div class="mx-imgBorder"]
> ![장치 온보딩 페이지](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 [Microsoft 365 끝점 DLP 시작하기](endpoint-dlp-getting-started.md)의 절차를 사용하여 장치를 등록하세요.

[엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)를 통해 장치를 온보딩한 경우, 해당 장치는 장치 목록에 자동으로 표시됩니다.

> [!div class="mx-imgBorder"]
> ![관리된 장치 목록](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>끝점 DLP 데이터 확인하기

 끝점 DLP는 MIME 형식에 따라 활동을 모니터링하여, 파일 확장명이 변경이 되더라도 작업이 캡처됩니다. 공개 미리 보기에서 다음을 모두 감시합니다.

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
- .java 파일

> [!NOTE]
> 끝점 DLP는 DLP 정책을 기준으로 위의 모든 유형의 파일을 평가하고 그에 따라 보호 조치를 적용합니다. DLP 정책과 일치하는 모든 파일은 차단되지 않은 경우에도 지원되는 모든 작업에 대해 감사됩니다. 또한 Word, PowerPoint, Excel, PDF 및 .csv 파일에서 수행되는 파일 작업은 DLP 정책이 있는지 또는 이러한 파일과 일치하는지 여부에 관계없이 기본적으로 감사됩니다.

장치가 등록되면 장치를 위치로 포함하는 모든 DLP 정책을 구성하고 배포하기 전에 감사 활동에 대한 정보가 활동 탐색기로 전달됩니다.

> [!div class="mx-imgBorder"]
> ![활동 탐색기의 끝점 DLP 이벤트](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

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
> ![USB 활동 특성에 복사](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>다음 단계

이제 끝점 DLP에 대해 살펴보았으므로 다음 단계는 다음과 같습니다.

1) [Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기](endpoint-dlp-getting-started.md)
2) [Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기](endpoint-dlp-using.md)

## <a name="see-also"></a>참고 항목

- [Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기](endpoint-dlp-getting-started.md)
- [Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기](endpoint-dlp-using.md)
- [데이터 손실 방지 개요](data-loss-prevention-policies.md)
- [DLP 정책 생성, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/)
- [내부자 위험 관리](insider-risk-management.md)
