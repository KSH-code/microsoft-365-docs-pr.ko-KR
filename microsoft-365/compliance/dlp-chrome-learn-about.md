---
title: Microsoft 규정 준수 확장에 대해 알아보기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Microsoft 규정 준수 확장을 통해 파일 활동 및 보호 작업을 Google Chrome 브라우저로 확장
ms.openlocfilehash: cf7a3cd2e26f2e7d7a116e4a609f98aeea78be19
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59193082"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a>Microsoft 규정 준수 확장에 대해 알아보기

[끝점 데이터 손실 방지](endpoint-dlp-learn-about.md)(끝점 DLP)는 [Microsoft 365 데이터 손실 방지(DLP)](dlp-learn-about-dlp.md)의 활동 모니터링 및 보호 기능을 Windows 10 장치의 중요한 항목으로 확장합니다. 장치가 Microsoft 365 규정 준수 솔루션에 등록된 경우 사용자가 중요한 항목으로 수행하는 작업에 대한 정보는 [활동 탐색기](data-classification-activity-explorer.md)에서 확인할 수 있으며 해당 항목에 대한 보호 작업은 [DLP 정책](create-test-tune-dlp-policy.md)을 통해 적용할 수 있습니다.

Windows 10 장치에 Microsoft 규정 준수 확장을 설치하면 조직에서는 사용자가 Google Chrome을 사용하여 클라우드 서비스에 중요한 항목에 액세스하거나 업로드하려고 할 때 이를 모니터링하고 DLP를 통해 보호 작업을 적용할 수 있습니다.  

## <a name="activities-you-can-monitor-and-take-action-on"></a>모니터링하고 조치를 취할 수 있는 활동

Microsoft 규정 준수 확장을 사용하여 Windows 10을 실행하는 장치에서 사용자가 중요한 항목에 대해 수행하는 다음 유형의 활동을 감사하고 관리할 수 있습니다.

활동 |설명  | 지원되는 정책 작업|
|---------|---------|---------|
|파일을 클라우드로 복사함  | 사용자가 Chrome 브라우저를 통해 제한된 서비스 도메인에 중요한 항목 업로드를 시도하는 경우 감지 |감사, 차단|
|인쇄된 파일  |사용자가 Chrome 브라우저에 열려 있는 중요한 항목을 로컬 또는 네트워크 프린터에 인쇄하려고 할 때 감지 |감사, 오버라이드로 차단, 차단|
|파일을 클립보드로 복사함 |사용자가 Chrome 브라우저에서 보고 있는 중요한 항목의 정보를 복사하려고 시도하는 경우를 감지한 다음 다른 앱, 프로세스 또는 항목에 붙여넣습니다. |감사, 오버라이드로 차단, 차단|
|이동식 저장소에 복사된 파일    | 사용자가 Chrome 브라우저에 열려 있는 중요한 항목에서 이동식 미디어 또는 USB 장치로 중요한 항목 또는 정보를 복사하려고 할 때 감지 |감사, 오버라이드로 차단, 차단|
|파일을 네트워크 공유에 복사함  |사용자가 Chrome 브라우저에 열려 있는 중요한 항목에서 네트워크 공유 또는 매핑된 네트워크 드라이브로 중요한 항목 또는 정보를 복사하려고 하는 경우 감지합니다.|감사, 오버라이드로 차단, 차단 |

## <a name="deployment-process"></a>배포 프로세스
1. [끝점 데이터 손실 방지 시작](endpoint-dlp-getting-started.md)
2. [Windows 10 장치용 온보딩 도구 및 방법](dlp-configure-endpoints.md)
3. [Windows 10 장치에 확장 설치](dlp-chrome-get-started.md)
4. 클라우드 서비스에 대한 업로드를 제한하는 [DLP 정책을 만들거나 편집](create-test-tune-dlp-policy.md)하거나 허용되지 않는 브라우저 작업으로 액세스하여 Windows 10 장치에 적용

## <a name="next-steps"></a>다음 단계

전체 배포 절차 및 시나리오는 [Microsoft 규정 준수 확장 시작하기](dlp-chrome-get-started.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [Microsoft 규정 준수 확장 시작하기](dlp-chrome-get-started.md)
- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](endpoint-dlp-learn-about.md)
- [Microsoft 끝점 데이터 손실 방지(미리 보기) 시작하기](endpoint-dlp-getting-started.md)
- [Microsoft 끝점 데이터 손실 방지(미리 보기) 사용하기](endpoint-dlp-using.md)
- [데이터 손실 방지에 대해 알아보기](dlp-learn-about-dlp.md)
- [DLP 정책 만들기, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [활동 탐색기 시작하기](data-classification-activity-explorer.md)
- [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/)
- [내부자 위험 관리](insider-risk-management.md)
