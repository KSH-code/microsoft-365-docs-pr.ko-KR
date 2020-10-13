---
title: Microsoft Threat Protection에서 자동화 된 조사 및 응답 기능 구성
description: Microsoft Threat Protection에서 자체 복구를 사용 하 여 자동화 된 조사 및 응답 구성
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom: autoir
ms.reviewer: evaldm, isco
f1.keywords: CSH
ms.openlocfilehash: 632c94e2823abf6a947c5ae7e14fac7b11bdae0c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429602"
---
# <a name="configure-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Microsoft Threat Protection에서 자동화 된 조사 및 응답 기능 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Microsoft 위협 보호에는 강력한 [자동화 조사 및 응답 기능이](mtp-autoir.md) 포함 되어 있어 보안 운영 팀을 훨씬 더 많은 시간과 노력을 절감할 수 있습니다. 자가 치유를 사용 하는 경우 이러한 기능은 보안 분석가가 위협에 대 한 조사 및 대응을 위해 수행 하 고 더 빠르게 확장할 수 있는 기능을 제공할 수 있도록 하는 단계를 모방 합니다. 이 문서에서는 Microsoft Threat Protection에서 자동화 된 조사 및 응답을 구성 하는 방법에 대해 설명 합니다.

자동화 된 조사 및 응답 기능을 구성 하려면 다음 단계를 수행 합니다.

1. [필수 구성 요소를 검토](#prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection)합니다.
2. [장치 그룹에 대 한 자동화 수준 검토 또는 변경](#review-or-change-the-automation-level-for-device-groups)
3. [Office 365에서 보안 및 경고 정책을 검토](#review-your-security-and-alert-policies-in-office-365)합니다.
4. [Microsoft Threat Protection이 켜져 있는지 확인](#make-sure-microsoft-threat-protection-is-turned-on)합니다.

그런 후 [에는 알림 센터에서 보류 중 및 완료 된 작업을 검토](#review-pending-and-completed-actions-in-the-action-center)합니다. 


## <a name="prerequisites-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 자동화 된 조사 및 응답을 위한 필수 구성 요소

|요구 사항 |세부 정보 |
|--|--|
|구독 요구 사항 |구독 중 하나: <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 보안<br/>-Microsoft 365 A5 보안<br/>-Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>[Microsoft Threat Protection 라이선스 요구 사항을](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)참조 하세요.|
|네트워크 요구 사항 |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 사용<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 구성 됨<br/>- [Azure ATP와 통합 된 Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 컴퓨터 요구 사항 |-Windows 10, 버전 1709 이상 설치 된 다음 위협 보호 서비스가 구성 된 windows 10 [릴리스 정보](https://docs.microsoft.com/windows/release-information/)를 참조 하세요.<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Microsoft Defender 바이러스 백신](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|전자 메일 콘텐츠 및 Office 파일 보호 |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) 구성 |
|권한 |-자동화 된 조사 및 응답 기능을 구성 하려면 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 전역 관리자 또는 보안 관리자 역할이 할당 되어 있어야 합니다 [https://admin.microsoft.com](https://admin.microsoft.com) .<br/><br/>-진행 중인 작업의 검토, 승인 또는 거부와 같은 자동화 된 조사 및 응답 기능을 사용 하는 데 필요한 사용 권한을 얻으려면 [Action center 작업에 필요한 사용 권한을](mtp-action-center.md#required-permissions-for-action-center-tasks)참조 하세요. |

## <a name="review-or-change-the-automation-level-for-device-groups"></a>장치 그룹에 대 한 자동화 수준 검토 또는 변경

자동화 된 조사가 실행 되는지 여부와, 재구성 작업이 자동으로 수행 되는지, 아니면 장치에 대 한 승인에만 적용 되는지를 조직의 장치 그룹 정책 등의 특정 설정에 따라 결정 해야 합니다. 장치 그룹 정책에 대해 설정 된 자동화 수준을 검토 합니다.

1. Microsoft Defender 보안 센터 ()로 이동 [https://securitycenter.windows.com](https://securitycenter.windows.com) 하 여 로그인 합니다.

2. **설정**  >  **사용 권한**  >  **장치 그룹**으로 이동 합니다. 

3. 장치 그룹 정책을 검토 합니다. 특히, **관리 수준** 열을 확인 합니다. **자동으로 전체 재구성 위협을**사용 하는 것이 좋습니다.  원하는 자동화 수준을 얻으려면 장치 그룹을 만들거나 편집 해야 할 수 있습니다. 이 작업에 대 한 도움말을 보려면 다음 문서를 참조 하세요.

   - [위협의 재구성 방법](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations#how-threats-are-remediated)
   
   - [장치 그룹 만들기 및 관리](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/machine-groups) 

## <a name="review-your-security-and-alert-policies-in-office-365"></a>Office 365에서 보안 및 경고 정책 검토

Microsoft는 특정 위험을 식별 하는 데 도움이 되는 기본 제공 [경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 제공 합니다. 이러한 위험에는 Exchange 관리자 권한 남용, 맬웨어 활동, 잠재적 외부 및 내부 위협, 정보 관리 위험 등이 있습니다. 일부 알림은 [Office 365에서 자동화 된 조사 및 응답](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)을 트리거할 수 있습니다. [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 기능이 올바르게 구성 되어 있는지 확인 합니다.

특정 경고 및 보안 정책에서 자동화 된 조사를 트리거할 수 있지만 전자 메일 및 콘텐츠에 대 한 재구성 작업이 자동으로 수행 되지 않습니다. 대신, 전자 메일 및 전자 메일 콘텐츠에 대 한 모든 수정 작업은 [작업 센터](mtp-action-center.md)에서 보안 운영 팀의 승인을 기다립니다.

Office 365의 보안 설정은 전자 메일 및 콘텐츠를 보호 하는 데 도움이 됩니다. 이러한 설정을 보거나 변경 하려면 [위협 으로부터 보호에 대](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)한 지침을 따르세요.

1. Microsoft 365 보안 센터 ()에서 [https://security.microsoft.com/](https://security.microsoft.com/) **정책**  >  **위협 방지**로 이동 합니다.

2. 다음의 모든 정책이 구성 되어 있는지 확인 합니다. 도움말 및 권장 사항을 보려면 [위협 으로부터 보호](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)를 참조 하세요.

   - [맬웨어 방지 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-1---anti-malware-protection)
   - [ATP 피싱 방지 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-2---anti-phishing-protection)
   - [ATP 안전한 첨부 파일 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-attachments-policies)
   - [ATP 안전한 링크 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#atp-safe-links-policies)
   - [스팸 방지 (Office 365)](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-3---anti-spam-protection) 

4. [SharePoint, OneDrive 및 Microsoft 팀에 대 한 Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads) 가 설정 되어 있는지 확인 합니다.

5. [전자 메일 보호에 대해 0 시간 자동 삭제](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats#zero-hour-auto-purge-for-email-in-eop) 가 적용 되는지 확인 합니다. 

8. (선택 사항) Microsoft 365 준수 센터 ()에서 [Office 365 경고 정책을](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) 검토 [https://compliance.microsoft.com/compliancepolicies](https://compliance.microsoft.com/compliancepolicies) 합니다. 위협 관리 범주에는 몇 가지 기본 경고 정책이 있습니다. 이러한 경고 중 일부는 자동 조사 및 응답을 트리거할 수 있습니다. 자세한 내용은 [Default alert 정책도](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?#default-alert-policies)를 참조 하십시오.
 
## <a name="make-sure-microsoft-threat-protection-is-turned-on"></a>Microsoft Threat Protection이 설정 되어 있는지 확인

1. Microsoft 365 보안 센터 ()로 이동 [https://security.microsoft.com](https://security.microsoft.com) 하 여 로그인 합니다.

2. 탐색 창에서 다음 이미지에 표시 된 것 처럼 **인시던트**, **작업 센터** **및 검색**을 찾습니다.

   :::image type="content" source="../../media/mtp-enable/mtp-on.png" alt-text="MTP 켜기":::

   - **인시던트**, **작업 센터**및 **사냥**이 표시 되 면 Microsoft Threat Protection이 설정 됩니다. 다음 절차를 진행 하 여 [장치 그룹에 대 한 자동화 수준을 검토 하거나 변경](#review-or-change-the-automation-level-for-device-groups)합니다.

   - **인시던트**, **작업 센터**또는 **사냥**을 볼 수 *없는* 경우 Microsoft Threat Protection이 설정 되어 있지 않을 수 있습니다. 이 경우에는 다음 단계를 진행 합니다.

3. 탐색 창에서 **Settings**  >  **Microsoft Threat Protection**설정을 선택 합니다. Microsoft Threat Protection이 켜져 있는지 확인 합니다. 

   도움이 필요하신가요? [Microsoft Threat Protection 설정을](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable)참조 하세요.

## <a name="review-pending-and-completed-actions-in-the-action-center"></a>알림 센터에서 보류 중 및 완료 된 작업 검토

Microsoft Threat Protection에서 자동화 된 조사 및 응답을 구성한 후에는 Action center ()를 방문 합니다 [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) . 여기에서 보류 중인 작업을 검토 및 승인 하 고 자동 업데이트 관리 작업을 확인할 수 있습니다. 

[알림 센터를 방문](mtp-action-center.md)합니다.
