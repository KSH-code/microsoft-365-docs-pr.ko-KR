---
title: Microsoft Defender AV에 대한 보고 도구 문제 해결
description: 업데이트 준수에서 Microsoft Defender AV 보호 상태 보고를 시도할 때 일반적인 문제 식별 및 해결
keywords: 문제 해결, 오류, 수정, 업데이트 준수, oms, 모니터링, 보고서, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ca62db922a13ab2cb3226eaf0efb92bfaf8c572b
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274895"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>업데이트 규정 준수에서 Microsoft Defender 바이러스 백신 보고 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> 2020년 3월 31일, 업데이트 준수의 Microsoft Defender 바이러스 백신 보고 기능이 제거됩니다. 보안 기능 및 업데이트를 더 Microsoft Endpoint Manager 사용하여 보안 준수 정책을 계속 [정의하고](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)검토할 수 있습니다.

업데이트 준수와 함께 Microsoft Defender 바이러스 백신 수 있습니다. E3, B, F1, VL 및 Pro 상태가 표시됩니다. 그러나 E5 라이선스의 경우 [끝점 포털용 Microsoft Defender를 사용해야 합니다.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 라이선스 옵션에 대한 자세한 내용은 Windows 10 [라이선스 옵션을 참조하세요.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

Windows [분석](/windows/deployment/update/update-compliance-using#wdav-assessment) 업데이트 준수를 사용하여 네트워크에서 장치를 사용하는 장치 또는 끝점의 보호 상태에 대한 보고를 받을 Microsoft Defender 바이러스 백신 문제가 발생할 수 있습니다.

일반적으로 문제의 가장 일반적인 지표는 다음입니다.
- 예상한 모든 장치의 소수 또는 하위 집합만 표시
- 어떤 장치도 볼 수 없습니다.
- 보고 있는 보고서 및 정보가 기한이 지난 경우(며칠이 지난 경우)

업데이트 준수와 관련이 없는 Microsoft Defender 바이러스 백신 서비스와 관련된 일반적인 오류 코드 및 이벤트 MICROSOFT DEFENDER 바이러스 백신 [참조하세요.](troubleshoot-microsoft-defender-antivirus.md) 

이러한 문제를 해결하는 데는 다음 세 단계가 있습니다.

1. 모든 선행 준비를 충족하는지 확인
2. 클라우드 기반 서비스에 Windows Defender 연결 확인
3. 지원 로그 제출

>[!IMPORTANT]
>일반적으로 업데이트 준수에 장치가 나타나기 시작하는 데 3일이 소요됩니다.


## <a name="confirm-prerequisites"></a>선행 준비 확인

장치가 업데이트 준수에 제대로 표시하려면 업데이트 준수 서비스 및 업데이트 준수 서비스에 대한 특정 선행 Microsoft Defender 바이러스 백신.

>[!div class="checklist"]
>- 끝점에서 단독 Microsoft Defender 바이러스 백신 보호 앱으로 사용하고 있습니다. 다른 바이러스 백신 앱을 사용하는 [경우 Microsoft Defender AV가](microsoft-defender-antivirus-compatibility.md) 자체적으로 비활성화되어 끝점이 업데이트 준수에 보고되지 않습니다.
> - [클라우드 제공 보호가 사용하도록 설정됩니다.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - 끝점에서 [Microsoft Defender AV 클라우드에 연결할 수 있습니다.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - 끝점이 1607 Windows 10 실행 중인 경우 Windows 10 진단 데이터를 고급 [수준으로 설정해야 합니다.](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)
> - 모든 요구 사항이 충족된 후 3일이 지났습니다.

"업데이트 준수와 함께 Microsoft Defender 바이러스 백신 수 있습니다. E3, B, F1, VL 및 Pro 상태가 표시됩니다. 그러나 E5 라이선스의 경우 끝점용 Microsoft Defender 포털( 를 사용해야 https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 합니다. 라이선스 옵션에 대한 자세한 내용은 Windows 10 라이선스 옵션을 참조하세요."

위의 선행 구성이 모두 충족된 경우 다음 단계로 진행하여 진단 정보를 수집하고 이를 저희에게 보내야 할 수 있습니다.

> [!div class="nextstepaction"]
> [업데이트 준수 문제 해결을 위한 진단 데이터 수집](collect-diagnostic-data.md)  

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender 바이러스 백신 Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [배포 Microsoft Defender 바이러스 백신](deploy-manage-report-microsoft-defender-antivirus.md)