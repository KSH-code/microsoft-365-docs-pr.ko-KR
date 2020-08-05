---
title: Microsoft Threat Protection의 자동화 된 조사 및 응답 기능
description: Microsoft Threat Protection의 자동화된 조사 및 대응 기능에 대한 개요를 확인하세요.
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: c45b7d1b01ee776e9519d67ee52d36b8f48bf0ef
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552357"
---
# <a name="automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 자동화 된 조사 및 응답 기능

**적용 대상:**
- Microsoft Threat Protection

보안 알림이 트리거되면 해당 경고를 확인 하 고 조직을 보호 하기 위한 단계를 수행 하는 보안 운영 팀이 진행 됩니다. 조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다. 보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다. Microsoft Threat Protection의 자동화 된 조사 및 응답 기능 ( *자동 복구* 기능이 라고도 함)이 도움이 될 수 있습니다. 

다음 비디오를 시청 하 여 자동화 된 자동 복구 기능의 작동 방식을 알아봅니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4BzwB]

자동화 된 조사 및 응답은 보안 운영 센터에 가상 분석가가 있는 것과 같습니다.

## <a name="your-virtual-analyst"></a>가상 분석가

계층 1/계층 2 보안 운영팀에 가상 분석가가 있다고 가정합니다. 가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다. 가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다. 이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다. 이 시나리오는 과학 fiction 같이 보이지만 그렇지 않습니다. 이러한 가상 분석가는 Microsoft Threat Protection 제품군의 일부로, 해당 이름은 *자동 조사 및 응답*입니다.

자동화 된 조사 및 응답을 통해 보안 운영 팀에서 보안 경고 및 인시던트를 처리 하기 위해 조직의 용량을 대폭 높일 수 있습니다. 자동 조사 및 응답을 통해 조사 및 업데이트 관리 작업을 처리 하는 비용을 줄이고 위협 방지 제품군을 최대한 활용할 수 있습니다. 자동화 된 조사 및 응답은 보안 운영 팀에 게 다음과 같은 도움을 줍니다.

1. 위협이 조치를 요구하는지 여부 확인
2. 필수 수정 조치 수행(또는 권장)
3. 어떤 추가 조사가 수행되어야 하는지 결정
4. 다른 경고가 발생하면 필요한 프로세스를 반복

## <a name="the-automated-investigation-process"></a>자동화된 조사 프로세스

**경고** > **인시던트** > **자동화된 조사** > **판단** > **수정 작업**

트리거된 경고는 자동화 된 조사를 시작할 수 있는 인시던트를 만듭니다. 이 조사를 수행하면 하나 이상의 수정 작업이 발생할 수 있습니다. 다음 표에 요약된대로 Microsoft Threat Protection에서 각각의 자동화된 조사는 Azure ATP(Advanced Threat Protection), Microsoft Defender online(Microsoft Defender ATP) 및 Office 365 Advanced Threat Protection(Office 365 ATP)간 신호의 연관성을 보여줍니다. 

|엔터티 |위협 보호 서비스  |
|---------|---------|
|장치(끝점이라고도 함)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|전자 메일 콘텐츠(사서함의 파일 및 메시지)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |

각 조사에서는 조사 되는 각 증거 조각에 대해 verdicts (*악의적*이 고 *의심 스러운*또는 *위협이 되지 않음*)을 생성 합니다. 위협 유형 및 결과 결과에 따라 업데이트 관리 작업은 조직의 보안 운영 팀의 승인을 받을 때 자동으로 수행 됩니다. 보류 중인 동작과 완료된 작업은 [알림 센터](mtp-action-center.md)에 나열되어 있습니다.

> [!TIP]
> Microsoft Threat Protection의 자동화 된 조사 및 응답 기능을 통해 누락 되었거나 지워지는이 감지 되었다고 생각 되 면 알려주세요. [Microsoft Threat Protection의 자동화 된 조사 및 응답 기능에서 가양성/네거티브를 보고 하는 방법을](mtp-autoir-report-false-positives-negatives.md)참조 하세요.

조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다. 문제가 있는 엔터티가 다른 곳에서 발견되는 경우에는 자동화된 조사가 해당 엔터티를 포함하도록 범위를 확장하고 일반적인 보안 플레이 북이 실행됩니다. 

> [!NOTE]
> 모든 경고가 자동 조사를 트리거하는 것은 아니며, 자동 재구성 작업의 모든 조사 결과에 해당 되지 않습니다. 이러한 모든 방식은 조직에 대해 자동화 된 조사 및 응답이 구성 되는 방식에 따라 달라 집니다. 

## <a name="requirements-for-automated-investigation-and-response-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 자동화 된 조사 및 응답 요구 사항

|요구 사항 |세부 정보 |
|--|--|
|구독 요구 사항 |다음 중 하나가 필요합니다. <br/>-Microsoft 365 E5 <br/>-Microsoft 365 A5 <br/>-Microsoft 365 E5 보안<br/>-Microsoft 365 A5 보안<br/>-Office 365 E5 plus Enterprise Mobility + Security E5 plus Windows E5<br/><br/>[Microsoft Threat Protection 라이선스 요구 사항을](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?#licensing-requirements)참조 하세요.|
|네트워크 요구 사항 |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 사용<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)(MCAS) 구성됨<br/>- [Azure ATP와 통합된 MCAS](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 컴퓨터 요구 사항 |-Windows 10, 버전 1709 이상 설치 된 다음 위협 보호 서비스가 구성 된 windows 10 [릴리스 정보](https://docs.microsoft.com/windows/release-information/)를 참조 하세요.<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) <br/>- [Windows Defender 바이러스 백신](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) |
|전자 메일 콘텐츠 및 Office 파일 보호 |[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) 구성 |
|권한 |-자동화 된 조사 및 응답을 구성 하려면 Azure Active Directory ( [https://portal.azure.com](https://portal.azure.com) ) 또는 Microsoft 365 관리 센터 ()에서 전역 관리자 또는 보안 관리자 역할이 할당 되어 있어야 합니다 [https://admin.microsoft.com](https://admin.microsoft.com) .<br/><br/>-자동화 된 조사 및 응답 기능을 사용 하려면 [작업 센터 작업에 필요한 권한을](mtp-action-center.md#required-permissions-for-action-center-tasks)참조 하세요. |

## <a name="next-steps"></a>다음 단계

- [자동화된 조사 및 대응과 관련된 조치 승인 또는 거부](mtp-autoir-actions.md)
- [알림 센터에 대한 자세한 정보](mtp-action-center.md)
