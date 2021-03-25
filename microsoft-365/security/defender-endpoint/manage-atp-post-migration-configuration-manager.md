---
title: Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리
description: Configuration Manager를 사용하여 끝점용 Microsoft Defender를 관리하는 방법 학습
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, Configuration Manager, windows defender Advanced Threat Protection, atp, edr
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
ms.openlocfilehash: bd6b6bd2721b686ab10922d09a9e94b9ebcce522
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185656"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager를 사용하여 끝점용 Microsoft Defender 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


[Microsoft Intune(Intune)](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) 및 [Microsoft Endpoint Configuration Manager(Configuration](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) Manager)를 포함하는 [Microsoft Endpoint Manager를](https://docs.microsoft.com/mem)사용하여 디바이스에 대한 조직의 위협 방지 기능(끝점이라고도 칭)을 관리하는 것이 좋습니다. 
- [Endpoint Manager에 대해 자세히 알아보시고](https://docs.microsoft.com/mem/endpoint-manager-overview)
- [Configuration Manager 및 Intune을 사용하여 Windows 10 장치에서 끝점용 Microsoft Defender 공동 관리](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Configuration Manager를 통해 끝점용 Microsoft Defender 구성

|작업   |자세한 정보를 알아볼 수 있는 리소스  |
|---------|---------|
|**Configuration Manager 콘솔이** 없는 경우 설치<br/><br/>*Configuration Manger 콘솔이 아직 없는 경우 이러한 리소스를 사용하여 비트를 다운로드하고 설치합니다.* |[설치 미디어 사용](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Configuration Manager 콘솔 설치](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Configuration Manager를 사용하여 끝점용** Microsoft Defender에 장치 온보딩 <br/><br/> *디바이스(또는 끝점)가 아직 끝점용 Microsoft Defender에 온보딩되지 않은 경우 Configuration Manager를 사용하여 이 작업을 할 수 있습니다.*   |[Configuration Manager를 통해 끝점용 Microsoft Defender에 온보딩](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**클라이언트 컴퓨터(끝점)에** 대한 맬웨어 방지 정책 및 Windows 방화벽 보안 관리<br/><br/>*끝점용 Microsoft Defender, 악용 방지, 응용 프로그램 제어, 맬웨어 방지, 방화벽 설정 등을 비롯한 끝점 보호 기능을 구성합니다.*  |[Configuration Manager: Endpoint Protection](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**조직의 장치에서 맬웨어** 방지 업데이트를 업데이트하는 방법 선택 <br/><br/>*Configuration Manager의 Endpoint Protection을 사용하면 조직의 장치에서 맬웨어 방지 정의를 최신으로 유지하는 여러 방법 중 선택할 수 있습니다.* |[Endpoint Protection에 대한 정의 업데이트 구성](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Configuration Manager를 사용하여 정의 업데이트 전달](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**직원이 인터넷에서** 악성 콘텐츠를 사용하는 앱을 사용하지 못하도록 네트워크 보호를 사용하도록 설정 <br/><br/>*테스트 환경에서 [네트워크](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 보호를 위해 먼저 감사 모드를 사용하여 롤아웃하기 전에 차단되는 앱을 보는 것이 좋습니다.* |[Configuration Manager를 통해 네트워크 보호 켜기](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성 <br/><br/>*제어된 폴더 액세스를 랜섬웨어 방지 보호라고도 합니다.*   |[끝점 보호: 제어된 폴더 액세스](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Microsoft Endpoint Configuration Manage에서 제어된 폴더 액세스 사용](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터 구성

아직 수행하지 않은 경우 경고를 보고, 위협 방지 기능을 구성하고, 조직의 전반적인 보안태세에 대한 자세한 정보를 볼 수 있도록 **Microsoft Defender** 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )를 구성합니다. 

Microsoft Defender 보안 센터에서 최종 사용자가 볼 수 있는 기능의 여부와 기능을 구성할 수 있습니다.

- [Microsoft Defender 보안 센터 개요](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [끝점 보호: Microsoft Defender 보안 센터](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>다음 단계

- [위협 및 취약성 관리 개요 보기](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Microsoft Defender 보안 센터 보안 작업 대시보드 방문](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune을 사용하여 끝점용 Microsoft Defender 관리](manage-atp-post-migration-intune.md)
