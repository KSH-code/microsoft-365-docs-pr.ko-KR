---
title: Microsoft 365 Defender에서 자동화된 조사 및 응답 기능 구성
description: Microsoft 365 Defender에서 자동 복구를 통해 자동화된 조사 및 대응 구성
search.appverid: MET150
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.technology: m365d
ms.openlocfilehash: c9a2f41b1ec77994ef656b948ae1270dc2458dff
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269531"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-365-defender"></a>Microsoft 365 Defender에서 자동화된 조사 및 응답 기능 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

Microsoft 365 Defender에는 보안 운영 팀에 많은 시간과 노력을 절약할 수 있는 강력한 자동화된 조사 및 대응 기능이 포함되어 있습니다. [](m365d-autoir.md) 자체 [복구를](m365d-autoir.md#how-automated-investigation-and-self-healing-works)통해 이러한 기능은 보안 분석가가 위협을 조사하고 대응하는 단계와 모방하여 더 빠르고 확장할 수 있습니다. 

이 문서에서는 다음 단계를 사용하여 Microsoft 365 Defender에서 자동화된 조사 및 응답을 구성하는 방법을 설명합니다.

1. [선행 준비를 검토합니다.](#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)
2. 장치 그룹의 자동화 [수준을 검토하거나 변경합니다.](#review-or-change-the-automation-level-for-device-groups)
3. [Office 365에서](#review-your-security-and-alert-policies-in-office-365)보안 및 경고 정책을 검토합니다.
4. [Microsoft 365 Defender가 켜져 있는지 확인](#make-sure-microsoft-365-defender-is-turned-on)

그런 다음 모든 설정이 끝날 때 관리 센터 에서 수정 작업을 보고 [관리할 수 있습니다.](m365d-autoir-actions.md)

## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender"></a>Microsoft 365 Defender의 자동화된 조사 및 대응을 위한 선행 작업

|요구 사항 |세부 정보 |
|:----|:----|
|구독 요구 사항 |다음 구독 중 하나: <br/>- Microsoft 365 E5<br/>- Microsoft 365 A5<br/>- Microsoft 365 E5 보안 추가 기능의 Microsoft 365 E3<br/>- Microsoft 365 A5 보안 추가 기능의 Microsoft 365 A3<br/>- Office 365 E5 및 Enterprise Mobility + Security E5 및 Windows E5<p> [Microsoft 365 Defender 라이선스 요구 사항을 참조하세요.](./prerequisites.md#licensing-requirements)|
|네트워크 요구 사항 |- [Id에 대한 Microsoft Defender 사용](/azure-advanced-threat-protection/what-is-atp)<br/>- [Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security) 구성<br/>- [Microsoft Defender for Identity 통합](/cloud-app-security/mdi-integration) |
|Windows 컴퓨터 요구 사항 |- Windows 10, 버전 1709 이상이 설치됨([Windows 10 릴리스 정보](/windows/release-information/)참조) <br/>- 구성된 위협 방지 서비스는 다음과 같습니다.<br/>- [끝점용 Microsoft Defender](../defender-endpoint/configure-endpoints.md)<br/>- [Microsoft Defender 바이러스 백신](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|전자 메일 콘텐츠 및 Office 파일에 대한 보호 |[구성된 Office 365용 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
|권한 | 자동화된 조사 및 응답 기능을 구성하려면 Azure Active Directory( ) 또는 Microsoft 365 관리 센터()에서 전역 관리자 또는 보안 관리자 역할이 [https://portal.azure.com](https://portal.azure.com) 할당되어 있어야 [https://admin.microsoft.com](https://admin.microsoft.com) 합니다.<p>보류 중인 작업의 검토, 승인 또는 거부와 같은 자동화된 조사 및 응답 기능과 함께 작업하는 데 필요한 사용 권한을 얻하려면 Action Center 작업에 필요한 사용 권한을 [참조하세요.](m365d-action-center.md#required-permissions-for-action-center-tasks) |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>장치 그룹의 자동화 수준 검토 또는 변경

자동화된 조사가 실행될지 여부와 수정 작업이 자동으로 수행되거나 장치에 대한 승인 시에만 수행될지 여부는 조직의 장치 그룹 정책과 같은 특정 설정에 따라 결정됩니다. 장치 그룹 정책에 대해 구성된 자동화 수준을 검토합니다.

1. Microsoft Defender 보안 센터()로 이동하여 [https://securitycenter.windows.com](https://securitycenter.windows.com) 로그인합니다.
2. 설정 사용  >  **권한 장치**  >  **그룹으로 이동합니다.**
3. 장치 그룹 정책을 검토합니다. 특히 수정 수준 **열을 살펴보아야** 합니다. 전체 - 위협을 **자동으로 수정하는 것이 좋습니다.**  원하는 자동화 수준을 얻기 위해 장치 그룹을 만들거나 편집해야 할 수 있습니다. 이 작업에 대한 도움말은 다음 문서를 참조합니다.
   - [위협을 수정하는 방법](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   - [장치 그룹 만들기 및 관리](/windows/security/threat-protection/microsoft-defender-atp/machine-groups)

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Office 365에서 보안 및 경고 정책 검토

Microsoft는 특정 위험을 [식별하는](../../compliance/alert-policies.md) 데 도움이 되는 기본 제공 경고 정책을 제공합니다. 이러한 위험에는 Exchange 관리자 권한 남용, 맬웨어 활동, 잠재적인 외부 및 내부 위협, 정보 거버넌스 위험이 포함됩니다. 일부 경고는 [Office 365에서](../office-365-security/office-365-air.md)자동화된 조사 및 응답을 트리거할 수 있습니다. [Office 365용 Defender](../office-365-security/defender-for-office-365.md) 기능이 올바르게 구성되어 있는지 확인합니다.

특정 경고 및 보안 정책이 자동화된 조사를 트리거할 수 있기는 하지만 전자 메일 및 콘텐츠에 대한 수정 작업은 자동으로 *수행되지 않습니다.* 대신, 전자 메일 및 전자 메일 콘텐츠에 대한 모든 수정 작업은 알림 센터의 보안 운영 팀이 승인을 [기다립니다.](m365d-action-center.md)

Office 365의 보안 설정은 전자 메일 및 콘텐츠를 보호하는 데 도움이 됩니다. 이러한 설정을 보거나 변경하려면 위협으로부터 보호의 [지침을 따르십시오.](../office-365-security/protect-against-threats.md)

1. Microsoft 365 보안 센터()에서 정책 [https://security.microsoft.com](https://security.microsoft.com) 정책 & **위협**  >  **정책으로 이동하십시오.**
2. 다음 정책을 모두 구성해야 합니다. 도움말 및 권장 사항을 얻었다면 [위협으로부터 보호를 참조하세요.](/microsoft-365/security/office-365-security/protect-against-threats)
   - [맬웨어 방지)](../office-365-security/protect-against-threats.md#part-1---anti-malware-protection)
   - [피싱 방지)](../office-365-security/protect-against-threats.md#part-2---anti-phishing-protection)
   - [안전한 첨부 파일](../office-365-security/protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365)
   - [안전한 링크](../office-365-security/protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365)
   - [스팸 방지](../office-365-security/protect-against-threats.md#part-3---anti-spam-protection)
3. [SharePoint, OneDrive 및 Microsoft Teams용 Office 365용 Microsoft Defender가](../office-365-security/protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on) 켜져 있는지 확인
4. 전자 메일 [보호를 위한 제로 아워 자동](../office-365-security/protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop) 제거가 적용된지 확인
5. 이 단계는 선택 사항입니다. Microsoft [365](../../compliance/alert-policies.md) 규정 준수 센터에서 Office 365 경고 정책을 검토합니다( [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) ). 위협 관리 범주에는 몇 가지 기본 경고 정책이 있습니다. 이러한 경고 중 일부는 자동화된 조사 및 응답을 트리거할 수 있습니다. 자세한 내용은 기본 경고 [정책 을 참조합니다.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="make-sure-microsoft-365-defender-is-turned-on"></a>Microsoft 365 Defender가 켜져 있는지 확인

:::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP on":::

1. Microsoft 365 보안 센터()에 [https://security.microsoft.com](https://security.microsoft.com) 로그인합니다.
2. 탐색 창에서 이전 이미지와 같이 인시던트, 작업 센터 및 헌팅을 검색합니다. 
   - 인시던트, 관리 **센터** 및 헌팅이 표시되어 있는 경우 Microsoft 365 Defender가 켜져 있습니다.   이 [문서의 장치 그룹에](#review-or-change-the-automation-level-for-device-groups) 대한 자동화 수준 검토 또는 변경 섹션을 참조하세요.
   -   *인시던트, 관리* 센터 또는 **헌팅이** 없는 경우 Microsoft 365 Defender가 켜져 있지 않을 수 있습니다. 이 경우 작업 [센터를 방문합니다.](m365d-action-center.md)
3. 탐색 창에서 설정   >  **Microsoft 365 Defender 를 선택합니다.** Microsoft 365 Defender가 켜져 있는지 확인 

> [!TIP]
> 도움이 필요하신가요? [Microsoft 365 Defender 켜기 를 참조합니다.](m365d-enable.md)

## <a name="next-steps"></a>다음 단계

- [Microsoft 365 Defender의 수정 작업](m365d-remediation-actions.md)
- [알림 센터 방문](m365d-action-center.md)
