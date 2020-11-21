---
title: Microsoft Defender 바이러스 백신에서 검색 되는 위협
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Microsoft Defender 바이러스 백신이 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협 으로부터 Windows 장치를 보호 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376710"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에서 검색 되는 위협

Microsoft Defender 바이러스 백신은 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협 으로부터 Windows 장치를 보호 합니다.

- 일반적으로 바이러스는 장치나 네트워크의 다른 파일에 코드를 첨부 하 여 확산 되어 감염 된 프로그램이 제대로 작동 하지 않을 수 있습니다.
- 맬웨어에는 손상을 유발할 수 있고 장치를 정상적으로 사용 하지 못하는 악성 파일, 응용 프로그램 및 코드가 포함 되어 있습니다. 또한 맬웨어는 무단 액세스를 허용 하 고, 시스템 리소스를 사용 하 고, 암호와 계정 정보를 도용 하 고, 컴퓨터에서 로그 아웃 하 고, ransom를 요청할 수 있습니다.
- 스파이웨어는 웹 브라우징 활동 등의 데이터를 수집 하 고 원격 서버로 데이터를 보냅니다.
 
위협 보호를 제공 하기 위해 Microsoft Defender 바이러스 백신은 여러 가지 방법을 사용 합니다. 이러한 방법에는 클라우드 전달 보호, 실시간 보호 및 전용 보호 업데이트가 포함 됩니다.

- 클라우드로 전달 되는 보호 기능을 사용 하면 신규 및 새로운 위협에 대 한 즉각적인 검색 및 차단을 제공 하는 데 도움이 됩니다.
- Always on 검사에서는 파일 및 프로세스 동작 모니터링 및 기타 기술 ( *실시간 보호* 라고도 함)을 사용 합니다.
- 전용 보호 업데이트는 컴퓨터 학습, 인적 및 자동화 된 대규모 데이터 분석, 심층 위협 저항 조사를 기반으로 합니다. 

맬웨어 및 Microsoft Defender 바이러스 백신에 대 한 자세한 내용은 다음 문서를 참조 하세요. 

- [맬웨어 & 기타 위협 이해](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft가 맬웨어 및 잠재적으로 원치 않는 응용 프로그램을 식별 하는 방법](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10의 차세대 보호 기능](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>타사 바이러스 백신 솔루션을 사용할 때 발생 하는 작업 

Microsoft Defender Antivirus는 운영 체제의 일부로, Windows 10을 실행 하는 장치에서 사용 하도록 설정 되어 있습니다. 그러나 Microsoft 제품이 아닌 바이러스 백신 솔루션을 사용 하 고 있으며 [끝점에 Microsoft defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)를 사용 하지 않는 경우 Microsoft Defender 바이러스 백신이 자동으로 사용 하지 않도록 설정 모드로 전환 됩니다.  

사용 안 함 모드일 때 사용자 및 고객은 예약 또는 주문형 검색에 대해 Microsoft Defender 바이러스 백신을 사용 하 여 위협을 식별할 수 있습니다. 그러나 Microsoft Defender 바이러스 백신은 더 이상 다음 작업을 수행 하지 않습니다.

- 기본 바이러스 백신 앱으로 사용 됩니다.
- 파일을 적극적으로 검사 합니다.
- 위협을 수정 하거나 해결 합니다.

타사 바이러스 백신 솔루션을 제거 하면 Microsoft Defender 바이러스 백신이 자동으로 활성 모드로 전환 되어 Windows 장치를 위협 으로부터 보호 합니다.

> [!TIP]
> - Microsoft 365을 사용 하는 경우 Microsoft Defender Antivirus를 기본 바이러스 백신 솔루션으로 사용 하는 것이 좋습니다. 통합을 통해 보호 기능이 향상 될 수 있습니다. 함께 사용할 경우 [Microsoft Defender Antivirus And Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus)를 참조 하세요.
> - Microsoft 제품이 아닌 바이러스 백신 솔루션을 사용 하는 경우에도 Microsoft Defender 바이러스 백신을 최신 상태로 유지 해야 합니다.

## <a name="what-to-expect-when-threats-are-detected"></a>위협이 검색 될 때 예상 되는 사항

Microsoft Defender 바이러스 백신에서 위협이 검색 되 면 다음과 같은 결과가 발생 합니다.

- 사용자가 [Windows에서 알림을](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e)받습니다. 
- 검색은 [Windows 보안 앱](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 의 **보호 기록** 페이지에 나열 됩니다.  
- [Windows 10 장치를 보호](secure-win-10-pcs.md) 하 고 [Intune에서 등록](/mem/intune/enrollment/windows-enrollment-methods)한 경우, **홈** 페이지의 **microsoft Defender 바이러스 백신** 카드에서 또는 탐색 창에서 & 바이러스 백신 **을 선택 하** 여 액세스할 수 있는 **활성 위협** 페이지의 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">microsoft 365 관리 센터</a> 에 위협 감지 및 통찰력이 표시 됩니다  >  **Threats & antivirus**.
    > [!NOTE]
    > **Microsoft Defender 바이러스 백신** 카드 및 **활성 위협** 페이지는 단계별로 롤아웃 되므로 즉시 액세스 하지 못할 수 있습니다.

대부분의 경우 사용자는 추가 작업을 수행할 필요가 없습니다. 악성 파일 또는 프로그램이 장치에서 검색 되는 즉시 Microsoft Defender 바이러스 백신은이를 차단 하 고 실행 되지 않도록 합니다. 또한 새로 검색 된 위협이 다른 장치 및 사용자도 보호 되도록 바이러스 백신 및 맬웨어 방지 엔진에 추가 됩니다.  

악의적인 파일 제거를 승인 하는 것과 같이 사용자가 수행 해야 하는 작업이 있으면 수신 된 알림에 해당 내용이 표시 됩니다. Microsoft Defender 바이러스 백신이 사용자 대신 수행 해야 하는 작업에 대 한 자세한 내용을 알아보거나, 사용자에 게 필요한 작업에 대 한 자세한 내용은 [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708)를 참조 하세요. IT 전문가/관리자로 위협 감지를 관리 하는 방법에 대 한 자세한 내용은 [검색 된 위협 검토 및 조치 수행](review-threats-take-action.md)을 참조 하세요.

다른 위협에 대해 자세히 알아보려면 다음 작업을 수행할 수 있는 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft 보안 인텔리전스 위협 사이트</a>를 방문 하세요. 

- 주요 위협에 대 한 최신 정보를 봅니다.
- 특정 지역에 대 한 최신 위협 보기
- 위협 백과 사전에서 특정 위협에 대 한 세부 정보를 검색 합니다.

## <a name="related-content"></a>관련 콘텐츠

[보안 Windows 10 장치](secure-windows-10-devices.md) (문서) \
[Microsoft Defender 바이러스 백신 평가](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (문서) \
[실시간 및 클라우드에서 배달 되는 바이러스 백신 보호 기능을 설정 하는 방법](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (문서) \
[Windows 보안 앱에서 Microsoft Defender 바이러스 백신을 설정 하 고 사용 하는 방법](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (문서) \
[그룹 정책을 사용 하 여 Microsoft Defender 바이러스 백신을 설정 하는 방법](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (문서) \
[바이러스 검사 정의를 업데이트 하는 방법](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (문서) \
[분석을 위해 맬웨어 및 비 맬웨어를 Microsoft에 제출 하는 방법](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (문서)