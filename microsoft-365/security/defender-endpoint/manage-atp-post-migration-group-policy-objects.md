---
title: 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender 관리
description: 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender를 관리하는 방법 학습
keywords: 마이그레이션 후, 관리, 운영, 유지 관리, 사용률, PowerShell, windows defender Advanced Threat Protection, atp, edr
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
ms.openlocfilehash: c21ac21f4369934375d44f5792afb874070ab074
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076580"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>그룹 정책 개체를 사용하여 끝점용 Microsoft Defender 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> Microsoft [Endpoint Manager를](https://docs.microsoft.com/mem) 사용하여 장치에 대한 조직의 위협 방지 기능을 관리하는 것이 좋습니다(끝점이라고도 합니다). Endpoint Manager에는 [Microsoft Intune 및](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) [Microsoft Endpoint Configuration Manager가 포함됩니다.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) **[Endpoint Manager에 대해 자세히 알아보시고, 끝점 관리자를 자세히 알아보아야 합니다.](https://docs.microsoft.com/mem/endpoint-manager-overview)** 

Azure Active Directory 도메인 서비스의 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender의 일부 설정을 관리할 수 있습니다.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>그룹 정책 개체를 사용하여 끝점에 대한 Microsoft Defender 구성

다음 표에는 그룹 정책 개체를 사용하여 끝점용 Microsoft Defender를 구성하기 위해 수행할 수 있는 다양한 작업이 나열됩니다.

|작업   |자세한 정보를 알아볼 수 있는 리소스  |
|---------|---------|
|**사용자 및 컴퓨터 개체에 대한 설정 관리** <br/><br/>*기본 제공 그룹 정책 개체를 사용자 지정하거나 조직의 요구 사항에 맞게 사용자 지정 그룹 정책 개체 및 조직 구성 단위를 만들 수 있습니다.*     |[Azure Active Directory 도메인 서비스 관리 도메인에서 그룹 정책 관리](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**Microsoft Defender 바이러스 백신 구성** <br/><br/>*조직 & 정책 설정, 제외, 수정 및 예약된 검사(끝점이라고도 하는 검사)를 비롯한 바이러스 백신 기능을 구성합니다.*   |[그룹 정책 설정을 사용하여 Microsoft Defender 바이러스 백신 구성 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[그룹 정책을 사용하여 클라우드 제공 보호 사용](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**조직의 공격 표면 감소 규칙 관리** <br/><br/>*폴더에 있는 파일을 제외하거나 사용자 & 알림에 사용자 지정 텍스트를 추가하여 공격 표면 감소 규칙을 사용자 지정합니다.* |[그룹 정책 개체를 사용하여 공격 표면 감소 규칙 사용자 지정](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Exploit Protection 설정 관리**<br/><br/>*Exploit Protection 설정을 사용자 지정하고 구성 파일을 가져온 다음 그룹 정책을 사용하여 해당 구성 파일을 배포할 수 있습니다.*  |[Exploit Protection 설정 사용자 지정](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Exploit Protection 구성 가져오기, 내보내기 및 배포](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[그룹 정책을 사용하여 구성 배포](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**직원이 인터넷에서** 악성 콘텐츠를 사용하는 앱을 사용하지 못하도록 네트워크 보호를 사용하도록 설정 <br/><br/>*테스트 환경에서 [네트워크](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) 보호를 위해 먼저 감사 모드를 사용하여 롤아웃하기 전에 차단되는 앱을 보는 것이 좋습니다.* |[그룹 정책을 사용하여 네트워크 보호 켜기](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**랜섬웨어로부터 보호하도록** 제어된 폴더 액세스 구성 <br/><br/>*[제어된 폴더 액세스를](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) 랜섬웨어 방지 보호라고도 합니다.*  |[그룹 정책을 사용하여 제어된 폴더 액세스 사용](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Microsoft Defender SmartScreen을 구성하여** 인터넷의 악성 사이트 및 파일로부터 보호합니다.  |[그룹 정책을 사용하여 Microsoft Defender SmartScreen 그룹 정책 및 MDM(모바일 장치 관리) 설정 구성](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|Windows를 실행하는 조직의 장치에 대한 정보를 보호하도록 암호화 및 **BitLocker** 구성 |[BitLocker 그룹 정책 설정](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|자격 증명 도난 공격으로부터 보호하도록 **Microsoft Defender Credential Guard** 구성 |[그룹 Windows Defender 사용하여 Credential Guard 사용](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Microsoft Defender 보안 센터 구성

아직 수행하지 않은 경우 경고를 보고, 위협 방지 기능을 구성하고, 조직의 전반적인 보안태세에 대한 자세한 정보를 볼 수 있도록 **Microsoft Defender** 보안 센터( [https://securitycenter.windows.com](https://securitycenter.windows.com) )를 구성합니다. 

Microsoft Defender 보안 센터에서 최종 사용자가 볼 수 있는 기능의 여부와 기능을 구성할 수 있습니다.

- [Microsoft Defender 보안 센터 개요](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [끝점 보호: Microsoft Defender 보안 센터](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>다음 단계

- [위협 및 취약성 관리 개요 보기](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Microsoft Defender 보안 센터 보안 작업 대시보드 방문](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Intune을 사용하여 끝점용 Microsoft Defender 관리](manage-atp-post-migration-intune.md)
