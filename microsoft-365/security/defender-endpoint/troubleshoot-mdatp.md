---
title: 엔드포인트용 Microsoft Defender 서비스 문제 해결
description: 서비스에 액세스하려고 할 때 서버 오류와 같은 알려진 문제에 대한 해결 방법과 해결 방법을 찾아야 합니다.
keywords: 끝점에 대한 Microsoft Defender 문제 해결, 서버 오류, 액세스 거부, 잘못된 자격 증명, 데이터 없음, 대시보드 포털, 허용, 이벤트 뷰어
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: d46fb5d456377a3089e5d6cfa45918eb42849227
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553862"
---
# <a name="troubleshoot-service-issues"></a>서비스 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

이 섹션에서는 Microsoft Defender for Endpoint 서비스를 사용할 때 발생할 수 있는 문제를 설명합니다.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>서버 오류 - 잘못된 자격 증명으로 인해 액세스가 거부되었습니다.

서비스에 액세스하려고 할 때 서버 오류가 발생하는 경우 브라우저 쿠키 설정을 변경해야 합니다.
쿠키를 허용하도록 브라우저를 구성합니다.

## <a name="elements-or-data-missing-on-the-portal"></a>포털에 누락된 요소 또는 데이터

일부 요소 또는 데이터가 누락된 Microsoft 365 Defender 프록시 설정으로 차단할 수 있습니다.

프록시 허용 `*.security.microsoft.com` 목록에 포함해야 합니다.

> [!NOTE]
> 다음 끝점을 추가할 때 HTTPS 프로토콜을 사용해야 합니다.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>끝점용 Microsoft Defender 서비스에서 이벤트 뷰어에 이벤트 또는 오류 로그 표시

Microsoft Defender [for](event-error-codes.md) Endpoint 서비스에서 보고하는 이벤트 ID 목록은 이벤트 뷰어를 사용하여 이벤트 및 오류 검토를 참조하세요. 이 문서에는 이벤트 오류에 대한 문제 해결 단계도 포함되어 있습니다.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>다시 시작한 후 끝점용 Microsoft Defender 서비스가 시작되지 못하고 오류 577이 표시

장치 온보딩이 성공적으로 완료되지만 다시 시작한 후 끝점용 Microsoft Defender가 시작되지 않는 경우 오류 577이 표시될 경우 정책에 Windows Defender 사용하지 않도록 설정되어 있지 않은지 검사합니다.

자세한 내용은 [정책에 Microsoft Defender 바이러스 백신 사용하지 않도록 설정되어 있지 않은지 확인을 참조하세요.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

## <a name="known-issues-with-regional-formats"></a>지역별 형식의 알려진 문제

### <a name="date-and-time-formats"></a>날짜 및 시간 형식

시간 및 날짜 형식에 몇 가지 알려진 문제가 있습니다.

지원되는 날짜 형식은 다음과 같습니다.

- MM/dd/yyyy
- dd/MM/yyyy

다음 날짜 및 시간 형식은 현재 지원되지 않습니다.

- 날짜 형식 yyyy/MM/dd
- 날짜 형식 dd/MM/yy
- 날짜 형식(yy) yyyy만 표시
- 시간 형식 HH:mm:ss는 지원되지 않습니다(12시간 AM/PM 형식은 지원되지 않습니다). 24시간 형식만 지원됩니다.

### <a name="use-of-comma-to-indicate-thousand"></a>0000

숫자에서 구분으로 콤보를 사용할 수 없습니다. 숫자가 1000을 나타내는 콤보로 구분되는 지역은 점만 구분 구분선으로만 사용할 수 있습니다. 예를 들어 15,5K는 15.5K로 표시됩니다.

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Microsoft Defender for Endpoint 테넌트가 유럽에서 자동으로 생성되었습니다.

Azure Defender를 사용하여 서버를 모니터링하면 끝점 테넌트용 Microsoft Defender가 자동으로 만들어집니다. 끝점용 Microsoft Defender 데이터는 기본적으로 유럽에 저장됩니다.

## <a name="related-topics"></a>관련 항목

- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
- [이벤트 뷰어를 사용하여 이벤트 및 오류 검토](event-error-codes.md)
