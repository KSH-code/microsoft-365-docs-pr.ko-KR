---
title: Windows 10 엔터프라이즈 보안 기능을 배포 합니다.
description: Microsoft 365 Enterprise의 일부로 Pc에서 Windows 10 엔터프라이즈 배포에 필요한 단계에 대 한 고급 지침을 제공 합니다.
keywords: Microsoft 365, Microsoft 365 Enterprise Microsoft 365 설명서, Windows 10 엔터프라이즈 보안
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: greglin
ms.openlocfilehash: d051f9e56d8e9986fbe0975c2bdc6c606b32a444
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870359"
---
# <a name="step-5-deploy-windows-10-enterprise-security-features"></a>5 단계: Windows 10 엔터프라이즈 보안 기능 배포

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Windows 10 위협 으로부터, 도움말 장치로, 보안 및 액세스 제어를 도와줄를 보호 하는 기능을 제공 합니다. 

이러한 기술에 대 한 자세한 내용은 참조 합니다.
* [액세스 보호](https://docs.microsoft.com/windows/access-protection/) -액세스 제어, S/MIME 디지털 인증서의 경우 자격 증명 Guard 사용자 계정 컨트롤에 대 한 설명 가상 스마트 카드, Windows Hello 비즈니스, 고급 보안이 포함 된 Windows 방화벽 등에 대 한
* [장치 보안](https://docs.microsoft.com/windows/device-security/) -AppLocker 포함, BitLocker, 장치 Guard 및 신뢰할 수 있는 플랫폼 모듈
* [위협 보호](https://docs.microsoft.com/windows/threat-protection/) -Windows Defender 보안 센터를 포함, Windows Defender 고급 위협 보호, Windows Defender 바이러스 백신 소프트웨어, Windows Defender 응용 프로그램 Guard, Windows Defender 스마트 화면 및 Windows 정보 보호

이 단계에는 배포, 관리, 구성 하는 방법 이러한 보안 기능을 사용 하 여 문제를 해결 보여줍니다.

* [Windows Defender Antivirus](#windows-defender-antivirus)
* [Windows Defender Exploit Guard](#windows-defender-exploit-guard)
* [Windows Defender Advanced Threat Protection](#windows-defender-advanced-threat-protection)

<a name="windows10-sec-av"></a>
## <a name="windows-defender-antivirus"></a>Windows Defender Antivirus
Windows Defender 바이러스 백신 소프트웨어 (AV)는 Windows 10에 기본적으로 제공 되는 맬웨어 방지 솔루션입니다. 데스크톱과 휴대용 컴퓨터 서버에 대 한 보안 및 맬웨어 방지 관리를 제공합니다. Windows Defender AV, 최소 요구 사항 및이 기능을 관리 하는 방법에 대 한 자세한 정보에 대 한 [Windows 10 및 Windows Server 2016 Windows Defender 바이러스 백신 소프트웨어](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)를 참조 하십시오.

같은 몇가지 사항을 Windows Defender ATP를 사용 하는 경우 또는 클라이언트로 기본 바이러스 백신, Windows Defender AV를 사용 하지 않는 경우 고려해 해야 합니다. 자세한 내용은 [Windows Defender AV 호환성](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/windows-defender-antivirus-compatibility)을 참조 합니다.

### <a name="deployment-and-management"></a>배포 및 관리
배포 하 고 Windows Defender AV를 관리 하려면 여기 지침을 따르십시오.

* [배포, 관리 및 Windows Defender AV에 대해 보고](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [관리 및 구성 도구에 대 한 참조 항목](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

### <a name="configuration"></a>구성
사용자는 다양 한 기능을 구성할 수 있습니다. 자세한 정보에 대 한 다음이 리소스를 참조 합니다.

* [Windows Defender AV 기능 구성](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)
* [관리 및 구성 도구에 대 한 참조 항목](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/configuration-management-reference-windows-defender-antivirus)

구성 옵션을 이해 하는데를 참조 하십시오 모든 설정의이 목록 (해당 그룹 정책 구성에 의해 정의 됨): [그룹 정책을 사용 하 여 설정을 구성 하 고 Windows Defender AV 관리](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/use-group-policy-windows-defender-antivirus)

보호 수준 및 Windows Defender AV의 네트워크에 영향을 평가할 수 있도록 [Windows Defender AV 보호 평가 가이드를](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/evaluate-windows-defender-antivirus) 사용할 수 있습니다. 초기 구성 만들기 (영문)에서 또는 '빠른 시작 가이드'으로 유용 하 고 정기적으로 업데이트를 구성 하 고 최대 보호를 확인 하는 기능을 사용 하는 가장 유용한 권장 사항을 제공 하는 합니다.

### <a name="reporting"></a>보고
예: System Center Configuration Manager 또는 Microsoft Intune 구성 도구를 사용 하 여 보고를 받을 수 있습니다. 업데이트 준수 (OM)에서 또는 프로그램 SIEM에서 Windows 이벤트 로그를 사용 하 여 보고 얻을 수 있습니다. Windows Defender ATP에 대 한 라이선스가 하는 경우 Windows Defender AV 감지에 보고 기능을 얻을 수 및 기본 복구를 수행 해야 합니다. 자세한 정보에 대 한 다음이 리소스를 참조 합니다.
* [배포, 관리 및 Windows Defender AV에 대해 보고](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/deploy-manage-report-windows-defender-antivirus)
* [Windows Defender AV 보호 기능에 대해 보고](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/report-monitor-windows-defender-antivirus)
* [Windows Defender ATP 포털 개요 (영문)](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>문제 해결
오류 및 이벤트 코드의 기본적인 문제를 해결 하는 정보에 대 한 [이벤트 로그를 검토 하 고 Windows Defender AV 관련 문제를 해결 하는 오류 코드를](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/troubleshoot-windows-defender-antivirus)참조 하십시오.

또한 Windows Defender 보안 인텔리전스 전송 시스템을 사용 하 여 문제 (예: 가양성)을 제출할 수 있습니다. 자세한 방법, [Microsoft로 전송 문제](https://www.microsoft.com/wdsi/filesubmission)를 참조 하십시오.

<a name="windows10-sec-eg"></a>
## <a name="windows-defender-exploit-guard"></a>Windows Defender Exploit Guard
Windows Defender 악용 Guard 새 집합인 Windows 10에 대 한 호스트 침입 방지 기능입니다. Windows Defender 악용 Guard, 최소 요구 사항 및이 기능을 관리 하는 방법에 대 한 자세한 정보에 대 한 [Windows Defender 악용 Guard](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)를 참조 합니다.

### <a name="deployment-management-and-configuration"></a>배포, 관리 및 구성
배포, 관리 및 Windows Defender 악용 Guard 구성, 하려면 다음 지침을 따르십시오.
* [이 악용 보호](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/exploit-protection-exploit-guard)
* [공격 노출 보호](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard?ocid=cx-docs-msa4053440)
* [네트워크 보호](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
* [폴더 액세스를 제어합니다.](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)

보호 수준 및 Windows Defender 악용 Guard의 네트워크에 영향을 평가할 수 있도록 일련의 평가 항목을 사용할 수 있습니다. 이 유용할 수 있습니다는 초기 구성 만들기 (영문)에서 또는 '빠른 시작 가이드'으로 및 지침 및 항목을 구성 하 고 최대 보호를 확인 하는 기능을 사용 하는 가장 유용한 권장 사항을 제공을 정기적으로 업데이트 합니다. 자세한 내용을 보려면 [Windows Defender 악용 Guard 평가](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/evaluate-windows-defender-exploit-guard)합니다.

### <a name="reporting"></a>보고
예: System Center Configuration Manager 또는 Intune 구성 도구를 사용 하 여 보고를 받을 수 있습니다. 프로그램 SIEM에서 Windows 이벤트 로그를 사용 하 여 보고 얻을 수 있습니다. Windows Defender ATP에 대 한 라이선스가 하는 경우 Windows Defender AV 감지에 보고 기능을 얻을 수 및 기본 복구를 수행 해야 합니다. 자세한 정보에 대 한 다음이 리소스를 참조 합니다.
* [Windows Defender 악용 Guard 이벤트 보기](https://docs.microsoft.com/windows/threat-protection/windows-defender-exploit-guard/event-views-exploit-guard)
* [Windows Defender ATP 포털 개요 (영문)](https://go.microsoft.com/fwlink/?linkid=861596)

### <a name="troubleshooting"></a>문제 해결
하면 및 수행할 수 있습니다 기본적인 문제해결 또는 필요에 따라 Microsoft.cab 파일에 제공 Windows Defender 보안 인텔리전스 전송 시스템을 사용 하 여 문제 (예: 가양성)를 전송 합니다. 자세한 방법, [Microsoft로 전송 문제](https://www.microsoft.com/wdsi/filesubmission)를 참조 하십시오.


<a name="windows10-sec-atp"></a>
## <a name="windows-defender-advanced-threat-protection"></a>Windows Defender Advanced Threat Protection
Windows Defender ATP, Microsoft 365 Enterprise E5 플랜과 에서만 사용할 수는 엔터프라이즈 고객 감지, 조사, 및가 네트워크에서 고급 위협에 응답할 수 있도록 하는 보안 서비스입니다. Windows Defender ATP, 최소 요구 사항 및이 기능을 관리 하는 방법에 대 한 자세한 정보를 참조 하십시오.

* [Windows Defender ATP](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
* [최소 요구 사항](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/minimum-requirements-windows-defender-advanced-threat-protection)

### <a name="deployment-management-and-configuration"></a>배포, 관리 및 구성
Windows Defender ATP를 배포 하려면 Windows 라이선스 오른쪽 했는지 확인 해야 합니다. 오른쪽 라이선스 있는지를 확인 한 후 데이터를 저장 하는 위치에 대 한 지리적 위치를 결정 하려면 필요 합니다. 그런 다음 서비스에 온 보 딩 끝점을 시작할 수 있습니다.

다음이 단계에 대 한 자세한 내용은 다음 주요 항목을 참조 합니다. 

* [라이선스 구축의 유효성을 검사 하 고 설정을 완료합니다](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/licensing-windows-defender-advanced-threat-protection)
* [데이터 저장소 및 정보 공개](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/data-storage-privacy-windows-defender-advanced-threat-protection)
* [온보드 끝점 및 설치 액세스](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/onboard-configure-windows-defender-advanced-threat-protection)

### <a name="detect-investigate-respond"></a>검색, 조사, 응답
성공적으로 온 보 딩 끝점 서비스 후 다양 한 대시보드에서 경고를 조사를 시작할 수 있습니다. 경고를 조사 했을 때, 되 면 알림 응답 작업을 수행할 수 있습니다. 

다음을 수행 하는 방법에 자세한 정보를 참조 합니다.
* [Windows Defender ATP 포털 개요 (영문)](https://go.microsoft.com/fwlink/?linkid=861596)
* [Windows Defender ATP 포털을 사용 하 여](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-windows-defender-advanced-threat-protection)
* [다음 응답 작업 수행](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/response-actions-windows-defender-advanced-threat-protection)

### <a name="integrate-with-other-products-and-tools"></a>기타 제품 및 도구와 통합
Windows Defender ATP을 통합 하 고 다양 한 기타 제품 및 해당 보안 기능을 확장 하는 도구를 지원 합니다. 

도구 및 기타 제품에서 자세한 정보를 참조 합니다.
* [SIEM 도구](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/configure-siem-windows-defender-advanced-threat-protection)
* [사용자 지정 알림 만들기](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/use-custom-ti-windows-defender-advanced-threat-protection)
* [Api를 사용 하 여](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/exposed-apis-windows-defender-advanced-threat-protection)
* [Power BI 보고서 작성](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/powerbi-reports-windows-defender-advanced-threat-protection)

### <a name="troubleshooting"></a>문제 해결
온 보 딩 하는 동안 또는 제품을 사용 하는 동안 문제가 발생할 수 있습니다. 문제를 해결 하는 방법에 자세한 정보를 참조 하십시오.
* [온 보 딩 문제를 해결](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-onboarding-windows-defender-advanced-threat-protection)
* [Windows Defender ATP 문제해결](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/troubleshoot-windows-defender-advanced-threat-protection)

## <a name="next-step"></a>다음 단계

[Windows 10 엔터프라이즈 인프라 종료 기준](windows10-exit-criteria.md)
