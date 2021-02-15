---
title: Microsoft Defender 바이러스 백신에서 탐지된 위협
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
description: Microsoft Defender 바이러스 백신이 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협으로부터 Windows 장치를 보호하는 방법을 알아보십시오.
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870902"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에서 탐지된 위협

Microsoft Defender 바이러스 백신은 바이러스, 맬웨어 및 스파이웨어와 같은 소프트웨어 위협으로부터 Windows 장치를 보호합니다.

- 바이러스는 일반적으로 장치 또는 네트워크의 다른 파일에 코드를 연결하여 확산되고 감염된 프로그램이 잘못 작동하도록 할 수 있습니다.
- 맬웨어에는 손상을 유발하고 장치의 정상적인 사용을 방해할 수 있는 악성 파일, 응용 프로그램 및 코드가 포함됩니다. 또한 맬웨어는 무단 액세스를 허용하고, 시스템 리소스를 사용하며, 암호 및 계정 정보를 도용하고, 컴퓨터를 잠그고 대리를 요청하는 등도 할 수 있습니다.
- 스파이웨어는 웹 검색 활동과 같은 데이터를 수집하고 데이터를 원격 서버로 전송합니다.
 
위협 방지를 제공하기 위해 Microsoft Defender 바이러스 백신은 여러 가지 방법을 사용했습니다. 이러한 방법에는 클라우드 제공 보호, 실시간 보호 및 전용 보호 업데이트가 포함됩니다.

- 클라우드 제공 보호는 새로운 위협을 거의 즉각적으로 감지하고 차단하는 데 도움이 됩니다.
- 항상 검사는 파일 및 프로세스 동작 모니터링 및 기타 기술(실시간 보호라고도 합니다)을 *사용합니다.*
- 전용 보호 업데이트는 기계 학습, 인간 및 자동화된 빅 데이터 분석 및 심층 위협 저항 연구를 기반으로 합니다. 

맬웨어 및 Microsoft Defender 바이러스 백신에 대한 자세한 내용은 다음 문서를 참조합니다. 

- [다른 위협에 & 맬웨어 이해](/windows/security/threat-protection/intelligence/understanding-malware)
- [Microsoft에서 맬웨어 및 사용자 원치 않는 응용 프로그램을 식별하는 방법](/windows/security/threat-protection/intelligence/criteria)
- [Windows 10의 차세대 보호](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Microsoft가 아닌 바이러스 백신 솔루션을 사용하는 경우 어떻게 하나요? 

Microsoft Defender 바이러스 백신은 운영 체제의 일부로, Windows 10을 실행하는 장치에서 사용하도록 설정됩니다. 그러나 Microsoft가 아닌 바이러스 백신 솔루션을 사용하고 있으며 [끝점용 Microsoft Defender를](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)사용하지 않는 경우 Microsoft Defender 바이러스 백신이 자동으로 비활성화 모드로 전환됩니다.  

사용하지 않도록 설정되어 있는 경우 사용자와 고객은 예약된 검사 또는 필요한 경우 검사에 여전히 Microsoft Defender 바이러스 백신을 사용하여 위협을 식별할 수 있습니다. 그러나 Microsoft Defender 바이러스 백신은 더 이상 다음을 실행하지 않습니다.

- 는 기본 바이러스 백신 앱으로 사용됩니다.
- 파일을 적극적으로 검색하여 위협을 검사합니다.
- 위협을 수정하거나 해결합니다.

Microsoft가 아닌 바이러스 백신 솔루션을 제거하면 Microsoft Defender 바이러스 백신이 자동으로 활성 모드로 전환되어 Windows 장치를 위협으로부터 보호합니다.

> [!TIP]
> - Microsoft 365를 사용하는 경우 Microsoft Defender 바이러스 백신을 기본 바이러스 백신 솔루션으로 사용할 수 있습니다. 통합은 더 나은 보호를 제공할 수 있습니다. 함께 [보기: Microsoft Defender 바이러스 백신 및 Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Microsoft가 아닌 바이러스 백신 솔루션을 사용하는 경우에도 Microsoft Defender 바이러스 백신을 최신 상태로 유지해야 합니다.

## <a name="what-to-expect-when-threats-are-detected"></a>위협이 감지될 때 예상되는 일

Microsoft Defender 바이러스 백신에서 위협이 감지되면 다음과 같은 상황이 발생하게 됩니다.

- 사용자는 [Windows에서 알림을 받게 됩니다.](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e) 
- 검색은 보호 기록 페이지의 [Windows 보안](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) **앱에 나열됩니다.**  
- [Windows 10](secure-win-10-pcs.md) 장치를 보호하고 [Intune에](/mem/intune/enrollment/windows-enrollment-methods)등록한 경우 조직에 등록된 장치가 800개 이하인 경우 위협 및 바이러스 백신 페이지의 **Microsoft** <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365</a>  관리 센터에서 위협 감지 및 정보를 볼 수 있습니다. 이 페이지에서는 홈 페이지(또는 상태 위협 & 바이러스 백신을 선택하여 탐색   >  **창)에서** 액세스할 수 있습니다.

    조직에 Intune에 등록된 장치가 800개가 넘는 경우 위협 및 바이러스 백신 페이지 대신 [Microsoft Endpoint Manager에서](/mem/endpoint-manager-overview) 위협 감지 및 인사이트를 볼지 묻는 메시지가 **표시됩니다.**
 
    > [!NOTE]
    > **Microsoft Defender 바이러스**  백신 카드 및 위협 및 바이러스 백신 페이지가 단계적으로 배포되고 있으므로 즉시 액세스할 수 없습니다.

대부분의 경우 사용자는 추가 작업을 수행하지 필요가 없습니다. 장치에서 악성 파일 또는 프로그램이 감지되는 즉시 Microsoft Defender 바이러스 백신은 해당 파일을 차단하고 실행을 차단합니다. 또한 새로 검색된 위협이 바이러스 백신 및 맬웨어 방지 엔진에 추가되어 다른 장치와 사용자도 보호됩니다.  

악의적인 파일 제거를 여는 등 사용자가 취해야 하는 작업이 있는 경우 알림에 표시됩니다. Microsoft Defender 바이러스 백신이 사용자 대신 수행하거나 사용자가 취해야 할 수 있는 작업에 대한 자세한 내용은 보호 기록을 [참조합니다.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) IT 전문가/관리자로 위협 감지를 관리하는 방법을 알아보는 방법에 대한 자세한 내용은 검색된 위협을 검토하고 조치를 [취하세요.](review-threats-take-action.md)

다양한 위협에 대한 자세한 내용은 다음 작업을 수행할 수 있는 <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft 보안</a>인텔리전스 위협 사이트를 방문하세요. 

- 상위 위협에 대한 현재 정보를 볼 수 있습니다.
- 특정 지역에 대한 최신 위협을 볼 수 있습니다.
- 위협 백과사전에서 특정 위협에 대한 세부 정보를 검색합니다.

## <a name="related-content"></a>관련 콘텐츠

[Windows 10 장치](secure-windows-10-devices.md) 보안(문서)\
[Microsoft Defender 바이러스 백신](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) 평가(문서)\
[실시간 및](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) 클라우드 제공 바이러스 백신 보호를 켜는 방법(문서)\
[Windows 보안 앱에서 Microsoft Defender 바이러스](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) 백신을 켜고 사용하는 방법(문서)\
[그룹 정책을 사용하여 Microsoft Defender 바이러스](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) 백신을 켜는 방법(문서)\
[바이러스 백신 정의를 업데이트하는](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) 방법(문서)\
분석을 위해 맬웨어 및 맬웨어가 아닌 [맬웨어를 Microsoft에 제출하는](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) 방법(문서)