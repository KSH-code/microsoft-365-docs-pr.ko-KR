---
title: 배포, 관리 및 Microsoft Defender 바이러스 백신
description: Intune, Microsoft Defender 바이러스 백신, 그룹 정책, PowerShell 또는 WMI를 Microsoft Endpoint Configuration Manager 배포하고 관리할 수 있습니다.
keywords: 배포, 관리, 업데이트, 보호, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 9a71a641940be6b3acd3fbf6070ec907299c15ba
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209980"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>배포, 관리 및 Microsoft Defender 바이러스 백신

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

여러 가지 방법으로 배포, 관리 Microsoft Defender 바이러스 백신 보고할 수 있습니다.

Microsoft Defender 바이러스 백신 클라이언트는 클라이언트의 핵심 부분으로 Windows 10 끝점에 대한 기존 배포는 적용되지 않습니다.

그러나 대부분의 경우 끝점에서 다음 표에 설명된 Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender 또는 그룹 정책 개체를 사용하여 끝점에서 보호 서비스를 사용하도록 설정해야 합니다.

다음에 대한 추가 링크도 있습니다.

- 제품 및 Microsoft Defender 바이러스 백신 업데이트를 포함하여 보안 보호 관리
- 보안 보호에 Microsoft Defender 바이러스 백신 보고

> [!IMPORTANT]
> 대부분의 경우 Windows 10 실행되고 Microsoft Defender 바이러스 백신 바이러스 백신 제품이 발견되는 경우 이 기능을 사용하지 않도록 설정됩니다. 타사 바이러스 백신 제품을 사용하지 않도록 설정하거나 제거해야 Microsoft Defender 바이러스 백신 합니다. 타사 바이러스 백신 제품을 다시 사용하도록 설정하거나 설치하는 경우 자동으로 Windows 10 사용하지 않도록 Microsoft Defender 바이러스 백신.

도구|배포 옵션(<a href="#fn2" id="ref2">2</a>)|관리 옵션(네트워크 전체 구성 및 정책 또는 기준 배포)([3](#fn3))|보고 옵션
---|---|---|---
Microsoft Intune|[Intune에서 끝점 보호 설정 추가](/intune/endpoint-protection-configure)|[Intune에서 장치 제한 설정 구성](/intune/device-restrictions-configure)| [Intune 콘솔을 사용하여 장치 관리](/intune/device-management)
Microsoft Endpoint Manager ([1)](#fn1)|[Endpoint Protection 지점 사이트 시스템 역할][] 및 [사용자 지정 클라이언트 설정으로 Endpoint Protection 사용][]|[기본 및 사용자 지정 맬웨어 방지 정책][] 및 [클라이언트 관리][]|기본 [Configuration Manager 모니터링 작업 영역][] 및 [전자 메일 알림][]
그룹 정책 및 Active Directory(도메인 가입)|그룹 정책 개체를 사용하여 구성 변경 내용을 배포하고 구성 Microsoft Defender 바이러스 백신 확인합니다.|GOS(그룹 정책 개체)를 사용하여 [Microsoft Defender 바이러스 백신에 대한 업데이트 옵션 구성][ 및 [Windows Defender 기능 구성][]|그룹 정책에서는 끝점 보고를 사용할 수 없습니다. [그룹 정책 목록을 생성하여 설정 또는 정책이 적용되지 않는지 확인][]
PowerShell|그룹 정책으로 배포하거나 Microsoft Endpoint Configuration Manager 끝점에서 수동으로 배포합니다.|Defender 모듈에서 사용할 수 있는 [Set-MpPreference] 및 [Update-MpSignature] cmdlet을 사용합니다.|적절한 [Defender 모듈에서 사용 가능한 Get- cmdlet][]
Windows Management Instrumentation|그룹 정책으로 배포하거나 Microsoft Endpoint Configuration Manager 끝점에서 수동으로 배포합니다.|[MSFT_MpPreference 클래스의 Set 메서드][] 및 [MSFT_MpSignature 클래스의 Update 메서드][]|[MSFT_MpComputerStatus][] 클래스 및 [Windows Defender WMIv2 Provider][]에서 관련 클래스의 get 메서드를 사용합니다.
Microsoft Azure|가상 Microsoft Antimalware 구성 또는 Visual Studio [cmdlet을](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios)사용하여 Azure 포털에서 Azure용 Azure PowerShell 배포합니다. [Azure Defender*에서 끝점 보호를 설치할 수 있습니다.](/azure/security-center/security-center-install-endpoint-protection)|가상 [Microsoft Antimalware cmdlet을](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) 사용하여 가상 컴퓨터 및 클라우드 서비스에 대한 Azure PowerShell 구성하거나 코드 [샘플 사용](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|가상 Microsoft Antimalware 및 클라우드 서비스에 대한 Azure PowerShell [cmdlet을](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) 사용하여 모니터링을 사용하도록 설정할 수 있습니다. 또한 Azure Active Directory 사용 현황 보고서를 검토하여 [감염된 장치][] 보고서를 포함한 의심스러운 활동을 파악하고 [Microsoft Defender 바이러스 백신 이벤트][]에 대해 보고하도록 SIEM 도구를 구성하고 해당 도구를 AAD의 앱으로 추가할 수 있습니다.

1. <span id="fn1" />클라우드 제공 보호와 관련된 일부 기능의 가용성은 Microsoft Endpoint Manager(현재 분기)와 2012 Configuration Manager의 System Center 다릅니다. 이 라이브러리에서는 Windows 10, Windows Server 2016 및 Microsoft Endpoint Manager(현재 분기)에 초점을 맞추고 있습니다. 주요 [차이점을](cloud-protection-microsoft-defender-antivirus.md) 설명하는 표는 Microsoft Defender 바이러스 백신 Microsoft 클라우드 제공 보호 사용을 참조합니다. [(테이블로 돌아가기)](#ref2)

2. <span id="fn2" />이 Windows 10 Microsoft Defender 바이러스 백신 추가 클라이언트 또는 서비스를 설치하거나 배포하지 않고도 사용할 수 있는 구성 요소입니다. 타사 바이러스 백신 제품이 제거되거나 더 이상 사용되지 않는 경우 자동으로 활성화됩니다(타사 바이러스 백신[Windows Server 2016).](microsoft-defender-antivirus-on-windows-server.md) 따라서 기존 배포는 필요하지 않습니다. 여기서 배포란 끝점 또는 서버에서 Microsoft Defender 바이러스 백신 구성 요소를 사용할 수 있도록 하는 것을 참조합니다. [(테이블로 돌아가기)](#ref2)

3. <span id="fn3" />제품 및 보호 업데이트 구성을 비롯한 기능 및 보호 구성은 이 라이브러리의 Microsoft Defender 바이러스 백신 [기능](configure-notifications-microsoft-defender-antivirus.md) 구성 섹션에 설명되어 있습니다. [(테이블로 돌아가기)](#ref2)

## <a name="in-this-section"></a>이 섹션의 내용

항목 | 설명
---|---
[보호 기능 Microsoft Defender 바이러스 백신 배포 및 사용](deploy-microsoft-defender-antivirus.md) | 클라이언트가 Windows 10 핵심 부분으로 설치되어 있으며 기존 배포가 적용되지 않는 경우 끝점에서 클라이언트를 Microsoft Endpoint Configuration Manager, Microsoft Intune 또는 그룹 정책 개체를 사용하도록 설정해야 합니다.
[업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md) | 끝점에서 클라이언트를 업데이트하는 Microsoft Defender 바이러스 백신(제품 업데이트) 및 보안 인텔리전스 업데이트(보호 업데이트)의 두 부분으로 구성됩니다. 그룹 정책, PowerShell 및 WMI를 사용하여 다양한 방법으로 보안 인텔리전스를 Microsoft Endpoint Configuration Manager 수 있습니다.
[보호 기능 모니터링 및 Microsoft Defender 바이러스 백신 보고](report-monitor-microsoft-defender-antivirus.md) | Microsoft Intune, Microsoft Endpoint Configuration Manager, Microsoft Operations Management Suite용 업데이트 준수 추가 기능 또는 타사 SIEM 제품(Windows 이벤트 로그 사용)을 사용하여 보호 상태를 모니터링하고 끝점 보호에 대한 보고서를 만들 수 있습니다.