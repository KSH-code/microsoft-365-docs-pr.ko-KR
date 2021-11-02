---
title: 새 버전의 Microsoft Defender for Endpoint에 대한 서버 마이그레이션 시나리오
description: 이 문서를 읽고 이전의 MMA 기반 솔루션에서 Endpoint 통합 솔루션 패키지용 현재 Defender로 서버를 마이그레이션하는 방법을 간략하게 살펴 보십시오.
keywords: 서버, 서버, 2012r2, 2016, 서버 마이그레이션, 장치 관리, 끝점 서버용 Microsoft Defender 구성, 끝점 서버용 Microsoft Defender 온보딩
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 10932b96b205e3e73ba6e5363ed2acd301d9cef5
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60643222"
---
# <a name="server-migration-scenarios-from-the-previous-mma-based-microsoft-defender-for-endpoint-solution"></a>이전의 MMA 기반 Microsoft Defender for Endpoint 솔루션의 서버 마이그레이션 시나리오

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- Windows Server 2012 R2
- Windows Server 2016

[!include[Prerelease information](../../includes/prerelease.md)]

> [!NOTE]
> 설치 또는 Microsoft Defender 바이러스 백신 진행하기 전에 항상 Windows Server 2016 업데이트해야 합니다. EDR 센서 구성 요소에 대한 정기적인 제품 개선 및 수정을 받으 Windows [업데이트 KB5005292가](https://go.microsoft.com/fwlink/?linkid=2168277) 적용되거나 승인되도록 합니다. 또한 보호 구성 요소를 업데이트된 유지 관리하기 위해 관리 Microsoft Defender 바이러스 백신 [기준을 적용하세요.](/microsoft-365/security/defender-endpoint/manage-updates-baselines-microsoft-defender-antivirus#monthly-platform-and-engine-versions)

이러한 지침은 R2 및 2013용 Microsoft Defender for Endpoint의 새로운 통합 솔루션 및 설치 관리자 Windows Server 2012 Windows Server 2016. 이 문서에는 이전 솔루션에서 현재 솔루션으로의 다양한 가능한 마이그레이션 시나리오에 대한 높은 수준의 지침이 포함되어 있습니다. 이러한 고급 단계는 사용자 환경에서 사용할 수 있는 배포 및 구성 도구에 맞게 조정하기 위한 지침입니다.

> [!NOTE]
> 끝점용 Microsoft Defender가 설치된 운영 체제 업그레이드는 지원되지 않습니다. 업그레이드를 진행하기 전에 먼저 오프보드를 제거하십시오.

> [!NOTE]
> 미리 보기 Microsoft Endpoint Configuration Manager 자동화 및 통합을 통해 자동화된 업그레이드를 수행하는 전체 기능을 MECM의 2111 릴리스에서 사용할 수 있습니다. 2107 릴리스부터 그룹 정책, PowerShell, Endpoint Protection 테넌트 연결 또는 로컬 구성뿐만 아니라 구성에 Microsoft Endpoint Manager 노드를 사용할 수 있습니다. 또한 기존 기능을 사용하여 수동 업그레이드 Microsoft Endpoint Configuration Manager 수 있습니다. 메서드를 참조하세요.

## <a name="installer-script"></a>설치 관리자 스크립트

업그레이드를 수행하지 Microsoft Endpoint Configuration Manager 또는 아직 업그레이드를 수행할 수 없는 경우 업그레이드를 용이하게 하기 위해 이 업그레이드 스크립트 를 [사용할 수 있습니다.](https://github.com/microsoft/mdefordownlevelserver) 다음과 같은 필수 단계를 자동화하는 데 도움이 될 수 있습니다.

1. 끝점용 Microsoft Defender의 OMS 작업 영역(OPTIONAL)을 제거합니다.
2. 설치된 System Center Endpoint Protection 클라이언트를 제거합니다.
3. 필요한 경우 R2(Windows Server 2012)를 다운로드하여 설치합니다. [](configure-server-endpoints.md#prerequisites)
4. 끝점용 Microsoft Defender를 설치합니다.
5. 에서 다운로드한  그룹 정책에 사용할 온보딩 스크립트를 [Microsoft Defender 보안 센터.](https://securitycenter.microsoft.com)

스크립트를 사용하려면 설치 및 온보딩 패키지도 배치한 설치 디렉터리에 다운로드합니다(서버 끝점 [구성 참조).](configure-server-endpoints.md)

예: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd"

## <a name="microsoft-endpoint-configuration-manager-migration-scenarios"></a>Microsoft Endpoint Configuration Manager 마이그레이션 시나리오 

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-including-system-center-endpoint-protection-scep-and-are-running-the-microsoft-monitoring-agent-mma-based-sensor-you-want-to-upgrade-to-the-microsoft-defender-for-endpoint-unified-solution-preview"></a>현재 Microsoft Endpoint Configuration Manager SCEP(System Center Endpoint Protection)를 포함하여 서버를 관리하고 MMA(Microsoft Monitoring Agent) 기반 센서를 실행하고 있습니다. 끝점 통합 솔루션 미리 보기용 Microsoft Defender로 업그레이드하려는 **경우**

>[!NOTE]
>버전 Microsoft Endpoint Configuration Manager 2107이 필요합니다.


마이그레이션 단계: 

1. 컴퓨터(Microsoft Defender 바이러스 백신)를 포함하여 Windows Server 2016.
2. 마이그레이션할 컴퓨터를 포함하기 위한 멤버 자격 규칙이 포함된 새 컬렉션을 만들 수 있습니다.
3. [응용 프로그램을 만들어](/mem/configmgr/apps/deploy-use/create-applications) 다음 작업을 수행합니다. 
   1. 끝점용 Microsoft Defender에 대한 MMA 작업 영역 구성을 제거합니다. [PowerShell을 사용하여 작업 영역 제거를 참조합니다.](/azure/azure-monitor/agents/agent-manage) 이 단계는 선택 사항입니다. 이전 EDR 센서가 활성화된 후 실행이 중지됩니다(몇 시간이 걸릴 수 있습니다).
   2. SCEP를 제거합니다.
   3. 해당되는 경우 [선행](configure-server-endpoints.md#prerequisites) 요구를 설치합니다.
   4. 끝점용 Microsoft Defender를 설치합니다(서버 [끝점 구성 참조).](configure-server-endpoints.md)
   5. 에서 다운로드한  그룹 정책에 사용할 온보딩 스크립트를 [Microsoft Defender 보안 센터.](https://securitycenter.microsoft.com) 

   > [!TIP]
   > 설치 관리자 [스크립트를](server-migration.md#installer-script) 응용 프로그램의 일부로 사용하여 위의 단계를 자동화할 수 있습니다.
4. 응용 프로그램을 새 컬렉션에 배포합니다.
5. 컬렉션에 기존 정책을 Endpoint Protection 및/또는 할당합니다.
6. 업데이트를 적용합니다.

### <a name="you-are-currently-using-microsoft-endpoint-configuration-manager-to-manage-your-servers-are-running-a-non-microsoft-antivirus-solution-and-the-mma-based-sensor-you-want-to-upgrade-to-the-new-microsoft-defender-for-endpoint"></a>현재 서버를 관리하기 위해 Microsoft Endpoint Configuration Manager Microsoft가 아닌 바이러스 백신 솔루션 및 MMA 기반 센서를 실행하고 있습니다. 새 끝점용 Microsoft Defender로 업그레이드하려는 경우

마이그레이션 단계:

1. 컴퓨터(Microsoft Defender 바이러스 백신)를 포함하여 Windows Server 2016.
2. 마이그레이션할 컴퓨터를 포함하기 위한 멤버 자격 규칙이 포함된 새 컬렉션을 만들 수 있습니다. 
3. 타사 바이러스 백신 관리가 더 이상 이러한 컴퓨터로 바이러스 백신을 푸시하지 않도록 합니다.*
4. MECM의 Endpoint Protection 노드에서 정책을 작성하고 새로 만든 컬렉션을 대상으로 합니다.*
5. 응용 프로그램을 만들어 다음 작업을 수행합니다.
   1. 끝점용 Microsoft Defender에 대한 MMA 작업 영역 구성을 제거합니다. [PowerShell을 사용하여 작업 영역 제거를 참조합니다.](/azure/azure-monitor/agents/agent-manage) 이 단계는 선택 사항입니다. 이전 EDR 센서가 활성화된 후 실행이 중지됩니다(몇 시간이 걸릴 수 있습니다).
   2. 해당되는 경우 [선행](configure-server-endpoints.md#prerequisites) 요구를 설치합니다.
   3. Windows Server 2012 R2 및 2016 패키지에 대한 Microsoft Defender for Endpoint를 설치하고 수동 모드를 **사용하도록 설정하십시오.** [명령줄을 Microsoft Defender 바이러스 백신 설치를 참조합니다.](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line)
   4. 에서 다운로드한  그룹 정책에 사용할 온보딩 스크립트를 [Microsoft Defender 보안 센터.](https://securitycenter.microsoft.com)
6. 업데이트를 적용합니다.
7. Microsoft가 아닌 바이러스 백신 콘솔을 사용하여 Microsoft가 아닌 다른 바이러스 백신 소프트웨어를 제거하거나 적절하게 Microsoft Endpoint Configuration Manager 제거합니다. 수동 모드 구성을 제거해야 합니다.*

팁: 설치 관리자 [](server-migration.md#installer script) 스크립트를 응용 프로그램의 일부로 사용하여 위의 단계를 자동화할 수 있습니다. 수동 모드를 사용하도록 설정하려면 -Passive 플래그를 적용합니다. 예: .\install.ps1 -RemoveMMA <YOUR_WORKSPACE_ID> -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive

*이러한 단계는 Microsoft가 아닌 바이러스 백신 솔루션을 교체하려는 경우만 적용됩니다. 함께 더 나은 보기: Microsoft Defender 바이러스 백신 [및 끝점용 Microsoft Defender를 참조합니다.](why-use-microsoft-defender-antivirus.md)


수동 모드에서 컴퓨터 이동을 위해 다음 키를 0으로 설정하십시오. 

경로: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection 이름: ForceDefenderPassiveMode 형식: REG_DWORD 값: 0

자세한 내용은 수동 [모드로 Microsoft Defender 바이러스 백신 필요를 참조하세요.](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server)


## <a name="other-migration-scenarios"></a>기타 마이그레이션 시나리오 

### <a name="you-have-a-server-that-has-been-onboarded-using-the-mma-based-microsoft-defender-for-endpoint-it-has-scep-installed-windows-server-2012-r2-or-microsoft-defender-antivirus-windows-server-2016-this-machine-is-not-managed-through-azure-defender-microsoft-endpoint-manager-or-microsoft-endpoint-configuration-manager"></a>MMA 기반의 끝점용 Microsoft Defender를 사용하여 온보딩된 서버가 있습니다. SCEP가 설치되어 있습니다(Windows Server 2012 R2) 또는 Microsoft Defender 바이러스 백신(Windows Server 2016). 이 **컴퓨터는** Azure Defender, Microsoft Endpoint Manager 또는 Microsoft Endpoint Configuration Manager.

1. 컴퓨터(Microsoft Defender 바이러스 백신)를 포함하여 Windows Server 2016.
2. 끝점용 Microsoft Defender에 대한 MMA 작업 영역 구성을 제거합니다. [PowerShell을 사용하여 작업 영역 제거를 참조합니다.](/azure/azure-monitor/agents/agent-manage)
3. R2에서 System Center Endpoint Protection(Windows Server 2012) 제거합니다.
4. 해당되는 경우 [선행](configure-server-endpoints.md#prerequisites) 요구를 설치합니다. 
5. 끝점용 Microsoft Defender [설치(서버 끝점 구성 참조)](configure-server-endpoints.md)
6. 에서 다운로드한  그룹 정책에 사용할 온보딩 스크립트를 [Microsoft Defender 보안 센터.](https://securitycenter.microsoft.com) 
7. 업데이트를 적용합니다.
8. 그룹 정책, PowerShell 또는 제3자 관리 솔루션을 사용하여 정책을 만들고 적용합니다.

> [!TIP]
> 설치 관리자 스크립트를 사용하여 위의 단계를 자동화할 수 있습니다.

### <a name="you-have-a-server-on-which-you-want-to-install-microsoft-defender-for-endpoint-it-has-a-non-microsoft-endpoint-protection-or-endpoint-detection-and-response-solution-installed-you-do-not-intend-to-use-microsoft-endpoint-configuration-manager-or-azure-defender-you-use-your-own-deployment-mechanism"></a>끝점용 Microsoft Defender를 설치할 서버가 있습니다. Microsoft가 아닌 끝점 보호 또는 끝점 감지 및 응답 솔루션이 설치되어 있습니다. Azure Defender 또는 azure Defender를 Microsoft Endpoint Configuration Manager 않습니다. 자체 배포 메커니즘을 사용하게 됩니다. 

1. 컴퓨터(Microsoft Defender 바이러스 백신)를 포함하여 Windows Server 2016.
2. Windows Server 2012 R2 & 2016 패키지에 대한 Microsoft Defender for Endpoint를 설치하고 수동 모드를 **사용하도록 설정하십시오.** [명령줄을 Microsoft Defender 바이러스 백신 설치를 참조합니다.](configure-server-endpoints.md#install-microsoft-defender-for-endpoint-using-command-line)
3. 에서 다운로드한 환경에 적합한 온보딩 스크립트를 [Microsoft Defender 보안 센터.](https://securitycenter.microsoft.com) 
4. 비 Microsoft 끝점 보호 또는 끝점 감지 및 응답 솔루션을 제거하고 수동 모드를 제거합니다.*
5. 업데이트를 적용합니다.
6. 그룹 정책, PowerShell 또는 제3자 관리 솔루션을 사용하여 정책을 만들고 적용합니다.

> [!TIP]
> 설치 관리자 [스크립트를 사용하여](server-migration.md#installer-script) 1~4단계를 자동화할 수 있습니다. 수동 모드를 사용하도록 설정하려면 온보딩하기 전에 Defender 바이러스 백신이 수동 모드로 전환되어 Microsoft가 아닌 맬웨어 방지 솔루션을 방해하지 않는 -Passive 플래그를 적용합니다. 그런 다음 등록 후 Defender 바이러스 백신이 수동 모드로 유지되도록 EDR 차단과 같은 EDR "ForceDefenderPassiveMode" 레지스트리 키를 설정해야 합니다. 예제: 자세한 내용은 수동 모드로 Microsoft Defender 바이러스 백신 `.\install.ps1 -OnboardingScript ".\WindowsDefenderATPOnboardingScript.cmd" -Passive` [필요를 참조하세요.](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server)

*이 단계는 Microsoft가 아닌 바이러스 백신 솔루션을 교체하려는 경우만 적용됩니다. 전체 기능 집합을 Microsoft Defender 바이러스 백신 Microsoft Defender for Endpoint에 포함된 웹 서비스를 사용하는 것이 좋습니다. 함께 더 나은 보기: Microsoft Defender 바이러스 백신 [및 끝점용 Microsoft Defender를 참조합니다.](why-use-microsoft-defender-antivirus.md) 


수동 모드에서 컴퓨터 이동을 위해 다음 키를 0으로 설정하십시오. 

경로: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection 이름: ForceDefenderPassiveMode 형식: REG_DWORD 값: 0

자세한 내용은 수동 [모드로 Microsoft Defender 바이러스 백신 필요를 참조하세요.](microsoft-defender-antivirus-on-windows-server.md#passive-mode-and-windows-server)

## <a name="azure-defender-scenarios"></a>Azure Defender 시나리오

### <a name="youre-using-azure-defender-the-microsoft-monitoring-agent-mma-andor-microsoft-antimalware-for-azure-scep-are-installed-and-you-want-to-upgrade"></a>Azure Defender를 사용하고 있습니다. MMA(Microsoft Monitoring Agent) 및/또는 AZURE용 Microsoft Antimalware(SCEP)가 설치되어 업그레이드하려는 경우
Azure Defender를 사용하는 경우 자동화된 업그레이드 프로세스를 활용할 수 있습니다. 보안 센터의 통합된 통합 EDR 끝점 [보호: 끝점용 Microsoft Defender를 참조합니다.](/azure/security-center/security-center-wdatp#enable-the-microsoft-defender-for-endpoint-integration)

## <a name="group-policy-configuration"></a>그룹 정책 구성
그룹 정책을 사용하는 구성의 경우 중앙 저장소에서 최신 ADMX 파일을 사용하여 올바른 끝점용 Defender 정책 옵션에 액세스하는지 확인합니다. 에서 [그룹](/troubleshoot/windows-client/group-policy/create-and-manage-central-store) 정책 관리 템플릿에 대한 중앙 저장소를 만들고 관리하는 방법을 참조하고 Windows 에서 사용할 최신 파일을 **Windows 10.**
