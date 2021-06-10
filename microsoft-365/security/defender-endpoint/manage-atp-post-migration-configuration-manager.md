---
title: Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리
description: Configuration Manager를 사용하여 끝점용 Microsoft Defender를 관리하는 방법 학습
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, Configuration Manager, 끝점용 Microsoft Defender, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 71ad8f52fd9347abdf0146969bb84a19d8883262
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843067"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


장치에 대한 조직의 [](/mem)위협 방지 기능(끝점이라고도 하는 Microsoft Endpoint Manager)을 [](/mem/configmgr/core/understand/introduction) 관리하려면 Microsoft Intune(Intune) 및 Microsoft Endpoint Configuration Manager(Configuration Manager)가 포함된 Microsoft Endpoint Manager 를 사용하는 것이 좋습니다. [](/mem/intune/fundamentals/what-is-intune) 
- [자세한 내용은 Endpoint Manager](/mem/endpoint-manager-overview)
- [Configuration Manager 및 Intune을 사용하여 Windows 10 디바이스에서 끝점용 Microsoft Defender 공동 관리](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager를 통해 끝점용 Microsoft Defender 구성

|작업  |자세한 정보를 알아볼 수 있는 리소스  |
|---------|---------|
|**Configuration Manager 콘솔이** 없는 경우 설치<br/><br/>*Configuration Manger 콘솔이 아직 없는 경우 이러한 리소스를 사용하여 비트를 다운로드하고 설치합니다.* |[설치 미디어 사용](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Configuration Manager 콘솔 설치](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Configuration Manager를 사용하여 끝점용** Microsoft Defender에 장치 온보딩 <br/><br/> *디바이스(또는 끝점)가 아직 끝점용 Microsoft Defender에 온보딩되지 않은 경우 Configuration Manager를 사용하여 이 작업을 할 수 있습니다.*   |[Configuration Manager를 통해 끝점용 Microsoft Defender에 온보딩](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**클라이언트 컴퓨터(끝점)Windows** 맬웨어 방지 정책 및 방화벽 보안 관리<br/><br/>*끝점용 Microsoft Defender, 악용 방지, 응용 프로그램 제어, 맬웨어 방지, 방화벽 설정 등을 비롯한 끝점 보호 기능을 구성합니다.*  |[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**조직의 장치에서 맬웨어** 방지 업데이트를 업데이트하는 방법 선택 <br/><br/>*Configuration Manager에서 Endpoint Protection 사용하여 조직의 장치에서 맬웨어 방지 정의를 최신으로 유지하는 여러 방법 중 선택할 수 있습니다.* |[사용자 정의 업데이트 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Configuration Manager를 사용하여 정의 업데이트 전달](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**직원이 인터넷에서** 악성 콘텐츠를 사용하는 앱을 사용하지 못하도록 네트워크 보호를 사용하도록 설정 <br/><br/>*테스트 환경에서 [네트워크](/microsoft-365/security/defender-endpoint/evaluate-network-protection) 보호를 위해 먼저 감사 모드를 사용하여 롤아웃하기 전에 차단되는 앱을 보는 것이 좋습니다.* |[Configuration Manager를 통해 네트워크 보호 켜기](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성 <br/><br/>*제어된 폴더 액세스를 랜섬웨어 방지 보호라고도 합니다.*   |[끝점 보호: 제어된 폴더 액세스](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Microsoft Endpoint Configuration Manage에서 제어된 폴더 액세스 사용](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>사용자 Microsoft Defender 보안 센터

아직 수행하지 않은 경우 경고를 보고 위협 방지 **기능을 구성하고 조직의** 전반적인 보안 Microsoft Defender 보안 센터 자세한 정보를 볼 수 있도록 Microsoft Defender 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )를 구성합니다. 

또한 최종 사용자가 2013에서 볼 수 있는 기능의 여부와 기능을 Microsoft Defender 보안 센터.

- [개요 Microsoft Defender 보안 센터](/microsoft-365/security/defender-endpoint/use)

- [끝점 보호: Microsoft Defender 보안 센터](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>다음 단계

- [개요를 위협 및 취약성 관리](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [보안 Microsoft Defender 보안 센터 대시보드 방문](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune을 사용하여 끝점용 Microsoft Defender 관리](manage-atp-post-migration-intune.md)
